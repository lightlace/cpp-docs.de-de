---
title: "Datenbindung mit ActiveX-Steuerelementen in Visual&#160;C++"
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
  - "ActiveX-Steuerelemente [C++], Datenbindung"
  - "Gebundene Steuerelemente [C++], ActiveX"
  - "Steuerelemente [C++], Datenbindung"
  - "Datenbindung [C++], ActiveX-Steuerelemente"
  - "Datengebundene Steuerelemente [C++], ActiveX"
ms.assetid: afe11d2b-eefe-43ce-958d-82d3d4dee158
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Datenbindung mit ActiveX-Steuerelementen in Visual&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datenbindung wird durch zwei ActiveX\-Steuerelementtypen implementiert: Datensteuerelemente und datengebundene Steuerelemente.  
  
 **Datensteuerelemente**  
 Datensteuerelemente sind für die Kapselung einer Datenbankabfrage und des abgerufenen Rowsets zuständig.  Die Microsoft\-Datensteuerelemente stellen eine Benutzeroberfläche mit einer Reihe von Schaltflächen bereit, mit denen Sie die Daten durchlaufen können.  Visual C\+\+ bietet zwei Zugriffstechnologien für Datensteuerelemente: [ADO und RDO](../../data/ado-rdo/data-access-ado-and-rdo.md).  
  
> [!IMPORTANT]
>  ADO\- und RDO\-Datensteuerelemente sind eine ältere Technologie, die mit einer früheren Version von Visual Studio veröffentlicht wurde, und möglicherweise in der aktuellen Version nicht verfügbar.  Um die Informationen in diesem Abschnitt zu verwenden, müssen Sie möglicherweise eine frühere Version abrufen, um das entsprechende Steuerelement abzurufen.  
  
 **Datengebundene Steuerelemente**  
 Datengebundene Steuerelemente sind für die Präsentation von Daten zuständig.  Sie stellen eine Verbindung mit Datensteuerelementen her, um Daten zu empfangen und diese in einer Reihe von Benutzeroberflächen darzustellen.  Eine Visual C\+\+\-Anwendung kann auch Variablen an Datenwerte binden, die in datengebundenen Steuerelementen festgelegt wurden. Siehe [CWnd::BindProperty](../Topic/CWnd::BindProperty.md).  
  
 Weitere Informationen zur Datenbindung finden Sie unter:  
  
-   [MFC\-ActiveX\-Steuerelemente: Verwenden der Datenbindung in einem ActiveX\-Steuerelement](../../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)  
  
-   [Datenzugriff: ADO und RDO](../../data/ado-rdo/data-access-ado-and-rdo.md)  
  
-   [ADO\-Datenbindung](../../data/ado-rdo/ado-databinding.md)  
  
-   [RDO\-Datenbindung](../../data/ado-rdo/rdo-databinding.md)  
  
-   [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md)  
  
-   [Festlegen von Ereignishandlern für ActiveX\-Steuerelemente](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [Abfangen von Fehlern](../../data/ado-rdo/error-trapping.md)  
  
-   [Einschränkungen der Datenbindung](../../data/ado-rdo/limitations-of-databinding.md)  
  
## Siehe auch  
 [Datengebundene Steuerelemente \(ADO und RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)