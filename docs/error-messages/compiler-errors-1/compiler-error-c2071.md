---
title: Compilerfehler C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 1dc9781bc0cf1bc6c7f879cc3971828983471c6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757747"
---
# <a name="compiler-error-c2071"></a>Compilerfehler C2071

'Bezeichner': Ungültige Speicherklasse

`identifier` wurde mit einer ungültigen [Speicher Klasse](../../c-language/c-storage-classes.md)deklariert. Dieser Fehler kann verursacht werden, wenn mehr als eine Speicherklasse für einen Bezeichner angegeben ist oder wenn die Definition mit der Speicherklassen-Deklaration nicht kompatibel ist.

Um dieses Problem zu beheben, verstehen Sie die beabsichtigte Speicher Klasse des Bezeichners – z. b. `static` oder `extern`–, und korrigieren Sie die Deklaration entsprechend.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2071 generiert.

```cpp
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

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
