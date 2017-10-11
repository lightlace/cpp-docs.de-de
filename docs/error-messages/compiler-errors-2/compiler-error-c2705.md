---
title: Compiler-Fehler C2705 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2705
dev_langs:
- C++
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 734287b37835d196ebfc131bc5f9392d0a712f3e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2705"></a>Compiler-Fehler C2705 generiert
'Bezeichnung': Unzulässiger Sprung in den Bereich "Ausnahmehandlerblock"  
  
 Die Ausführung springt zu einer Bezeichnung in einem `try` / `catch`, `__try` / `__except`, `__try` / `__finally` Block. Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Im folgende Beispiel wird C2705 generiert:  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```
