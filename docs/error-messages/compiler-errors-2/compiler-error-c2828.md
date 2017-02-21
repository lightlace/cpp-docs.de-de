---
title: "Compilerfehler C2828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Operator' in binärem Format kann nicht global überschrieben werden  
  
 Der Operator kann kein binäres Format außerhalb eines Objekts aufweisen.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Definieren Sie den überladenen Operator als lokalen Operator eines Objekts.  
  
2.  Wählen Sie einen geeigneten unären Operator für die Überladung.