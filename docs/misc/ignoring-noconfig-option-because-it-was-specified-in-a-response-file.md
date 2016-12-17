---
title: "Die /noconfig-Option wird ignoriert, da sie in einer Antwortdatei angegeben wurde."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc2025"
  - "bc2025"
helpviewer_keywords: 
  - "BC2025"
ms.assetid: 87fb393d-e17f-4e50-8d98-d9dfeba30c3e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Die /noconfig-Option wird ignoriert, da sie in einer Antwortdatei angegeben wurde.
Die `/noconfig`\-Option weist den Compiler an, nicht mit der Datei „Vbc.rsp“ zu kompilieren. Da der Compiler die Datei „Vbc.rsp“ jedoch vor allen anderen Antwortdateien verarbeitet, kann er die `/noconfig`\-Option in einer Antwortdatei nicht berücksichtigen.  
  
 **Fehler\-ID:** BC2025  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `/noconfig`\-Option aus der Antwortdatei.  
  
2.  Geben Sie die `/noconfig`\-Option an, wenn Sie den Befehlszeilencompiler aufrufen.  
  
## Siehe auch  
 [\/noconfig](../Topic/-noconfig.md)   
 [@ \(Specify Response File\)](../Topic/@%20\(Specify%20Response%20File\)%20\(Visual%20Basic\).md)