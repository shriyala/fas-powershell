# Remove-FasMsTemplate

Uninstall a Microsoft Certificate Template from an Active Directory environment.

## Syntax

`Remove-FasMsTemplate -Name <String> [<CommonParameters>]`

## Detailed Description

This commandlet can be used to delete Microsoft Certificate Templates currently installed in an Active Directory Deployment. If the template is currently published on a Certificate Authority, running this command will unpublish it. Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. This includes information such as the validity period and how the certificate should be authorized. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft GUI tools.

## Related Commands

-  [New-FasMsTemplate](New-FasMsTemplate.md)

-  [Get-FasMsTemplate](Get-FasMsTemplate.md)

-  [Publish-FasMsTemplate](Publish-FasMsTemplate.md)

-  [Unpublish-FasMsTemplate](Unpublish-FasMsTemplate.md)

## Parameters

| Name | Description                                                         | Required? | Pipeline Input        | Default Value |
|------|---------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name | Specifies the name of the Microsoft Certificate Template to delete. | true      | true (ByPropertyName) | (required)    |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of certificate templates.

## Examples

### EXAMPLE 1

    C:\PS> Remove-FasMsTemplate -Name Citrix_SmartcardLogon

Deletes the Citrix\_SmartcardLogon Certificate Template from Active Directory
