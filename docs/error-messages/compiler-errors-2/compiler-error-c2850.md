---
title: "Compilerfehler C2850"
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
  - "C2850"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2850"
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2850
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstrukt': Nur für Dateibereich zulässig. Kann nicht in Konstrukt geschachtelt werden  
  
 Konstrukte, z. B. einige Pragmas, sind nur im globalen Gültigkeitsbereich zulässig.  
  
 Im folgenden Beispiel wird C2850 generiert:  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```