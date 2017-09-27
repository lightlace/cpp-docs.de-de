---
title: Ereignisbehandlung in systemeigenem C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling, Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ff5032966cb44ff8d14dd6e0a33fb5f8cf56ed7
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="event-handling-in-native-c"></a>Ereignisbehandlung in systemeigenem C++
In systemeigenen C++-Ereignisbehandlung richten Sie ein Ereignis und einen Ereignisempfänger mithilfe der [Event_source](../windows/event-source.md) und [Event_receiver](../windows/event-receiver.md) -Attribute angeben `type` = `native`. Diese Attribute ermöglichen es den Klassen, auf die sie angewendet werden, in einem systemeigenen Nicht-COM-Kontext Ereignisse auszulösen und Ereignisse zu behandeln.  
  
## <a name="declaring-events"></a>Deklarieren von Ereignissen  
 In einer Ereignisquellenklasse verwenden die [__event](../cpp/event.md) Schlüsselwort in einer Methodendeklaration, um die Methode als Ereignis zu deklarieren. Stellen Sie sicher, dass Sie die Methode deklarieren, aber nicht definieren. Andernfalls wird ein Compilerfehler verursacht, da der Compiler die Methode implizit definiert, wenn er in einem Ereignis ausgeführt wird. Systemeigene Ereignisse können Methoden mit null oder mehr Parametern sein. Der Rückgabetyp kann "void" oder ein ganzzahliger Typ sein.  
  
## <a name="defining-event-handlers"></a>Definieren von Ereignishandlern  
 In einer Ereignisempfängerklasse definieren Sie Ereignishandler, die Methoden mit Signaturen sind (Rückgabetypen, Argumente und Aufrufkonventionen), die mit dem Ereignis übereinstimmen, das sie behandeln.  
  
## <a name="hooking-event-handlers-to-events"></a>Verknüpfen von Ereignishandlern mit Ereignissen  
 In einer Ereignisempfängerklasse verwenden Sie auch die systeminterne Funktion [__hook](../cpp/hook.md) um Ereignisse Ereignishandlern zuzuordnen und [__unhook](../cpp/unhook.md) um Ereignisse von den Ereignishandlern zu trennen. Sie können mehrere Ereignisse mit einem Ereignishandler oder mehrere Ereignishandler mit einem Ereignis verknüpfen.  
  
## <a name="firing-events"></a>Auslösen von Ereignissen  
 Um ein Ereignis auszulösen, rufen Sie einfach die Methode auf, die als Ereignis in der Ereignisquellen-Klasse deklariert wurde. Wenn Handler an das Ereignis geknüpft wurden, werden die Handler aufgerufen.  
  
### <a name="native-c-event-code"></a>Systemeigener C++-Ereigniscode  
 Das folgende Beispiel zeigt, wie ein Ereignis im systemeigenen C++-Code ausgelöst wird. Informationen zum Kompilieren und Ausführen des Beispiels finden Sie in den Kommentaren im Code.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```  
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../cpp/event-handling.md)
