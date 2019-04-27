---
title: Compilerwarnung (Stufe 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 9a7f42b2dd65644d3f2abec58236a0b93cc6f635
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207232"
---
# <a name="compiler-warning-level-1-c4269"></a>Compilerwarnung (Stufe 1) C4269

'Bezeichner': 'const' Automatische Daten, die mit dem vom Compiler generierten Standardkonstruktor initialisiert, verursachen unzuverlässige Ergebnisse

Ein **const** automatische Instanz von einer nicht trivialen Klasse mit einem vom Compiler generierten Standardkonstruktor initialisiert wird.

## <a name="example"></a>Beispiel

```
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

Da diese Instanz der Klasse, auf dem Stapel, der anfängliche Wert generiert wird `m_data` kann alles sein. Darüber hinaus ist eine **const** -Instanz, den Wert der `m_data` nie geändert werden kann.