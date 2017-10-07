---
title: __hook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __hook_cpp
dev_langs:
- C++
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 21bb75853d8664ad46bc48fc907946ae5a147f9a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="hook"></a>__hook
Ordnet eine Handlermethode einem Ereignis zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 **&***SourceClass* `::` *EventMethod*  
 Ein Zeiger auf die Ereignismethode, an die Sie die Ereignishandlermethode binden:  
  
-   Systemeigene C++-Ereignisse: *SourceClass* ist die Ereignisquellenklasse und *EventMethod* ist das Ereignis.  
  
-   COM-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses und *EventMethod* ist einer der Methoden.  
  
-   Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse und *EventMethod* ist das Ereignis.  
  
 `interface`  
 Den Namen der Schnittstelle verknüpft wird, um `receiver`, nur für COM-Ereignisempfänger, in dem die *Layout_dependent* Parameter von der [Event_receiver](../windows/event-receiver.md) -Attribut ist **"true"**.  
  
 *Datenquelle*  
 Ein Zeiger auf eine Instanz der Ereignisquelle. Abhängig vom Code `type` im angegebenen **Event_receiver**, *Quelle* kann eines der folgenden sein:  
  
-   Ein systemeigener Ereignisquellen-Objektzeiger.  
  
-   Ein **IUnknown**-basierte Zeiger (COM-Quelle).  
  
-   Ein Zeiger des verwalteten Objekts (für verwaltete Ereignisse).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Ein Zeiger, der an die Ereignishandlermethode gebunden werden soll. Der Handler wird als eine Methode einer Klasse oder als Verweis auf selbige angegeben; wenn Sie den Klassennamen nicht angeben, geht `__hook` davon aus, dass die Klasse diejenige ist, in welcher er aufgerufen wird.  
  
-   Systemeigene C++-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
-   COM-Ereignisse: *ReceiverClass* ist die ereignisempfängerschnittstelle und `HandlerMethod` ist einer der Handler.  
  
-   Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.  
  
 `receiver`(optional)  
 Ein Zeiger auf eine Instanz der Ereignisempfängerklasse. Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur verwendet, in der `__hook` aufgerufen wird.  
  
## <a name="usage"></a>Verwendung  
 Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die systeminterne Funktion `__hook` in einem Ereignisempfänger, um eine Handlermethode einer Ereignismethode zuzuordnen oder an sie zu binden. Der angegebene Handler wird aufgerufen, wenn die Quelle das angegebene Ereignis auslöst. Sie können mehrere Handler an ein einzelnes Ereignis binden oder mehrere Ereignisse an einen einzigen Handler.  
  
 Es gibt zwei Formen von `__hook`. Können Sie die erste (Four-Argument) Formular in den meisten Fällen insbesondere für COM-Ereignisempfänger, in dem die *Layout_dependent* Parameter von der [Event_receiver](../windows/event-receiver.md) -Attribut ist **"false" **.  
  
 In diesen Fällen müssen Sie nicht alle Methoden an eine Schnittstelle binden, bevor nicht bei einer der Methoden ein Ereignis ausgelöst wird; nur die Methode für die Ereignisbehandlung muss eingebunden werden. Sie können die zweite (Two-Argument) Formular von `__hook` nur für einen COM-Ereignisempfänger, in dem *Layout_dependent***= "true"**.  
  
 `__hook` gibt einen Long-Wert zurück. Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist (verwaltete Ereignisse lösen eine Ausnahme aus).  
  
 Der Compiler überprüft, ob ein Ereignis vorhanden ist und ob die Ereignissignatur der Delegatsignatur entspricht.  
  
 Mit Ausnahme von COM-Ereignissen können `__hook` und `__unhook` außerhalb des Ereignisempfängers aufgerufen werden.  
  
 Eine Alternative zur Verwendung von `__hook` ist die Verwendung des Operators "+=".  
  
 Informationen zu codieren verwaltete Ereignisse in der neuen Syntax finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) Beispiele.  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)
