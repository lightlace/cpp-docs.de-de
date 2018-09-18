---
title: Compilerfehler C2861 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94210350e0483b46eb86579b837501a5291bda4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037254"
---
# <a name="compiler-error-c2861"></a>Compilerfehler C2861

"Funktionsname": eine Schnittstellenmemberfunktion kann nicht definiert werden

Der Compiler hat das Interface-Schlüsselwort oder eine Struktur als eine Schnittstelle abgeleitet gefunden dann jedoch eine Funktion der Definition.  Eine Schnittstelle kann nicht über eine Definition für eine Memberfunktion enthalten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2861 generiert:

```
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861

```