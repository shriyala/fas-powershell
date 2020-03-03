# Remove-FasUserCertificate

## Synopsis
Remove cached certificates on the Federated Authentication Service.

## Syntax

```
Remove-FasUserCertificate [-UserPrincipalName <String>] [-Rule <String>] [-CertificateDefinition <String>]
 [-SecurityContext <String>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command deletes certificates and private keys managed by the Federated Authentication Service. 
This may affect users who are currently using Virtual Smart Cards as the private key will be immediately unavailable. 
The Federated Authentication Service will automatically remove certificates when they have expire, so it is unusually not necessary to explicitly delete them.

Caution: Using this cmdlet with no filter parameters will delete all user certificates.

Note that this command does not itself prevent equivalent certificates being regenerated when the user next logs in, nor does it revoke certificates that are currently in use.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Remove-FasUserCertificate -UserPrincipalName "fred@citrixtest.net"
```

Description

-----------

This code immediately deletes all certificates and private keys associated with certificates issued to fred@citrixtest.net.

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
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateDefinition
Filter by Certificate Type.

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

### -SecurityContext
Filter by Security Context.

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
This cmdlet does not have a return value

## Notes

## Related Links

[New-FasUserCertificate]()

[Get-FasUserCertificate]()


