---
title: Compilerfehler C3458
ms.date: 11/04/2016
f1_keywords:
- C3458
helpviewer_keywords:
- C3458
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
ms.openlocfilehash: 07749677dbaa84de205adf38aadee6867a553852
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676810"
---
# <a name="compiler-error-c3458"></a>Compilerfehler C3458

'attribut1': Das Attribut 'attribut2' wurde bereits für 'konstrukt' angegeben

Zwei Attribute, die sich gegenseitig ausschließen, wurden für dasselbe Konstrukt angegeben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3458 generiert:

```
// C3458.cpp
// compile with: /clr /c
[System::Reflection::DefaultMember("Chars")]
public ref class MyString {
public:
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458
   property char default[int] {
      char get(int index);
      void set(int index, char c);
   }
};
```