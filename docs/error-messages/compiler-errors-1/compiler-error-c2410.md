---
title: "Compilerfehler C2410 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2410"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2410"
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2410
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Mehrdeutiger Membername in 'Kontext'  
  
 Der Bezeichner ist in diesem Kontext ein Member mehrerer Strukturen oder Unions.  
  
 Verwenden Sie einen Struktur\- oder Unionspezifizierer für den Operanden, durch den der Fehler verursacht wurde.  Ein Struktur\- oder Unionspezifizierer ist ein Bezeichner vom Typ `struct` oder `union` \(entweder ein `typedef`\-Name oder eine Variable vom gleichen Typ wie die Struktur oder die Union, auf die verwiesen wird\).  Der Spezifizierer muss der linke Operand des ersten Memberauswahloperators \(.\) sein, damit der Operand verwendet werden kann.