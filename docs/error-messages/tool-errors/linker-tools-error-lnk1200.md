---
title: "Linkertoolfehler LNK1200 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolfehler LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Lesen der Programmdatenbank 'Dateiname'  
  
 Die Programmdatenbank \(PDB\) konnte nicht gelesen werden.  
  
 Dieser Fehler kann durch eine beschädigte Datei verursacht werden.  
  
 Wenn `filename` die PDB für eine Objektdatei ist, kompilieren Sie die Objektdatei mithilfe von [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) neu.  
  
 Wenn `filename` die PDB für die Hauptausgabedatei ist und dieser Fehler beim inkrementellen Verknüpfen aufgetreten ist, löschen Sie die PDB und führen eine erneute Verknüpfung durch.