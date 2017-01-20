---
title: "Default Control Events"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Dialog editor, default control events"
  - "controls [C++], default control events"
  - "events [C++], controls"
  - "dialog box controls, events"
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Default Control Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Folgenden sehen Sie eine Auflistung von Steuerelementen und den zugehörigen Standardereignissen:  
  
|Steuerelementname|Standardereignis|  
|-----------------------|----------------------|  
|Animationssteuerung|**ACN\_START**|  
|Kontrollkästchen|**BN\_CLICKED**|  
|Kombinationsfeld|**CBN\_SELCHANGE**|  
|Benutzerdefiniert|**TTN\_GETDISPINFO**|  
|Datums\-\/Zeitauswahl|**DTN\_DATETIMECHANGE**|  
|Eingabefeld|**EN\_CHANGE**|  
|Gruppenfeld|\(Nicht zutreffend\)|  
|Abkürzungstaste|**NM\_OUTOFMEMORY**|  
|IP\-Adresse|**IPN\_FIELDCHANGED**|  
|List|**LVN\_ITEMCHANGE**|  
|Listenfeld|**LBN\_SELCHANGE**|  
|Monatskalender|**MCN\_SELCHANGE**|  
|Bildsteuerelemente|\(Nicht zutreffend\)|  
|Statuskontrolle|**NM\_CUSTOMDRAW**|  
|Schaltfläche|**BN\_CLICKED**|  
|Optionsfeld|**BN\_CLICKED**|  
|Rich\-Edit|**EN\_CHANGE**|  
|Bildlaufleiste|**NM\_THEMECHANGED**|  
|Schieberegler|**NM\_CUSTOMDRAW**|  
|Drehfeld|**UDN\_DELTAPOS**|  
|Statischer Text|\(Nicht zutreffend\)|  
|Registerkarte|**TCN\_SELCHANGE**|  
|Strukturansicht|**TVN\_SELCHANGE**|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [Bearbeiten eines Meldungshandlers](../mfc/reference/editing-a-message-handler.md)   
 [Definieren eines Meldungshandlers für eine reflektierte Meldung](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Deklarieren einer auf der neuen Steuerelementklasse basierenden Variablen](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)