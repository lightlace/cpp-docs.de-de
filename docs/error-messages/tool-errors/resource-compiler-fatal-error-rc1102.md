---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1102"
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
  - "RC1102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1102"
ms.assetid: bd2091f8-ef5e-4151-a8d6-98043e9422b6
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Schwerwiegender Fehler RC1102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Interner Fehler: Zu viele Argumente für RCPP  
  
 Es wurden zu viele Argumente an den Präprozessor des Ressourcencompilers übergeben.  Reduzieren Sie die Anzahl der mit der Option zum Definieren von Symbolen \(**\/d**\) definierten Symbole, indem Sie diese in der Quelle neu definieren.  Dieser Fehler kann auch durch Angabe zu vieler Suchpfade für Includedateien verursacht werden, wenn die Option zur Pfadsuche \(**\/i**\) verwendet wird.