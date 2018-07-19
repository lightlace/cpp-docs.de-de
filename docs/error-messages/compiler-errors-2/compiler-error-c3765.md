---
title: Compilerfehler C3765 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb8370a5c9c25fee211636214a82f22c05ccb311
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274767"
---
# <a name="compiler-error-c3765"></a>Compilerfehler C3765
'Ereignis': Definieren Sie ein Ereignis kann nicht in einer Klasse/Struktur 'Typ' als ein Event_receiver gekennzeichnet  
  
 Wenn eine Klasse mit gekennzeichnet ist die [Event_receiver](../../windows/event-receiver.md) -Attribut die Klasse kann nicht enthalten, eine [__event](../../cpp/event.md) Deklaration.  
  
 Im folgende Beispiel wird C3765 generiert:  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```