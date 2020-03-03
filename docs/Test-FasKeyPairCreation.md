# Test-FasKeyPairCreation

## Synopsis
Creates a key pair.

## Syntax

```
Test-FasKeyPairCreation [-AddToPrivateKeyPool <Boolean>] [-PrivateKeyPoolSizeLimit <Int32>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command creates a key pair using the FAS server's configured cryptographic settings.

Use this command to verify key pair creation is working.

The created key pair is discarded by default; use the AddToPrivateKeyPool parameter to add the key pair to the FAS server's private key pool
for use in a subsequent certificate signing request (CSR).
Doing this is advantageous because key pair creation is resource intensive.

Even if AddToPrivateKeyPool is set to $true, the created key pair is still discarded if the private key pool has reached its target size (as defined
by the FAS server's PrivateKeyPoolSize configuration setting).
Use the PrivateKeyPoolSizeLimit parameter to allow the key pool to
expand beyond its configured target size.

When the FAS service is stopped gracefully, unused keys in the private key pool are destroyed.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Test-FasKeyPairCreation -AddToPrivateKeyPool $true
```

Description

-----------

This code creates a key pair, and if successful adds the key pair to the FAS server's private key pool,
provided the key pool has not already reached its target size.

## Parameters

### -AddToPrivateKeyPool
If true, the created key pair is added to the FAS server's private key pool; if false the key pair is discarded

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateKeyPoolSizeLimit
Override the target private key pool size in the FAS server configuration (0 means do not override)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### Variable, based on property name.
This cmdlet does accept input from the pipeline but only by property name.

## Outputs

### DiagnosticTestResult
This cmdlet returns a DiagnosticTestResult object

## Notes

## Related Links

[Get-FasPrivateKeyPoolInfo]()


