---
title: "Compilerfehler C2439"
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
  - "C2439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2439"
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Member konnte nicht initialisiert werden  
  
 Ein Klassen\-, Struktur\- oder Unionmember kann nicht initialisiert werden.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde versucht, eine indirekte Basisklasse oder Struktur zu initialisieren.  
  
2.  Es wurde versucht, einen geerbten Member einer Klasse oder Struktur zu initialisieren.  Ein geerbter Member sollte durch den Konstruktor der Klasse oder Struktur initialisiert werden.