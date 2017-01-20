---
title: "Compilerfehler C2856"
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
  - "C2856"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2856"
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2856
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma hdrstop kann sich nicht innerhalb eines \#if\-Blockes befinden  
  
 Das `hdrstop`\-Pragma darf sich nicht im Rumpf eines Blockes für die bedingte Kompilierung befinden.  
  
 Verschieben Sie die `#pragma hdrstop`\-Anweisung in einen Bereich, der nicht in einem `#if/#endif`\-Block enthalten ist.