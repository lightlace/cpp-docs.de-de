---
title: "Mathematischer Fehler M6205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6205"
ms.assetid: fd28e7c9-a463-4a9c-a863-cc9e75315550
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Mathematischer Fehler M6205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': \_TLOSS error  
  
 Es trat ein Genauigkeitsverlust auf.  
  
 Dieser Fehler tritt beispielsweise dann auf, wenn als Operand der Funktionen **sin**, **cos** oder **tan** eine sehr große Zahl eingesetzt wird, da dieser auf eine Zahl zwischen 0 und 2\*pi umgerechnet werden muss.