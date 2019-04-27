---
title: Compilerfehler C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230528"
---
# <a name="compiler-error-c2466"></a>Compilerfehler C2466

ein Array von Konstanten Größe 0 kann nicht zugeordnet werden.

Ein Array ist reserviert oder mit Größe 0 (null) deklariert. Der Konstante Ausdruck für die Größe des Arrays muss eine ganze Zahl größer als 0 (null) sein. Eine Arraydeklaration mit einem Nullindex ist zulässig, nur für eine Klasse, Struktur oder union-Member und nur mit Microsoft-Erweiterungen ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Im folgende Beispiel wird die C2466 generiert:

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```