---
title: "Compilerwarnung (Stufe 1) C4683 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4683"
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung (Stufe 1) C4683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***function* ': Die Ereignisquelle hat einen 'Out'\-Parameter. Seien Sie vorsichtig, wenn Sie für mehrere Ereignishandler eine Hookfunktion erstellen**  
  
 Wenn eine COM\-Ereignisquelle von mehreren Ereignissenken abgefragt wird, wird der Wert eines Out\-Parameters u. U. ignoriert.  
  
 In den folgenden Situationen treten Speicherverluste auf:  
  
1.  Wenn eine Methode einen Out\-Parameter hat, der intern reserviert ist, z. B. BSTR \*.  
  
2.  Wenn das Ereignis mindestens zwei Handler hat \(d. h. ein Multicastereignis ist\)  
  
 Die Ursache für den Speicherverlust liegt darin, dass der Out\-Parameter von mindestens zwei Handlern festgelegt, aber nur vom letzten Handler an die Aufrufsite zurückgegeben wird.  
  
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