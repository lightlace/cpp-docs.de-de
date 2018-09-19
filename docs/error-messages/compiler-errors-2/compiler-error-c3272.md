---
title: Compilerfehler C3272 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eaadad23d5647a0f27f4bbd9119c192f406da265
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018559"
---
# <a name="compiler-error-c3272"></a>Compilerfehler C3272

"Symbol": Symbol erfordert "FieldOffset", da es ein Member des Typs "Typname" ist, der mit "StructLayout(LayoutKind::Explicit)" definiert wurde.

Wenn `StructLayout(LayoutKind::Explicit)` aktiv ist, müssen Felder mit `FieldOffset`gekennzeichnet werden.

Im folgenden Beispiel wird C3272 generiert:

```
// C3272_2.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
ref struct X
{
   int data_;   // C3272
   // try the following line instead
   // [FieldOffset(0)] int data_;
};
```
