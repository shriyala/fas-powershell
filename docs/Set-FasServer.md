# Set-FasServer

Set information on a Federated Authentication Service (FAS) server.

## Syntax

`Set-FasServer [-MaintenanceMode <Boolean>] [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]`

## Detailed Description

This cmdlet can modify information about a Federated Authentication Service (FAS) servers. In particular, this can enable/disable Maintenance mode making the Fas Server rejects new connections (callers will fail over to different FAS servers).

## Related Commands

## Parameters

| Name            | Description                                                                         | Required? | Pipeline Input        | Default Value      |
|-----------------|-------------------------------------------------------------------------------------|-----------|-----------------------|--------------------|
| MaintenanceMode | Set the MaintenanceMode flag                                                        | false     | true (ByPropertyName) | (default)          |
| Address         | Address of FAS Server (or \$NULL to use \$CitrixFasAddress)                         | false     | true (ByPropertyName) | \$CitrixFasAddress |
| UserName        | User name to use for authentication to FAS server (\$NULL for current user account) | false     | true (ByPropertyName) | \$NULL             |
| Password        | Password for authentication to FAS server (\$NULL for current user account)         | false     | true (ByPropertyName) | \$NULL             |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of FAS server objects

## Examples

### EXAMPLE 1

    C:\PS> $CitrixFasAddress = (Get-FasServer)[0].Address
    C:\PS> Set-FasServer -MaintenanceMode $FALSE

This code lists the FAS Servers configured via Group Policy.
