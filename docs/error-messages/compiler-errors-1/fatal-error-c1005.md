---
title: "Schwerwiegender Fehler C1005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1005"
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeichenfolge zu lang für Puffer  
  
 Eine Zeichenfolge in einer Zwischendatei des Compilers hat zu einem Pufferüberlauf geführt.  
  
 Sie erhalten diesen Fehler möglicherweise, wenn der an die Compileroptionen [\/Fd](../../build/reference/fd-program-database-file-name.md) oder [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) übergebene Parameter größer als 256 Bytes ist.