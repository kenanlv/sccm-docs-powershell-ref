﻿---
description: Gets a reporting service point.
external help file: AdminUI.PS.dll-Help.xml
Module Name: ConfigurationManager
ms.date: 05/02/2019
schema: 2.0.0
title: Get-CMReportingServicePoint
---

# Get-CMReportingServicePoint

## SYNOPSIS
Gets a reporting service point.

## SYNTAX

### SearchByName (Default)
```
Get-CMReportingServicePoint [-AllSite] [-SiteCode <String>] [[-SiteSystemServerName] <String>]
 [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```

### SearchByValue
```
Get-CMReportingServicePoint [-AllSite] -InputObject <IResultObject> [-DisableWildcardHandling]
 [-ForceWildcardHandling] [<CommonParameters>]
```

## DESCRIPTION
The **Get-CMReportingServicePoint** cmdlet gets a reporting service point.
A reporting service point is a site system role that is installed on a server that runs Microsoft SQL Server Reporting Services.

> [!NOTE]
> Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:\>`. For more information, see [getting started](/powershell/sccm/overview).

## EXAMPLES

### Example 1: Get a reporting service point
```
PS XYZ:\> Get-CMReportingServicePoint -SiteSystemServerName "CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM" -SiteCode "CM1" >>\Cmrsp01\Get-CMReportingServicePoint_data.txt
```

This command gets a reporting service point from the Configuration Manager site that has the site code CM1 on the site system server named CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM.
The command directs the output to the file \Cmrsp01\Get-CMReportingServicePoint_data.txt.

## PARAMETERS

### -AllSite
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: AllSites

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: IResultObject
Parameter Sets: SearchByValue
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SiteCode
Specifies the site code of the Configuration Manager site that hosts the site system role.

```yaml
Type: String
Parameter Sets: SearchByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteSystemServerName
Specifies a fully qualified domain name (FQDN) of the server that hosts the site system role.

```yaml
Type: String
Parameter Sets: SearchByName
Aliases: Name, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ConfigurationManagement.ManagementProvider.IResultObject

## OUTPUTS

### IResultObject[]#SMS_SCI_SysResUse

### IResultObject#SMS_SCI_SysResUse

## NOTES

## RELATED LINKS

[Add-CMReportingServicePoint](Add-CMReportingServicePoint.md)

[Remove-CMReportingServicePoint](Remove-CMReportingServicePoint.md)

[Set-CMReportingServicePoint](Set-CMReportingServicePoint.md)


