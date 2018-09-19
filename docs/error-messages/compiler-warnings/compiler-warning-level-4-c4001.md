---
title: Compilerwarnung (Stufe 4) C4001 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c325656b9e61ee324a3b9f171413f1020440f9ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025411"
---
# <a name="compiler-warning-level-4-c4001"></a>Compilerwarnung (Stufe 4) C4001

nicht dem Standard entsprechende Erweiterung "einzeiliger Kommentar" wurde verwendet.

> [!NOTE]
> Diese Warnung wird in Visual Studio 2017 Version 15.5 entfernt, weil einzeilige Kommentare in C99 standard sind.

Einzeilige Kommentare sind in C++ standard "und" standard in C99 C ab.
Strikte ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), C-Dateien, einzeilige Kommentare, enthalten, die Warnung C4001 durch die Verwendung einer nicht dem Standard entsprechende Erweiterung. Da einzeilige Kommentare in C++ standard sind, erzeugen C-Dateien, die mit einzeilige Kommentare nicht C4001 beim Kompilieren mit Microsoft-Erweiterungen (/ Ze).

## <a name="example"></a>Beispiel

Um die Warnung zu deaktivieren, heben Sie die auskommentierung [#pragma warning(Disable:4001) aus](../../preprocessor/warning.md).

```
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```