---
title: Compilerfehler C2555 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f91ec33db2d3a7b6772556233a3c99b501ede76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017338"
---
# <a name="compiler-error-c2555"></a>Compilerfehler C2555

'Class1 ':: function1: überschreibende virtuelle Funktion unterscheidet sich und ist nicht von 'Class2 ':: function2 kovariant zurückgeben

Haben eine virtuelle Funktion und die abgeleiteten überschreibenden Funktion Parameterlisten identisch, jedoch unterschiedliche Rückgabetypen. Eine überschreibende-Funktion in einer abgeleiteten Klasse kann nicht von einer virtuellen Funktion in einer Basisklasse nur durch ihren Rückgabetyp unterscheiden.

Um diesen Fehler zu beheben, wandeln Sie den Rückgabewert, nachdem die virtuelle Funktion aufgerufen wurde.

Dieser Fehler kann auch angezeigt, wenn Sie mit "/ CLR" kompilieren.   Z. B. Visual C++ entspricht der folgenden C#-Deklaration:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

echt

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Weitere Informationen zu C2555 finden Sie in der Knowledge Base-Artikel Q240862.

Im folgende Beispiel wird die C2555 generiert:

```
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```