---
title: Compilerfehler C2861 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18c51d01b8f273d4546f3411405fe511e31799ef
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2861"></a>Compilerfehler C2861
"Funktionsname": eine Schnittstellenmemberfunktion kann nicht definiert werden  
  
 Der Compiler hat das Interface-Schlüsselwort oder eine Struktur als Schnittstelle abgeleitet, aber dann ein Element gefunden Definition-Funktion.  Eine Schnittstelle darf keine Definition für eine Memberfunktion enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2861 generiert:  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```
