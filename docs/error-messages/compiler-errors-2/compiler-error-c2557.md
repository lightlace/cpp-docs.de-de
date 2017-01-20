---
title: "Compilerfehler C2557"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2557"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2557"
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2557
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Private und geschützte Member können nicht ohne Konstruktor initialisiert werden.  
  
 Nur Member und Freunde können einem privaten oder geschützten Member einen Wert zuweisen. Nicht öffentliche Member sollten im Klassenkonstruktor initialisiert werden.