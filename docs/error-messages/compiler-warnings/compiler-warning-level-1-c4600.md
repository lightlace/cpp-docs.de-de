---
title: Compilerwarnung (Stufe 1) C4600 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4600
dev_langs:
- C++
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27b020fdd87e35633b6a6da74d8c51c63fc1604e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079361"
---
# <a name="compiler-warning-level-1-c4600"></a>Compilerwarnung (Stufe 1) C4600

\#Pragma 'Makroname': eine gültige nicht leere Zeichenfolge erwartet

Sie können keine leere Zeichenfolge angeben, wenn Sie mithilfe von Push übertragen oder einen Makronamen entweder mit der [Pop_macro](../../preprocessor/pop-macro.md) oder [Push_macro](../../preprocessor/push-macro.md).

Im folgende Beispiel wird die C4600 generiert:

```
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```