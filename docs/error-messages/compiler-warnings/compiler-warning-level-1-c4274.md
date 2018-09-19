---
title: Compilerwarnung (Stufe 1) C4274 | Microsoft-Dokumentation
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
ms.openlocfilehash: 5f6db0ee96674beda51ab02c8651e6f4960a0bf8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094687"
---
# <a name="compiler-warning-level-1-c4274"></a>Compilerwarnung (Stufe 1) C4274

\#Ident ignoriert; finden Sie in der Dokumentation zu #pragma Comment (Exestr, "String")

Die `#ident` -Direktive, die eine vom Benutzer angegebene Zeichenfolge in das Objekt oder eine ausführbare Datei einfügt, ist veraltet. Daher ignoriert der Compiler die Direktive an.

> [!CAUTION]
>  Warnung C4274 Sie verwenden die [#pragma Comment (Exestr, "String")](../../preprocessor/comment-c-cpp.md) Richtlinie. Allerdings wird diese Empfehlung ist veraltet und werden in einer zukünftigen Version des Compilers überarbeitet werden. Bei Verwendung der `#pragma` Direktive, das Linkertool (LINK.exe) den von der Richtlinie erzeugte Kommentardatensatz ignoriert und gibt die Warnung [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Statt die `#ident` Direktive, es wird empfohlen, dass Sie eine Ressourcenzeichenfolge für Datei-Version in Ihrer Anwendung verwenden.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie die `#ident "` *Zeichenfolge* `"` Richtlinie.

## <a name="see-also"></a>Siehe auch

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Linkertoolwarnung LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md)