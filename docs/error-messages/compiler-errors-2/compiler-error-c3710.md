---
title: Compilerfehler C3710
ms.date: 11/04/2016
f1_keywords:
- C3710
helpviewer_keywords:
- C3710
ms.assetid: 18bec009-5b6f-464a-a21e-5d58a6936504
ms.openlocfilehash: 3c060d5b01c0d918071681996e76258eba0ce943
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753418"
---
# <a name="compiler-error-c3710"></a>Compilerfehler C3710

"Function": Ungültige Syntax zum Angeben eines Ereignis Handlers in __hook/\__unhook

Wenn Sie einen Ereignishandler mit [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md)angeben, muss der Handler eine gültige Methode sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3710 generiert.

```cpp
// C3710.cpp
// compile with: /link /opt:noref
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>
#include <stdio.h>

[event_source(native)]
class CEventSrc
{
public:
    __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
    void handler1()
    {
        printf_s("Executing handler1().\n");
    }

    void HookEvents(CEventSrc* pSrc)
    {
        __hook(&CEventSrc::event1, pSrc, 0);   // C3710
        // try the following line instead
        // __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);
    }

    void UnhookEvents(CEventSrc* pSrc)
    {
        __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);
    }
};

int main()
{
    CEventSrc eventSrc;
    CEventRec eventRec;
    eventRec.HookEvents(&eventSrc);
    eventSrc.event1();
    eventRec.UnhookEvents(&eventSrc);
}
```
