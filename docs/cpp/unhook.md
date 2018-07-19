---
title: __unhook | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 069d206418fd392e28114d977b3448f8306a3119
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943879"
---
# <a name="unhook"></a>__unhook
Trennt eine Handlermethode von einem Ereignis.  
  
## <a name="syntax"></a>Syntax  
  
```cpp 
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 **&** *SourceClass* `::` *EventMethod*  
 Ein Zeiger auf die Ereignismethode, von der Sie die Ereignishandlermethode lösen:  
  
-   Systemeigene C++-Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
-   COM-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses und *EventMethod* ist einer der Methoden.  
  
-   Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
 *interface*  
 Der Name der Schnittstelle von verknüpft wird *Empfänger*, nur für COM-Ereignisempfängern, bei denen die *Layout_dependent* Parameter der [Event_receiver](../windows/event-receiver.md) -Attribut ist **"true"**.  
  
 *source*  
 Ein Zeiger auf eine Instanz der Ereignisquelle. Je nach Code `type` im angegebenen **Event_receiver**, *Quelle* kann einen der folgenden sein:  
  
-   Ein systemeigener Ereignisquellen-Objektzeiger.  
  
-   Ein **IUnknown**-basierte Zeiger (COM-Quelle).  
  
-   Ein Zeiger des verwalteten Objekts (für verwaltete Ereignisse).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Ein Zeiger auf die Ereignishandlermethode, die von einem Ereignis gelöst werden soll. Der Handler, die als eine Methode einer Klasse oder einen Verweis auf die gleiche angegeben ist. Wenn Sie nicht den Klassennamen angeben **__unhook** geht davon aus der Klasse, in dem sie aufgerufen wird.  
  
-   Systemeigene C++-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
-   COM-Ereignisse: *ReceiverClass* ist die ereignisempfängerschnittstelle und `HandlerMethod` ist einer der Handler.  
  
-   Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
 *Empfänger*(optional)  
 Ein Zeiger auf eine Instanz der Ereignisempfängerklasse. Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur, in der **__unhook** aufgerufen wird.  
  
## <a name="usage"></a>Verwendung  
 Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.  
  
## <a name="remarks"></a>Hinweise  
 Die intrinsische Funktion **__unhook** in einem Ereignisempfänger, um die Zuordnung aufheben, oder "lösen" eine Handlermethode von einer Ereignismethode.  
  
 Es gibt drei Arten von **__unhook**. Sie können in den meisten Fällen das erste (four-argument) Formular verwenden. Sie können das zweite (Two-Argument) Formular von **__unhook** nur für einen COM-Ereignisempfänger verwenden; hebt dies die gesamte-Schnittstelle. Sie können das dritte (one-argument) Formular verwenden, um bei allen Delegaten aus der angegebenen Quelle die Bindung zu lösen.  
  
 Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist (verwaltete Ereignisse lösen eine Ausnahme aus).  
  
 Wenn Sie aufrufen **__unhook** für ein Ereignis und Ereignishandler, der nicht bereits verknüpft sind, hat er keine Auswirkungen.  
  
 Zur Kompilierzeit überprüft der Compiler, dass das Ereignis vorhanden ist und führt eine Parametertypüberprüfung mit dem angegebenen Handler aus.  
  
 Mit Ausnahme von COM-Ereignisse **__hook** und **__unhook** außerhalb des Ereignisempfängers aufgerufen werden kann.  
  
 Eine Alternative zur Verwendung **__unhook** den =-Operator verwendet wird.  
  
 Weitere Informationen über die Codierung von verwalteter Ereignissen in der neuen Syntax finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) für Beispiele.  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)