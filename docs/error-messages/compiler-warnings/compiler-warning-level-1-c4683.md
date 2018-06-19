---
title: Compilerwarnung (Stufe 1) C4683 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418bf25d565c616d5bc4aaf58361c4f28df298ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285342"
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