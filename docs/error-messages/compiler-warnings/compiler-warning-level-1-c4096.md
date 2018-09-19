---
title: Compilerwarnung (Stufe 1) C4096 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4096
dev_langs:
- C++
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef2aaf3f37e9699547c3a85c55a2f72d4baab7a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047693"
---
# <a name="compiler-warning-level-1-c4096"></a>Compilerwarnung (Stufe 1) C4096

"a": Schnittstelle ist nicht mit einem COM-Schnittstelle wird nicht nach IDL emittiert

Eine Schnittstellendefinition, die Sie als COM-Schnittstelle für verfügen möglicherweise nicht als COM-Schnittstelle definiert wurde und daher nicht ausgegeben, um die IDL-Datei.

Finden Sie unter [Schnittstellenattribute](../../windows/interface-attributes.md) für eine Liste der Attribute, die angeben, eine Schnittstelle ist eine COM-Schnittstelle.

Im folgende Beispiel wird die C4096 generiert:

```
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```