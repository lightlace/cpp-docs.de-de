---
title: Compilerfehler C3701 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3701
dev_langs: C++
helpviewer_keywords: C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 723deeb35dc16aff4535c1961261ba705f8ee364
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3701"></a>Compilerfehler C3701
'Funktion': Event_source hat keine Ereignisse  
  
 Sie haben versucht, [Event_source](../../windows/event-source.md) auf eine Klasse, die keine Ereignismethoden enthält. Um diesen Fehler zu beheben, fügen Sie ein oder mehrere Ereignisse auf die Klasse.  
  
 Im folgende Beispiel wird C3701 generiert:  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```