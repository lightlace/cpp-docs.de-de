---
title: "Eigenschaftenseiten (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datentransferfunktionen für Eigenschaftenseiten in MFC"
  - "Eigenschaftenseiten, Globale MFC-Funktionen"
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Eigenschaftenseiten (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eigenschaftenseiten werden die aktuellen Werte bestimmter OLE\-Steuerelement\-Eigenschaften in einem anpassbaren, von grafischer Benutzeroberfläche zum Anzeigen und Bearbeiten an, indem sie einen DatenZuordnungsmechanismus auf Grundlage den Dialogdatenaustausch \(DDX\) unterstützen.  
  
 Dieser DatenZuordnungsmechanismus ordnet Eigenschaftenseitenkontrollen zu den einzelnen Eigenschaften des OLE\-Steuerelements zu.  Der Wert der Steuerelementeigenschaft gibt den Status oder die Inhalte des Eigenschaftenseitensteuerelements.  Die Zuordnung zwischen Eigenschaftenseitenkontrollen und Eigenschaften wird von **DDP\_**\-Funktionsaufrufe in der Memberfunktion `DoDataExchange` der Eigenschaftenseite angegeben.  Die folgende Liste **DDP\_**\-Funktion, die Daten mithilfe der Eigenschaftenseite des Steuerelements eingegeben haben:  
  
### Eigenschaftenseiten\-Datenübertragung  
  
|||  
|-|-|  
|[DDP\_CBIndex](../Topic/DDP_CBIndex.md)|Verweist den ausgewählten Index der Zeichenfolge in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements.|  
|[DDP\_CBString](../Topic/DDP_CBString.md)|Verweist die ausgewählte Zeichenfolge in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements.  Die ausgewählte Zeichenfolge kann, mit den gleichen Buchstaben wie der Eigenschaftswert starten muss jedoch nicht, um ihn vollständig übereinstimmen.|  
|[DDP\_CBStringExact](../Topic/DDP_CBStringExact.md)|Verweist die ausgewählte Zeichenfolge in einem Kombinationsfeld mit der Eigenschaft eines Steuerelements.  Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen genau übereinstimmen.|  
|[DDP\_Check](../Topic/DDP_Check.md)|Verknüpft ein Kontrollkästchen in der Eigenschaftenseite des Steuerelements mit der Eigenschaft eines Steuerelements.|  
|[DDP\_LBIndex](../Topic/DDP_LBIndex.md)|Verweist den ausgewählten Index der Zeichenfolge in einem Listenfeld mit der Eigenschaft eines Steuerelements.|  
|[DDP\_LBString](../Topic/DDP_LBString.md)|Verweist die ausgewählte Zeichenfolge in einem Listenfeld mit der Eigenschaft eines Steuerelements.  Die ausgewählte Zeichenfolge kann, mit den gleichen Buchstaben wie der Eigenschaftswert starten muss jedoch nicht, ihn vollständig übereinstimmen.|  
|[DDP\_LBStringExact](../Topic/DDP_LBStringExact.md)|Verweist die ausgewählte Zeichenfolge in einem Listenfeld mit der Eigenschaft eines Steuerelements.  Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen genau übereinstimmen.|  
|[DDP\_PostProcessing](../Topic/DDP_PostProcessing.md)|Beendet die Eigentumsübertragungswerte aus dem Steuerelement.|  
|[DDP\_Radio](../Topic/DDP_Radio.md)|Verweist eine Optionsfeldgruppe in der Eigenschaftenseite des Steuerelements mit der Eigenschaft eines Steuerelements.|  
|[DDP\_Text](../Topic/DDP_Text.md)|Verknüpft ein Steuerelement in der Eigenschaftenseite des Steuerelements mit der Eigenschaft eines Steuerelements.  Diese Funktion behandelt mehrere unterschiedliche Typen von Eigenschaften, wie **double**, **short**, `BSTR` und **long**.|  
  
 Weitere Informationen zum `DoDataExchange`\-Funktion und Eigenschaftenseiten, finden Sie im Artikel [ActiveX\-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Im Folgenden wird eine Reihe von Makros, die verwendet werden, um Eigenschaftenseiten für ein OLE\-Steuerelement zu erstellen und zu verwalten:  
  
### Eigenschaftenseiten  
  
|||  
|-|-|  
|[BEGIN\_PROPPAGEIDS](../Topic/BEGIN_PROPPAGEIDS.md)|Startet die Liste von IDs Eigenschaftenseite.|  
|[END\_PROPPAGEIDS](../Topic/END_PROPPAGEIDS.md)|Beendet die Liste von IDs Eigenschaftenseite.|  
|[PROPPAGEID](../Topic/PROPPAGEID.md)|Deklariert eine Eigenschaftenseite der Steuerelementklasse.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)