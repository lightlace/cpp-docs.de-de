---
title: Compilerfehler C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 2ec39768a88da049c6a31ca2a9de226e25479c99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571469"
---
# <a name="compiler-error-c2842"></a>Compilerfehler C2842

„Klasse“: Ein verwalteter oder WinRT-Typ kann keinen eigenen „operator new“- oder „operator delete“-Operator definieren.

Sie können definieren, Ihre eigenen ** new-Operator oder **Delete-Operator** speicherbelegung auf dem systemeigenen Heap zu verwalten. Verweisklassen können diese Operatoren jedoch nicht definieren, da sie nur dem verwalteten Heap zugewiesen sind.

Weitere Informationen finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2842 generiert.

```
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
