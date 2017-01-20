---
title: "Compilerfehler C2654"
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
  - "C2654"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2654"
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2654
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Zugriff auf Element von außerhalb einer Methode  
  
 Innerhalb einer Deklaration wird auf einen Member zugegriffen.  Auf Memberdaten kann nur in Memberfunktionen zugegriffen werden.  
  
 Dieser Fehler kann verursacht werden, wenn Variablen in einer Deklaration initialisiert werden.  Verwenden Sie zu diesem Zweck einen Konstruktor.