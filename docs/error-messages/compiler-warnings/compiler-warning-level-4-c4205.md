---
title: Compilerwarnung (Stufe 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 1b165d2bdb2fb50df89fdd77c734c054a40b6e95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401227"
---
# <a name="compiler-warning-level-4-c4205"></a>Compilerwarnung (Stufe 4) C4205

nicht dem Standard entsprechende Erweiterung: Deklaration einer statischen Funktion im Gültigkeitsbereich der Funktion

Mit Microsoft-Erweiterungen (/ Ze) **statische** Funktionen können innerhalb einer anderen Funktion deklariert werden. Die Funktion erhält für globalen Gültigkeitsbereich.

## <a name="example"></a>Beispiel

```
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

Diese Initialisierungen sind ungültig, ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).