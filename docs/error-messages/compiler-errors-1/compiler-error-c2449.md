---
title: "Compilerfehler C2449 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2449"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2449"
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2449
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"{" auf Dateiebene gefunden \- fehlt der Funktionskopf?  
  
 Im Dateigültigkeitsbereich wurde eine geöffnete geschweifte Klammer gefunden.  
  
 Dieser Fehler kann durch ein Semikolon zwischen einem Funktionskopf und der öffnenden geschweiften Klammer der Funktionsdefinition verursacht werden.  
  
 Im folgenden Beispiel wird C2499 generiert:  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```