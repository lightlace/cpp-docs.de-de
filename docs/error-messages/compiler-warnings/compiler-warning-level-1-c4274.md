---
title: Compiler (Stufe 1) C4274 | Microsoft-Dokumentation
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: fbba1e6dde180e77afe7ed8960849ee8cc0fd108
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4274"></a>Compiler (Stufe 1) C4274
\#Ident ignoriert; finden Sie in der Dokumentation zu #pragma Comment (Exestr, 'String')  
  
 Die `#ident` -Direktive, die eine benutzerdefinierte Zeichenfolge in das Objekt oder die ausführbare Datei einfügt, ist veraltet. Infolgedessen ignoriert der Compiler die Direktive.  
  
> [!CAUTION]
>  Warnung C4274 Sie verwenden die [#pragma Comment (Exestr, 'String')](../../preprocessor/comment-c-cpp.md) Richtlinie. Allerdings wird diese Empfehlung ist veraltet und wird in einer zukünftigen Version des Compilers überarbeitet werden. Bei Verwendung der `#pragma` -Direktive das Linkertool (LINK.exe) den von der Direktive erzeugten Kommentardatensatz ignoriert und Warnung [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Statt die `#ident` Richtlinie, es wird empfohlen, dass Sie eine Ressourcenzeichenfolge für Datei-Version in Ihrer Anwendung verwenden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `#ident "` *Zeichenfolge* `"` Richtlinie.  
  
## <a name="see-also"></a>Siehe auch  
 [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Linkertoolwarnung Lnk4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md)
