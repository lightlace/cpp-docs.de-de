---
title: Compilerfehler C2139 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2139
dev_langs:
- C++
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8da6a8bb4ca7630a3deff3b1ec79ca512ae2e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090094"
---
# <a name="compiler-error-c2139"></a>Compilerfehler C2139

'Typ': eine nicht definierte Klasse ist als Argument für das systeminterne Typmerkmal 'Eigenschaft' des Compilers nicht zulässig.

Ein ungültiges Argument wurde an eine Typeigenschaft übergeben.

Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2139 generiert.

```
// C2139.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class C;
class D {};

class E {
public:
   virtual void Test() {}
};

int main() {
   cout << is_polymorphic<C>::value << endl;   // C2139
   cout << is_polymorphic<D>::value << endl;   // OK
   cout << is_polymorphic<E>::value << endl;   // OK
}
```