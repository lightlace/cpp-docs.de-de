---
title: "Compilerfehler C3705 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3705"
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Die ereignisauslösende Schnittstelle konnte nicht gefunden werden  
  
 Um COM\-Ereignisse zu verwenden, müssen Sie eine Ereignisschnittstelle definieren.  Beachten Sie, dass die `#include`\-Zeilen der ATL\-Headerdateien aus dem folgenden Beispiel für die Verwendung von COM\-Ereignissen erforderlich sind.  Um diesen Fehler zu beheben, kommentieren Sie die Definition der `IEvents`\-Schnittstelle im Beispielcode aus.  
  
 Im folgenden Beispiel wird C3705 generiert:  
  
```  
// C3705.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following 4 lines to resolve.  
// [object, uuid("00000000-0000-0000-0000-000000000003")]  
// __interface IEvents : IUnknown {  
//    HRESULT event1([in] int i);  
// };  
  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]  
class CEventSrc : public IBase {  
public:  
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```