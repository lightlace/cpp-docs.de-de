---
title: Compilerwarnung (Stufe 1) C4269 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dc986c98028530b8a5d4d25047305fd1a8effef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027276"
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