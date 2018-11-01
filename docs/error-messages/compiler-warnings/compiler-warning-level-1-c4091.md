---
title: Compilerwarnung (Stufe 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 87432a74dfe7c09a52f436d4e91b3f70eb66856b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491740"
---
# <a name="compiler-warning-level-1-c4091"></a>Compilerwarnung (Stufe 1) C4091

'Schlüsselwort': auf der linken Seite von 'Typ' ignoriert wird, wenn keine Variable deklariert wurde

Der Compiler hat eine Situation, in denen der Benutzer soll wahrscheinlich eine Variable deklariert werden, aber der Compiler konnte sich nicht um die Variable zu deklarieren.

## <a name="example"></a>Beispiel

Ein `__declspec` Attribut am Anfang einer benutzerdefinierten Typdeklaration gilt für die Variable dieses Typs. C4091 weist darauf hin, dass keine Variable deklariert wurde. Im folgende Beispiel wird die C4091 generiert.

```
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>Beispiel

Wenn ein Bezeichner eine Typdefinition ist, kann nicht es auch ein Variablenname sein. Im folgende Beispiel wird die C4091 generiert.

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```