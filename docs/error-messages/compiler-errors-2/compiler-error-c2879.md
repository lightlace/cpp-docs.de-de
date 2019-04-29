---
title: Compilerfehler C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378900"
---
# <a name="compiler-error-c2879"></a>Compilerfehler C2879

'Symbol': nur ein vorhandener Namespace einen alternativen Namen ein Namespace-Aliasdefinition erhalten.

Sie können nicht erstellt werden ein [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) auf ein Symbol als ein Namespace.

Im folgende Beispiel wird die C2879 generiert:

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```