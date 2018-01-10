---
title: Compilerfehler C3704 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3704
dev_langs: C++
helpviewer_keywords: C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 720af3b0ae1fa0727041e03e1573fbba4dccfae5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3704"></a>Compilerfehler C3704
'Funktion': eine Vararg-Methode kann keine Ereignisse auslösen  
  
 Sie haben versucht, [__event](../../cpp/event.md) für eine Vararg-Methode. Um diesen Fehler zu beheben, ersetzen die `fireEvent(int i, ...)` rufen Sie mit der `fireEvent(int i)` aufrufen, wie im folgenden Codebeispiel gezeigt.  
  
 Im folgende Beispiel wird C3704 generiert:  
  
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