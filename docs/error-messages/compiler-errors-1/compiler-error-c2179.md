---
title: Compilerfehler C2179 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2179
dev_langs:
- C++
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b56437dfe5b9be75ae93dea46890d408ea2dc66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111629"
---
# <a name="compiler-error-c2179"></a>Compilerfehler C2179

'Typ': Ein Attributargument kann keine Typparameter verwenden.

Ein generischer Typparameter wird zur Laufzeit aufgelöst. Allerdings muss ein Attributparameter, zum Zeitpunkt der Kompilierung der aufgelöst werden. Sie können einen generischen Typparameter aus diesem Grund können nicht als Argument für ein Attribut verwenden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2179 generiert.

```
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```