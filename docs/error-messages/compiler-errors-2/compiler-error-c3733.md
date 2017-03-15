---
title: "Compilerfehler C3733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3733"
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ereignis': Ungültige Syntax zur Spezifizierung eines COM\-Ereignisses. Haben Sie '\_\_interface' vergessen?  
  
 Für ein COM\-Ereignis wurde die falsche Syntax verwendet.  Um den Fehler zu beheben, ändern Sie den Ereignistyp, oder korrigieren die Syntax entsprechend den COM\-Ereignisregeln.  
  
 Im folgenden Beispiel wird C3733 generiert:  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```