---
title: Compilerfehler C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: b52797b945b1a652506b4a85171e60a91544bbf0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282828"
---
# <a name="compiler-error-c2190"></a>Compilerfehler C2190

erste Parameterliste länger als zweite Liste

Eine C-Funktion wurde ein zweites Mal mit einer kürzeren Parameterliste deklariert. C# unterstützt keine überladene Funktionen.

Im folgende Beispiel wird die C2190 generiert:

```
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```