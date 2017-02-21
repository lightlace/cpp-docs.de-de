---
title: "Compilerfehler C2827 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2827"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2827"
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2827
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Operator' in unärem Format kann nicht global überschrieben werden  
  
 Der Operator kann kein unäres Format außerhalb eines Objekts aufweisen.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Definieren Sie den überladenen Operator als lokalen Operator eines Objekts.  
  
2.  Wählen Sie einen geeigneten unären Operator für die Überladung.