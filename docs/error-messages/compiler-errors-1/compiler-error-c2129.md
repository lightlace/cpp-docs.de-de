---
title: "Compilerfehler C2129"
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
  - "C2129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2129"
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Statische Funktion 'Funktion' wurde deklariert, aber nicht definiert  
  
 Ein Vorwärtsverweis bezieht sich auf eine als `static` deklarierte Funktion, die nicht definiert wurde.  
  
 Eine `static`\-Funktion muss innerhalb des Gültigkeitsbereichs der Datei definiert werden.  Wird die Funktion außerhalb dieser Datei definiert, muss sie `extern` deklariert werden.