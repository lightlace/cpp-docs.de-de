---
title: "__hook"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__hook_cpp"
  - "__hook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__hook-Schlüsselwort [C++]"
  - "Ereignishandler, Verbinden mit Ereignissen"
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# __hook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet eine Handlermethode einem Ereignis zu.  
  
## Syntax  
  
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
  
#### Parameter  
 **&** *SourceClass* `::` *EventMethod*  
 Ein Zeiger auf die Ereignismethode, an die Sie die Ereignishandlermethode binden:  
  
-   Systemeigene C\+\+\-Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
-   COM\-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses, und *EventMethod* ist eine ihrer Methoden.  
  
-   Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
 `interface`  
 Der Name der Schnittstelle, an die `receiver` gebunden wird. Gilt nur bei COM\-Ereignisempfängern, bei welchen der *layout\_dependent*\-Parameter des [event\_receiver](../windows/event-receiver.md)\-Attributs **true** ist.  
  
 *source*  
 Ein Zeiger auf eine Instanz der Ereignisquelle.  Abhängig vom Code `type`, der in **event\_receiver** angegeben wird, kann *source* einer der folgenden Werte sein:  
  
-   Ein systemeigener Ereignisquellen\-Objektzeiger.  
  
-   Ein **IUnknown**\-basierter Zeiger \(COM\-Quelle\).  
  
-   Ein Zeiger des verwalteten Objekts \(für verwaltete Ereignisse\).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Ein Zeiger, der an die Ereignishandlermethode gebunden werden soll.  Der Handler wird als eine Methode einer Klasse oder als Verweis auf selbige angegeben; wenn Sie den Klassennamen nicht angeben, geht `__hook` davon aus, dass die Klasse diejenige ist, in welcher er aufgerufen wird.  
  
-   Systemeigene C\+\+\-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse, und `HandlerMethod` ist der Handler.  
  
-   COM\-Ereignisse: *ReceiverClass* ist die Ereignisempfängerschnittstelle, und `HandlerMethod` ist einer der Handler.  
  
-   Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse, und `HandlerMethod` ist der Handler.  
  
 `receiver`\(optional\)  
 Ein Zeiger auf eine Instanz der Ereignisempfängerklasse.  Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur verwendet, in der `__hook` aufgerufen wird.  
  
## Verwendung  
 Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.  
  
## Hinweise  
 Verwenden Sie die systeminterne Funktion `__hook` in einem Ereignisempfänger, um eine Handlermethode einer Ereignismethode zuzuordnen oder an sie zu binden.  Der angegebene Handler wird aufgerufen, wenn die Quelle das angegebene Ereignis auslöst.  Sie können mehrere Handler an ein einzelnes Ereignis binden oder mehrere Ereignisse an einen einzigen Handler.  
  
 Es gibt zwei Formen von `__hook`.  Sie können die erste Form \(vier Argumente\) in den meisten Fällen verwenden, insbesondere für COM\-Ereignisempfänger, in denen der *layout\_dependent*\-Parameter des [event\_receiver](../windows/event-receiver.md)\-Attributs **false** ist.  
  
 In diesen Fällen müssen Sie nicht alle Methoden an eine Schnittstelle binden, bevor nicht bei einer der Methoden ein Ereignis ausgelöst wird; nur die Methode für die Ereignisbehandlung muss eingebunden werden.  Sie können die zweite Form \(zwei Argumente\) von `__hook` nur für einen COM\-Ereignisempfänger verwenden, in dem *layout\_dependent***\=true** ist.  
  
 `__hook` gibt einen Long\-Wert zurück.  Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist \(verwaltete Ereignisse lösen eine Ausnahme aus\).  
  
 Der Compiler überprüft, ob ein Ereignis vorhanden ist und ob die Ereignissignatur der Delegatsignatur entspricht.  
  
 Mit Ausnahme von COM\-Ereignissen können `__hook` und `__unhook` außerhalb des Ereignisempfängers aufgerufen werden.  
  
 Eine Alternative zur Verwendung von `__hook` ist die Verwendung des Operators "\+\=".  
  
 Weitere Informationen über die Codierung von verwalteten Ereignissen in der neuen Syntax finden Sie unter [event](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Beispiel  
 Beispiele finden Sie unter [Ereignisbehandlung in systemeigenem C\+\+](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)