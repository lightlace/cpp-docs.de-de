---
title: "Compilerfehler C3708"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3708"
ms.assetid: 45e71564-9c7f-437f-98d8-a735ce162ed0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle': Ungültige Verwendung von 'Schlüsselwort'. Es muss ein Member einer kompatiblen Ereignisquelle sein  
  
 Um eine Schnittstelle als Ereignis zu deklarieren, muss sich die Ereignisdeklaration in einer Ereignisquelle befinden.  
  
 Im folgenden Beispiel wird C3708 generiert:  
  
```  
// C3708.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="MyLibrary")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface II {  
   HRESULT func();  
};  
  
__event __interface I;   // C3708  
  
// put the event in an event source  
[ coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000003") ]  
struct E : II {  
   __event __interface II;  
};  
```