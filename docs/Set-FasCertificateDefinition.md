# Set-FasCertificateDefinition

## Synopsis
Modify an existing Certificate Definition object (recipe for issuing a certificate).

## Syntax

```
Set-FasCertificateDefinition -Name <String> [-CertificateTemplate <String>]
 [-AuthorizationCertificate <String>] [-CertificateAuthorities <String[]>] [-PolicyOids <String>]
 [-InSession <Boolean>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
Change the confiration of an existing Certificate Definition object that the FAS is using to generate certificates.

When generating a certificate, the FAS requires various pieces of information. 
Including:
    - The CertificateTemplate to request (see Get-FasMsTemplate)
    - A list of loadbalanced/failover Certificate Authority Addresses (see Get-FasMsCertificateAuthority)
    - A reference to the AuthorizationCertificate to use to Authorize the request (see Get-FasAuthorizationCertificate)
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
C:\PS> Set-FasCertificateDefinition -Name MyCertificateDefinition -CertificateAuthorities $DefaultCA -MsTemplate "Citrix_SmartcardLogon" -AuthorizationCertificate $AuthorizationCertificate
```

Description

-----------

Updates an existing certificate definition to use the first authorization certificate to issue Citrix_SmartcardLogon certificates from the default CA

## Parameters

### -Name
Specify the name of the certificate definition to modify

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateTemplate
Change the name of Certificate Template to use to issue this certificate

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

### -AuthorizationCertificate
Change a the Guid Id of an AuthorizationCertificate object

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

### -CertificateAuthorities
Change the list of Addresses of Certificate Authorities that can issue these certificates

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyOids
Change the list of Issuance Policy OIDs to request in the certificate

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
Default value: (default)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet does not return a value

## Notes

## Related Links

[New-FasCertificateDefinition]()

[Get-FasCertificateDefinition]()

[Remove-FasCertificateDefinition]()


