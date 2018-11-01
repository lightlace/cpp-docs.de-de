---
title: Compilerfehler C3083
ms.date: 11/04/2016
f1_keywords:
- C3083
helpviewer_keywords:
- C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
ms.openlocfilehash: 5ff049d3fcfb2c3dbc28baacdecee9b313574fc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641404"
---
# <a name="compiler-error-c3083"></a>Compilerfehler C3083

'Funktion': das Symbol auf der linken Seite des ein '::' muss ein Typ sein

Eine Funktion wurde falsch aufgerufen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3083 generiert.

```
// C3083.cpp
// compile with: /c
struct N {
   ~N();
};

struct N1 {
   ~N1();
};

N::N::~N() {}   // C3083
N1::~N1() {}   // OK
```