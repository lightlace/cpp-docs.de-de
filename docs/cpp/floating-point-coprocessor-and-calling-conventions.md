---
title: "Gleitkomma-Koprozessor und Aufrufkonventionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gleitkomma-Coprozessor"
  - "Gleitkommazahlen"
  - "Gleitkommazahlen, Coprozessor"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gleitkomma-Koprozessor und Aufrufkonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie Assemblyroutinen für den Fließkomma\-Koprozessor schreiben, müssen Sie das Fließkommasteuerwort beibehalten und den Koprozessorstapel bereinigen, es sei denn, Sie geben einen **float**\- oder **double**\-Wert zurück \(den die Funktion in ST\(0\) zurückgeben sollte\).  
  
## Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)