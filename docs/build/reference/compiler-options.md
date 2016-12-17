---
title: "Compileroptionen"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler"
  - "Compileroptionen, C++"
  - "IPF (Visual C++-Compiler)"
  - "Itanium (Visual C++-Compiler)"
  - "x64 (Visual C++-Compiler)"
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Compileroptionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"cl.exe" ist ein Tool, mit dem die Microsoft C und C\+\+\-Compiler sowie \-Linker gesteuert werden können. "cl.exe" kann nur auf Betriebssystemen ausgeführt werden, auf denen Microsoft Visual Studio unterstützt wird.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]\-Eingabeaufforderung aus starten.  Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei\-Explorer aus starten.  
  
 Die Compiler erzeugen Objektdateien \(OBJ\-Dateien\) im Common Object File Format \(COFF\).  Der Linker generiert ausführbare Dateien \(EXE\-Dateien\) oder DLLs \(Dynamic Link Libraries\).  
  
 Beachten Sie, dass bei allen Compileroptionen die Groß\- und Kleinschreibung berücksichtigt wird.  
  
 Zum Kompilieren ohne Verknüpfen verwenden Sie den Befehl [\/c](../../build/reference/c-compile-without-linking.md).  
  
## Suchen einer Option  
 Wenn Sie eine bestimmte Compileroption suchen, ziehen Sie eine der folgenden Listen zu Rate:  
  
-   [Compileroptionen alphabetisch sortiert](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)  
  
## Angeben von Optionen  
 In den Themen zu den einzelnen Compileroptionen wird erläutert, wie die jeweilige Option in der Entwicklungsumgebung eingestellt werden kann.  Informationen über das Festlegen von Optionen außerhalb der Entwicklungsumgebung, finden Sie unter:  
  
-   [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL\-Befehlsdateien](../../build/reference/cl-command-files.md)  
  
-   [CL\-Umgebungsvariablen](../../build/reference/cl-environment-variables.md)  
  
## Verwandte Buildtools  
 Zum Erstellen der Ausgabedatei verwenden Sie [NMAKE](../../build/nmake-reference.md).  
  
 Wenn das Durchsuchen von Klassen unterstützt werden soll, verwenden Sie [BSCMAKE](../../build/reference/bscmake-reference.md).  
  
 Auch die [Linkeroptionen](../../build/reference/linker-options.md) beeinflussen die Erstellungsweise des Programms.  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Schnelle Kompilierung](../../build/reference/fast-compilation.md)   
 [CL: Starten des Linkers](../../build/reference/cl-invokes-the-linker.md)