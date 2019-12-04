---
title: Compilerfehler C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 47320c79dbbfc2152c126c80d1eb8c061f3ceb3a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757916"
---
# <a name="compiler-error-c3709"></a>Compilerfehler C3709

"Function": Ungültige Syntax zum Angeben eines Ereignisses in __hook/\__unhook

Wenn Sie eine Ereignis Quelle mit [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md)angeben, muss der erste Parameter eine gültige Ereignismethode sein, und der zweite Parameter muss ein gültiges Ereignis Quell Objekt (keine Methode) sein.

Im folgenden Beispiel wird C3709 generiert:

```cpp
// C3709.cpp
// compile with: /LD
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
   }

   void HookEvents(CEventSrc* pSrc)
   {
      __hook(bad, pSrc, CEventRec::handler1);   // C3709
      // Try the following line instead:
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc)
   {
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};
```
