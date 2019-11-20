# Publish-FasMsTemplate

## Synopsis
Publish an installed Microsoft Certificate Template on a Microsoft Certificate Authority.

## Syntax

```
Publish-FasMsTemplate -Name <String> -CertificateAuthority <String> [<CommonParameters>]
```

## Description
This commandlet authorizes a Microsoft Certificate Authority to issue certificates based on a Microsoft Certificate Template.

Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. 
This includes information such as the validity period and how the certificate should be authorized.

Not all Certificate Authorities issue certificates of all types. 
This commandlet instructs a Certificate Authority to add an installed Certificate Template as a type of certificate that can be issued. 
 

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft GUI tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $ca = Get-FasMSCertificateAuthority -default
C:\PS> Publish-FasMsTemplate -Name Citrix_SmartcardLogon -CertificateAuthority $ca.Address
```

Description

-----------

Publishes the Citrix_SmartcardLogon template on the certificate authority on dc.citrixtest.net

## Parameters

### -Name
Specifies the name of the Microsoft Certificate Template to publish.

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

### -CertificateAuthority
Specifies the Certificate Authority that should publish this template.

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

[Unpublish-FasMsTemplate]()

[Get-FasMsCertificateAuthority]()


