# Get-FasMsTemplate

## Synopsis
Lists the Microsoft Certificate Templates currently installed in an Active Directory environment.

## Syntax

```
Get-FasMsTemplate [-Name <String>] [<CommonParameters>]
```

## Description
This commandlet lists information about the Microsoft Certificate Templates currently installed in an Active Directory Deployment

Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. 
This includes information such as the validity period and how the certificate should be authorized.

Certificate Templates can be referenced by their name and unique OID string. 
This commandlet also returns the security descriptor that controls access to the Certificate Template as an SDDL string.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Get-FasMsTemplate -Name Citrix_SmartcardLogon
```

Description

-----------

Return information about the certificate template named Citrix_SmartcardLogon that is installed in Active Directory

## Parameters

### -Name
Specifies a particular template name to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Retrieve all templates
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### List of Templates
This cmdlet returns a list of certificate templates.

## Notes

## Related Links

[New-FasMsTemplate]()

[Publish-FasMsTemplate]()

[Unpublish-FasMsTemplate]()

[Remove-FasMsTemplate]()


