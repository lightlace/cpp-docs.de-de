---
title: "Festlegen von Ereignishandlern f&#252;r ActiveX-Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Ereignisse"
  - "Ereignisse [C++], ActiveX-Steuerelemente"
ms.assetid: c076386f-c78b-4dc9-9201-a544252d5337
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Festlegen von Ereignishandlern f&#252;r ActiveX-Steuerelemente
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX\-Steuerelemente können so programmiert werden, dass sie auf Ereignisse reagieren.  Mithilfe von **ControlEvents** können Sie die in einem Steuerelement verfügbaren Ereignisse in den Eigenschaften anzeigen und Ereignishandler erstellen.  Die Ereignisbehandlung wird im Allgemeinen dazu verwendet, Änderungen in der Datenquellenabfrage aufzufangen.  Zu den Änderungen gehören:  
  
-   Implementieren einer Suche.  Sobald ein Steuerelement \(z. B. ein DBKombi\-Feld\) seinen Wert ändert, wird das Änderungsereignis aufgefangen, um die Abfrage eines Datensteuerelements zu aktualisieren.  
  
-   Implementieren einer Master\/Detailbeziehung.  Einem Dialogfeld werden zwei Datensteuerelemente hinzugefügt: eines für den Masterabschnitt und ein zweites für den Detailabschnitt.  Sobald sich die erste Datenquelle ändert, wird die Abfrage der zweiten Datenquelle über einen Ereignishandler aktualisiert.  
  
-   Fehlerbehebung.  Die meisten Steuerelemente verfügen über ein Fehlerereignis, aus dem Sie einen Fehlerhandler erstellen können \(siehe [Fehlerbehebung](../../data/ado-rdo/error-trapping.md)\).  
  
 Weitere Informationen finden Sie unter [Zuordnung von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md).  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)