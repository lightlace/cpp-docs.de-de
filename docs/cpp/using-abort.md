---
title: "Verwenden von &quot;abort&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort-Funktion"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden von &quot;abort&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch Aufrufen der Funktion [Abbruch](../c-runtime-library/reference/abort.md) wird eine sofortige Beendigung verursacht.  Dies umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte.  Außerdem wird jegliche spezielle Verarbeitung umgangen, die mit der `atexit`\-Funktion angegeben wurde.  
  
## Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)