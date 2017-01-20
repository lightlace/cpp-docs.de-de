---
title: "Elapsed Time: General-Purpose Classes"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "calculating dates and times"
  - "Berechnungen, Datum und Uhrzeit"
  - "Datumsangaben, calculating intervals"
  - "Verstrichene Zeit"
  - "Verstrichene Zeit, Berechnen"
  - "intervals, Datum und Uhrzeit"
  - "Uhrzeit, elapsed"
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Elapsed Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Verfahren wird veranschaulicht, wie die Differenz zwischen zwei `CTime`\-Objekten abgeleitet wird und ein `CTimeSpan` Ergebnis abruft.  
  
#### So Laufzeit berechnen  
  
1.  Verwenden Sie die `CTime` und `CTimeSpan`\-Objekte, um die Laufzeit zu berechnen, wie folgt:  
  
     [!CODE [NVC_ATLMFC_Utilities#174](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#174)]  
  
     Nachdem Sie `elapsedTime` berechnet haben, können Sie die Memberfunktionen von `CTimeSpan` verwenden, um die Komponenten des Werts für die verstrichene Zeit zu extrahieren.  
  
## Siehe auch  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)