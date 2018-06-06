---
title: Compilerfehler C3278 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3278
dev_langs:
- C++
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b993aaaee0e50eacf47ce594b4c5efa47f83dd18
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705074"
---
# <a name="compiler-error-c3278"></a>Compilerfehler C3278

> direkter Aufruf der Schnittstellenmethode oder reinen Methode '*Methode*"wird zur Laufzeit einen Fehler.

## <a name="remarks"></a>Hinweise

Es erfolgte ein Aufruf für eine Schnittstellenmethode oder eine reine Methode, was nicht zulässig ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3278 generiert:

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```