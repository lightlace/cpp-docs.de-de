---
title: Compilerwarnung (Stufe 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 97ad076325b11329896d98367fb3ac311ec5ded9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051568"
---
# <a name="compiler-warning-level-1-c4804"></a>Compilerwarnung (Stufe 1) C4804

"Operation": unsichere Verwendung des Typs "bool" in Vorgang

Diese Warnung gilt für den Fall, dass Sie eine `bool` Variable oder einen Wert auf unerwartete Weise verwendet haben. Beispielsweise wird C4804 generiert, wenn Sie Operatoren verwenden, z. b. den negativen unären Operator ( **-** ) oder den Komplement Operator (`~`). Der Compiler wertet den Ausdruck aus.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4804 generiert:

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```