---
title: "Compilerfehler C2705 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2705"
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Marke': Unzulässiger Sprung in einen 'Ausnahmehandlerblock'\-Gültigkeitsbereich  
  
 Die Ausführung springt zu einer Marke innerhalb eines der Blöcke `try`\/`catch`, `__try`\/`__except`, `__try`\/`__finally`.  **Weitere Informationen finden Sie unter** [Ausnahmebehandlung](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Im folgenden Beispiel wird C2705 generiert:  
  
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