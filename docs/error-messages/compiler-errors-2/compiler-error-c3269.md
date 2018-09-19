---
title: Compilerfehler C3269 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3269
dev_langs:
- C++
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84cb9acdd6444b934e7ec51691d87a6912880de2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061800"
---
# <a name="compiler-error-c3269"></a>Compilerfehler C3269

'Funktion': eine Memberfunktion einer verwalteten oder WinRTtype kann nicht mit '...' deklariert werden

Verwaltete und WinRT-Klassenmemberfunktionen können keine Parameterlisten variabler Länge deklarieren.

Im folgenden Beispiel wird C3269 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
