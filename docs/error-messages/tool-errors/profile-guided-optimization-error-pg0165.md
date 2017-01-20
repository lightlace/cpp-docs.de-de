---
title: "Fehler in profilgesteuerter Optimierung: PG0165"
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
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Fehler in profilgesteuerter Optimierung: PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen 'Dateiname.pgd': 'PGD\-Version wird nicht unterstützt \(Versionen stimmen nicht überein\)'.  
  
 PGD\-Dateien beziehen sich auf ein bestimmtes Compilertoolset.  Dieser Fehler wird generiert, wenn Sie einen anderen Compiler verwenden als den, der für *Filename*.pgd verwendet wurde.  Dieser Fehler gibt an, dass diesem Compilertoolset die Daten aus *Filename*.pgd nicht verwenden kann, um das aktuelle Programm zu optimieren.  
  
 Um dieses Problem, Sie *Filename*.pgd mit dem aktuellen Compilertoolsets beheben.