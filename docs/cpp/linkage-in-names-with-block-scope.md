---
title: "Verkn&#252;pfung in Namen mit Blockbereich | Microsoft Docs"
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
  - "Blockbereich [C++]"
  - "Externe Verknüpfung, Bereich der Verknüpfungsregeln"
  - "Verknüpfung [C++], Bereich der Verknüpfungsregeln"
  - "Namen [C++], Bereich der Verknüpfungsregeln"
  - "Bereich [C++], Verknüpfungsregeln"
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verkn&#252;pfung in Namen mit Blockbereich
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Bindungsregeln gelten für Namen mit Blockgültigkeitsbereich \(lokale Namen\):  
  
-   Die Namen, die als `extern` deklariert werden, verfügen über eine externe Bindung, es sei denn, sie wurden zuvor als **static** deklariert.  
  
-   Alle anderen Namen mit Blockgültigkeit haben keine Bindung.  
  
## Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)