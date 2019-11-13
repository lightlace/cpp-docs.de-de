---
title: Compilerwarnung (Stufe 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 8567e7392537507a25121977448ac47ec079316b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051366"
---
# <a name="compiler-warning-level-1-c4677"></a>Compilerwarnung (Stufe 1) C4677

"Funktion": die Signatur des nicht privaten Members enthält den privaten Assemblytyp "private_type".

Ein Typ mit öffentlichem Zugriff außerhalb der Assembly verwendet einen Typ, der über privaten Zugriff außerhalb der Assembly verfügt. Eine Komponente, die auf den Typ der öffentlichen Assembly verweist, kann nicht das Typelement oder die Member verwenden, die auf den privaten Assemblytyp verweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4677 generiert.

```cpp
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