---
title: "/DEFAULTLIB (Standardbibliothek festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.DefaultLibraries"
  - "/defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEFAULTLIB (Linkeroption)"
  - "DEFAULTLIB (Linkeroption)"
  - "-DEFAULTLIB (Linkeroption)"
  - "Bibliotheken, Hinzufügen zur Liste der"
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /DEFAULTLIB (Standardbibliothek festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEFAULTLIB:library  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *library*  
 der Name einer Bibliothek, die beim Auflösen externer Verweise gesucht wird.  
  
## Hinweise  
 Die Option **\/DEFAULTLIB** fügt eine *Bibliothek* zur Liste der Bibliotheken hinzu, die **LINK** beim Auflösen von Verweisen durchsucht.  Eine mit **\/DEFAULTLIB** angegebene Bibliothek wird nach den in der Befehlszeile genannten Bibliotheken und vor den in OBJ\-Dateien genannten Standardbibliotheken durchsucht.  
  
 Die Option [\/NODEFAULTLIB \(Bibliotheken ignorieren\)](../../build/reference/nodefaultlib-ignore-libraries.md) überschreibt die Option **\/DEFAULTLIB**:*Bibliothek*.  Die Option [\/NODEFAULTLIB \(Bibliotheken ignorieren\)](../../build/reference/nodefaultlib-ignore-libraries.md) überschreibt **\/DEFAULTLIB**:*Bibliothek*, wenn in beiden Optionen derselbe *Bibliothek*sname verwendet wird.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
-   Die Linkeroption ist in der Visual Studio\-Entwicklungsumgebung nicht verfügbar.  Wenn Sie eine Bibliothek in der Verknüpfungsphase einfügen möchten, müssen Sie auf der Eigenschaftenseite **Eingabe** die Eigenschaft **Zusätzliche Abhängigkeiten** verwenden.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)