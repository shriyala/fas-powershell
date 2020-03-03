# Test-FasUserCertificateCrypto

## Synopsis
Performs a test signature operation with a user certificate.

## Syntax

```
Test-FasUserCertificateCrypto -UserPrincipalName <String> -Rule <String> [-CertificateDefinition <String>]
 [-HashingAlgorithm <String>] [-Address <String>] [-UserName <String>] [-Password <String>]
 [<CommonParameters>]
```

## Description
This command signs a piece of data using the private key bound to the user certificate with the given properties (i.e.
UPN and rule).
The signature created is discarded.

Use this test to verify cyptography is working for a particular user certificate.

If the certificate does not exist on the FAS server, it is not created and the test will fail.

If a Certificate Definition is not supplied, the test is performed using the first Certificate Definition of the specified Rule.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Test-FasUserCertificateCrypto -UserPrincipalName "fred@citrixtest.net" -Rule Default
```

Description

-----------

This code performs a test signature using a user certificate

## Parameters

### -UserPrincipalName
Specify the UPN assoicated with the user certificate.

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

### -Rule
Specify the Rule associated with the user certificate.

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

### -CertificateDefinition
Specify the Certificate Definition associated with the user certificate.
If not supplied, the first Certificate Definition of the Rule is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (the first certificate definition in the given rule)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

[New-FasUserCertificate]()

[Get-FasUserCertificate]()

[Test-FasCrypto]()


