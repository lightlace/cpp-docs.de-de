---
title: "Verwenden von &quot;abort&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort-Funktion"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von &quot;abort&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch Aufrufen der Funktion [Abbruch](../c-runtime-library/reference/abort.md) wird eine sofortige Beendigung verursacht.  Dies umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte.  Außerdem wird jegliche spezielle Verarbeitung umgangen, die mit der `atexit`\-Funktion angegeben wurde.  
  
## Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)