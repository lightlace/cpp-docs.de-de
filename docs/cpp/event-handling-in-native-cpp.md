---
title: "Ereignisbehandlung in systemeigenem C++"
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
  - "Ereignisbehandlung, Visual C++"
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Ereignisbehandlung in systemeigenem C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der systemeigenen C\+\+\-Ereignisbehandlung installieren Sie eine Ereignisquelle und einen Ereignisempfänger mithilfe der Attribute [event\_source](../windows/event-source.md) und [event\_receiver](../windows/event-receiver.md) oder durch die Angabe von `type`\=`native`.  Diese Attribute ermöglichen es den Klassen, auf die sie angewendet werden, in einem systemeigenen Nicht\-COM\-Kontext Ereignisse auszulösen und Ereignisse zu behandeln.  
  
## Deklarieren von Ereignissen  
 In einer Ereignisquellenklasse verwenden Sie das [\_\_event](../cpp/event.md)\-Schlüsselwort in einer Methodendeklaration, um die Methode als Ereignis zu deklarieren.  Stellen Sie sicher, dass Sie die Methode deklarieren, aber nicht definieren. Andernfalls wird ein Compilerfehler verursacht, da der Compiler die Methode implizit definiert, wenn er in einem Ereignis ausgeführt wird.  Systemeigene Ereignisse können Methoden mit null oder mehr Parametern sein.  Der Rückgabetyp kann "void" oder ein ganzzahliger Typ sein.  
  
## Definieren von Ereignishandlern  
 In einer Ereignisempfängerklasse definieren Sie Ereignishandler, die Methoden mit Signaturen sind \(Rückgabetypen, Argumente und Aufrufkonventionen\), die mit dem Ereignis übereinstimmen, das sie behandeln.  
  
## Verknüpfen von Ereignishandlern mit Ereignissen  
 Sie können in einer Ereignisempfängerklasse auch die systeminterne Funktion [\_\_hook](../cpp/hook.md) benutzen, um Ereignisse zu Ereignishandlern zuzuordnen, und Sie können [\_\_unhook](../cpp/unhook.md) verwenden, um Ereignisse von den Ereignishandlern zu trennen.  Sie können mehrere Ereignisse mit einem Ereignishandler oder mehrere Ereignishandler mit einem Ereignis verknüpfen.  
  
## Auslösen von Ereignissen  
 Um ein Ereignis auszulösen, rufen Sie einfach die Methode auf, die als Ereignis in der Ereignisquellen\-Klasse deklariert wurde.  Wenn Handler an das Ereignis geknüpft wurden, werden die Handler aufgerufen.  
  
### Systemeigener C\+\+\-Ereigniscode  
 Das folgende Beispiel zeigt, wie ein Ereignis im systemeigenen C\+\+\-Code ausgelöst wird.  Informationen zum Kompilieren und Ausführen des Beispiels finden Sie in den Kommentaren im Code.  
  
## Beispiel  
  
### Code  
  
```  
// evh_native.cpp  
#include <stdio.h>  
  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
  
[event_receiver(native)]  
class CReceiver {  
public:  
   void MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
   }  
  
   void MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
   }  
  
   void hookEvent(CSource* pSource) {  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void unhookEvent(CSource* pSource) {  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   CSource source;  
   CReceiver receiver;  
  
   receiver.hookEvent(&source);  
   __raise source.MyEvent(123);  
   receiver.unhookEvent(&source);  
}  
```  
  
### Output  
  
```  
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## Siehe auch  
 [Ereignisbehandlung](../cpp/event-handling.md)