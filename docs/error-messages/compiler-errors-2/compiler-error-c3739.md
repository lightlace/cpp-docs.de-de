---
title: Compilerfehler C3739 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3739
dev_langs: C++
helpviewer_keywords: C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3fa62f908f152e127669d1cd935fafdb75d413f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3739"></a>Compilerfehler C3739
'Klasse': die Syntax wird nur unterstützt, wenn der Parameter 'Layout_dependent' Event_receiver "true" ist  
  
 Sie haben versucht, eine gesamte Schnittstelle von Ereignissen zu verknüpfen, aber `layout_dependent` auf [Event_receiver](../../windows/event-receiver.md) Attribut ist nicht "true"; Sie müssen ein einzelnes Ereignis zu einem Zeitpunkt verknüpfen.  
  
 Im folgende Beispiel wird C3739 generiert:  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```