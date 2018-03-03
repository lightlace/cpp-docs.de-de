---
title: "-\"await\" (Aktivieren der Unterstützung Coroutine) | Microsoft Docs"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47134532b16d1b5a907e4ed3170a0827316d7c65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="await-enable-coroutine-support"></a>/ await (Enable Coroutine-Unterstützung)  
  
Verwenden der **/ "await"** Compileroption, um Compiler-Unterstützung für Coroutinen zu aktivieren.  
  
## <a name="syntax"></a>Syntax  
  
> / "await"  
  
## <a name="remarks"></a>Hinweise  
  
Die **/ "await"** -Compileroption kann Compiler-Unterstützung für den Schlüsselwörtern "und" C++ Coroutinen **Co_await**, **Co_yield**, und **Co_return**. Diese Option ist standardmäßig deaktiviert. Informationen zur Unterstützung für Coroutinen in Visual Studio finden Sie unter der [Visual Studio-Team-Blog](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Weitere Informationen zum standard Coroutinen Vorschlag finden Sie unter [N4628 Arbeitsentwurf, technische Spezifikation für die C++-Erweiterungen für Coroutinen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).  

Die **/ "await"** Option ist in Visual Studio 2015 ab.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie das Projekt **Eigenschaftenseiten** (Dialogfeld).   
  
2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
3. Geben Sie die **/ "await"** -Compileroption in der **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
  
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)