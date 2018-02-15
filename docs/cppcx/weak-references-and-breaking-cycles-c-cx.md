---
title: Schwache Verweise und unterbrochene Zyklen (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a98dc4dd43b40f378a91713770c4c5500c790d0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Schwache Verweise und unterbrochene Zyklen (C++/CX)
In jedem Typsystem, dem Verweiszählung zugrunde liegt, können Verweise auf Typen *zyklisch*sein, d. h. ein Objekt kann auf ein zweites Objekt verweisen, dieses auf ein drittes Objekt, usw., bis das letzte Objekt zurück zum ersten Objekt verweist. In einem Verweiszyklus können Objekte nicht ordnungsgemäß gelöscht werden, wenn der Verweiszähler eines Objekts null wird. Zur einfacheren Behebung dieses Problem C + c++ / CX bietet die [Platform:: WeakReference-Klasse](../cppcx/platform-weakreference-class.md) Klasse. Ein `WeakReference` -Objekt unterstützt die [Resolve](../cppcx/platform-weakreference-class.md#resolve) -Methode, die NULL zurückgibt, wenn das Objekt nicht mehr vorhanden ist, oder eine [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) -Ausnahme auslöst, wenn das Objekt nicht vom Typ `T`ist.  
  
 `WeakReference` muss beispielsweise verwendet werden, wenn der `this` Zeiger in einem Lambda-Ausdruck erfasst wird, der einen Ereignishandler definieren soll. Es wird empfohlen, benannte Methoden zu verwenden, wenn Sie Ereignishandler definieren, aber wenn Sie ein Lambda für einen Ereignishandler verwenden möchten. Wenn Sie einen Verweiszählungszyklus in einer anderer Situation unterbrechen müssen, verwenden Sie `WeakReference`. Im Folgenden ein Beispiel:  
  
```  
  
using namespace Platform::Details;  
using namespace Windows::UI::Xaml;  
using namespace Windows::UI::Xaml::Input;  
using namespace Windows::UI::Xaml::Controls;  
  
Class1::Class1()  
{  
    // Class1 has a reference to m_Page  
    m_Page = ref new Page();  
  
    // m_Page will have a reference to this Class1  
    // so create a weak reference to this  
    WeakReference wr(this);  
    m_Page->DoubleTapped += ref new DoubleTappedEventHandler(   
        [wr](Object^ sender, DoubleTappedRoutedEventArgs^ args)  
    {  
       // Use the weak reference to get the object  
       Class1^ c = wr.Resolve<Class1>();  
       if (c != nullptr)  
       {  
           c->m_eventFired = true;  
       }  
       else  
       {  
           // Inform the event that this handler should be removed  
           // from the subscriber list  
           throw ref new DisconnectedException();  
       }  
    });   
}  
  
}  
```  
  
 Wenn ein Ereignishandler eine `DisconnectedException`auslöst, wird der Handler aus der Abonnentenliste entfernt.  
  
## <a name="see-also"></a>Siehe auch  


