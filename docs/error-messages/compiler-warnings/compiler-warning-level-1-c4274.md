---
title: Compilerwarnung (Stufe 1) C4274 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4519258a10937ad96528f34484a44d398a0cd0ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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