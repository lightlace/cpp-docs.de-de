---
title: "Linkertoolfehler LNK1140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1140"
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zu viele Module für die Programmdatenbank; Binden mit \/PDB:NONE erforderlich  
  
 Das Projekt enthält mehr als 4096 Module.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Verknüpfen Sie erneut unter Verwendung von [\/PDB:NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Kompilieren Sie einige Module ohne Debuginformationen.  
  
3.  Verringern Sie die Anzahl der Module.