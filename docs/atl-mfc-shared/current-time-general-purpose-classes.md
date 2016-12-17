---
title: "Current Time: General Purpose Classes"
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
  - "Aktuelle Uhrzeit, CTime object"
  - "Initialisieren von Objekten, with the current time"
  - "Prozeduren, getting current time"
  - "Uhrzeit, getting current"
  - "Uhrzeit, setting current"
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Current Time: General Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das folgende Verfahren veranschaulicht, wie ein `CTime`\-Objekt erstellt und mit der aktuellen Zeit initialisiert.  
  
#### Um die aktuelle Uhrzeit abrufen  
  
1.  Ordnen Sie ein `CTime`\-Objekt zu, wie folgt:  
  
     [!CODE [NVC_ATLMFC_Utilities#171](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#171)]  
  
    > [!NOTE]
    >  Nicht initialisierte `CTime`\-Objekte werden nicht zu einer Gültigkeitszeit initialisiert.  
  
2.  Rufen Sie die `CTime::GetCurrentTime`\-Funktion auf, um die aktuelle Zeit vom Betriebssystem abzurufen.  Diese Funktion gibt ein `CTime`\-Objekt, das verwendet werden kann, um den Wert von `CTime` festzulegen, wie folgt zurück:  
  
     [!CODE [NVC_ATLMFC_Utilities#172](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#172)]  
  
     Da `GetCurrentTime` eine statische Memberfunktion aus der `CTime`\-Klasse ist, müssen Sie den Namen mit dem Namen der Klasse und des Bereichsauflösungsoperators \(`::`\), `CTime::GetCurrentTime()` qualifizieren.  
  
 Natürlich können die zwei Schritte, die zuvor beschriebenen wurden, in eine Programmanweisung über kombiniert werden, wie folgt:  
  
 [!CODE [NVC_ATLMFC_Utilities#173](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#173)]  
  
## Siehe auch  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)