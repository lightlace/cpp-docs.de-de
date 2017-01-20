---
title: "Compilerfehler C3765"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3765"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3765"
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3765
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ereignis': Ein Ereignis kann nicht in einer Klasse\/Struktur 'Typ' definiert werden, die als ein event\_receiver gekennzeichnet ist  
  
 Wenn eine Klasse mit dem [event\_receiver](../../windows/event-receiver.md)\-Attribut gekennzeichnet ist, kann die Klasse keine [\_\_event](../../cpp/event.md)\-Deklaration enthalten.  
  
 Im folgenden Beispiel wird C3765 generiert:  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```