---
title: "lock::operator=="
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "lock::operator=="
  - "msclr.lock.operator=="
  - "msclr::lock::operator=="
  - "lock.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::operator=="
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
caps.latest.revision: 6
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# lock::operator==
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gleichheitsoperator.  
  
## Syntax  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### Parameter  
 `t`  
 Das auf Gleichheit zu prüfende Objekt.  
  
## Rückgabewert  
 Gibt `true`, wenn `t` mit dem Objekt der Sperre befindet; andernfalls `false` zurück.  
  
## Beispiel  
  
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
  
  **Gleich\!**   
## Anforderungen  
 **Headerdatei** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [lock\-Member](../dotnet/lock-members.md)   
 [lock::operator\!\=](../dotnet/lock-operator-inequality.md)