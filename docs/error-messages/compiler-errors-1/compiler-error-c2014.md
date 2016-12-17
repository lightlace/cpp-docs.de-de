---
title: "Compilerfehler C2014"
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
  - "C2014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2014"
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Präprozessordirektive muss mit dem ersten Zeichen in der Zeile beginnen  
  
 Das `#`\-Zeichen einer Präprozessordirektive muss das erste Zeichen in einer Zeile sein, die keinen Leerraum darstellt.  
  
 Im folgenden Beispiel wird C2014 generiert:  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 Mögliche Lösung:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```