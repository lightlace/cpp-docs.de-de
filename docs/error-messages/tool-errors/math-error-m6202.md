---
title: "Mathematischer Fehler M6202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Mathematischer Fehler M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : \_SING error  
  
 Der angegebenen Funktion wurde ein Parameter übergeben, der einen Singularitätswert dieser Funktion bezeichnet.  Die Funktion ist für dieses Argument nicht definiert.  
  
 Dieser Fehler führt zum Aufruf der `_matherr`\-Funktion mit dem Namen der Funktion, ihrer Argumente und des Fehlertyps.  Die `_matherr`\-Funktion kann neu geschrieben werden, um die Behandlung bestimmter Laufzeitfehler der Gleitkommaarithmetik anzupassen.