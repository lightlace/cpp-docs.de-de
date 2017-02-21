---
title: "Compilerfehler C2008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2008"
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeichen': unerwartetes Zeichen in Makrodefinition  
  
 Das Zeichen folgt unmittelbar auf den Makronamen.  Um den Fehler zu beheben, fügen Sie ein Leerzeichen hinter dem Makronamen ein.  
  
 Im folgenden Beispiel wird C2008 generiert:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Mögliche Lösung:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```