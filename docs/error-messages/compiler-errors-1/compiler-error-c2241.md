---
title: "Compilerfehler C2241"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2241"
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Memberzugriff ist eingeschränkt.  
  
 Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.  
  
### So beheben Sie den Fehler \(unterschiedliche Lösungsmöglichkeiten\)  
  
1.  Ändern Sie die Zugriffsebene des Members.  
  
2.  Deklarieren Sie den Member als `friend` der zugreifenden Funktion.