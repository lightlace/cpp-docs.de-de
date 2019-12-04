---
title: Compilerfehler C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: aba4de518b9296fadc4746540e4e738c74908617
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743821"
---
# <a name="compiler-error-c2466"></a>Compilerfehler C2466

ein Array der Konstanten Größe 0 kann nicht zuzuordnen werden.

Ein Array wird zugeordnet oder mit der Größe 0 (null) deklariert. Der Konstante Ausdruck für die Array Größe muss eine ganze Zahl größer als 0 (null) sein. Eine Array Deklaration mit einem Index mit Nullen ist nur für eine Klasse, Struktur oder Union-Member und nur mit Microsoft-Erweiterungen ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)) zulässig.

Im folgenden Beispiel wird C2466 generiert:

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
