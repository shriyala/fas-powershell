# New-FasUserCertificate

## Synopsis
Generate and cache a certificate for a user on the Federated Authentication Service.

## Syntax

```
New-FasUserCertificate -UserPrincipalName <String> -Rule <String> -CertificateDefinition <String>
 [-SecurityContext <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command creates a certificate for a user on the Federated Authentication Service. 
This can be used for testing purposes, or run at "off-peak" times to spread the load of certificate generation that would otherwise happen at user logon.

A new certificate is not generated if a cached certificate for the user already exists.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> New-FasUserCertificate -UserPrincipalName "fred@citrixtest.net" -Rule "default" -CertificateDefinition "default_Definition"
```

Description

-----------

This code generates and caches a certificate for fred@citrixtest.net.

## Parameters

### -UserPrincipalName
Specify the UPN of the user for whom this certificate is being generated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rule
Specify the Rule name (Federated Authentication Service configuration) this certificate is associated with.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateDefinition
Specify the Certificate Definition to use when generating the certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityContext
Specify the Security Context to use when generating the certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $CitrixFasAddress
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
User name to use for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Password for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns the user certificate if successful

## Notes

## Related Links

[Get-FasUserCertificate]()

[Remove-FasUserCertificate]()


