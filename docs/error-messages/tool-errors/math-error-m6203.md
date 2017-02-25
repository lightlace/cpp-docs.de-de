---
title: "Mathematischer Fehler M6203 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6203"
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Mathematischer Fehler M6203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : \_OVERFLOW error  
  
 Das Ergebnis der angegebenen Funktion kann wegen seiner Größe nicht repräsentiert werden.  
  
 Dieser Fehler führt zum Aufruf der `_matherr`\-Funktion mit dem Namen der Funktion, ihrer Argumente und des Fehlertyps.  Die `_matherr`\-Funktion kann neu geschrieben werden, um die Behandlung bestimmter Laufzeitfehler der Gleitkommaarithmetik anzupassen.