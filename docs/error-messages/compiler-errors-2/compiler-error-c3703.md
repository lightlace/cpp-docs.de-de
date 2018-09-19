---
title: Compilerfehler C3703 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3703
dev_langs:
- C++
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 730409d9db313294e23693b6d50d4b0aff0f8869
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043884"
---
# <a name="compiler-error-c3703"></a>Compilerfehler C3703

'Ereignishandler': eine Ereignishandlermethode muss dieselbe Speicherklasse wie die Quelle "Ereignis" haben

Ein [Ereignis](../../cpp/event-handling.md) verfügt über eine andere Speicherklasse als der Ereignishandler mit dem es verknüpft ist. Beispielsweise tritt dieser Fehler auf, wenn der Ereignishandler eine statischen Memberfunktion ist und das Ereignis nicht statisch ist. Um diesen Fehler zu beheben, geben Sie das Ereignis und den Ereignishandler dieselbe Speicherklasse.

Im folgende Beispiel wird die C3703 generiert:

```
// C3703.cpp
// C3703 expected
#include <stdio.h>

[event_source(type=native)]
class CEventSrc {
public:
   __event static void MyEvent();
};

[event_receiver(type=native)]
class CEventHandler {
public:
   // delete the following line to resolve
   void MyHandler() {}

   // try the following line instead
   // static void MyHandler() {}

   void HookIt(CEventSrc* pSource) {
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }

   void UnhookIt(CEventSrc* pSource) {
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }
};

int main() {
   CEventSrc src;
   CEventHandler hnd;

   hnd.HookIt(&src);
   __raise src.MyEvent();
   hnd.UnhookIt(&src);
}
```