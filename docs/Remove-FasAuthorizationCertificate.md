# Remove-FasAuthorizationCertificate

This command deletes a FAS Authorization Certificate and associated private key

## Syntax

`Remove-FasAuthorizationCertificate -Id <String> [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This command deletes a FAS Authorization Certificate and associated private key. Note that this may affect the operation of the FAS server.

## Related Commands

-  [New-FasAuthorizationCertificate](New-FasAuthorizationCertificate.md) 

-  [Get-FasAuthorizationCertificate](Get-FasAuthorizationCertificate.md)

## Parameters

| Name     | Description                                                                         | Required? | Pipeline Input        | Default Value |
|----------|-------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Id       | Guid of the Authorization Certificate to delete                                     | true      | true (ByPropertyName) | \$NULL        |
| UserName | User name to use for authentication to FAS server (\$NULL for current user account) | false     | true (ByPropertyName) | \$NULL        |
| Password | Password for authentication to FAS server (\$NULL for current user account)         | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
    C:\PS> Remove-FasAuthorizationCertificate -Id (Get-FasAuthorizationCertificate)[0].Id

This code lists the Authorization certificates on a FAS server and deletes the first one in the list.
