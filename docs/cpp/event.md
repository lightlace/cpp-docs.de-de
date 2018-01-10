---
title: __event | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs: C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4750d156ef4f0f817e1eecec1f4a0842fc229046
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="event"></a>__event
Deklariert ein Ereignis.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort `__event` kann auf eine Methodendeklaration, eine Schnittstellendeklaration oder eine Datenmemberdeklaration angewendet werden. Sie können jedoch das `__event`-Schlüsselwort nicht verwenden, um einen Member einer geschachtelten Klasse zu qualifizieren.  
  
 Je nachdem, ob Ereignisquelle und Empfänger systemeigenes C++, COM oder verwaltet (.NET Framework) sind, können Sie die folgenden Konstrukte als Ereignisse verwenden:  
  
|Systemeigenes C++|COM|Verwaltet (.NET Framework)|  
|------------------|---------|--------------------------------|  
|Methode|—|Methode|  
|—|interface|—|  
|—|—|Datenmember|  
  
 Verwendung [__hook](../cpp/hook.md) in einem Ereignisempfänger, um eine Handlermethode einer Ereignismethode zuzuordnen. Beachten Sie, dass nach dem Erstellen eines Ereignisses mit dem `__event`-Schlüsselwort alle Ereignishandler, die nacheinander in dieses Ereignis eingebunden werden, bei Aufruf des Ereignisses aufgerufen werden.  
  
 Eine `__event`-Methodendeklaration kann keine Definition enthalten. Eine Definition wird implizit generiert, sodass die Ereignismethode aufgerufen werden kann, als wenn sie eine normale Methode wäre.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="native-events"></a>Systemeigene Ereignisse  
 Systemeigene Ereignisse sind Methoden. Der Rückgabetyp ist normalerweise `HRESULT` oder `void`, kann jedoch ein beliebiger ganzzahliger Typ sein, einschließlich `enum`. Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet, ist für den Fall, dass ein Ereignishandler einen Wert ungleich 0 (null) zurückgibt, eine Fehlerbedingung definiert. In diesem Fall werden durch das ausgelöste Ereignis die anderen Delegaten aufgerufen.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) Beispielcode.  
  
## <a name="com-events"></a>COM-Ereignisse  
 COM-Ereignisse sind Schnittstellen. Die Parameter einer Methode in eine Quellschnittstelle des Ereignisses muss **in** Parameter (Dies wird jedoch nicht streng erzwungen), da ein **out** Parameter ist nicht sinnvoll, beim Multicasting. Eine Warnung der Stufe 1 wird ausgegeben, wenn Sie verwenden ein **out** Parameter.  
  
 Der Rückgabetyp ist normalerweise `HRESULT` oder `void`, kann jedoch ein beliebiger ganzzahliger Typ sein, einschließlich `enum`. Wenn ein Ereignis einen ganzzahligen Rückgabetyp verwendet und ein Ereignishandler einen Wert ungleich 0 (null) zurückgibt, handelt es sich um eine Fehlerbedingung. In diesem Fall werden durch das ausgelöste Ereignis Aufrufe anderer Delegaten abgebrochen. Beachten Sie, dass der Compiler eine Quellschnittstelle des Ereignisses als automatisch markiert ein [Quelle](../windows/source-cpp.md) in der generierten IDL-Datei.  
  
 Die [__interface](../cpp/interface.md) -Schlüsselwort ist immer erforderlich, nach dem `__event` für eine COM-Ereignisquelle.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) Beispielcode.  
  
## <a name="managed-events"></a>Verwaltete Ereignisse  
 Informationen zum Programmieren der Ereignisse in der neuen Syntax, finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).  
  
 Verwaltete Ereignisse sind Datenmember oder Methoden. Bei Verwendung mit einem Ereignis muss der Rückgabetyp eines Delegaten kompatibel mit werden die [Common Language Specification](/dotnet/standard/language-independence-and-language-independent-components). Der Rückgabetyp des Ereignishandlers muss dem Rückgabetyp des Delegaten entsprechen. Weitere Informationen zu Delegaten finden Sie unter [Delegaten und Ereignisse](../dotnet/delegates-and-events.md). Wenn ein verwaltetes Ereignis ein Datenmember ist, muss ihr Typ ein Zeiger auf einen Delegaten sein.  
  
 In .NET Framework können Sie einen Datenmember behandeln, als wäre er eine Methode selbst (d. h. die `Invoke`-Methode des entsprechenden Delegaten). Sie müssen den Delegattyp vordefinieren, um einen verwalteten Ereignisdatenmember zu deklarieren. Im Gegensatz dazu definiert eine verwaltete Ereignismethode implizit den entsprechenden verwalteten Delegaten, sofern er noch nicht definiert ist. Sie können beispielsweise einen Ereigniswert wie `OnClick` als Ereignis wie folgt angeben:  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 Wenn Sie implizit ein verwaltetes Ereignis deklarieren, können Sie add- und remove-Accessoren angeben, die aufgerufen werden, wenn Ereignishandler hinzugefügt oder entfernt werden. Sie können auch die Methode definieren, die das Ereignis außerhalb der Klasse aufruft (auslöst).  
  
## <a name="example-native-events"></a>Beispiel: Systemeigene Ereignisse  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>Beispiel: COM-Ereignisse  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)