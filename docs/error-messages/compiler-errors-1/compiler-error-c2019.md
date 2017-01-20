---
title: "Compilerfehler C2019"
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
  - "C2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2019"
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Präprozessordirektive erwartet, 'Zeichen' gefunden  
  
 Das Zeichen folgte auf ein `#`\-Zeichen, es handelt sich jedoch nicht um den ersten Buchstaben einer Präprozessordirektive.  
  
 Im folgenden Beispiel wird C2019 generiert:  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 Mögliche Lösung:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```