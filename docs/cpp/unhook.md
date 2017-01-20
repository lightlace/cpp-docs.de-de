---
title: "__unhook"
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
  - "__unhook"
  - "__unhook_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unhook-Schlüsselwort [C++]"
  - "Ereignishandler, Aufhebung der Zuordnung von Ereignissen"
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# __unhook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Trennt eine Handlermethode von einem Ereignis.  
  
## Syntax  
  
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
  
#### Parameter  
 **&** *SourceClass* `::` *EventMethod*  
 Ein Zeiger auf die Ereignismethode, von der Sie die Ereignishandlermethode lösen:  
  
-   Systemeigene C\+\+\-Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
-   COM\-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses, und *EventMethod* ist eine ihrer Methoden.  
  
-   Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.  
  
 `interface`  
 Der Name der Schnittstelle, der von `receiver` gelöst wird. Gilt nur bei COM\-Ereignisempfängern, bei welchen der *layout\_dependent*\-Parameter des [event\_receiver](../windows/event-receiver.md)\-Attributs **true** ist.  
  
 *source*  
 Ein Zeiger auf eine Instanz der Ereignisquelle.  Abhängig vom Code `type`, der in **event\_receiver** angegeben wird, kann *source* einer der folgenden Werte sein:  
  
-   Ein systemeigener Ereignisquellen\-Objektzeiger.  
  
-   Ein **IUnknown**\-basierter Zeiger \(COM\-Quelle\).  
  
-   Ein Zeiger des verwalteten Objekts \(für verwaltete Ereignisse\).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Ein Zeiger auf die Ereignishandlermethode, die von einem Ereignis gelöst werden soll.  Der Handler wird als eine Methode einer Klasse oder als Verweis auf selbige angegeben; wenn Sie den Klassennamen nicht angeben, geht `__unhook` davon aus, dass die Klasse diejenige ist, in welcher er aufgerufen wird.  
  
-   Systemeigene C\+\+\-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse, und `HandlerMethod` ist der Handler.  
  
-   COM\-Ereignisse: *ReceiverClass* ist die Ereignisempfängerschnittstelle, und `HandlerMethod` ist einer der Handler.  
  
-   Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse, und `HandlerMethod` ist der Handler.  
  
 `receiver`\(optional\)  
 Ein Zeiger auf eine Instanz der Ereignisempfängerklasse.  Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur verwendet, in der `__unhook` aufgerufen wird.  
  
## Verwendung  
 Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.  
  
## Hinweise  
 Verwenden Sie die systeminterne Funktion `__unhook` in einem Ereignisempfänger, um eine Handlermethode von einer Ereignismethode zu lösen bzw. die Zuordnung aufzuheben.  
  
 Es gibt drei Formen von `__unhook`.  Sie können in den meisten Fällen das erste \(four\-argument\) Formular verwenden.  Sie können das zweite \(two\-argument\) Formular von `__unhook` nur für einen COM\-Ereignisempfänger verwenden. Dadurch wird die gesamte Ereignisschnittstelle gelöst.  Sie können das dritte \(one\-argument\) Formular verwenden, um bei allen Delegaten aus der angegebenen Quelle die Bindung zu lösen.  
  
 Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist \(verwaltete Ereignisse lösen eine Ausnahme aus\).  
  
 Wenn Sie `__unhook` für ein Ereignis und einen Ereignishandler aufrufen, die nicht bereits verknüpft sind, hat dies keine Auswirkungen.  
  
 Zur Kompilierzeit überprüft der Compiler, dass das Ereignis vorhanden ist und führt eine Parametertypüberprüfung mit dem angegebenen Handler aus.  
  
 Mit Ausnahme von COM\-Ereignissen können `__hook` und `__unhook` außerhalb des Ereignisempfängers aufgerufen werden.  
  
 Eine Alternative zur Verwendung von `__unhook` ist die Verwendung des Operators "\-\=".  
  
 Weitere Informationen über die Codierung von verwalteten Ereignissen in der neuen Syntax finden Sie unter [event](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Beispiel  
 Beispiele finden Sie unter [Ereignisbehandlung in systemeigenem C\+\+](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_raise](../cpp/raise.md)