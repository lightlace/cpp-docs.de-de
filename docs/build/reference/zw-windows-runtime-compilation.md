---
title: "/ZW (Windows-Runtime-Kompilierung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.CompileAsWinRT"
  - "/zw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ZW"
  - "/ZW-Compileroption"
  - "Windows-Runtime-Compileroption"
  - "-ZW"
  - "-ZW-Compileroption"
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /ZW (Windows-Runtime-Kompilierung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kompiliert Quellcode zur Unterstützung von [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\) für die Erstellung von [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps.  
  
 Wenn Sie **\/ZW** zum Kompilieren verwenden, geben Sie immer auch **\/EHsc** an.  
  
## Syntax  
  
```cpp  
/ZW /EHsc /ZW:nostdlib /EHsc  
```  
  
## Argumente  
 nostdlib  
 Gibt an, dass Platform.winmd, Windows.Foundation.winmd und andere Standard\-Windows\-Metadatendateien \(.winmd\) nicht automatisch in die Kompilierung eingeschlossen werden.  Stattdessen müssen Sie die Compileroption [\/FU \(Name Forced \#using File\)](../../build/reference/fu-name-forced-hash-using-file.md) verwenden, um explizit Windows\-Metadatendateien anzugeben.  
  
## Hinweise  
 Wenn Sie die Option **\/ZW** angeben, unterstützt der Compiler die folgenden Funktionen:  
  
-   Die erforderlichen Metadatendateien, Namespaces, Datentypen und Funktionen, die Ihre App benötigt, um in der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt zu werden  
  
-   Automatische Referenzzählung von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Objekten und automatisches Verwerfen eines Objekts, wenn seine Referenzzählung auf Null geht  
  
 Da der Incremental Linker die in .obj\-Dateien enthaltenen Windows\-Metadaten unter Verwendung der Option **\/ZW** nicht unterstützt, ist die Option [\/Gm \(Minimale Neuerstellung aktivieren\)](../../build/reference/gm-enable-minimal-rebuild.md) inkompatibel mit **\/ZW**.  
  
 Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C\+\+](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md).  
  
## Anforderungen  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)