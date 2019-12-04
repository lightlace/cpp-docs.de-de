---
title: Compilerfehler C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 96a6b1b81d2d82328dcb4ceaca376f247f785c13
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737945"
---
# <a name="compiler-error-c3222"></a>Compilerfehler C3222

'Parameter': Für Memberfunktionen eines verwalteten oder WinRT-Typs oder generische Funktionen können keine Standardargumente deklariert werden.

Es ist nicht zulässig, einen Methodenparameter mit einem Standardargument zu deklarieren. Eine überladene Form der Methode ist eine Möglichkeit, dieses Problem zu umgehen. Das heißt, dass Sie eine Methode mit demselben Namen ohne Parameter definieren und anschließend die Variable im Methodentext initialisieren.

Im folgenden Beispiel wird C3222 generiert:

```cpp
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
