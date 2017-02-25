---
title: "Compilerfehler C2286 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2286"
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeiger auf Member von 'Bezeichner' bereits auf Vererbung festgelegt \- erneute Deklaration wird ignoriert  
  
 Für die Klasse sind zwei Darstellungen von Memberzeigern vorhanden.  
  
 Weitere Informationen finden Sie unter [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2286 generiert:  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```