---
title: Compilerfehler C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 95344b5ef675f566f433dfeaed9dee5c38ef77d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598275"
---
# <a name="compiler-error-c2071"></a>Compilerfehler C2071

'Bezeichner': Ungültige Speicherklasse

`identifier` mit einem ungültigen SE deklarovalo [Speicherklasse](../../c-language/c-storage-classes.md). Dieser Fehler kann verursacht werden, wenn mehr als eine Speicherklasse für einen Bezeichner angegeben ist oder wenn die Definition mit der Speicherklassen-Deklaration nicht kompatibel ist.

Um dieses Problem zu beheben, verstehen Sie die beabsichtigte Speicherklasse des Bezeichners – z. B. `static` oder `extern`–, und beheben Sie die Deklaration zur Übereinstimmung.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2071 generiert.

```
// C2071.cpp
// compile with: /c
struct C {
   extern int i;   // C2071
};
struct D {
   int i;   // OK, no extern on an automatic
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2071 generiert.

```
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```