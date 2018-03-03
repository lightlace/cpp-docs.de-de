---
title: / FA, / FA (Listendatei) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs:
- C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0cd569cf16e7b2a14faaa119eacaef0994d09dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fa-fa-listing-file"></a>/FA, /Fa (Listendatei)
Erstellt eine Listendatei Assemblercode enthält.  
  
## <a name="syntax"></a>Syntax  
  
> **/ FA**[**c**\][**s**\][**u**]  
> **/ FA**_Pfadnamen_  
  
## <a name="remarks"></a>Hinweise  
Die `/FA` Compileroption generiert eine Assembler-Listendatei für jede Übersetzungseinheit in der Kompilierung, die in der Regel eine C- oder C++-Quelldatei entspricht. Standardmäßig ist nur Assembler in der Auflistung enthalten, die als ANSI codiert ist. Das optionale `c`, `s`, und `u` Argumente `/FA` Steuerelement Computer gibt an, ob Code oder Quellcode werden zusammen mit der Assembler auflisten, und gibt an, ob die Auflistung als UTF-8 codiert ist.  
  
Standardmäßig jede Listendatei Ruft den gleichen Basisnamen wie die Quelldatei und verfügt über eine ASM-Erweiterung. Wenn Computercode eingeschlossen wird, mithilfe der `c` Listendatei-Option verfügt über eine COD-Erweiterung. Sie können ändern, Name und Erweiterung der Listendatei und des Verzeichnisses, in dem sie mithilfe erstellt wird, der `/Fa` Option.  

### <a name="fa-arguments"></a>/ FA-Argumente  
Keine  
Nur Assembler Sprache ist in der Auflistung enthalten.  
  
`c`  
Dies ist optional. Enthält Computercode in der Auflistung.  
  
`s`  
Dies ist optional. Enthält Quellcode in der Auflistung.  
  
`u`Dies ist optional. Die Listendatei in UTF-8-Format codiert und enthält ein Byte-sortierungsmarkierung. Standardmäßig wird die Datei als ANSI codiert. Verwendung `u` eine Listendatei erstellen, ordnungsgemäß auf allen Systemen anzeigt, oder wenn Sie Unicode verwenden Quellcodedateien als Eingabe für den Compiler.  
  
Wenn beide `s` und `u` angegeben wurden, und wenn eine Quellcodedatei verwendet eine Unicode-Codierung als UTF-8, und klicken Sie dann auf die Codezeilen, in der Datei ASM eventuell nicht korrekt angezeigt.  
  
### <a name="fa-argument"></a>/ FA-argument  
Keine  
Eine *Quelle*ASM-Datei wird für alle Quellcodedateien in der Kompilierung erstellt.  
  
*FileName* eine Listendatei mit dem Namen *Filename*ASM befindet sich im aktuellen Verzeichnis. Dies gilt nur beim Kompilieren einer einzelnen Quellcodedatei.  
  
*filename.Extension*  
Eine mit dem Namen Listendatei *filename.extension* im aktuellen Verzeichnis befindet. Dies gilt nur beim Kompilieren einer einzelnen Quellcodedatei.  
  
*Verzeichnis*\  
Eine *Source_file*ASM-Datei erstellt und platziert Sie in der angegebenen *Directory* für alle Quellcodedateien in der Kompilierung. Beachten Sie den erforderlichen nachgestellten umgekehrten Schrägstrich ein. Nur Pfade auf den aktuellen Datenträger sind zulässig.  
  
*Directory*\\*Filename* eine Listendatei mit dem Namen *Filename*ASM platziert wird in der angegebenen *Directory*. Dies gilt nur beim Kompilieren einer einzelnen Quellcodedatei.  
  
*Directory*\\*filename.extension*  
Eine mit dem Namen Listendatei *filename.extension* platziert wird in der angegebenen *Verzeichnis*. Dies gilt nur beim Kompilieren einer einzelnen Quellcodedatei.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Öffnen der **C/C++-** Ordner, und wählen die **Ausgabedateien** Eigenschaftenseite.  
  
3.  Ändern der **Assembler-Ausgabe** -Eigenschaft zum Festlegen der `/FAc` und `/FAs` Optionen für Assembler, Computer und Quellcode. Ändern der **verwenden Unicode für Assembler auflisten** -Eigenschaft zum Festlegen der `/FAu` Option für die ANSI oder UTF-8-Ausgabe. Ändern der **Ort der Standortliste für ASM** festzulegende der `/Fa` Option für die Auflistung von Dateinamen und Speicherort.  
  
Beachten Sie, diese Einstellung sowohl **Assembler-Ausgabe** und **verwenden Unicode für Assembler auflisten** Eigenschaften können dazu führen, dass [Befehlszeilen Warnung D9025](../../error-messages/tool-errors/command-line-warning-d9025.md). Verwenden Sie diese Optionen in der IDE zu kombinieren, die **zusätzliche Optionen** -Feld in der **Befehlszeile** Eigenschaftenseite stattdessen.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>. An `/FAu`, finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="example"></a>Beispiel  
Die folgende Befehlszeile produziert eine kombinierte mit Quellcode und Computercode Angebot HELLO.cod:  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)