---
title: "Mathematischer Fehler M6202"
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
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Mathematischer Fehler M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : \_SING error  
  
 Der angegebenen Funktion wurde ein Parameter übergeben, der einen Singularitätswert dieser Funktion bezeichnet.  Die Funktion ist für dieses Argument nicht definiert.  
  
 Dieser Fehler führt zum Aufruf der `_matherr`\-Funktion mit dem Namen der Funktion, ihrer Argumente und des Fehlertyps.  Die `_matherr`\-Funktion kann neu geschrieben werden, um die Behandlung bestimmter Laufzeitfehler der Gleitkommaarithmetik anzupassen.