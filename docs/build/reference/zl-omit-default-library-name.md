---
title: -Zl (Standardbibliotheksname) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
dev_langs:
- C++
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c14a3217334c2c43bac7fbcce8b0bfd60a609d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="zl-omit-default-library-name"></a>/Zl (Kein Standardbibliotheksname)
Lässt den C-Laufzeit Standardbibliotheksnamen aus der OBJ-Datei an. Standardmäßig legt der Compiler den Namen der Bibliothek in der OBJ-Datei ab, um den Linker zur richtigen Bibliothek zu leiten.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zl  
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über die Standardbibliothek finden Sie unter [Use Run-Time Library](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 Sie können **Zl** OBJ-Dateien kompiliert eine Bibliothek abgelegt werden sollen. Obwohl das Weglassen der Bibliotheksname nur eine kleine Menge an Speicherplatz für einen einzelnen OBJ-Datei speichert, spielt der Gesamtspeicherplatz, gespeichert in einer Bibliothek, die viele Objektmodule enthält.  
  
 Diese Option ist eine erweiterte Option. Festlegen dieser Option werden bestimmte Unterstützung der C-Laufzeit-Bibliothek, die möglicherweise, durch die Anwendung erforderlich, was zu Link-Time-Fehler, wenn die Anwendung abhängig ist diese Unterstützung entfernt. Wenn Sie diese Option verwenden, müssen Sie die erforderlichen Komponenten auf andere Weise bereitstellen.  
  
 Verwendung [/NODEFAULTLIB (Bibliotheken ignorieren)](../../build/reference/nodefaultlib-ignore-libraries.md). Ignorieren der Library-Verweise in allen OBJ-Dateien den Linker weiterleiten.  
  
 Weitere Informationen finden Sie unter [CRT Library Features (CRT-Bibliotheksfunktionen)](../../c-runtime-library/crt-library-features.md).  
  
 Beim Kompilieren mit **Zl**, `_VC_NODEFAULTLIB` definiert ist.  Zum Beispiel:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **weglassen Standard-Bibliotheksnamen** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)