---
title: Compilerwarnung (Stufe 1) C4946
ms.date: 11/04/2016
f1_keywords:
- C4946
helpviewer_keywords:
- C4946
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
ms.openlocfilehash: f215c621486bf223d8f6c90b0a4f4ae119ad4b1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280569"
---
# <a name="compiler-warning-level-1-c4946"></a>Compilerwarnung (Stufe 1) C4946

reinterpret_cast wird zwischen verknüpften Klassen verwendet: 'Klasse1' und 'Klasse2'

Verwenden Sie keine ["reinterpret_cast"](../../cpp/reinterpret-cast-operator.md) zwischen verwandten Typen umgewandelt. Verwenden Sie ["static_cast"](../../cpp/static-cast-operator.md) stattdessen oder für die polymorphe Typen verwenden [Dynamic_cast](../../cpp/dynamic-cast-operator.md).

Standardmäßig wird diese Warnung deaktiviert ist. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Im folgenden Codebeispiel wird die C4946 generiert:

```
// C4946.cpp
// compile with: /W1
#pragma warning (default : 4946)
class a {
public:
   a() : m(0) {}
   int m;
};

class b : public virtual a {
};

class b2 : public virtual a {
};

class c : public b, public b2 {
};

int main() {
   c* pC = new c;
   a* pA = reinterpret_cast<a*>(pC);   // C4946
   // try the following line instead
   // a* pA = static_cast<a*>(pC);
}
```