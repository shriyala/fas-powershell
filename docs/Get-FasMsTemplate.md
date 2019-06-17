# Get-FasMsTemplate

Lists the Microsoft Certificate Templates currently installed in an Active Directory environment.

## Syntax

`Get-FasMsTemplate [-Name <String>] [<CommonParameters>]`

## Detailed Description

This commandlet lists information about the Microsoft Certificate Templates currently installed in an Active Directory Deployment Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. This includes information such as the validity period and how the certificate should be authorized. Certificate Templates can be referenced by their name and unique OID string. This commandlet also returns the security descriptor that controls access to the Certificate Template as an SDDL string.

## Related Commands

-  [New-FasMsTemplate](New-FasMsTemplate.md)

-  [Publish-FasMsTemplate](Publish-FasMsTemplate.md)

-  [Unpublish-FasMsTemplate](Unpublish-FasMsTemplate.md)

-  [Remove-FasMsTemplate](Remove-FasMsTemplate.md)

## Parameters

| Name | Description                                       | Required? | Pipeline Input        | Default Value          |
|------|---------------------------------------------------|-----------|-----------------------|------------------------|
| Name | Specifies a particular template name to retrieve. | true      | true (ByPropertyName) | Retrieve all templates |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### List of Templates

This cmdlet returns a list of certificate templates.

## Examples

### EXAMPLE 1

    C:\PS> Get-FasMsTemplate -Name Citrix_SmartcardLogon

Return information about the certificate template named Citrix\_SmartcardLogon that is installed in Active Directory
