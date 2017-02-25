---
title: "Compilerfehler C2854 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2854"
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler in \#pragma hdrstop  
  
 Durch `#pragma hdrstop` wird ein ungültiger Dateiname angegeben.  Dem Pragma kann ein optionaler Dateiname in runden Klammern und Anführungszeichen folgen:  
  
 Im folgenden Beispiel wird C2854 generiert:  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```