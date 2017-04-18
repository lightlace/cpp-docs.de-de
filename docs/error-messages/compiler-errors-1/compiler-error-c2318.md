---
title: Compilerfehler C2318 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2318
dev_langs:
- C++
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 47c3b697b4731547f694822e9a4494e365619adc
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2318"></a>Compilerfehler C2318
Kein try-Block mit diesem catch-Handler verbunden  
  
 Es ist ein `catch` -Handler definiert, vor diesem ist aber kein `try` -Block angegeben.  
  
 Im folgenden Beispiel wird C2318 generiert:  
  
```  
// C2318.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   // no try block  
   catch( int ) {}   // C2318  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2318b.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try{}  
   catch( int ) {}  
}  
```
