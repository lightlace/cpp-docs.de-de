---
title: "Compilerfehler C2307 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2307"
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragma 'Pragma' muss sich außerhalb der Funktion befinden, wenn inkrementelle Kompilierung aktiviert ist  
  
 Sie müssen das `data_seg`\-Pragma zwischen Funktionen platzieren, wenn Sie die inkrementelle Kompilierung verwenden.