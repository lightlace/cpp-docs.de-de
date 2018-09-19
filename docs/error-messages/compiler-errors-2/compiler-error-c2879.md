---
title: Compilerfehler C2879 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 632142ea0efd8a9d009f18b898213cfa92514b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042475"
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