# New-FasPolicyOid

Create and register a new Issuance Policy Oid in the domain.

## Syntax

`New-FasPolicyOid -Name <String> [-Group [<String>]] [<CommonParameters>]`

## Detailed Description

This cmdlet registers a new Issuance Policy Oid with the domain by name, optionally specifying associated LDAP security group DN. Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft LDAP configuration tools.

## Related Commands

-  [Get-FasPolicyOid](Get-FasPolicyOid.md) 

-  [Set-FasPolicyOid](Set-FasPolicyOid.md) 

-  [Remove-FasPolicyOid](Remove-FasPolicyOid.md)

## Parameters

| Name  | Description                                                                                        | Required? | Pipeline Input        | Default Value |
|-------|----------------------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name  | Specifies the name of the new policy oid to register                                               | true      | true (ByPropertyName) | (default)     |
| Group | Specifies the DN of a Universal Security Group to associate with this Policy OID (or leave \$NULL) | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> New-FasPolicyOid -Name "Finance User Assurance" -Group "CN=FinanceGroup,CN=Users,DC=citrixtest,DC=net"

This command creates an OID that when included in a logon certificate will dynamically assign the user to the "FinanceGroup" Universal Security Group
