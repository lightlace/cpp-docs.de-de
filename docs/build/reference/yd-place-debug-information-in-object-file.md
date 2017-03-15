---
title: "/Yd (Debuginformationen in Objektdatei ablegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yd (Compileroption) [C++]"
  - "Debuggen [C++], Debuginformationsdateien"
  - "Yd (Compileroption) [C++]"
  - "-Yd (Compileroption) [C++]"
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Yd (Debuginformationen in Objektdatei ablegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn diese Option zusammen mit der [\/Yc](../../build/reference/yc-create-precompiled-header-file.md)\-Option und der [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option verwendet wird, werden die vollständigen Debuginformationen in sämtlichen Objektdateien analysiert, die aus der vorkompilierten Headerdatei \(PCH\-Datei\) erstellt werden.  Veraltet.  
  
## Syntax  
  
```  
/Yd  
```  
  
## Hinweise  
 **\/Yd** ist veraltetet, verwenden Sie stattdessen [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]. Von **\/Zi** wird nun das Schreiben mehrerer Objekte in eine einzelne PDB\-Datei unterstützt.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
 Solange es nicht erforderlich ist, eine Bibliothek zu verteilen, die Debuginformationen enthält, verwenden Sie die [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option anstelle von **\/Z7** und **\/Yd**.  
  
 Das Speichern vollständiger Debuginformationen in jeder OBJ\-Datei ist nur notwendig, um Bibliotheken mit Debuginformationen weiterzugeben.  Es verlangsamt die Kompilierung und erfordert beträchtliche Speicherkapazitäten.  Wenn **\/Yc** und **\/Z7** ohne **\/Yd** verwendet werden, speichert der Compiler allgemeine Debuginformationen in der ersten OBJ\-Datei, die von der PCH\-Datei erstellt wird.  Der Compiler fügt diese Informationen nicht in die OBJ\-Dateien ein, die anschließend von der PCH\-Datei erstellt werden, sondern fügt Querverweise auf diese Informationen ein.  Unabhängig von der Anzahl der OBJ\-Dateien, die die PCH\-Datei verwenden, enthält nur eine OBJ\-Datei die allgemeinen Debuginformationen.  
  
 Obwohl dieses Standardverhalten kürzere Erstellungszeiten zur Folge hat und die Anforderungen an den Festplattenspeicher reduziert werden, ist es nicht wünschenswert, wenn eine kleine Änderung die Neuerstellung der OBJ\-Datei mit den allgemeinen Debuginformationen erfordert.  In diesem Fall muss der Compiler alle OBJ\-Dateien neu erstellen, die Querverweise auf die ursprüngliche OBJ\-Datei enthalten.  Darüber hinaus ist es problematisch, auf die Querverweise einer einzigen OBJ\-Datei zu vertrauen, wenn eine gemeinsame PCH\-Datei von verschiedenen Projekten verwendet wird.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Beispiele  
 Angenommen, Sie arbeiten mit zwei Basisdateien, F.cpp und G.cpp, die jeweils die folgenden **\#include**\-Anweisungen enthalten:  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 Mit dem nachfolgenden Befehl werden die vorkompilierte Headerdatei **ETC.pch** und die Objektdatei **F.obj** erstellt:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 Die Objektdatei **F.obj** schließt Typ\- und Symbolinformationen für **WINDOWS.h** und **ETC.h** ein \(sowie beliebige andere Headerdateien, die darin enthalten sind\).  Sie können nun den vorkompilierten Header **ETC.pch** verwenden, um die Quelldatei **G.cpp** zu kompilieren:  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 Die Objektdatei **G.obj** schließt die Debuginformationen für den vorkompilierten Header nicht ein, sondern verweist direkt auf diese Informationen in der Datei **F.obj**.  Beachten Sie, dass Sie **F.obj** einbinden müssen.  
  
 Wenn der vorkompilierte Header nicht mit **\/Z7** kompiliert wurde, können Sie ihn dennoch bei späteren Kompilierungen zusammen mit **\/Z7** verwenden.  Die Debuginformationen werden in der aktuellen Objektdatei gespeichert, jedoch stehen lokale Symbole für Funktionen und Typen, die im vorkompilierten Header definiert sind, dem Debugger nicht zur Verfügung.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)