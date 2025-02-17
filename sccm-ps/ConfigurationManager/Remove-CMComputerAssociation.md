---
description: Deletes a computer association from Configuration Manager.
external help file: AdminUI.PS.dll-Help.xml
Module Name: ConfigurationManager
ms.date: 05/07/2019
schema: 2.0.0
title: Remove-CMComputerAssociation
---

# Remove-CMComputerAssociation

## SYNOPSIS
Deletes a computer association from Configuration Manager.

## SYNTAX

### SearchByNameMandatory (Default)
```
Remove-CMComputerAssociation -DestinationComputer <String> [-Force] -SourceComputer <String>
 [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SearchByValueMandatory
```
Remove-CMComputerAssociation [-Force] -InputObject <IResultObject> [-DisableWildcardHandling]
 [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SearchByIdMandatory
```
Remove-CMComputerAssociation [-Force] -MigrationId <String> [-DisableWildcardHandling] [-ForceWildcardHandling]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CMComputerAssociation** cmdlet deletes a computer association from Configuration Manager.
You can specify the association to remove by specifying both computers in the association or by specifying the association ID, or you can use the **Get-CMComputerAssociation** cmdlet to get an association to remove.

> [!NOTE]
> Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:\>`. For more information, see [getting started](/powershell/sccm/overview).

## EXAMPLES

### Example 1: Remove an association by using computer names
```
PS XYZ:\> Remove-CMComputerAssociation -DestinationComputer "West155" -SourceComputer "West073"
```

This command removes the computer association between the computers named West155 and West073.

### Example 2: Remove an association by using an ID
```
PS XYZ:\> Remove-CMComputerAssociation -MigrationId "MID1207" -Force
```

This command removes the computer association that has the ID MID1207.
This command uses the *Force* parameter, so the cmdlet does not prompt you for confirmation before it removes the association.

### Example 3: Remove an association by using a variable
```
PS XYZ:\> $CMCA = Get-CMComputerAssociation -MigrationId "MID1207"
PS XYZ:\> Remove-CMComputerAssociation -InputObject $CMCA -Force
```

The first command gets the computer association that has the ID MID1207, and saves it in the $CMCA variable.

The second command removes the association saved in the $CMCA variable.
This command uses the *Force* parameter, so the cmdlet does not prompt you for confirmation before it removes the association.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputer
Specifies the name of a destination computer.

```yaml
Type: String
Parameter Sets: SearchByNameMandatory
Aliases: RestoreName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableWildcardHandling

This parameter treats wildcard characters as literal character values. You can't combine it with **ForceWildcardHandling**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceWildcardHandling

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with **DisableWildcardHandling**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies a computer association object.
To obtain a computer association object, use the Get-CMComputerAssociation cmdlet.

```yaml
Type: IResultObject
Parameter Sets: SearchByValueMandatory
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MigrationId
Specifies the ID of a computer association.

```yaml
Type: String
Parameter Sets: SearchByIdMandatory
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputer
Specifies the name of the source computer.

```yaml
Type: String
Parameter Sets: SearchByNameMandatory
Aliases: SourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet doesn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ConfigurationManagement.ManagementProvider.IResultObject

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-CMComputerAssociation](Get-CMComputerAssociation.md)

[New-CMComputerAssociation](New-CMComputerAssociation.md)

[Set-CMComputerAssociation](Set-CMComputerAssociation.md)


