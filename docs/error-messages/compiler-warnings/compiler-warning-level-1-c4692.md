---
title: Compilerwarnung (Stufe 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: e7ec657956c72f1e321227d54b796164292f0c0e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052492"
---
# <a name="compiler-warning-level-1-c4692"></a>Compilerwarnung (Stufe 1) C4692

'Funktion': Die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp 'systemeigener_Typ'

Ein außerhalb der Assembly sichtbarer Typ enthält eine Memberfunktion, deren Signatur wiederum einen systemeigenen Typ enthält, der außerhalb der Assembly nicht sichtbar ist. Deshalb sollte die Memberfunktion nicht aufgerufen werden, wenn der darin enthaltene Typ außerhalb der Assembly instanziiert wird.

Weitere Informationen finden Sie unter [Typsichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4692 generiert.

```cpp
// C4692.cpp
// compile with: /W1 /c /clr
#pragma warning(default:4692)
class Private_Native_Class {};
public class Public_Native_Class {};
public ref class Public_Ref_Class {
public:
   void Test(Private_Native_Class *) {}   // C4692
   void Test2(Public_Native_Class *) {}   // OK
};
```