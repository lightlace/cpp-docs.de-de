---
title: "-C (Kompilieren ohne Verknüpfen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /c
dev_langs: C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 112e063af9c56ead8ae7e8f59fe88853ff55f7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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