---
title: Compilerfehler C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: 23dfe1d95ab75f253fc2a7b4b00dfcd1aaaa3bbf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623521"
---
# <a name="compiler-error-c2191"></a>Compilerfehler C2191

zweite Parameterliste länger als erste Liste

Eine C-Funktion wurde ein zweites Mal mit einer längeren Parameterliste deklariert. C# unterstützt keine überladene Funktionen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2191 generiert:

```
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```