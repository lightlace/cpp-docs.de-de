---
title: "Schwerwiegender Fehler C1009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1009"
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: zu tiefe Schachtelung von Makros  
  
 Der Compiler hat versucht, zu viele Makros gleichzeitig zu erweitern.  Der Compiler unterstützt die Schachtelung von Makros bis zu einer maximalen Tiefe von 256 Ebenen.  Teilen Sie geschachtelte Makros in einfachere Makros auf.