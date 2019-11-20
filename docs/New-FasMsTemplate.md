# New-FasMsTemplate

## Synopsis
Installs a Microsoft Certificate Template file into the current Active Directory environment.

## Syntax

```
New-FasMsTemplate -FileName <String> [-Acl <String>] [<CommonParameters>]
```

## Description
Loads a certificate template XML file and installs it to Active Directory, optionally setting a security descriptor.

Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. 
This includes information such as the validity period and how the certificate should be authorized.

The Citrix Federated Authentication Service supplies a number of human-readable XML certificate templates that can be reviewed and installed using this commandlet. 
Alternatively the equivalent templates can be created using the standard Microsoft Certifiate Template Administration tools.

By default the ACL placed on the Certificate Template will allow only Domain Administrators to have full control of the installed Certificate Template. 
If this is not suitable the -Acl \<SDDL\> parameter can be used to specify a security descriptor.

Note that this cmdlet must be run using a High Privilege user account. 
Equivalent configuration can be done manually using the Microsoft GUI tools, or scripted using the CX509CertificateTemplateADWritable COM object in CertEnroll.dll:

$template = \[System.IO.File\]::ReadAllBytes("$Pwd\Citrix_SecureServerRole.certificatetemplate")
$CertEnrol = New-Object -ComObject X509Enrollment.CX509EnrollmentPolicyWebService
$CertEnrol.InitializeImport($template)
$comtemplate = $CertEnrol.GetTemplates().ItemByIndex(0)

$writabletemplate = New-Object -ComObject X509Enrollment.CX509CertificateTemplateADWritable
$writabletemplate.Initialize($comtemplate)
$writabletemplate.Commit(1, $NULL)

## Examples

### Example 1
PS C:\\\>

```
C:\PS> New-FasMsTemplate -FileName ./Citrix_SmartcardLogon.certificatetemplate" -Acl "D:PAI(A;OICI;FA;;;DA)"
```

Description

-----------

Read the specified certificate template file and install it into Active Directory applying a "Domain Administrator Full Control" ACL

## Parameters

### -FileName
Specifies the .certificatetemplate file to install.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: (required)
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Acl
Specify an ACL to apply to the Certificate Template in SDDL format.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: D:PAI(A;OICI;FA;;;DA)
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
This cmdlet does not return a value

## Notes

## Related Links

[Get-FasMsTemplate]()

[Publish-FasMsTemplate]()

[Unpublish-FasMsTemplate]()

[Remove-FasMsTemplate]()


