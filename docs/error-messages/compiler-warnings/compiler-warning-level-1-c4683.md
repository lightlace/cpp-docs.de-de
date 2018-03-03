---
title: Compilerwarnung (Stufe 1) C4683 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a8ca498a3c95a1b37229f6ac973cf74a8e28ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4683"></a>Compilerwarnung (Stufe 1) C4683
**'**   
 ***Funktion* ": Ereignisquelle hat einen 'Out'-Parameter, seien Sie äußerst vorsichtig, wenn mehrere Ereignishandler einbinden**  
  
 Wenn mehr als eine Ereignissenke auf eine COM-Ereignisquelle abhört, kann der Wert eines Ausgabeparameters ignoriert.  
  
 Achten Sie darauf, dass ein Speicherverlust in den folgenden Situationen auftreten:  
  
1.  Wenn eine Methode einen Ausgabeparameter, der intern zugeordnet ist besitzt, z. B. einen BSTR *.  
  
2.  Wenn das Ereignis mehrere Ereignishandler (ist ein multicast-Ereignis)  
  
 Der Grund für den Speicherverlust ist, dass der Out-Parameter, indem mehrere Handler festlegen, doch nur von der letzten Handler zur Aufrufsite zurückgegeben.  
  
 Im folgenden Beispiel wird C4683 generiert:  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```