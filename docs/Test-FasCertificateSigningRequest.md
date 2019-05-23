# Test-FasCertificateSigningRequest

## Synopsis
Performs a test certificate signing request (CSR)

## Syntax

```
Test-FasCertificateSigningRequest -UserPrincipalName <String> -Rule <String> [-CertificateDefinition <String>]
 [-CertificateAuthority <String>] [-SecurityContext <String>] [-ReuseCachedTestKey <String>]
 [-Address <String>] [-UserName <String>] [-Password <String>] [<CommonParameters>]
```

## Description
This command performs a test CSR.
Any resulting certificate is discarded.

Use this test to verify CSRs to the Certificate Authority are working.

The supplied Certificate Definition defines the certificate template, authorization certificate and policy oids
used for the CSR.
The supplied Certificate Authority address must be present in the supplied CertificateDefinition.

If ReuseCachedTestKey is false, a new key-pair is created for the CSR.

If ReuseCachedTestKey is true, the test re-uses a cached key-pair for the CSR in order to avoid the overhead of generating a new key-pair.
The cached key-pair is generated on demand per UPN, and is re-used for a maximum of 1 hour, after which a new key-pair is generated.

## Examples

### Example 1
PS C:\\\>

```
C:\PS> $CitrixFasAddress=(Get-FasServer)[0].Address
C:\PS> Test-FasCertificateSigningRequest -UserPrincipalName "fred@citrixtest.net" -Rule Default
```

Description

-----------

This code performs a test CSR.

## Parameters

### -UserPrincipalName
Specify the UPN of the user for whom this certificate is being generated.

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
Specify the Rule name to use when generating the CSR.

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
Specify the Certificate Definition to use when generating the CSR.
If not supplied, the first Certificate Definition of the Rule is used.

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

### -CertificateAuthority
Specify the address of Certificate Authority to send the CSR to.
If not supplied, the first Certificate Authority of the Certificate Definition is used.

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

### -SecurityContext
Specify the Security Context to use when generating the certificate.

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

### -ReuseCachedTestKey
Specify whether to re-use a test key-pair in the CSR.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Address
Address of FAS Server (or $NULL to use $CitrixFasAddress).

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
User name to use for authentication to FAS server ($NULL for current user account).

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
Password for authentication to FAS server ($NULL for current user account).

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

