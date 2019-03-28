# Set-FasServer

## Synopsis
Set information on a Federated Authentication Service (FAS) server.

## Syntax

```
Set-FasServer [-MaintenanceMode <Boolean>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
This cmdlet can modify information about a Federated Authentication Service (FAS) servers. 
In particular, this can enable/disable Maintenance mode making the Fas Server rejects new connections (callers will fail over to different FAS servers).

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress = (Get-FasServer)[0].Address
C:\PS> Set-FasServer -MaintenanceMode $FALSE
```

Description

-----------

This code lists the FAS Servers configured via Group Policy.

## Parameters

### -MaintenanceMode
Set the MaintenanceMode flag

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (default)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $CitrixFasAddress
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
User name to use for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Password for authentication to FAS server ($NULL for current user account)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns a list of FAS server objects

## Notes

## Related Links

