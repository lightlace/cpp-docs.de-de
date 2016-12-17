---
title: "Compilerfehler C2673"
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
  - "C2673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2673"
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Globale Funktionen haben keinen 'this'\-Zeiger  
  
 Eine globale Funktion hat versucht, auf `this` zuzugreifen.  
  
 Im folgenden Beispiel wird C2673 generiert:  
  
```  
// C2673.cpp  
int main() {  
   this = 0;   // C2673  
}  
```