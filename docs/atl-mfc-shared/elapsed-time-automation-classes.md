---
title: "Elapsed Time: Automation Classes"
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
  - "Automation classes, Verstrichene Zeit"
  - "calculating dates and times"
  - "Berechnungen, Datum und Uhrzeit"
  - "Datumsangaben, calculating intervals"
  - "Verstrichene Zeit, calculating in Automation"
  - "intervals, Datum und Uhrzeit"
  - "Uhrzeit, elapsed"
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Elapsed Time: Automation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Prozedur zeigt, wie die Differenz zwischen zwei `CTime`\-Objekten abgeleitet wird und ein `CTimeSpan` Ergebnis abruft.  
  
#### So Laufzeit berechnen  
  
1.  Erstellen Sie zwei `COleDateTime`\-Objekte.  
  
2.  Legen Sie eines der `COleDateTime`\-Objekte auf die aktuelle Zeit fest.  
  
3.  Führen Sie eine zeitintensive Aufgabe aus.  
  
4.  Legen Sie das andere `COleDateTime`\-Objekt auf die aktuelle Zeit fest.  
  
5.  Nehmen Sie den Unterschied zwischen den beiden Zeiten.  
  
     [!CODE [NVC_ATLMFC_Utilities#178](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#178)]  
  
## Siehe auch  
 [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md)