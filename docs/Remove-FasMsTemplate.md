# Remove-FasMsTemplate

## Synopsis
Uninstall a Microsoft Certificate Template from an Active Directory environment.

## Syntax

```
Remove-FasMsTemplate -Name <String> [<CommonParameters>]
```

## Description
This commandlet can be used to delete a Microsoft Certificate Template currently installed in an Active Directory Deployment.

Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. 
This includes information such as the validity period and how the certificate should be authorized.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft GUI tools.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Remove-FasMsTemplate -Name Citrix_SmartcardLogon
```

Description

-----------

Deletes the Citrix_SmartcardLogon Certificate Template from Active Directory

## Parameters

### -Name
Specifies the name of the Microsoft Certificate Template to delete.

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
This cmdlet returns a list of certificate templates.

## Notes

## Related Links

[New-FasMsTemplate]()

[Get-FasMsTemplate]()

[Publish-FasMsTemplate]()

[Unpublish-FasMsTemplate]()


