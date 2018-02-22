# Get-FasMsCertificateAuthority

Retrieve information about the Microsoft Certificate Authorities installed in the domain.

## Syntax

`Get-FasMsCertificateAuthority [-Address <String>] [-Default [<Boolean>]] [<CommonParameters>]`

## Detailed Description

This commandlet retrieves information about the Microsoft Certificate Authorities installed in the domain, including their unique identifying addresses.

## Related Commands

-  [Publish-FasMsTemplate](Publish-FasMsTemplate.md) 

-  [Unpublish-FasMsTemplate](Unpublish-FasMsTemplate.md)

## Parameters

| Name    | Description                                                                                                   | Required? | Pipeline Input        | Default Value |
|---------|---------------------------------------------------------------------------------------------------------------|-----------|-----------------------|---------------|
| Address | Specifies the address of the Microsoft Certificate Authority to retrieve information about (or list them all) | false     | true (ByPropertyName) | \$NULL        |
| Default | Return the default or primary Microsoft Certificate Authority in the current domain.                          | false     | true (ByPropertyName) | \$FALSE       |

## Input Type

### Variable, based on property name

This cmdlet does accept input from the pipeline but only by property name.

## Return Values

### void

This cmdlet returns a list of Microsoft Certificate Authority objects

## Examples

### EXAMPLE 1

    C:\PS> Get-FasMsCertificateAuthority -Default

This command retrieves the address of the default Microsoft Certificate Authority in this domain.
