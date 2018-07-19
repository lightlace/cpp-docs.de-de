---
title: Compilerwarnung (Stufe 1) C4274 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b941fc0cb32e268e33d3b0e1ae66079e8decaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286145"
---
# <a name="compiler-warning-level-1-c4274"></a>Compilerwarnung (Stufe 1) C4274
\#Ident ignoriert; finden Sie in der Dokumentation für #pragma-Kommentar (Exestr, 'String')  
  
 Die `#ident` -Direktive, die eine benutzerdefinierte Zeichenfolge in das Objekt oder die ausführbare Datei einfügt, ist veraltet. Infolgedessen ignoriert der Compiler die Direktive an.  
  
> [!CAUTION]
>  Warnung C4274 Sie verwenden die [#pragma-Kommentar (Exestr, 'String')](../../preprocessor/comment-c-cpp.md) Richtlinie. Allerdings wird diesen Rat ist veraltet und wird in einer zukünftigen Version des Compilers überarbeitet werden. Bei Verwendung der `#pragma` -Direktive das Linkertool (LINK.exe) den von der Richtlinie erzeugte Kommentardatensatz ignoriert und Warnung [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Statt die `#ident` Richtlinie, es wird empfohlen, dass Sie eine Datei Ressource Versionszeichenfolge in Ihrer Anwendung verwenden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `#ident "` *Zeichenfolge* `"` Richtlinie.  
  
## <a name="see-also"></a>Siehe auch  
 [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Linkertoolwarnung Lnk4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md)