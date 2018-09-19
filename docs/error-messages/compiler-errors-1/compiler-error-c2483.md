---
title: Compilerfehler C2483 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be2a2caef9e1252bf1ab36253a7f5f715b94d5a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031612"
---
# <a name="compiler-error-c2483"></a>Compilerfehler C2483

>"*Bezeichner*": Objekt mit dem Konstruktor oder Destruktor kann nicht als "thread" deklariert werden

Diese Fehlermeldung ist in Visual Studio 2015 und höher veraltet. In früheren Versionen Variablen deklariert, mit der `thread` Attribut kann nicht initialisiert werden, mit einem Konstruktor oder ein anderer Ausdruck, der Auswertung der Laufzeit erfordert. Ein statischer Ausdruck ist erforderlich, um das Initialisieren `thread` Daten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2483 generiert in Visual Studio 2013 und früheren Versionen.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>Siehe auch

[thread](../../cpp/thread.md)