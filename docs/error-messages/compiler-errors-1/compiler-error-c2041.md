---
title: "Compilerfehler C2041"
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
  - "C2041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2041"
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Ziffer 'Zeichen' für Basis 'Zahl'  
  
 Das angegebene Zeichen ist keine zulässige Basisziffer \(z. B. oktal oder hexadezimal\).  
  
 Im folgenden Beispiel wird C2041 generiert:  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 Mögliche Lösung:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```