# Set-FasPolicyOid

Change the Universal Security Group associated with an Issuance Policy Oid registered in the domain.

## Syntax

`Set-FasPolicyOid -Path <String> -Group [<String>] [<CommonParameters>]`

## Detailed Description

This cmdlet modifies the security group associated with a new Issuance Policy Oid registered in the domain by name. Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Related Commands

-  [New-FasPolicyOid](New-FasPolicyOid.md)

-  [Get-FasPolicyOid](Get-FasPolicyOid.md)

-  [Remove-FasPolicyOid](Remove-FasPolicyOid.md)

## Parameters

| Name  | Description                                                                                        | Required? | Pipeline Input        | Default Value |
|-------|----------------------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name  | Specifies the LDAP Path of the policy oid to modify.                                               | true      | true (ByPropertyName) | (default)     |
| Group | Specifies the DN of a Universal Security Group to associate with this Policy OID (or leave \$NULL) | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $PolicyOid=Get-FasPolicyOid -Name "Finance User Assurance"
    C:\PS> Set-FasPolicyOid -Path $PolicyOid.Path -Group "CN=FinanceGroup,CN=Users,DC=citrixtest,DC=net"

This code looks up the LDAP Path of the "Finance User Assurance" OID and sets the associated group as the "FinanceGroup" Universal Security Group
