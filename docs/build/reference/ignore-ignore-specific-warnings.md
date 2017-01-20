---
title: "/IGNORE (Bestimmte Warnungen ignorieren)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/ignore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNORE (Linkeroption)"
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# /IGNORE (Bestimmte Warnungen ignorieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNORE:warning[,warning]  
```  
  
## Parameter  
 `warning`  
 Die Anzahl der zu unterdrückenden Linkerwarnungen liegt im Bereich von 4000 auf 4999.  
  
## Hinweise  
 Standardmäßig meldet LINK alle Warnungen.  Legen Sie **\/IGNORE:**`warning`fest, um dem Linker mitzuteilen, eine bestimmte Warnungsnummer zu unterdrücken.  Wenn Sie mehrere Warnungen ignorieren, trennen Sie Warnungsnummern jeweils durch Komma.  
  
 Der Linker lässt einige Warnungen nicht ignoriert.  In dieser Tabelle werden die Warnungen aufgelistet, die nicht durch **\/IGNORE** unterdrückt werden:  
  
|Linker\-Warnung||  
|---------------------|-|  
|LNK4017|`keyword` Erklärung für die Zielplattform nicht unterstützt; ignoriert|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|Unbekannte Option "`option`"; ignoriert|  
|LNK4062|'`option`'nicht kompatibel mit dem''`architecture`' Zielcomputer; Option ignoriert|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|Ignoriert "`option1`" aufgrund der "`option2`" Spezifikation|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|Einstiegspunkt '`function`' ist nicht \_\_stdcall mit '`number`' Bytes an Argumenten; Abbild kann möglicherweise nicht ausgeführt werden.|  
|LNK4088|Anwendung wurde durch die Option \/Force generiert; Abbild kann möglicherweise nicht ausgeführt werden.|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|kein Argument angegeben mit der Option '`option`'; Schalter wird ignoriert|  
|LNK4203|Fehler beim Lesen der Programmdatenbank '`filename`'; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' fehlen Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' fehlen aktuelle Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|Vorkompilierte Typinformationen nicht gefunden; '`filename`' nicht verknüpft oder überschrieben; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4207|'`filename`' kompiliert\/Yc\/Yu\/Z7; PDB kann nicht erstellt werden; Kompilieren Sie mit\/ZI; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4208|Inkompatibles PDB\-Format in '`filename`'; Löschen und erneut erstellen; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|LNK4209|Debuginformationen beschädigt; Kompilieren Sie Modul erneut; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` wird nicht mehr unterstütz; ignoriert|  
|LNK4228|'`option`' ungültig für eine DLL; ignoriert|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|Ungültige Direktive \/`directive` gefunden; ignoriert|  
  
 Im Allgemeinen repräsentieren Linkerwarnungen, die nicht ignoriert werden können, Buildfehler, Befehlszeilenfehler oder Fehler bei der Konfiguration, die Sie beheben müssen.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Ordner **Linker** die Eigenschaftenseite **Befehlszeile** aus.  
  
3.  Ändern Sie die Eigenschaft **Zusätzliche Optionen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.