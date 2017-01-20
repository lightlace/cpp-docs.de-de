---
title: "/LIBPATH (Libpath-Pfad hinzuf&#252;gen)"
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
  - "/libpath"
  - "VC.Project.VCLinkerTool.AdditionalLibraryDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LIBPATH (Linkeroption)"
  - "Libpath-Pfad hinzufügen (Linkeroption)"
  - "Überschreibung des Bibliothekspfads der Umgebung"
  - "LIBPATH (Linkeroption)"
  - "-LIBPATH (Linkeroption)"
  - "Bibliothekspfad (Linkeroption)"
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /LIBPATH (Libpath-Pfad hinzuf&#252;gen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LIBPATH:dir  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `dir`  
 ein Pfad, den der Linker durchsucht, bevor er den in der Umgebungsvariablen **LIB** angegebenen Pfad durchsucht.  
  
## Hinweise  
 Mit der Option **\/LIBPATH** wird der Bibliothekspfad aus der Umgebungsvariablen überschrieben.  Der Linker durchsucht zuerst den in dieser Option angegebenen Pfad und danach den in der Umgebungsvariablen **LIB** angegebenen Pfad.  Sie können für jede eingegebene **\/LIBPATH**\-Option nur ein Verzeichnis angeben.  Wenn Sie mehrere Verzeichnisse angeben möchten, müssen Sie mehrere **\/LIBPATH**\-Optionen eingeben.  Der Linker durchsucht dann die angegebenen Verzeichnisse in der gegebenen Reihenfolge.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Bearbeiten Sie die Eigenschaft **Zusätzliche Bibliotheksverzeichnisse**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)