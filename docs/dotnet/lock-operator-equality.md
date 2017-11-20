---
title: Lock::Operator == | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
dev_langs: C++
helpviewer_keywords: lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33e372deb0bbae86efdf1a7c928d45e673e0b334
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="lockoperator"></a>lock::operator==
Gleichheitsoperator.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `t`  
 Das Objekt auf Gleichheit verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `true` Wenn `t` ist identisch mit der Sperrenobjekt `false` andernfalls.  
  
## <a name="example"></a>Beispiel  
  
```  
// msl_lock_op_eq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   lock l1(o1);  
   if (l1 == o1) {  
      Console::WriteLine("Equal!");  
   }  
}  
```  
  
```Output  
Equal!  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\lock.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [Lock-Member](../dotnet/lock-members.md)   
 [lock::operator!=](../dotnet/lock-operator-inequality.md)