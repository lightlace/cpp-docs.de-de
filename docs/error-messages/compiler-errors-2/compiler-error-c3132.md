---
title: Compilerfehler C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: 1a97e04747cb92909380e66d1f4ea8ca62183054
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424170"
---
# <a name="compiler-error-c3132"></a>Compilerfehler C3132

"Funktion-Parameter": Parameterarrays können nur auf formale Argumente vom Typ "eindimensionales verwaltetes Array" angewendet werden

Die <xref:System.ParamArrayAttribute> -Attribut wurde auf einen Parameter, der kein eindimensionales Array war angewendet.

Im folgende Beispiel wird die C3132 generiert:

```
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```