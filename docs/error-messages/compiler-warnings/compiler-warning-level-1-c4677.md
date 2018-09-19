---
title: Compilerwarnung (Stufe 1) C4677 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6a3f57ba0e3d4c15c83711a86bb8482fa8b0596
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049384"
---
# <a name="compiler-warning-level-1-c4677"></a>Compilerwarnung (Stufe 1) C4677

'Funktion': die Signatur des nicht privaten Members enthält den privaten Assemblytyp 'Private_type'

Ein Typ mit öffentlicher Zugriff außerhalb der Assembly verwendet einen Typ, der privaten Zugriff außerhalb der Assembly enthält. Eine Komponente, die den Typ der öffentliche Assemblyzugriff verweist ist nicht möglich, den Typ dieses Element oder Elemente, die auf den privaten Assemblytyp zu verweisen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4677 generiert.

```
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```