---
title: "/OUT (Ausgabedateiname) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT (C++-Linkeroption)"
  - "Linker [C++], Ausgabedateien"
  - "OUT (Linkeroption)"
  - "-OUT (Linkeroption)"
  - "Ausgabedateien, name (Linkeroption)"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /OUT (Ausgabedateiname)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 ein benutzerdefinierter Name für die Ausgabedatei.  Er wird anstelle des Standardnamens verwendet.  
  
## Hinweise  
 Die \/OUT\-Option überschreibt den Standardnamen und den Standardspeicherort des Programms, das der Linker erstellt.  
  
 Standardmäßig bildet der Linker den Dateinamen aus dem Basisnamen der zuerst angegebenen OBJ\-Datei und aus der entsprechenden Erweiterung \(**.exe** oder **.dll**\).  
  
 Mit dieser Option wird der Standardbasisname für eine MAP\-Datei oder eine Importbibliothek gebildet.  Ausführliche Informationen finden Sie unter [\/MAP \(Zuordnungsdatei generieren\)](../../build/reference/map-generate-mapfile.md) und [\/IMPLIB \(Name der Importbibliothek\)](../../build/reference/implib-name-import-library.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Ausgabedatei**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)