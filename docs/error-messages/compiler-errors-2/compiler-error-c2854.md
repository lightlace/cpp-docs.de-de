---
title: Compilerfehler C2850
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: a1c30e1fa0f70e5e7bb4b1c97421ca06913fc6f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628968"
---
# <a name="compiler-error-c2854"></a>Compilerfehler C2850

Syntaxfehler in #pragma hdrstop

Die `#pragma hdrstop` wird ein ungültiger Dateiname. Das Pragma kann einen optionalen Dateinamen in Klammern und Anführungszeichen folgen:

Im folgende Beispiel wird die C2854 generiert:

```
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```