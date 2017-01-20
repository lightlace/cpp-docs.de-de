---
title: "C++-Kommentare"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Codekommentare, C++"
  - "Kommentare, C++-Code"
  - "Kommentare, Dokumentierender Code"
  - "Leerraum, C++-Kommentare"
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Kommentare
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Kommentar ist Text, den der Compiler ignoriert, der jedoch für Programmierer hilfreich ist.  Kommentare werden in der Regel verwendet, um Code zu Referenzzwecken mit Anmerkungen zu versehen.  Der Compiler behandelt sie als Leerzeichen.  Sie können Kommentare beim Testen verwenden, um bestimmte Codezeilen als inaktiv festzulegen. Allerdings sind `#if`\/`#endif`\-Präprozessordirektiven hierfür besser geeignet, da Sie Code, der Kommentare enthält, umschließen, aber Kommentare nicht schachteln können.  
  
 Es gibt folgende Möglichkeiten, einen C\+\+\-Kommentar zu schreiben:  
  
-   Die Zeichen `/*` \(Schrägstrich, Sternchen\), gefolgt von einer beliebigen Folge von Zeichen \(einschließlich neuer Zeilen\), gefolgt von den Zeichen `*/`.  Diese Syntax ist mit der Syntax von ANSI C identisch.  
  
-   Die Zeichen `//` \(zwei Schrägstriche\), gefolgt von einer beliebigen Folge von Zeichen.  Eine neue Zeile, der nicht direkt ein umgekehrter Schrägstrich vorangestellt ist, beendet diese Art des Kommentars.  Daher wird dies häufig als "einzeiliger Kommentar" bezeichnet.  
  
 Die Kommentarzeichen \(`/*`, `*/` und `//`\) verfügen über keine besondere Bedeutung innerhalb einer Zeichenkonstante, eines Zeichenfolgenliterals oder eines Kommentars.  Kommentare, die die erste Syntax verwenden, können deshalb nicht geschachtelt werden.  
  
## Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)