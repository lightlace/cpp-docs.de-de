---
title: Compilerwarnung (Stufe 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 84a0d4c541f67742d68c7f08e0dda52ccd350d04
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626714"
---
# <a name="compiler-warning-level-1-c4269"></a>Compilerwarnung (Stufe 1) C4269

"Bezeichner": "Konstante" automatische Daten, die mit dem vom Compiler generierten Standardkonstruktor initialisiert werden, erzeugen unzuverlässige Ergebnisse

Eine **Konstante automatische Instanz einer nicht** trivialen Klasse wird mit einem vom Compiler generierten Standardkonstruktor initialisiert.

## <a name="example"></a>Beispiel

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

Da diese Instanz der-Klasse auf dem Stapel generiert wird, kann der Anfangswert von `m_data` beliebiger Wert sein. Da es sich **um eine Konstante** Instanz handelt, kann der Wert von `m_data` nie geändert werden.