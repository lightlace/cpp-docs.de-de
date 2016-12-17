---
title: "/CLRTHREADATTRIBUTE (Festlegen des CLR-Threadattributs)"
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
  - "VC.Project.VCLinkerTool.CLRThreadAttribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRTHREADATTRIBUTE (Linkeroption)"
  - "-CLRTHREADATTRIBUTE (Linkeroption)"
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# /CLRTHREADATTRIBUTE (Festlegen des CLR-Threadattributs)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Threadattribut für den Einstiegspunkt des CLR\-Programms explizit an.  
  
## Syntax  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### Parameter  
 MTA  
 Wendet das MTAThreadAttribute\-Attribut auf den Einstiegspunkt des Programms an.  
  
 NONE  
 Entspricht einer nicht vorhandenen Angabe von \/CLRTHREADATTRIBUTE.  Common Language Runtime \(CLR\) legt das Standardthreadingattribut fest.  
  
 STA  
 Wendet das STAThreadAttribute\-Attribut auf den Einstiegspunkt des Programms an.  
  
## Hinweise  
 Das Festlegen des Threadattributs ist nur bei Erstellen einer EXE\-Datei gültig, da es den Einstiegspunkt des Hauptthreads betrifft.  
  
 Wenn Sie den Standardeinstiegspunkt \(z. B. main oder wmain\) verwenden, geben Sie das Threadingmodell entweder durch Verwenden von \/CLRTHREADATTRIBUTE oder durch Platzieren des Threadingattributs \(STAThreadAttribute oder MTAThreadAttribute\) in der Standardeinstiegsfunktion an.  
  
 Wenn Sie einen nicht standardmäßigen Einstiegspunkt verwenden, geben Sie das Threadingmodell entweder durch Verwenden von \/CLRTHREADATTRIBUTE oder durch Platzieren des Threadingattributs in der nicht standardmäßigen Einstiegsfunktion an. Geben Sie anschließend den nicht standardmäßigen Einstiegspunkt mit [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) an.  
  
 Wenn das im Quellcode angegebene Threadingmodell nicht mit dem durch \/CLRTHREADATTRIBUTE angegebenen Threadingmodell übereinstimmt, wird \/CLRTHREADATTRIBUTE vom Linker ignoriert und das im Quellcode angegebene Threadingmodell angewendet.  
  
 Sie müssen z. B. Singlethreading verwenden, wenn Ihr CLR\-Programm ein COM\-Objekt hostet, das Singlethreading verwendet.  Wenn das CLR\-Programm Multithreading verwendet, kann kein COM\-Objekt gehostet werden, das Singlethreading verwendet.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die **CLR\-Threadattribut**\-Eigenschaft.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)