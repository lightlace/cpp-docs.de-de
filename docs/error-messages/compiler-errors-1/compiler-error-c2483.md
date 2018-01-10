---
title: Compilerfehler C2483 | Microsoft Docs
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2483
dev_langs: C++
helpviewer_keywords: C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f7f9f30724c02d44e054bf16ff1460370c30e06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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