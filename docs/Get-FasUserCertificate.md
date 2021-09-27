# Get-FasUserCertificate

## Synopsis
List cached certificates on the Federated Authentication Service.

## Syntax

```
Get-FasUserCertificate [-UserPrincipalName <String>] [-Rule <String>] [-CertificateDefinition <String>]
 [-SecurityContext <String>] [-KeyInfo <Boolean>] [-MaximumRecordCount <Int>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command lists the user certificates managed by the Federated Authentication Service.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Get-FasUserCertificate
```

Description

-----------

This code lists all currently cached certificates on the Federated Authentication Service.

## Parameters

### -UserPrincipalName
Filter by UPN on certificate.

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

### -Rule
Filter by Rule name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateDefinition
Filter by Certificate Definition.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityContext
Filter by Security Context.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyInfo
Include private key information in the returned data.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $false
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumRecordCount
Limit the number of certificates to return.

```yaml
Type: Int
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 250
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
This cmdlet returns a list of FasUserCertificate object

## Notes

## Related Links

[New-FasUserCertificate]()

[Remove-FasUserCertificate]()


