---
title: Compilerwarnung (Stufe 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: f73fa8e09baab127e7755ebe3def69c2fb585744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207206"
---
# <a name="compiler-warning-level-1-c4274"></a>Compilerwarnung (Stufe 1) C4274

\#ident ignored; see documentation for #pragma comment(exestr, 'string')

Die `#ident` -Direktive, die eine vom Benutzer angegebene Zeichenfolge in das Objekt oder eine ausführbare Datei einfügt, ist veraltet. Daher ignoriert der Compiler die Direktive an.

> [!CAUTION]
>  Warnung C4274 Sie verwenden die [#pragma Comment (Exestr, "String")](../../preprocessor/comment-c-cpp.md) Richtlinie. Allerdings wird diese Empfehlung ist veraltet und werden in einer zukünftigen Version des Compilers überarbeitet werden. Bei Verwendung der `#pragma` Direktive, das Linkertool (LINK.exe) den von der Richtlinie erzeugte Kommentardatensatz ignoriert und gibt die Warnung [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Statt die `#ident` Direktive, es wird empfohlen, dass Sie eine Ressourcenzeichenfolge für Datei-Version in Ihrer Anwendung verwenden.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie die `#ident "` *Zeichenfolge* `"` Richtlinie.

## <a name="see-also"></a>Siehe auch

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Linkertoolwarnung LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md)