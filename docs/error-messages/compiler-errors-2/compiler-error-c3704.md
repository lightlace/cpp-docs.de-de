---
title: "Compilerfehler C3704"
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
  - "C3704"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3704"
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3704
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Eine vararg\-Methode kann keine Ereignisse auslösen  
  
 Sie haben versucht, [\_\_event](../../cpp/event.md) für eine **vararg**\-Methode zu verwenden.  Um diesen Fehler zu beheben, ersetzen Sie den Aufruf `fireEvent(int i, ...)`, wie im folgenden Codebeispiel dargestellt, durch den Aufruf `fireEvent(int i)`.  
  
 Im folgenden Beispiel wird C3704 generiert:  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```