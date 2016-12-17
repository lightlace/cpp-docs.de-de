---
title: "Ereignisbehandlung in COM"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM, Ereignisse"
  - "Deklarieren von Ereignissen"
  - "Deklarieren von Ereignissen, Ereignisbehandlung in COM"
  - "Deklarieren von Ereignissen, In COM"
  - "Ereignishandler"
  - "Ereignishandler, COM"
  - "Ereignisbehandlung"
  - "Ereignisbehandlung, Informationen über Ereignishandler"
  - "Ereignisbehandlung, COM"
  - "Ereignisempfänger, In der Ereignisbehandlung"
  - "Ereignisempfänger, Übereinstimmung von Name und Signatur"
  - "Ereignisquellen, In der Ereignisbehandlung"
  - "Einbinden von Ereignissen"
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Ereignisbehandlung in COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der COM\-Ereignisbehandlung richten Sie eine Ereignisquelle und einen Ereignisempfänger mithilfe der [event\_source](../windows/event-source.md)\- und [event\_receiver](../windows/event-receiver.md)\-Attribute oder durch die Angabe von `type`\=**com** ein.  Diese Attribute fügen den geeigneten Code für benutzerdefinierte Schnittstellen, Dispatchschnittstellen und duale Schnittstellen ein, damit die Klassen, auf die sie angewendet werden, Ereignisse über COM\-Verbindungspunkte auslösen und behandeln können.  
  
## Deklarieren von Ereignissen  
 In einer Ereignisquellklasse verwenden Sie das [\_\_event](../cpp/event.md)\-Schlüsselwort für eine Schnittstellendeklaration, um die Methoden dieser Schnittstelle als Ereignisse zu deklarieren.  Die Ereignisse der Schnittstelle werden ausgelöst, wenn Sie die Ereignisse als Schnittstellenmethoden aufrufen.  Methoden für Ereignisschnittstellen können null oder mehr Parameter haben \(die alle **in**\-Parameter sein sollen\).  Der Rückgabetyp kann "void" oder ein ganzzahliger Typ sein.  
  
## Definieren von Ereignishandlern  
 In einer Ereignisempfängerklasse definieren Sie Ereignishandler, die Methoden mit Signaturen sind \(Rückgabetypen, Argumente und Aufrufkonventionen\), die mit dem Ereignis übereinstimmen, das sie behandeln.  Für COM\-Ereignisse müssen Aufrufkonventionen nicht übereinstimmen. Ausführliche Informationen finden Sie unter [Layoutabhängige COM\-Ereignisse](#vcconeventhandlingincomanchorlayoutdependentcomevents).  
  
## Verknüpfen von Ereignishandlern mit Ereignissen  
 Sie können in einer Ereignisempfängerklasse auch die systeminterne Funktion [\_\_hook](../cpp/hook.md) benutzen, um Ereignisse zu Ereignishandlern zuzuordnen, und Sie können [\_\_unhook](../cpp/unhook.md) verwenden, um Ereignisse von den Ereignishandlern zu trennen.  Sie können mehrere Ereignisse mit einem Ereignishandler oder mehrere Ereignishandler mit einem Ereignis verknüpfen.  
  
> [!NOTE]
>  Normalerweise gibt es zwei Möglichkeiten, um es einem COM\-Ereignisempfänger zu ermöglichen, auf Schnittstellendefinitionen von Ereignisquellen zuzugreifen.  Die erste Möglichkeit besteht in einer gemeinsamen Headerdatei, wie unten gezeigt.  Die zweite Methode ist die Verwendung von [\#import](../preprocessor/hash-import-directive-cpp.md) mit dem `embedded_idl`\-Importqualifizierer, sodass die Typbibliothek der Ereignisquelle in die TLH\-Datei geschrieben wird, wobei der attributgenerierte Code beibehalten wird.  
  
## Auslösen von Ereignissen  
 Um ein Ereignis auszulösen, rufen Sie einfach eine Methode in der Schnittstelle auf, die mit dem `__event`\-Schlüsselwort in der Ereignisquellklasse deklariert wurde.  Wenn Handler an das Ereignis geknüpft wurden, werden die Handler aufgerufen.  
  
### COM\-Ereigniscode  
 Das folgende Beispiel zeigt, wie ein Ereignis in einer COM\-Klasse ausgelöst wird.  Informationen zum Kompilieren und Ausführen des Beispiels finden Sie in den Kommentaren im Code.  
  
```  
// evh_server.h  
#pragma once  
  
[ dual, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IEvents {  
   [id(1)] HRESULT MyEvent([in] int value);  
};  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT FireEvent();  
};  
  
class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;  
```  
  
 Anschließend der Server:  
  
```  
// evh_server.cpp  
// compile with: /LD  
// post-build command: Regsvr32.exe /s evh_server.dll  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include "evh_server.h"  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;   
  
   HRESULT FireEvent() {  
      __raise MyEvent(123);  
      return S_OK;  
   }  
};  
```  
  
 Und im Anschluss der Client:  
  
```  
// evh_client.cpp  
// compile with: /link /OPT:NOREF  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <stdio.h>  
#include "evh_server.h"  
  
[ module(name="EventReceiver") ];  
  
[ event_receiver(com) ]  
class CReceiver {  
public:  
   HRESULT MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   HRESULT MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   void HookEvent(IEventSource* pSource) {  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void UnhookEvent(IEventSource* pSource) {  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   // Create COM object  
   CoInitialize(NULL);  
   {  
      IEventSource* pSource = 0;  
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);  
      if (FAILED(hr)) {  
         return -1;  
      }  
  
      // Create receiver and fire event  
      CReceiver receiver;  
      receiver.HookEvent(pSource);  
      pSource->FireEvent();  
      receiver.UnhookEvent(pSource);  
   }  
   CoUninitialize();  
   return 0;  
}  
```  
  
### Ausgabe  
  
```  
MyHandler1 was called with value 123.  
MyHandler2 was called with value 123.  
```  
  
##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Layoutabhängige COM\-Ereignisse  
 Layoutabhängigkeit ist nur bei der COM\-Programmierung ein Problem.  Bei systemeigener und verwalteter Ereignisbehandlung müssen die Signaturen \(Rückgabetyp, Aufrufkonvention und Argumente\) der Handler ihren Ereignissen entsprechen, aber die Handlernamen müssen nicht mit ihren Ereignissen übereinstimmen.  
  
 Wenn Sie jedoch in einer COM\-Ereignisbehandlung den *layout\_dependent*\-Parameter des **event\_receiver** auf **true** festlegen, wird die Übereinstimmung von Name und Signatur erzwungen.  Dies bedeutet, dass die Namen und Signaturen der Handler im Ereignisempfänger exakt mit den Namen und Signaturen der Ereignisse übereinstimmen müssen, mit denen sie verknüpft sind.  
  
 Wenn *layout\_dependent* auf **false** festgelegt ist, können die Aufrufkonvention und die Speicherklasse \(virtuell, statisch usw.\) zwischen der auslösenden Ereignismethode und den Hookmethoden \(ihren Delegaten\) nach Bedarf kombiniert werden.  Es ist etwas effizienter, *layout\_dependent*\=**true** festzulegen.  
  
 Nehmen Sie z. B. an, `IEventSource` wird definiert, um über die folgenden Methoden zu verfügen:  
  
```  
[id(1)] HRESULT MyEvent1([in] int value);  
[id(2)] HRESULT MyEvent2([in] int value);  
```  
  
 Angenommen, die Ereignisquelle weist das folgende Format auf:  
  
```  
[coclass, event_source(com)]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;  
  
   HRESULT FireEvent() {  
      MyEvent1(123);  
      MyEvent2(123);  
      return S_OK;  
   }  
};  
```  
  
 Im Ereignisempfänger muss dann jeder Handler, der an eine Methode `IEventSource` gebunden ist, dem zugehörigen Namen und der zugehörigen Signatur entsprechen, wie hier gezeigt:  
  
```  
[coclass, event_receiver(com, true)]  
class CReceiver {  
public:  
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1  
      ...  
   }  
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2  
      ...  
   }  
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)  
      ...  
   }  
   void HookEvent(IEventSource* pSource) {  
      __hook(IFace, pSource);  // Hooks up all name-matched events   
                               // under layout_dependent = true  
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid  
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid  
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid  
   }  
};  
```  
  
## Siehe auch  
 [Ereignisbehandlung](../cpp/event-handling.md)