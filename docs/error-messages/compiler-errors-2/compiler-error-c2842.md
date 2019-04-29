---
title: Compilerfehler C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 99b2c86d1e914c9425c2664d4e858bba6cb99486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382943"
---
# <a name="compiler-error-c2842"></a>Compilerfehler C2842

> "*Klasse*": ein verwaltetes oder WinRT-Typ kann keine definiert seine eigenen "Operator new" oder "Operator delete"

## <a name="remarks"></a>Hinweise

Sie können definieren, Ihre eigenen **new-Operator** oder **Delete-Operator** speicherbelegung auf dem systemeigenen Heap zu verwalten. Verweisklassen können diese Operatoren jedoch nicht definieren, da sie nur dem verwalteten Heap zugewiesen sind.

Weitere Informationen finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2842 generiert.

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
