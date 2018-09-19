---
title: Compilerfehler C2871 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2871
dev_langs:
- C++
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e960dd6bc9fdf81d6a1bb127330f1066628fffd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117620"
---
# <a name="compiler-error-c2871"></a>Compilerfehler C2871

'Name': ein Namespace mit diesem Namen ist nicht vorhanden.

Dieser Fehler tritt auf, wenn Sie einen Bezeichner übergeben, die keinem Namespace ist ein [mit](../../cpp/namespaces-cpp.md#using_directives) Richtlinie.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2871 generiert:

```cpp
// C2871.cpp
// compile with: /c
namespace a {
   int fn(int i) { return i; }
}
namespace b {
   using namespace d;   // C2871 because d is not a namespace
   using namespace a;   // OK
}
```