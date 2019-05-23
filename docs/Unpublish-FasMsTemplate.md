# Unpublish-FasMsTemplate

## Synopsis
Stop publishing a Microsoft Certificate Template on a Microsoft Certificate Authority.

## Syntax

```
Unpublish-FasMsTemplate -Name <String> -CertificateAuthority <String> [<CommonParameters>]
```

## Description
This command instructs a Microsoft Certificate Authority to stop publishing a Microsoft Certificate Template.
 

After running this command, the Certificate Authority will no longer issue certificates of this type.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft GUI tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $ca = Get-FasMSCertificateAuthority -default
C:\PS> Unpublish-FasMsTemplate -Name Citrix_SmartcardLogon -CertificateAuthority $ca.Address
```

Description

-----------

This command instructs the certificate authority on dc.citrixtest.net to stop issuing certificates based on the Citrix_SmartcardLogon template.

## Parameters

### -Name
Specifies the name of the Microsoft Certificate Template to stop publishing.

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
Specifies the Certificate Authority that should no longer publish this template.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet does not return a value

## Notes

## Related Links

[Publish-FasMsTemplate]()

[Get-FasMsCertificateAuthority]()


