---
title: "Compilerfehler C2460"
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
  - "C2460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2460"
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner1': Verwendet gerade definierten 'Bezeichner2'  
  
 Eine Klasse oder Struktur \(`identifier2`\) wurde als Member derselben Klasse bzw. Struktur \(`identifier1`\) deklariert.  Rekursive Definitionen von Klassen und Strukturen sind nicht zulässig.  
  
 Im folgenden Beispiel wird C2460 generiert:  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 Verwenden Sie stattdessen einen Zeigerverweis in der Klasse.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```