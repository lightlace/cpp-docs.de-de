---
title: Compilerwarnung (Stufe 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 66b8d42b63bcbf328703523c4eeda7a047f4643c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374572"
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