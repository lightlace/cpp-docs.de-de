---
title: Compilerfehler C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 1a3d0d754557bbc811d1017ed1491181333e82dc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766780"
---
# <a name="compiler-error-c3869"></a>Compilerfehler C3869

Gcnew-Einschränkung fehlt die leere Parameterliste Liste '(')

Die `gcnew` speziellen Einschränkung wurde ohne die leere Parameterliste angegeben. Finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3869 generiert.

```
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```