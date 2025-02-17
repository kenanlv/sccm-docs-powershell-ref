---
description: Creates an operating system image update schedule.
external help file: AdminUI.PS.dll-Help.xml
Module Name: ConfigurationManager
ms.date: 05/07/2019
schema: 2.0.0
title: New-CMOperatingSystemImageUpdateSchedule
---

# New-CMOperatingSystemImageUpdateSchedule

## SYNOPSIS
Creates an operating system image update schedule.

## SYNTAX

### NewScheduleByInputObject (Default)
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>]
 -InputObject <IResultObject> [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]>
 [-UpdateDistributionPoint <Boolean>] [-Utc <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NewScheduleByName
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>]
 [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>]
 [-Utc <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NewScheduleById
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>]
 [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>]
 [-Utc <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NewScheduleByScheduleInputObject
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-CustomSchedule <DateTime>]
 [-RemoveSupersededUpdates <Boolean>] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>]
 [-Utc <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NewScheduleByIdRunNow
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] -Id <String>
 [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]>
 [-UpdateDistributionPoint <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NewScheduleByInputObjectRunNow
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] -InputObject <IResultObject>
 [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]>
 [-UpdateDistributionPoint <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NewScheduleByNameRunNow
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] -Name <String>
 [-RemoveSupersededUpdates <Boolean>] [-RunNow] -SoftwareUpdate <IResultObject[]>
 [-UpdateDistributionPoint <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NewScheduleByScheduleInputObjectRunNow
```
New-CMOperatingSystemImageUpdateSchedule [-ContinueOnError <Boolean>] [-RemoveSupersededUpdates <Boolean>]
 [-RunNow] -SoftwareUpdate <IResultObject[]> [-UpdateDistributionPoint <Boolean>] [-DisableWildcardHandling]
 [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-CMOperatingSystemImageUpdateSchedule** cmdlet creates an operating system image update schedule.

> [!NOTE]
> Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:\>`. For more information, see [getting started](/powershell/sccm/overview).

## EXAMPLES

### Example 1: Create an operating system image update schedule
```
PS ABC:\> $Win10Image = Get-CMOperatingSystemImage -Name "Windows 10 Enterprise"
PS ABC:\> $Win10SU = Get-CMSoftwareUpdate -UpdateGroupName "Win10SUgroup01"
PS ABC:\> New-CMOperatingSystemImageUpdateSchedule -Name $Win10Image.Name -SoftwareUpdate $Win10SU -RunNow -ContinueOnError $True
```

The first command gets the operating system image object named Windows 10 Enterprise and stores the object in the $Win10Image variable.

The second command gets the software update object for the update group named Win10SUgroup01 and stores the object in the $Win10SU variable.

The last command creates an operating system image update schedule to update the operating system image named Windows 10 Enterprise with the update stored in $Win10SU.
The update will run now, and will continue to apply the updates even if an error is encountered.

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

### -ContinueOnError
Indicates whether software updates should be applied to the image even when there is an error.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomSchedule
Specifies the date and time when the software updates are applied to the operating system image.

```yaml
Type: DateTime
Parameter Sets: NewScheduleByInputObject, NewScheduleByName, NewScheduleById, NewScheduleByScheduleInputObject
Aliases:

Required: False
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

### -Id
Specifies the ID of an operating system image.

```yaml
Type: String
Parameter Sets: NewScheduleByIdRunNow
Aliases: PackageId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an operating system image object.
To obtain an operating system image object, use the [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage.md) cmdlet.

```yaml
Type: IResultObject
Parameter Sets: NewScheduleByInputObject, NewScheduleByInputObjectRunNow
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of an operating system image.

```yaml
Type: String
Parameter Sets: NewScheduleByNameRunNow
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSupersededUpdates
{{ Fill RemoveSupersededUpdates Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: CleanUp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow
Indicates that the update should run now.

```yaml
Type: SwitchParameter
Parameter Sets: NewScheduleByIdRunNow, NewScheduleByInputObjectRunNow, NewScheduleByNameRunNow, NewScheduleByScheduleInputObjectRunNow
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftwareUpdate
Specifies an array of software update objects.
To obtain a software update object, use the [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate.md) cmdlet.

```yaml
Type: IResultObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateDistributionPoint
Indicates whether the operating system image on distribution points is updated after the software updates are applied.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: UpdateDistributionPointsWithImage, UpdateDistributionPoints

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Utc
Indicates whether to use UTC time.

```yaml
Type: Boolean
Parameter Sets: NewScheduleByInputObject, NewScheduleByName, NewScheduleById, NewScheduleByScheduleInputObject
Aliases:

Required: False
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

### IResultObject#SMS_ImageServicingSchedule

## NOTES

## RELATED LINKS

[Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule.md)

[Clear-CMOperatingSystemImageUpdateSchedule](Clear-CMOperatingSystemImageUpdateSchedule.md)
