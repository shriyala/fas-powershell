# New-FasMsTemplate

Installs a Microsoft Certificate Template file into the current Active Directory environment.

## Syntax

`New-FasMsTemplate -FileName <String> [-Acl <String>] [<CommonParameters>]`

## Detailed Description

Loads a certificate template XML file and installs it to Active Directory, optionally setting a security descriptor. Microsoft Certificate Authority uses Certificate Templates to describe the types of certificates that it can issue. This includes information such as the validity period and how the certificate should be authorized. The Citrix Federated Authentication Service supplies a number of human-readable XML certificate templates that can be reviewed and installed using this commandlet. Alternatively the equivalent templates can be created using the standard Microsoft Certifiate Template Administration tools. By default the ACL placed on the Certificate Template will allow only Domain Administrators to have full control of the installed Certificate Template. If this is not suitable the -Acl &lt;SDDL&gt; parameter can be used to specify a security descriptor. Note that this cmdlet must be run using a High Privilege user account. Equivalent configuration can be done manually using the Microsoft GUI tools, or scripted using the CX509CertificateTemplateADWritable COM object in CertEnroll.dll: \$template = \[System.IO.File\]::ReadAllBytes("\$Pwd\\Citrix\_SecureServerRole.certificatetemplate") \$CertEnrol = New-Object -ComObject X509Enrollment.CX509EnrollmentPolicyWebService \$CertEnrol.InitializeImport(\$template) \$comtemplate = \$CertEnrol.GetTemplates().ItemByIndex(0) \$writabletemplate = New-Object -ComObject X509Enrollment.CX509CertificateTemplateADWritable \$writabletemplate.Initialize(\$comtemplate) \$writabletemplate.Commit(1, \$NULL)

## Related Commands

-  [Get-FasMsTemplate](Get-FasMsTemplate.md) 

-  [Publish-FasMsTemplate](Publish-FasMsTemplate.md) 

-  [Unpublish-FasMsTemplate](Unpublish-FasMsTemplate.md) 

-  [Remove-FasMsTemplate](Remove-FasMsTemplate.md)

## Parameters

| Name     | Description                                                         | Required? | Pipeline Input        | Default Value         |
|----------|---------------------------------------------------------------------|-----------|-----------------------|-----------------------|
| FileName | Specifies the .certificatetemplate file to install.                 | true      | true (ByPropertyName) | (required)            |
| Acl      | Specify an ACL to apply to the Certificate Template in SDDL format. | true      | true (ByPropertyName) | D:PAI(A;OICI;FA;;;DA) |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet does not return a value

## Examples

### EXAMPLE 1

    C:\PS> New-FasMsTemplate -FileName ./Citrix_SmartcardLogon.certificatetemplate" -Acl "D:PAI(A;OICI;FA;;;DA)"

Read the specified certificate template file and install it into Active Directory applying a "Domain Administrator Full Control" ACL
