---
title: Compilerfehler C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: 0c9804666bfd73f98541f95434b9cebf5185d2ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566815"
---
# <a name="compiler-error-c3384"></a>Compilerfehler C3384

"type_parameter" : Die Werteinschränkung und die ref-Einschränkung schließen sich gegenseitig aus

Sie können einen generischen Typ nicht gleichzeitig auf `value class` und `ref class`einschränken.

Finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3384 generiert.

```
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```