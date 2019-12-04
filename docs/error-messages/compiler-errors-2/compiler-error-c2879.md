---
title: Compilerfehler C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6c7238faf94a2493894534ae5684634b65bb4342
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736294"
---
# <a name="compiler-error-c2879"></a>Compilerfehler C2879

' Symbol ': nur ein vorhandener Namespace kann einen alternativen Namen durch eine Namespace-alias Definition erhalten.

Es ist nicht möglich, einen [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) für ein anderes Symbol als einen Namespace zu erstellen.

Im folgenden Beispiel wird C2879 generiert:

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```
