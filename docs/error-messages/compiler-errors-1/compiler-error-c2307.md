---
title: "Compilerfehler C2307"
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
  - "C2307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2307"
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragma 'Pragma' muss sich außerhalb der Funktion befinden, wenn inkrementelle Kompilierung aktiviert ist  
  
 Sie müssen das `data_seg`\-Pragma zwischen Funktionen platzieren, wenn Sie die inkrementelle Kompilierung verwenden.