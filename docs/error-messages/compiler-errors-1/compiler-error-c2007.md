---
title: "Compilerfehler C2007"
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
  - "C2007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2007"
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#define\-Syntax  
  
 Hinter einer `#define`\-Direktive ist kein Bezeichner angegeben.  Verwenden Sie einen Bezeichner, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2007 generiert:  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 Mögliche Lösung:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```