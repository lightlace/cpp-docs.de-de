---
title: "/LN (Erstellen eines MSIL-Moduls) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/LN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LN (Compileroption) [C++]"
  - "-LN (Compileroption) [C++]"
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /LN (Erstellen eines MSIL-Moduls)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt fest, dass ein Assemblymanifest nicht in die Ausgabedatei eingefügt wird.  
  
## Syntax  
  
```  
/LN  
```  
  
## Hinweise  
 Standardmäßig ist **\/LN** nicht aktiviert \(ein Assemblymanifest wird in die Ausgabedatei eingefügt\).  
  
 Wenn **\/LN** verwendet wird, muss auch eine der [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)\-Optionen verwendet werden.  
  
 Ein verwaltetes Programm, das keine Assemblymetadaten im Manifest aufweist, wird als Modul bezeichnet.  Wenn Sie mit [\/c \(Kompilieren ohne Verknüpfen\)](../../build/reference/c-compile-without-linking.md) und **\/LN** kompilieren, legen Sie in der Linkerphase die [\/NOASSEMBLY \(MSIL\-Modul erstellen\)](../../build/reference/noassembly-create-a-msil-module.md)\-Option fest, um ein Modul zu erstellen.  
  
 Sie sollten Module erstellen, wenn Sie Assemblys mit einer komponentenbasierte Methode erstellen möchten.  Auf diese Weise können Sie Typen erstellen und sie in Module kompilieren.  Anschließend generieren Sie eine Assembly aus einem oder mehreren Modulen.  Weitere Informationen zum Erstellen von Assemblys aus Modulen finden Sie unter [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md) oder [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
 Die Standarddateierweiterung für ein Modul handelt .netmodule.  
  
 In [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]\-Versionen vor Visual C\+\+ 2005 wurde ein Modul mit **\/clr:noAssembly** erstellt.  
  
 Der Visual C\+\+\-Linker akzeptiert .netmodule\-Dateien, als Eingabe und der Ausgabedatei erzeugt vom Linker eine Assembly oder .netmodule ohne Ablaufabhängigkeit auf einem der .netmodules ist, die als Eingabe für den Linker wurden.  Weitere Informationen finden Sie unter [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
-   Geben in der Linkerphase [\/NOASSEMBLY \(MSIL\-Modul erstellen\)](../../build/reference/noassembly-create-a-msil-module.md) an, um die Ausgabedatei zu erstellen.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Diese Compileroption kann nicht programmgesteuert geändert werden.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)