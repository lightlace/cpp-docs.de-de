---
title: "Compilerfehler C2241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2241"
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Memberzugriff ist eingeschränkt.  
  
 Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.  
  
### So beheben Sie den Fehler \(unterschiedliche Lösungsmöglichkeiten\)  
  
1.  Ändern Sie die Zugriffsebene des Members.  
  
2.  Deklarieren Sie den Member als `friend` der zugreifenden Funktion.