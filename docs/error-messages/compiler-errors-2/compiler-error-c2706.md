---
title: "Compilerfehler C2706"
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
  - "C2706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2706"
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

illegal \_\_except ohne matching \_\_try \(Es fehlt "}" in \_\_try block?\)  
  
 Der Compiler konnte keine schließende Klammer für einen `__try`\-Block finden.  
  
 Im folgenden Beispiel wird C2706 generiert:  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```