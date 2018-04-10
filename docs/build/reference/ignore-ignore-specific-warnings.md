---
title: -IGNORE (bestimmte Warnungen ignorieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /OVERWRITE
dev_langs:
- C++
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d8815438ce56629bd120c30b0d0db9fef96916d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (Bestimmte Warnungen ignorieren)
```  
/IGNORE:warning[,warning]  
```  
  
## <a name="parameters"></a>Parameter  
 `warning`  
 Die Anzahl der zu unterdrückenden Linkerwarnungen liegt im Bereich von 4000 auf 4999.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig meldet LINK alle Warnungen. Geben Sie **/ignorieren:** `warning` anzuweisen, den Linker an, eine bestimmte Warnungsnummer zu unterdrücken. Wenn Sie mehrere Warnungen ignorieren, trennen Sie Warnungsnummern jeweils durch Komma.  
  
 Der Linker lässt einige Warnungen nicht ignoriert. Diese Tabelle enthält die nicht von der unterdrückte Warnungen **/ignorieren**:  
  
|Linker-Warnung||  
|--------------------|-|  
|LNK4017|`keyword`die Anweisung für die Zielplattform nicht unterstützt. ignoriert|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|Unbekannte Option "`option`"; ignoriert|  
|LNK4062|'`option`'nicht kompatibel mit dem''`architecture`' Zielcomputer; Option ignoriert|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|Ignoriert "`option1`" aufgrund der "`option2`" Spezifikation|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|Einstiegspunkt '`function`' ist nicht __stdcall mit '`number`' Bytes an Argumenten; Abbild kann möglicherweise nicht ausgeführt werden.|  
|LNK4088|Anwendung wurde durch die Option /Force generiert; Abbild kann möglicherweise nicht ausgeführt werden.|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|kein Argument angegeben mit der Option '`option`'; Schalter wird ignoriert|  
|LNK4203|Fehler beim Lesen der Programmdatenbank '`filename`'; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' fehlen Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' fehlen aktuelle Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|Vorkompilierte Typinformationen nicht gefunden; '`filename`' nicht verknüpft oder überschrieben; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4207|'`filename`' kompiliert/Yc/Yu/Z7; PDB kann nicht erstellt werden; Kompilieren Sie mit/ZI; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4208|Inkompatibles PDB-Format in '`filename`'; Löschen und erneut erstellen; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4209|Debuginformationen beschädigt; Kompilieren Sie Modul erneut; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option`wird nicht mehr unterstützt. ignoriert|  
|LNK4228|'`option`' ungültig für eine DLL; ignoriert|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|Ungültige Direktive /`directive` gefunden; ignoriert|  
  
 Im Allgemeinen repräsentieren Linkerwarnungen, die nicht ignoriert werden können, Buildfehler, Befehlszeilenfehler oder Fehler bei der Konfiguration, die Sie beheben müssen.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  In der **Linker** Ordner, wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
3.  Ändern der **Zusatzoptionen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.