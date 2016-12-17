---
title: "Linkertoolfehler LNK1200"
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
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Lesen der Programmdatenbank 'Dateiname'  
  
 Die Programmdatenbank \(PDB\) konnte nicht gelesen werden.  
  
 Dieser Fehler kann durch eine beschädigte Datei verursacht werden.  
  
 Wenn `filename` die PDB für eine Objektdatei ist, kompilieren Sie die Objektdatei mithilfe von [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) neu.  
  
 Wenn `filename` die PDB für die Hauptausgabedatei ist und dieser Fehler beim inkrementellen Verknüpfen aufgetreten ist, löschen Sie die PDB und führen eine erneute Verknüpfung durch.