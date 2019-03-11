---
title: Schwache Verweise und unterbrochene Zyklen (C++/CX)
ms.date: 01/22/2017
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
ms.openlocfilehash: 252c9c1d2af0bc6911beca094d97f46e681ba2f6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747072"
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Schwache Verweise und unterbrochene Zyklen (C++/CX)

In jedem Typsystem, dem Verweiszählung zugrunde liegt, können Verweise auf Typen *zyklisch*sein, d. h. ein Objekt kann auf ein zweites Objekt verweisen, dieses auf ein drittes Objekt, usw., bis das letzte Objekt zurück zum ersten Objekt verweist. In einem Verweiszyklus können Objekte nicht ordnungsgemäß gelöscht werden, wenn der Verweiszähler eines Objekts null wird. Können Sie die Lösung dieses Problems C++ / CX stellt der [Platform:: WeakReference-Klasse](../cppcx/platform-weakreference-class.md) Klasse. Ein `WeakReference` -Objekt unterstützt die [Resolve](../cppcx/platform-weakreference-class.md#resolve) -Methode, die NULL zurückgibt, wenn das Objekt nicht mehr vorhanden ist, oder eine [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) -Ausnahme auslöst, wenn das Objekt nicht vom Typ `T`ist.

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
