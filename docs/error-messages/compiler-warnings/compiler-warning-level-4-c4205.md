---
title: Compilerwarnung (Stufe 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: e46642494e55769a0676f0e33af0ca40c31939ad
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541803"
---
# <a name="compiler-warning-level-4-c4205"></a>Compilerwarnung (Stufe 4) C4205

nicht dem Standard entsprechende Erweiterung: statische Funktionsdeklaration im Funktionsbereich

Mit Microsoft Extensions (/Ze) können **statische** Funktionen innerhalb einer anderen Funktion deklariert werden. Die Funktion erhält einen globalen Gültigkeitsbereich.

## <a name="example"></a>Beispiel

```c
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

Diese Initialisierungen sind unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ungültig.