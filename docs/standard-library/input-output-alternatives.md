---
title: "Eingabe-/Ausgabealternativen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E/A [C++], alternatives"
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: 8
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Eingabe-/Ausgabealternativen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ stellt mehrere Alternativen für E\/A\-Programmierung bereit:  
  
-   C\-Laufzeitbibliothek direkt, ungepufferte E\/A.  
  
-   ANSI C\-Laufzeitbibliotheksstream E\/A.  
  
-   Konsole und Port direkte E\/A.  
  
-   Microsoft Foundation Class\-Bibliothek.  
  
-   Microsoft\-C\+\+\-Standardbibliothek.  
  
 Die der iostream\-Headerdatei Klassen sind zur gepuffert, E\/A des formatierten Texts nützlich.  Sie sind außerdem für ungepufferte oder binäre E\/A nützlich, wenn Sie eine C\+\+\-Programmierungsschnittstelle benötigen und sich entscheiden, die \(Microsoft Foundation Class \(MFC\) nicht verwenden.  Die der iostream\-Headerdatei Klassen sind eine objektorientierte E\/A\-Alternative an C\-Laufzeitfunktionen.  
  
 Sie können der iostream\-Headerdatei Klassen mit dem Betriebssystem Microsoft Windows verwenden.  Zeichenfolgen\- und Dateistreams arbeiten ohne Einschränkungen, die Zeichenmodusstreamobjekte `cin`, `cout`, `cerr` und `clog` sind mit der Windows\-grafischenBenutzeroberfläche inkonsistent.  Sie können benutzerdefinierte Streamklassen auch abgeleitet werden, die direkt mit der Umgebungsvariable interagieren.  
  
## Siehe auch  
 [Funktionsweise eines Streams](../standard-library/what-a-stream-is.md)