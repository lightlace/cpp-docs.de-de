---
title: Compilerwarnung (Stufe 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: f3a6497ae7fc2bb3a73684c9dc76401cf96ca3fa
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991310"
---
# <a name="compiler-warning-level-4-c4268"></a>Compilerwarnung (Stufe 4) C4268

' Identifier ': ' Konstante ' statische/globale Daten, die mit dem vom Compiler generierten Standardkonstruktor initialisiert wurden, füllen das Objekt mit Nullen

Eine **globale oder statische Instanz einer nicht** trivialen Klasse wird mit einem vom Compiler generierten Standardkonstruktor initialisiert.

## <a name="example"></a>Beispiel

```cpp
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

Da diese Instanz der-Klasse **konstant**ist, kann der Wert von `m_data` nicht geändert werden.
