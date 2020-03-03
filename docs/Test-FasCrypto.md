# Test-FasCrypto

## Synopsis
Performs a test signature operation

## Syntax

```
Test-FasCrypto [-HashingAlgorithm <String>] [-ReuseCachedTestKey <Boolean>] [-Address <String>]
 [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command signs a piece of data using a test private key.
The signature created is discarded.

Use this test to verify cyptography is working.

If ReuseCachedTestKey is false, a new key-pair is created for the signing operation.

If ReuseCachedTestKey is true, the test re-uses a cached key-pair for the signing operation in order to avoid the overhead of generating a new key-pair.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Test-FasCrypto
```

Description

-----------

This code performs a signature using a test private key

## Parameters

### -HashingAlgorithm
Specify the hashing algorithm to use when performing the signature.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReuseCachedTestKey
Specify whether to re-use a test key-pair in the signing operation.

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

[Test-FasUserCertificateCrypto]()


