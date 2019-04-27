---
title: Compilerfehler C2788
ms.date: 11/04/2016
f1_keywords:
- C2788
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
ms.openlocfilehash: 0025aa5211c2736860bdd30cad4315f63fba9337
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256892"
---
# <a name="compiler-error-c2788"></a>Compilerfehler C2788

'Bezeichner': mehr als eine GUID, die diesem Objekt zugeordnet

Die [__uuidof](../../cpp/uuidof-operator.md) -Operator akzeptiert einen benutzerdefinierten Typ mit einer GUID verbundenen oder ein Objekt eines solchen benutzerdefinierten Typs. Dieser Fehler tritt auf, wenn das Argument ein Objekt mit mehreren GUIDs ist.

Im folgende Beispiel wird die C2788 generiert:

```
// C2788.cpp
#include <windows.h>
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};
template <class T, class U> class MyClass {};

typedef MyClass<A,B> MyBadClass;
typedef MyClass<A,A> MyGoodClass;

int main() {
   __uuidof(MyBadClass);    // C2788
   // try the following line instead
   __uuidof(MyGoodClass);
}
```