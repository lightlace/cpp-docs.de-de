---
title: -Diagnose (Diagnose Compileroptionen) | Microsoft Docs
ms.custom: 
ms.date: 11/11/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs:
- C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a1c893b530bfa895e5ec127bd0aea2fb0df4ff3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/Diagnostics (Diagnose Compileroptionen)  
  
Verwenden der **/diagnostics** Compileroption, um die Anzeige der Informationen zum Fehler und Warnungen Speicherort angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
/diagnostics:{caret|classic|column}
```  

## <a name="remarks"></a>Hinweise  
Die **/diagnostics** -Compileroption steuert die Anzeige von Fehler- und Warnungsinformationen.  
  
Die **/diagnostics:classic** ist die Standardoption, die nur die Nummer der Zeile meldet, wo das Problem gefunden wurde.  
  
Die **/diagnostics:column** Option enthält auch die Spalte, in denen das Problem gefunden wurde. Dadurch können Sie die Identifizierung des spezifischen Sprachkonstrukt oder der Zeichen, das das Problem verursacht.  
  
Die **/diagnostics:caret** Option enthält die Spalte, in dem das Problem gefunden wurde, und fügt ein Caretzeichen (^) unter dem Speicherort in der Codezeile, in dem das Problem erkannt wurde.  
  
Beachten Sie, dass in einigen Fällen, die der Compiler erkennt kein Problem, wo es aufgetreten ist. Beispielsweise kann ein fehlendes Semikolon nicht erkannt werden, bis Weitere, unerwartete Symbole aufgetreten sind. Die Spalte wird gemeldet, und die Einfügemarke befindet, in denen der Compiler hat festgestellt, dass etwas falsch ist, die ist nicht immer wurde, in dem Sie Ihre Korrektur vornehmen müssen.  
  
Die **/diagnostics** Option ist verfügbar in Visual Studio 2017 ab.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie das Projekt **Eigenschaftenseiten** (Dialogfeld).   
  
2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **allgemeine** Eigenschaftenseite.  
  
3. Verwenden Sie das Dropdown-Steuerelement in der **Diagnose Format** Feld Wählen Sie eine Diagnose Anzeigeoption. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)