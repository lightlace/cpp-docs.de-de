---
title: Compilerfehler C2217 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4eb8b9fcaffa30f3a5ced5362a0f9d54a45f07e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050618"
---
# <a name="compiler-error-c2217"></a>Compilerfehler C2217

"attribute1" muss "attribute2"

Das erste Funktionsattribut ist das zweite Attribut erforderlich.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Unterbrechen (`__interrupt`) Funktion deklariert wird, als `near`. Unterbrechen Funktionen muss `far`.

1. Unterbrochen mit deklarierte Funktion `__stdcall`, oder `__fastcall`. Diese Funktionen müssen mithilfe C++ Aufrufkonventionen.

## <a name="example"></a>Beispiel

C2217 kann auch auftreten, wenn Sie versuchen, einen Delegaten an eine CLR-Funktion zu binden, die eine Variable Anzahl von Argumenten akzeptiert. Wenn die Funktion auch Parameterarrayüberladung verfügt, verwenden Sie stattdessen. Im folgende Beispiel wird die C2217 generiert.

```
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```