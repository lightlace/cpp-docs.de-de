---
title: "Compilerfehler C2133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2133"
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Unbekannte Größe  
  
 Ein Array ohne Größenangabe wurde als Member einer Klasse, Struktur, Union oder Enumeration deklariert.  Memberarrays ohne Größenangabe sind mit der Option **\/Za** \(ANSI C\) nicht zulässig.  
  
 Im folgenden Beispiel wird C2133 generiert:  
  
```  
// C2133.cpp  
// compile with: /Za  
struct X {  
   int a[0];   // C2133 unsized array  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2133b.cpp  
// compile with: /c  
struct X {  
   int a[0];   // no /Za  
};  
```