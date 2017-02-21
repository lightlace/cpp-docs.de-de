---
title: "/PROFILE (Leistungstools-Profiler) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Profile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PROFILE (Linkeroption)"
  - "-PROFILE (Linkeroption)"
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /PROFILE (Leistungstools-Profiler)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Ausgabedatei, die mit dem Leistungstoolprofiler verwendet werden kann.  
  
## Syntax  
  
```  
/PROFILE  
```  
  
## Hinweise  
 \/PROFILE impliziert die folgenden Linkeroptionen:  
  
-   [\/OPT:REF](../../build/reference/opt-optimizations.md)  
  
-   \/OPT:NOICF  
  
-   [\/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [\/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)  
  
 \/PROFILE bewirkt, dass der Linker einen Verschiebungsabschnitt im Programmabbild generiert.  Ein Verschiebungsabschnitt ermöglicht dem Profiler, das Programmabbild zu transformieren, um Profildaten abzurufen.  
  
 **\/PROFILE** ist nur in Enterprise\-Versionen \(Teamentwicklung\) nur verfügbar.  Weitere Informationen zu PREfast finden Sie unter [Übersicht über die Codeanalyse für C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die Eigenschaft **Profil**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)