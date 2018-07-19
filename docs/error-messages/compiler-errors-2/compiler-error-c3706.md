---
title: Compilerfehler C3706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cb54dfce6a6974fcf09886f2d13047cdab53ced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265245"
---
# <a name="compiler-error-c3706"></a>Compilerfehler C3706
'Funktion': eine COM-Schnittstelle, COM-Ereignisse ausgelöst werden muss  
  
 Die Ereignisschnittstelle, die Sie verwenden, um COM-Ereignisse auslösen muss es sich um eine COM-Schnittstelle sein. In diesem Fall der Benutzeroberfläche entweder mit einem Visual C++-Attribut definiert werden soll, oder mit importiert [#import](../../preprocessor/hash-import-directive-cpp.md) aus einer Typbibliothek mit #import des Embedded_idl-Attribut.  
  
 Beachten Sie, dass die `#include` Zeilen der ATL-Headerdateien, die im folgenden Beispiel gezeigt für die Verwendung von COM-Ereignisse erforderlich sind. Um diesen Fehler zu beheben, stellen `IEvents` (die Ereignisse-Schnittstelle) eine COM-Schnittstelle, durch Anwenden eines der folgenden Attribute zur Schnittstellendefinition: [Objekt](../../windows/object-cpp.md), [duale](../../windows/dual.md), oder [ Dispinterface](../../windows/dispinterface.md).  
  
 Wenn eine Schnittstelle aus einer Headerdatei, die von MIDL generiert wird, wird Sie von der Compiler nicht als COM-Schnittstelle erkannt.  
  
 Im folgende Beispiel wird C3706 generiert:  
  
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