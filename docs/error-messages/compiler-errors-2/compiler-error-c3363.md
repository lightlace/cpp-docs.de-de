---
title: Compilerfehler C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: eca598233dbe4cae4730e952b45945653ec8ffaa
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775881"
---
# <a name="compiler-error-c3363"></a>Compilerfehler C3363

"Typ" : "Typ-ID" kann nur auf einen Typ angewendet werden.

Der [typeid](../../extensions/typeid-cpp-component-extensions.md) -Operator wurde falsch verwendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3363 generiert:

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```