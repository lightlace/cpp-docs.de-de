---
title: Compilerfehler C3761 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3761
dev_langs:
- C++
helpviewer_keywords:
- C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d543634bf91411fcaa6acaa0b53c8b4820c6c021
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018404"
---
# <a name="compiler-error-c3761"></a>Compilerfehler C3761

'Funktion': "Retval" kann nur für das letzte Argument einer Funktion verwendet werden.

Die [Retval](../../windows/retval.md) -Attribut wurde auf ein Funktionsargument, die nicht das letzte Argument in der Liste verwendet.

Im folgende Beispiel wird die C3761 generiert:

```
// C3761.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name=test) ];

[dispinterface]
__interface I
{
   [id(1)] HRESULT func([out, retval] int* i, [in] int j);
   // try the following line instead
   // [id(1)] HRESULT func([in] int i, [out, retval] int* j);
};

[coclass]
struct C : I {   // C3761
   HRESULT func(int* i, int j)
   // try the following line instead
   // HRESULT func(int j, int* i)
   {
      return S_OK;
   }
};

int main()
{
}
```