---
title: "Schwerwiegender Fehler C1099"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1099"
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kompilierungsabbruch durch Modul für Bearbeiten und Fortfahren  
  
 Durch Bearbeiten und Fortfahren wurde eine vorkompilierte Headerdatei in Vorbereitung für das Kompilieren von Codeänderungen geladen, aber nachfolgende Maßnahmen \(z. B. Codeänderungen vor der vorkompilierten `#include`\-Headeranweisung oder das Beenden des Debuggers\) verhindern, dass die Kompilierung mit diesem Prozess von „Bearbeiten und Fortfahren“ beendet wird. Sie müssen keine Maßnahmen ergreifen, um diesen Fehler zu beheben.