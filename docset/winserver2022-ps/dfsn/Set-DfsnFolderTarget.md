---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceFolderTarget.cdxml-help.xml
manager: jasgro
Module Name: DFSN
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dfsn/set-dfsnfoldertarget?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsnFolderTarget
---

# Set-DfsnFolderTarget

## SYNOPSIS
Changes settings for a target of a DFS namespace folder.

## SYNTAX

```
Set-DfsnFolderTarget [-Path] <String> [-TargetPath] <String> [[-State] <State>]
 [[-ReferralPriorityClass] <ReferralPriorityClass>] [[-ReferralPriorityRank] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsnRootTarget** cmdlet changes settings for a target of a Distributed File System (DFS) namespace folder.
You can change the state of the DFS namespace target and configure priority class and priority rank for referrals.

A DFS namespace folder has one or more folder targets that are shared folders on computers.
When a client attempts to connect to a folder, the DFS namespace server provides a list of folder targets, called referrals.
The server determines the order for referrals and clients attempt to connect to a folder target in the order that the server provides.

For more information about DFS namespaces, see [Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Change the state for a folder target
```
PS C:\> Set-DfsnFolderTarget -Path "\\Contoso\AccountingResources\LegacySoftware" -TargetPath "\\Contoso-FS\LegacySoftware" -State Online
```

This command changes the state for a target for the folder \\\\Contoso\AccountingResources\LegacySoftware to Online.
The folder target is \\\\Contoso-FS\LegacySoftware.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Path
Specifies a path for the DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferralPriorityClass
Specifies the priority class for a DFS namespace folder target.
Target priority offers you the ability to classify and rank in-site targets.
You can specify targets to receive the highest or lowest preference, and you can divide the remaining targets based on their site cost for a DFS client to connect to them.
The acceptable values for this parameter are:

- GlobalHigh.
The highest priority class for a DFS target.
Targets assigned this class receive global preference. 
- SiteCostHigh.
The highest site cost priority class for a DFS target.
Targets assigned this class receive the most preference among targets of the same site cost for a given DFS client.
- SiteCostNormal.
The middle or normal site cost priority class for a DFS target. 
- SiteCostLow.
The lowest site cost priority class for a DFS target.
Targets assigned this class receive the least preference among targets of the same site cost for a given DFS client.
- GlobalLow.
The lowest level of priority class for a DFS target.
Targets assigned this class receive the least preference globally.

```yaml
Type: ReferralPriorityClass
Parameter Sets: (All)
Aliases: PriorityClass, Class
Accepted values: sitecostnormal, globalhigh, sitecosthigh, sitecostlow, globallow

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferralPriorityRank
Specifies the priority rank, as an integer, for a target of the DFS namespace folder.
Lower values have greater preference.
A value of zero (0) is the greatest preference.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: PriorityRank, Rank

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the DFS namespace folder target.
The acceptable values for this parameter are:

- Online
- Offline

Clients do not receive referrals for a DFS namespace target that is offline.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 
Accepted values: Offline, Online

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPath
Specifies a path for a target of the DFS namespace folder.
This cmdlet changes settings for the target that the path specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Target, DfsTarget, FolderTarget

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolderTarget

## NOTES

## RELATED LINKS

[Get-DfsnFolderTarget](./Get-DfsnFolderTarget.md)

[New-DfsnFolderTarget](./New-DfsnFolderTarget.md)

[Remove-DfsnFolderTarget](./Remove-DfsnFolderTarget.md)

[Set-DfsnFolderTarget](./Set-DfsnFolderTarget.md)
