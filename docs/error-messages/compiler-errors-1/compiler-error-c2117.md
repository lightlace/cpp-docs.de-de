---
title: "Compilerfehler C2117"
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
  - "C2117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2117"
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Arraygrenzen\-Überlauf  
  
 Ein Array verfügt über zu viele Initialisierer:  
  
-   Größe und Anzahl von Arrayelementen und Initialisierer weichen voneinander ab.  
  
-   Eine Zeichenfolge bietet keinen Platz für den NULL\-Terminator.  
  
 Im folgenden Beispiel wird C2117 generiert:  
  
```  
// C2117.cpp  
int main() {  
   char abc[4] = "abcd";   // C2117  
   char def[4] = "abd";   // OK  
}  
```