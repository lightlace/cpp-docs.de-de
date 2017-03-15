---
title: "Gleitkomma-Koprozessor und Aufrufkonventionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gleitkomma-Coprozessor"
  - "Gleitkommazahlen"
  - "Gleitkommazahlen, Coprozessor"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Gleitkomma-Koprozessor und Aufrufkonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie Assemblyroutinen für den Fließkomma\-Koprozessor schreiben, müssen Sie das Fließkommasteuerwort beibehalten und den Koprozessorstapel bereinigen, es sei denn, Sie geben einen **float**\- oder **double**\-Wert zurück \(den die Funktion in ST\(0\) zurückgeben sollte\).  
  
## Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)