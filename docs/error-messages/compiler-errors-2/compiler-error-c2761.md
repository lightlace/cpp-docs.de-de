---
title: Compilerfehler C2761 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2761
dev_langs:
- C++
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2083f08ad79a9fd53148e7c166ec276a9ddf4cde
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075240"
---
# <a name="compiler-error-c2761"></a>Compilerfehler C2761

'Funktion': die erneute Deklaration der Funktion nicht zulässig

Eine Memberfunktion kann nicht erneut deklariert werden. Sie können definieren, jedoch nicht neu deklariert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2761 generiert.

```
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761

```

## <a name="example"></a>Beispiel

Nicht statische Member einer Klasse oder Struktur können nicht definiert werden.  Im folgende Beispiel wird die C2761 generiert.

```
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```