---
title: -Fp (Name. PCH-Datei) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs:
- C++
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77ba54705ec4037f1c98a2ae1832dddcc551956e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fp-name-pch-file"></a>/Fp (Name der PCH-Datei)
Stellt einen Pfadnamen für einen vorkompilierten Header statt mit dem Standardnamen für den Pfad an.  
  
## <a name="syntax"></a>Syntax  
  
> **/ Fp**_Pfadnamen_  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option mit [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md) oder [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md) einen Pfadnamen für einen vorkompilierten Header statt mit dem Standardnamen für den Pfad angeben. Sie können auch **/fp** mit **"/ Yc"** die Verwendung einer vorkompilierten Headerdatei an, die nicht die **"/ Yc"***Filename* Argument und aus der Basisname der Quelldatei.  
  
 Wenn Sie eine Erweiterung nicht als Teil des Pfadnamens angeben, wird davon ausgegangen, dass eine Erweiterung PCH. Wenn Sie ein Verzeichnis ohne einen Dateinamen angeben, wird der Standarddateiname VC*x*0.pch, wobei *x* die Hauptversion von Visual C++ verwendet wird.  
  
 Sie können auch die **/fp** mit option **"/ Yu"**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **vorkompilierte Header** Eigenschaftenseite.  
  
4.  Ändern der **vorkompilierten Headerdatei** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Wenn eine vorkompilierte Headerdatei für eine Debugversion des Programms erstellt werden soll, und Sie Header-Dateien und Quellcode kompilieren, können Sie z. B. einen Befehl angeben:  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl spezifiziert die Verwendung einer vorkompilierten Headerdatei mit dem Namen MYPCH.pch. Der Compiler davon ausgegangen, dass der Quellcode in PROG.cpp MyApp.h vorkompiliert wurde vorkompilierte Code in MYPCH.pch befindet. Er verwendet den Inhalt des MYPCH.pch und den Rest von PROG.cpp zur Erstellung einer OBJ-Datei kompiliert. Die Ausgabe dieses Beispiels ist eine Datei namens PROG.exe.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)