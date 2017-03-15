---
title: "VarArgs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# VarArgs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Parameter über VarArgs übergeben werden \(z. B. Argumente mit Ellipsen\), wird im Wesentlichen die normale Parameterübergabe angewendet, einschließlich dem Zwischenspeichern des fünften und der nachfolgenden Argumente.  Durch die aufgerufene Funktion wird auch in diesem Fall sichergestellt, dass Argumente gespeichert werden, deren Adressen akzeptiert wurden.  Nur Gleitkommawerte sind sowohl im Ganzzahl\- als auch im Gleitkommaregister enthalten, wenn von der aufgerufenen Funktion der Wert in den Ganzzahlregistern erwartet wird.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)