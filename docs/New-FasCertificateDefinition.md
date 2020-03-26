# New-FasCertificateDefinition

## Synopsis
Create a Certificate Definition object (recipe for issuing a certificate).

## Syntax

```
New-FasCertificateDefinition [-Name <String>] -CertificateTemplate <String> -AuthorizationCertificate <String>
 -CertificateAuthorities <String[]> [-PolicyOids <String>] [-InSession <Boolean>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
Create a Certificate Definition object that FAS will use to generate user certificates.

When generating a certificate, FAS requires various pieces of information. 
Including:
    - The CertificateTemplate to request (see Get-FasMsTemplate)
    - A list of loadbalanced/failover Certificate Authority Addresses (see Get-FasMsCertificateAuthority)
    - The id of the AuthorizationCertificate to use to Authorize the request (see Get-FasAuthorizationCertificate)
    - A list of additional Issuance Policy OIDs to add to the certificate request (see Get-FasPolicyOid)
    - A flag indicating if the certificate can be used as an in-session Virtual Smart Card, or only for the logon process.

Note that Certificate Definition objects can only be created and managed by the FAS Server administrator, although they can be referenced by "Rule" administrators.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> $DefaultCA=(Get-FasMsCertificateAuthority -Default).Address
C:\PS> $AuthorizationCertificate=(Get-FasAuthorizationCertificate)[0].Id
C:\PS> New-FasCertificateDefinition -CertificateAuthorities $DefaultCA -MsTemplate "Citrix_SmartcardLogon" -AuthorizationCertificate $AuthorizationCertificate
```

Description

-----------

This code generates a certificate definition that uses the first authorization certificate to issue Citrix_SmartcardLogon certificates from the default CA

## Parameters

### -Name
Specify the name of this Certificate Definition (if not specified, defaults to the CertificateTemplate name)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [CertificateTemplate name]
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateTemplate
Specify the name of Certificate Template to use to issue this certificate

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

### -AuthorizationCertificate
Specify the Id of an AuthorizationCertificate object

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

### -CertificateAuthorities
Specify a list of Addresses of Certificate Authorities that can issue these certificates

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyOids
Specify a list of Issuance Policy OIDs to request in the certificate

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (empty)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InSession
Set to $FALSE to only allow this certificate to be used for authentication

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $FALSE
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
This cmdlet does not return a value

## Notes

## Related Links

[Get-FasCertificateDefinition]()

[Set-FasCertificateDefinition]()

[Remove-FasCertificateDefinition]()

[Get-FasAuthorizationCertificate]()

[Get-FasPolicy]()

[Get-FasMsTemplate]()

[Get-FasMsCertificateAuthority]()


