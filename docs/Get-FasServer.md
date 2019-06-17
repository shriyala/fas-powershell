# Get-FasServer

Retrieve information about the Federated Authentication Service (FAS) servers configured via Group Policy.

## Syntax

`Get-FasServer [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This cmdlet returns information about the Federated Authentication Service (FAS) servers configured on this server via GPO. In particular this includes the addresses for remote configuration.

## Related Commands

## Parameters

| Name     | Description                                                                           | Required? | Pipeline Input        | Default Value |
|----------|---------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Address  | Specify a particular FAS server to contact (or \$NULL to list all configured servers) | false     | true (ByPropertyName) | \$NULL        |
| UserName | User name to use for authentication to FAS server (\$NULL for current user account)   | false     | true (ByPropertyName) | \$NULL        |
| Password | Password for authentication to FAS server (\$NULL for current user account)           | false     | true (ByPropertyName) | \$NULL        |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of FAS server objects

## Examples

### EXAMPLE 1

    C:\PS> Get-FasServer

This code lists the FAS Servers configured via Group Policy.
