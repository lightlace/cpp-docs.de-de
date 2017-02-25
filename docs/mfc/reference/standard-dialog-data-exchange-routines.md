---
title: "Standard-Dialogdatenaustauschroutinen | Microsoft Docs"
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
  - "Standarddialog, Datenaustausch Routinen"
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Standard-Dialogdatenaustauschroutinen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema führt die Standardroutinen des Dialogdatenaustauschs \(DDX\) auf, die für Dialogfeldkontrollen des Common MFC verwendet werden.  
  
> [!NOTE]
>  Die Standarddialogdatenaustauschroutinen werden in der Headerdatei afxdd\_.h. definiert.  Allerdings sollten Anwendungen afxwin.h enthalten.  
  
### DDX\-Funktionen  
  
|||  
|-|-|  
|[DDX\_CBIndex](../Topic/DDX_CBIndex.md)|Initialisiert oder ruft den Index der aktuellen Auswahl eines Kombinationsfeldsteuerelements ab.|  
|[DDX\_CBString](../Topic/DDX_CBString.md)|Initialisiert oder ruft den aktuellen Inhalt des Eingabefelds eines Kombinationsfeldsteuerelements ab.|  
|[DDX\_CBStringExact](../Topic/DDX_CBStringExact.md)|Initialisiert oder ruft den aktuellen Inhalt des Eingabefelds eines Kombinationsfeldsteuerelements ab.|  
|[DDX\_Check](../Topic/DDX_Check.md)|Initialisiert oder ruft den aktuellen Zustand eines CheckBox\-Steuerelements ab.|  
|[DDX\_Control](../Topic/DDX_Control.md)|Ordnet ein angegebenes Steuerelement innerhalb eines Dialogfelds unter.|  
|[DDX\_DateTimeCtrl](../Topic/DDX_DateTimeCtrl.md)|Initialisiert oder ruft Datum und\/oder Zeitdaten eines Steuerelements für die Datums\- und Zeitauswahl ab.|  
|[DDX\_IPAddress](../Topic/DDX_IPAddress.md)|Initialisiert oder ruft den aktuellen Wert eines IP\-Adressensteuerelements ab.|  
|[DDX\_LBIndex](../Topic/DDX_LBIndex.md)|Initialisiert oder ruft den Index der aktuellen Auswahl eines Listenfeld\-Steuerelements ab.|  
|[DDX\_LBString](../Topic/DDX_LBString.md)|Initialisiert oder ruft die aktuelle Auswahl in eines Listenfeld\-Steuerelements ab.|  
|[DDX\_LBStringExact](../Topic/DDX_LBStringExact.md)|Initialisiert oder ruft die aktuelle Auswahl in eines Listenfeld\-Steuerelements ab.|  
|[DDX\_MonthCalCtrl](../Topic/DDX_MonthCalCtrl.md)|Initialisiert oder ruft den aktuellen Wert eines Monatskalender\-Steuerelements ab.|  
|[DDX\_Radio](../Topic/DDX_Radio.md)|Initialisiert oder ruft den 0 basierenden Index der Funksteuerung ab, die gerade innerhalb einer Funksteuerungsgruppe überprüft wird.|  
|[DDX\_Scroll](../Topic/DDX_Scroll.md)|Initialisiert oder ruft die aktuelle Position des Thumb\-Elements eines Bildlaufsteuer ab.|  
|[DDX\_Slider](../Topic/DDX_Slider.md)|Initialisiert oder ruft die aktuelle Position des Thumb\-Elements eines Schieberegler\-Steuerelements ab.|  
|[DDX\_Text](../Topic/DDX_Text.md)|Initialisiert oder ruft den aktuellen Wert eines Bearbeitungssteuerelements ab.|  
  
## Siehe auch  
 [Standarddialogfeld\-Datenvalidierungs\-Routinen](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)