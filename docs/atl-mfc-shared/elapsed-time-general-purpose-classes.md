---
title: "Elapsed Time: General-Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
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