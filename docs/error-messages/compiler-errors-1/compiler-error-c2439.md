---
title: "Compilerfehler C2439 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2439"
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Member konnte nicht initialisiert werden  
  
 Ein Klassen\-, Struktur\- oder Unionmember kann nicht initialisiert werden.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde versucht, eine indirekte Basisklasse oder Struktur zu initialisieren.  
  
2.  Es wurde versucht, einen geerbten Member einer Klasse oder Struktur zu initialisieren.  Ein geerbter Member sollte durch den Konstruktor der Klasse oder Struktur initialisiert werden.