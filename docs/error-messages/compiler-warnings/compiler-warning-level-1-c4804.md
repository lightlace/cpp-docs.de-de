---
title: Compilerwarnung (Stufe 1) C4804 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4804
dev_langs:
- C++
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd1d1659ad6c8716cebf37a99f234af7b41f5745
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094805"
---
# <a name="compiler-warning-level-1-c4804"></a>Compilerwarnung (Stufe 1) C4804

'Operation': unsichere Verwendung des Typs "Bool", Vorgang

Diese Warnung gilt für bei der Verwendung einer `bool` Variable oder ein Wert in der erwarteten Weise. C4804 wird beispielsweise generiert, bei der Verwendung Operatoren wie z. B. den negativen unäroperator (**-**) oder dem Komplementoperator (`~`). Der Compiler wertet den Ausdruck.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4804 generiert:

```
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