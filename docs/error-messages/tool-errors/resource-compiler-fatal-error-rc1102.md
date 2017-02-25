---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1102 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1102"
ms.assetid: bd2091f8-ef5e-4151-a8d6-98043e9422b6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Schwerwiegender Fehler RC1102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Interner Fehler: Zu viele Argumente für RCPP  
  
 Es wurden zu viele Argumente an den Präprozessor des Ressourcencompilers übergeben.  Reduzieren Sie die Anzahl der mit der Option zum Definieren von Symbolen \(**\/d**\) definierten Symbole, indem Sie diese in der Quelle neu definieren.  Dieser Fehler kann auch durch Angabe zu vieler Suchpfade für Includedateien verursacht werden, wenn die Option zur Pfadsuche \(**\/i**\) verwendet wird.