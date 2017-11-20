---
title: Compileroptionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 490814f85199450d4261bf4071184b75b5ea10c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-options"></a>Compileroptionen
CL.exe ist ein Tool, das die Microsoft C- und C++-Compiler und Linker steuert. CL.exe kann nur unter Betriebssystemen ausgeführt werden, die Microsoft Visual Studio unterstützen.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Eingabeaufforderung aus starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.  
  
 Die Compiler erzeugen Objektdateien (OBJ-Dateien) im Common Object File Format (COFF). Der Linker generiert ausführbare Dateien (EXE-Dateien) oder DLLs (Dynamic Link Libraries).  
  
 Beachten Sie, dass bei allen Compileroptionen die Groß- und Kleinschreibung berücksichtigt wird.  
  
 Verwenden Sie zum Kompilieren ohne Verknüpfen [/c](../../build/reference/c-compile-without-linking.md).  
  
## <a name="finding-an-option"></a>Suchen einer Option  
 Wenn Sie eine bestimmte Compileroption suchen, ziehen Sie eine der folgenden Listen zu Rate:  
  
-   [Compileroptionen alphabetisch sortiert](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>Angeben von Optionen  
 In den Themen zu den einzelnen Compileroptionen wird erläutert, wie die jeweilige Option in der Entwicklungsumgebung eingestellt werden kann. Informationen über das Festlegen von Optionen außerhalb der Entwicklungsumgebung, finden Sie unter:  
  
-   [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL-Befehlsdateien](../../build/reference/cl-command-files.md)  
  
-   [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>Verwandte Buildtools  
 Verwendung [NMAKE](../../build/nmake-reference.md) zum Erstellen der Ausgabedatei.  
  
 Verwendung [BSCMAKE](../../build/reference/bscmake-reference.md) zum Durchsuchen von Klassen unterstützt.  
  
 [Optionen des Linkers](../../build/reference/linker-options.md) außerdem Auswirkungen auf die Erstellungsweise des Programms.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Schnelle Kompilierung](../../build/reference/fast-compilation.md)   
 [CL: Starten des Linkers](../../build/reference/cl-invokes-the-linker.md)