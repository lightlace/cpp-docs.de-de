---
title: Compilerfehler C3133 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3133
dev_langs:
- C++
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 269cc2c22d260b058f16263e4ee73e4a480920eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023396"
---
# <a name="compiler-error-c3133"></a>Compilerfehler C3133

Attribute können nicht auf Varargs in C++ angewendet werden

Ein Attribut wurde falsch angewendet. Attribute können nicht auf die Auslassungspunkte, die Variable Argumente darstellen angewendet werden.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3133 generiert.

```
// C3133.cpp
// compile with: /clr /c
ref struct MyAttr: System::Attribute {};
void Func([MyAttr]...);   // C3133
void Func2([MyAttr] int i);   // OK
```