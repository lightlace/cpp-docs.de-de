---
title: Compilerwarnung (Stufe 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: ceb7e65a292e5b9e9ef960ca9553183b703c93f0
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991693"
---
# <a name="compiler-warning-level-4-c4001"></a>Compilerwarnung (Stufe 4) C4001

nicht dem Standard entsprechende Erweiterung "einzeiligen Kommentar" wurde verwendet.

> [!NOTE]
> Diese Warnung wird in Visual Studio 2017 Version 15,5 entfernt, da einzeilige Kommentare in C99 standardmäßig sind.

Einzeilige Kommentare sind standardmäßig C++ in und Standard in C beginnend mit C99.
Im Rahmen der Strict-ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) generieren C-Dateien, die einzeilige Kommentare enthalten, C4001 aufgrund der Verwendung einer nicht dem Standard entsprechende Erweiterung. Da einzeilige Kommentare in C++Standard sind, wird bei C-Dateien, die einzeilige Kommentare enthalten, bei der Kompilierung mit Microsoft-Erweiterungen (/Ze) keine C4001 erzeugt.

## <a name="example"></a>Beispiel

Zum Deaktivieren der Warnung heben Sie die Auskommentierung [#pragma Warnung (deaktivieren: 4001)](../../preprocessor/warning.md)auf.

```cpp
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```
