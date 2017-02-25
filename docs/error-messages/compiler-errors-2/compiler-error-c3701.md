---
title: "Compilerfehler C3701 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3701"
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': event\_source hat keine Ereignisse  
  
 Sie haben versucht, [event\_source](../../windows/event-source.md) für eine Klasse zu verwenden, die keine Ereignismethoden enthält.  Um diesen Fehler zu korrigieren, fügen Sie der Klasse eines oder mehrere Ereignisse hinzu.  
  
 Im folgenden Beispiel wird C3701 generiert:  
  
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