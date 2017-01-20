---
title: "Compilerfehler C2828"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Operator' in binärem Format kann nicht global überschrieben werden  
  
 Der Operator kann kein binäres Format außerhalb eines Objekts aufweisen.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Definieren Sie den überladenen Operator als lokalen Operator eines Objekts.  
  
2.  Wählen Sie einen geeigneten unären Operator für die Überladung.