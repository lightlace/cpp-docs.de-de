---
title: __unhook | Microsoft Docs
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
ms.openlocfilehash: b95ff49c9b1f088ac38ffb0791f18f249b211e72
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="unhook"></a>__unhook
Trennt eine Handlermethode von einem Ereignis.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
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
  
-   Systemeigene C++-Ereignisse: *SourceClass* ist die Ereignisquellenklasse und *EventMethod* ist das Ereignis.  
  
-   COM-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses und *EventMethod* ist einer der Methoden.  
  
-   Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse und *EventMethod* ist das Ereignis.  
  
 `interface`  
 Der Schnittstellenname aus entfernt wird `receiver`, nur für COM-Ereignisempfänger, in dem die *Layout_dependent* Parameter von der [Event_receiver](../windows/event-receiver.md) -Attribut ist **"true"**.  
  
 *Datenquelle*  
 Ein Zeiger auf eine Instanz der Ereignisquelle. Abhängig vom Code `type` im angegebenen **Event_receiver**, *Quelle* kann eines der folgenden sein:  
  
-   Ein systemeigener Ereignisquellen-Objektzeiger.  
  
-   Ein **IUnknown**-basierte Zeiger (COM-Quelle).  
  
-   Ein Zeiger des verwalteten Objekts (für verwaltete Ereignisse).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Ein Zeiger auf die Ereignishandlermethode, die von einem Ereignis gelöst werden soll. Der Handler wird als eine Methode einer Klasse oder als Verweis auf selbige angegeben; wenn Sie den Klassennamen nicht angeben, geht `__unhook` davon aus, dass die Klasse diejenige ist, in welcher er aufgerufen wird.  
  
-   Systemeigene C++-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
-   COM-Ereignisse: *ReceiverClass* ist die ereignisempfängerschnittstelle und `HandlerMethod` ist einer der Handler.  
  
-   Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
 `receiver`(optional)  
 Ein Zeiger auf eine Instanz der Ereignisempfängerklasse. Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur verwendet, in der `__unhook` aufgerufen wird.  
  
## <a name="usage"></a>Verwendung  
 Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die systeminterne Funktion `__unhook` in einem Ereignisempfänger, um eine Handlermethode von einer Ereignismethode zu lösen bzw. die Zuordnung aufzuheben.  
  
 Es gibt drei Formen von `__unhook`. Sie können in den meisten Fällen das erste (four-argument) Formular verwenden. Sie können das zweite (two-argument) Formular von `__unhook` nur für einen COM-Ereignisempfänger verwenden. Dadurch wird die gesamte Ereignisschnittstelle gelöst. Sie können das dritte (one-argument) Formular verwenden, um bei allen Delegaten aus der angegebenen Quelle die Bindung zu lösen.  
  
 Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist (verwaltete Ereignisse lösen eine Ausnahme aus).  
  
 Wenn Sie `__unhook` für ein Ereignis und einen Ereignishandler aufrufen, die nicht bereits verknüpft sind, hat dies keine Auswirkungen.  
  
 Zur Kompilierzeit überprüft der Compiler, dass das Ereignis vorhanden ist und führt eine Parametertypüberprüfung mit dem angegebenen Handler aus.  
  
 Mit Ausnahme von COM-Ereignissen können `__hook` und `__unhook` außerhalb des Ereignisempfängers aufgerufen werden.  
  
 Eine Alternative zur Verwendung von `__unhook` ist die Verwendung des Operators "-=".  
  
 Informationen zu codieren verwaltete Ereignisse in der neuen Syntax finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) Beispiele.  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)