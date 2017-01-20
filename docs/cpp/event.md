---
title: "__event"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__event_cpp"
  - "__event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__event-Schlüsselwort [C++]"
  - "Ereignisse [C++], __event"
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# __event
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert ein Ereignis.  
  
## Syntax  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## Hinweise  
 Das Schlüsselwort `__event` kann auf eine Methodendeklaration, eine Schnittstellendeklaration oder eine Datenmemberdeklaration angewendet werden.  Sie können jedoch das `__event`\-Schlüsselwort nicht verwenden, um einen Member einer geschachtelten Klasse zu qualifizieren.  
  
 Je nachdem, ob Ereignisquelle und Empfänger systemeigenes C\+\+, COM oder verwaltet \(.NET Framework\) sind, können Sie die folgenden Konstrukte als Ereignisse verwenden:  
  
|Systemeigenes C\+\+|COM|Verwaltet \(.NET Framework\)|  
|-------------------------|---------|----------------------------------|  
|Methode|—|Methode|  
|—|Schnittstelle|—|  
|—|—|Datenmember|  
  
 Verwenden Sie [\_\_hook](../cpp/hook.md) in einem Ereignisempfänger, um einer Handlermethode eine Ereignismethode zuzuordnen.  Beachten Sie, dass nach dem Erstellen eines Ereignisses mit dem `__event`\-Schlüsselwort alle Ereignishandler, die nacheinander in dieses Ereignis eingebunden werden, bei Aufruf des Ereignisses aufgerufen werden.  
  
 Eine `__event`\-Methodendeklaration kann keine Definition enthalten. Eine Definition wird implizit generiert, sodass die Ereignismethode aufgerufen werden kann, als wenn sie eine normale Methode wäre.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Systemeigene Ereignisse  
 Systemeigene Ereignisse sind Methoden.  Der Rückgabetyp ist normalerweise `HRESULT` oder `void`, kann jedoch ein beliebiger ganzzahliger Typ sein, einschließlich `enum`.  Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet, ist für den Fall, dass ein Ereignishandler einen Wert ungleich 0 \(null\) zurückgibt, eine Fehlerbedingung definiert. In diesem Fall werden durch das ausgelöste Ereignis die anderen Delegaten aufgerufen.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Beispielcode erhalten Sie unter [Event Handling in Native C\+\+](../cpp/event-handling-in-native-cpp.md).  
  
## COM\-Ereignisse  
 COM\-Ereignisse sind Schnittstellen.  Die Parameter einer Methode in einer Ereignisquellschnittstelle sollten **in**\-Parameter sein \(dies wird allerdings nicht erzwungen\). Ein **out**\-Parameter ist beim Multicasting nicht hilfreich.  Ein Warnung der Stufe 1 wird ausgegeben, wenn Sie einen **out**\-Parameter verwenden.  
  
 Der Rückgabetyp ist normalerweise `HRESULT` oder `void`, kann jedoch ein beliebiger ganzzahliger Typ sein, einschließlich `enum`.  Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet und ein Ereignishandler einen Wert ungleich 0 \(null\) zurückgibt, handelt es sich um eine Fehlerbedingung. In diesem Fall werden durch das ausgelöste Ereignis Aufrufe anderer Delegaten abgebrochen.  Beachten Sie, dass der Compiler eine Quellschnittstelle des Ereignisses automatisch als [source](../windows/source-cpp.md) im generierten IDL markiert.  
  
 Das [\_\_interface](../cpp/interface.md)\-Schlüsselwort ist immer nach `__event` für eine COM\-Ereignisquelle erforderlich.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Beispielcode erhalten Sie unter [Event Handling in COM](../cpp/event-handling-in-com.md).  
  
## Verwaltete Ereignisse  
 Weitere Informationen über die Codierung von Ereignissen in der neuen Syntax finden Sie unter [event](../windows/event-cpp-component-extensions.md).  
  
 Verwaltete Ereignisse sind Datenmember oder Methoden.  Bei Verwendung mit einem Ereignis muss der Rückgabetyp eines Delegaten mit der [Common Language Specification](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel sein.  Der Rückgabetyp des Ereignishandlers muss dem Rückgabetyp des Delegaten entsprechen.  Weitere Informationen über Delegate finden Sie unter [\_\_delegate](../misc/delegate.md).  Wenn ein verwaltetes Ereignis ein Datenmember ist, muss ihr Typ ein Zeiger auf einen Delegaten sein.  
  
 In .NET Framework können Sie einen Datenmember behandeln, als wäre er eine Methode selbst \(d. h. die `Invoke`\-Methode des entsprechenden Delegaten\).  Sie müssen den Delegattyp vordefinieren, um einen verwalteten Ereignisdatenmember zu deklarieren.  Im Gegensatz dazu definiert eine verwaltete Ereignismethode implizit den entsprechenden verwalteten Delegaten, sofern er noch nicht definiert ist.  Sie können beispielsweise einen Ereigniswert wie `OnClick` als Ereignis wie folgt angeben:  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 Wenn Sie implizit ein verwaltetes Ereignis deklarieren, können Sie add\- und remove\-Accessoren angeben, die aufgerufen werden, wenn Ereignishandler hinzugefügt oder entfernt werden.  Sie können auch die Methode definieren, die das Ereignis außerhalb der Klasse aufruft \(auslöst\).  
  
## Beispiel: Systemeigene Ereignisse  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## Beispiel: COM\-Ereignisse  
  
```  
// EventHandling_COM_Event.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT MyEvent();  
};  
 [ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]  
class CSource : public IEventSource {  
public:  
   __event __interface IEventSource;  
   HRESULT FireEvent() {  
      __raise MyEvent();  
      return S_OK;  
   }  
};  
```  
  
## Beispiel: Verwaltete Ereignisse  
  
```  
// EventHandling_Managed_Event.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[event_source(managed)]  
public __gc class CPSource {  
  
public:  
   __event void MyEvent(Int16 nValue);  
};  
```  
  
 Wenn ein Attribut auf ein Ereignis angewendet wird, können Sie angeben, dass das Attribut entweder auf die generierten Methoden oder auf die Invoke\-Methode des generierten Delegaten angewendet wird.  Der Standard \(`event:`\) muss das Attribut auf das Ereignis anwenden.  
  
```  
// EventHandling_Managed_Event_2.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[attribute(All, AllowMultiple=true)]  
public __gc class Attr {};  
  
public __delegate void D();  
  
public __gc class X {  
public:  
   [method:Attr] __event D* E;  
   [returnvalue:Attr] __event void noE();  
};  
```  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)