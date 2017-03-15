---
title: "Fehler in profilgesteuerter Optimierung: PG0165 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Fehler in profilgesteuerter Optimierung: PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen 'Dateiname.pgd': 'PGD\-Version wird nicht unterstützt \(Versionen stimmen nicht überein\)'.  
  
 PGD\-Dateien beziehen sich auf ein bestimmtes Compilertoolset.  Dieser Fehler wird generiert, wenn Sie einen anderen Compiler verwenden als den, der für *Filename*.pgd verwendet wurde.  Dieser Fehler gibt an, dass diesem Compilertoolset die Daten aus *Filename*.pgd nicht verwenden kann, um das aktuelle Programm zu optimieren.  
  
 Um dieses Problem, Sie *Filename*.pgd mit dem aktuellen Compilertoolsets beheben.