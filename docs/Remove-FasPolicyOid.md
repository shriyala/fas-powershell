# Remove-FasPolicyOid

Remove a registered Issuance Policy Oid in the domain.

## Syntax

`Remove-FasPolicyOid -Path <String> [<CommonParameters>]`

## Detailed Description

This cmdlet removes an existing Issuance Policy Oid registered in the domain. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Related Commands

-  [New-FasPolicyOid](New-FasPolicyOid.md)

-  [Get-FasPolicyOid](Get-FasPolicyOid.md)

-  [Set-FasPolicyOid](Set-FasPolicyOid.md)

## Parameters

| Name | Description                                          | Required? | Pipeline Input        | Default Value |
|------|------------------------------------------------------|-----------|-----------------------|---------------|
| Name | Specifies the LDAP Path of the Policy Oid to delete. | true      | true (ByPropertyName) | (default)     |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $PolicyOid=Get-FasPolicyOid -Name "Finance User Assurance"
    C:\PS> Remove-FasPolicyOid -Path $PolicyOid.Path

This code looks up the LDAP Path of the "Finance User Assurance" OID and deletes it.
