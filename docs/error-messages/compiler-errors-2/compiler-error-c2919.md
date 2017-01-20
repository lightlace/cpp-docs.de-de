---
title: "Compiler Error C2919"
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
  - "C2919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2919"
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': Operatoren können nicht direkt auf der veröffentlichten Oberfläche eines WinRT\-Typs verwendet werden.  
  
 Das Windows\-Runtime\-Typsystem unterstützt nicht die Operatormemberfunktionen auf der veröffentlichten Oberfläche eines Typs.  Dies liegt daran, weil nicht alle Sprachen Operatormemberfunktionen verwenden können.  Sie können private oder interne Operatormemberfunktionen erstellen, die über C\+\+\-Code in derselben Klasse oder Kompilationskomponente aufgerufen werden können.  
  
 Entfernen Sie zum Beheben dieses Problems die Operatormemberfunktion aus der öffentlichen Schnittstelle, oder ändern Sie sie in eine benannte Memberfunktion.  Benennen Sie die Memberfunktion beispielsweise anstelle von `operator==` in `Equals` um.