---
title: "/FUNCTIONPADMIN (Erstellen eines Hotpatch-f&#228;higen Abbildes) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/functionpadmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FUNCTIONPADMIN (Linkeroption)"
  - "-FUNCTIONPADMIN (Linkeroption)"
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /FUNCTIONPADMIN (Erstellen eines Hotpatch-f&#228;higen Abbildes)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bereitet ein Image für Hotpatching vor.  
  
## Syntax  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## Hinweise  
 wobei  
  
 `space` \(optional\)  
 Die Menge Padding, der dem Anfang jeder Funktion hinzuzufügen, 5, 6, 16 oder x86\-Bilder erfordern. fünf Bytes Abstand, benötigen x64\-Bilder 6 Bytes, und die Bilder, die für die Itanium\-Prozessorfamilie erstellt werden, erfordern 16 Bytes Innenabstand zu Beginn jeder Funktion.  
  
 In der Standardeinstellung fügt der Compiler auf Grundlage des Computertyps des Abbildes die erforderliche Menge an Füllzeichen in das Abbild ein.  
  
 Damit vom Linker ein Hotpatch\-fähiges Abbild erstellt wird, müssen die OBJj\-Dateien mit [\/hotpatch \(Erstellen eines Hotpatch\-fähigen Abbildes\)](../../build/reference/hotpatch-create-hotpatchable-image.md) kompiliert werden.  
  
 Wenn Sie beim Kompilieren ein Abbild mit einem einzelnen Aufruf von cl.exe verknüpfen, impliziert **\/hotpatch** die Option **\/functionpadmin**.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)