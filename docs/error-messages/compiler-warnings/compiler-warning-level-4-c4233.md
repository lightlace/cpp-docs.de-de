---
title: Compilerwarnung (Stufe 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 361e00b7361aab51ea077d7e248503f3654e5e58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401058"
---
# <a name="compiler-warning-level-4-c4233"></a>Compilerwarnung (Stufe 4) C4233

> nicht dem Standard entsprechende Erweiterung: "*Schlüsselwort*' Schlüsselwort nur in C++ unterstützt und nicht in C

Der Compiler kompiliert den Quellcode als C und nicht in C++, und Sie verwendet ein Schlüsselwort, das nur in C++ gültig ist. Der Compiler kompiliert die Quelldatei als C, wenn die Erweiterung der Quelldatei c ist, oder Sie mittels [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md). Fügen Sie z. B. um C4233 in eine Warnung der Stufe 4 zu machen, diese Zeile auf die Quellcodedatei:

```cpp
#pragma warning(4:4233)
```
