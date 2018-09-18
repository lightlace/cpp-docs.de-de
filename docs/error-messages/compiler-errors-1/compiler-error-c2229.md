---
title: Compilerfehler C2229 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b235b5fae84ba605ecec5419f9334ccfa0a4be6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035590"
---
# <a name="compiler-error-c2229"></a>Compilerfehler C2229

Typ "Identifier" wurde ein ungültiger NULL-array

Ein Member einer Struktur oder ein Bit enthält ein Array der Größe 0 (null), die nicht das letzte Element ist.

Da Sie eine NULL Array Größe wie das letzte Element der Struktur verwenden können, müssen Sie seine Größe angeben, beim Zuweisen der Struktur.

Wenn 0 (null) großen Arrays nicht der letzte Member der Struktur ist, kann der Compiler nicht den Offset für die verbleibenden Felder berechnen.

Im folgende Beispiel wird die C2229 generiert:

```
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```