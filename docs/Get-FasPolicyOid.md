# Get-FasPolicyOid

Retrieve information about the Issuance Policy Oids registered in the domain.

## Syntax

`Get-FasPolicyOid [-Name <String>] [-Path <String>] [<CommonParameters>]`

## Detailed Description

This commandlet retrieves information about the Issuance Policy Oids registered in the domain, including their human readable name and associated security groups. Certificate Issuance Policy Oids are attributes that can optionally be included in certificates issued by the Microsoft Certificate Authority. By default, these include Low/Medium/High Assurance levels and provide an indication of the level or type of approval to which a certificate holder has been authorized. When logging in, Windows will dynamically add the user to additional Universal Security Groups that have been associated with these Oids.

## Related Commands

-  [New-FasPolicyOid](New-FasPolicyOid.md) 

-  [Set-FasPolicyOid](Set-FasPolicyOid.md) 

-  [Remove-FasPolicyOid](Remove-FasPolicyOid.md)

## Parameters

| Name    | Description                                                                       | Required? | Pipeline Input        | Default Value |
|---------|-----------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Name    | Specifies the name of a policy oid to retrieve (or \$NULL to list them all).      | false     | true (ByPropertyName) | \$NULL        |
| Default | Specifies the LDAP path of a policy oid to retrieve (or \$NULL to list them all). | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of Microsoft Policy Oid objects

## Examples

### EXAMPLE 1

    C:\PS> Get-FasPolicyOid

This command retrieves the address Policy Oids registered in this forest.
