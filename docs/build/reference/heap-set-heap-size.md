---
title: "/HEAP (Heapgr&#246;&#223;e festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.HeapCommitSize"
  - "/heap"
  - "VC.Project.VCLinkerTool.HeapReserveSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HEAP (Linkeroption)"
  - "Heapzuordnung, Einstellen der Heapgröße"
  - "HEAP (Linkeroption)"
  - "-HEAP (Linkeroption)"
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /HEAP (Heapgr&#246;&#223;e festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/HEAP:reserve[,commit]  
```  
  
## Hinweise  
 Durch die Option **\/HEAP** wird die Heapgröße in Bytes festgelegt.  Diese Option ist nur für die Generierung von EXE\-Dateien vorgesehen.  
  
 Das *reserve*\-Argument gibt die gesamte Heapreservierung im virtuellen Speicher an.  Die Standardheapgröße beträgt 1 MB.  Der Linker rundet den angegebenen Wert auf die nächsten 4 Bytes auf.  
  
 Wie das optionale `commit`\-Argument interpretiert wird, hängt vom jeweiligen Betriebssystem ab.  Unter Windows NT\/Windows 2000 wird damit die physikalische Speichermenge bezeichnet, die zu einem Zeitpunkt belegt werden soll.  Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei.  Mit einem höheren `commit`\-Wert kann eine Zeitersparnis erreicht werden, wenn die Anwendung mehr Heapspeicher benötigt; gleichzeitig erhöht sich dadurch aber auch der Arbeitsspeicherbedarf und möglicherweise die Ladezeit.  
  
 Geben Sie die Werte für *reserve* und *commit* dezimal oder in C\-Notation an.  
  
 Diese Funktion ist auch über eine Moduldefinitionsdatei mit [HEAPSIZE](../../build/reference/heapsize.md) verfügbar.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **System**.  
  
4.  Ändern Sie die Eigenschaft **Heapbestätigungsgröße**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)