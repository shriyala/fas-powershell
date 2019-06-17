# Remove-FasAuthorizationCertificate

## Synopsis
This command deletes a FAS Authorization Certificate and associated private key

## Syntax

```
Remove-FasAuthorizationCertificate -Id <String> [-DeleteUserCerts <Boolean>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command deletes a FAS Authorization Certificate and associated private key. 
Note that this may affect the operation of the FAS server.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Remove-FasAuthorizationCertificate -Id (Get-FasAuthorizationCertificate)[0].Id
```

Description

-----------

This code lists the Authorization certificates on a FAS server and deletes the first one in the list.

## Parameters

### -Id
Guid of the Authorization Certificate to delete

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: $NULL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeleteUserCerts
Flag to indicate if the user certificates should also be deleted

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $TRUE
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

### -Address
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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
This cmdlet does not return a value

## Notes

## Related Links

[New-FasAuthorizationCertificate]()

[Get-FasAuthorizationCertificate]()


