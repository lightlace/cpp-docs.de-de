---
title: Compilerfehler C3400 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3400
dev_langs:
- C++
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35231ffda3a072b0720acc4c866dd2e3684c88fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024553"
---
# <a name="compiler-error-c3400"></a>Compilerfehler C3400

Zirkuläre Einschränkungsabhängigkeit mit „constraint_1“ und „constraint_2“

Der Compiler hat zirkuläre Einschränkungen erkannt.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3400 generiert:

```
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```