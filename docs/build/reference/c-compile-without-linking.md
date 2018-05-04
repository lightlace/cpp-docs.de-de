---
title: -C (Kompilieren ohne Verknüpfen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /c
dev_langs:
- C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86bd1ddcb6d44cfa433d4119f90eb02695089aa4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="c-compile-without-linking"></a>/c (Kompilieren ohne Verknüpfen)
Verhindert den automatischen Aufruf von LINK.  
  
## <a name="syntax"></a>Syntax  
  
```  
/c  
```  
  
## <a name="remarks"></a>Hinweise  
 Beim Kompilieren mit **/c** nur OBJ-Dateien erstellt. Sie müssen LINK mit den entsprechenden Dateien und Optionen zum Ausführen der verknüpfungsframework-Phase des Builds explizit aufrufen.  
  
 Alle internen Projekt erstellt, in der Entwicklungsumgebung verwendet die **/c** standardmäßig die Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
-   Diese Option ist nicht in der Entwicklungsumgebung zur Verfügung.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile erstellt die Objektdateien FIRST.obj und Second.obj erstellt. Die Datei THIRD.obj wird ignoriert.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Um eine ausführbare Datei zu erstellen, müssen Sie den LINK aufrufen:  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)