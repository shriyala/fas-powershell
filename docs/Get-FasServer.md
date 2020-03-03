# Get-FasServer

## Synopsis
Retrieve information about the Federated Authentication Service (FAS) servers configured via Group Policy.

## Syntax

```
Get-FasServer [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This cmdlet returns information about the Federated Authentication Service (FAS) servers configured on this server via GPO. 
In particular this includes the addresses for remote configuration.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> Get-FasServer
```

Description

-----------

This code lists the FAS Servers configured via Group Policy.

## Parameters

### -Address
Specify a particular FAS server to contact (or omit to list all configured servers)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (list all configured servers)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### void
This cmdlet returns a list of FAS server objects

## Notes

## Related Links

[Set-FasServer]()


