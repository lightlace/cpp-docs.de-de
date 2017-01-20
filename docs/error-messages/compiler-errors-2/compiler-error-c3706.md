---
title: "Compilerfehler C3706"
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
  - "C3706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3706"
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Nur eine COM\-Schnittstelle kann COM\-Ereignisse auslösen  
  
 Die Ereignisschnittstelle, die zum Auslösen von COM\-Ereignissen verwendet wird, muss eine COM\-Schnittstelle sein.  In diesem Fall sollte die Schnittstelle entweder mithilfe eines Visual C\+\+\-Attributs definiert oder über [\#import](../../preprocessor/hash-import-directive-cpp.md) mit embedded\_idl\-Attribut importiert werden.  
  
 Beachten Sie, dass die `#include`\-Zeilen der ATL\-Headerdateien aus dem folgenden Beispiel für die Verwendung von COM\-Ereignissen erforderlich sind.  Um diesen Fehler zu beheben, wandeln Sie `IEvents` \(die ereignisauslösende Schnittstelle\) in eine COM\-Schnittstelle um, indem Sie eines der folgenden Attribute auf die Schnittstellendefinition anwenden: [object](../../windows/object-cpp.md), [dual](../../windows/dual.md) oder [dispinterface](../../windows/dispinterface.md).  
  
 Wenn eine Schnittstelle aus einer von MIDL erzeugten Headerdatei stammt, wird diese vom Compiler nicht als COM\-Schnittstelle erkannt.  
  
 Im folgenden Beispiel wird C3706 generiert:  
  
```  
// C3706.cpp  
// compile with: /c  
// C3706 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following line to resolve.  
// [object, uuid="12341234-1234-1234-1234-123412341237"]  
__interface IEvents : IUnknown {  
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]  
};  
  
[dual, uuid="12341234-1234-1234-1234-123412341235"]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]  
class CEventSrc : public IBase {  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```