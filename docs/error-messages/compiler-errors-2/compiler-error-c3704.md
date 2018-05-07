---
title: Compilerfehler C3704 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3b1f255852def5e04d75751b0a902fb7072545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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