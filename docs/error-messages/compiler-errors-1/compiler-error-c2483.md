---
title: Compilerfehler C2483 | Microsoft Docs
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
ms.openlocfilehash: 0a10fd33ebeef43904db964fc327fb749029f963
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2483"></a>Compilerfehler C2483

>"*Bezeichner*": Objekt mit dem Konstruktor oder Destruktor kann nicht 'thread' deklariert werden

Diese Fehlermeldung wird in Visual Studio 2015 und höher veraltet. In früheren Versionen Variablen deklariert, mit der `thread` Attribut kann nicht initialisiert werden, mit einem Konstruktor oder ein anderer Ausdruck, der zur Laufzeit Auswertung erfordert. Ein statischer Ausdruck ist erforderlich, um initialisieren `thread` Daten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2483 generiert in Visual Studio 2013 und früheren Versionen.

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