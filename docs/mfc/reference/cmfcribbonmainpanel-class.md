---
title: "CMFCRibbonMainPanel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonMainPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMainPanel class"
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMFCRibbonMainPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Favoritenmenübandbereich, der angezeigt wird, wenn Sie auf [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) klicken.  
  
## Syntax  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Standardkonstruktor.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md)|Fügt ein Menübandelement im linken Bereich des Anwendungsschaltflächenbereichs hinzu.  \(Überschreibungen [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).\)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](../Topic/CMFCRibbonMainPanel::AddRecentFilesList.md)|Fügt eine Textzeichenfolge dem neuen Dateilistenmenü hinzu.|  
|[CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md)|Fügt ein Menübandelement im unteren Bereich des Menüband\-Anwendungsbereichs hinzu.|  
|[CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md)|Fügt ein Menübandelement im rechten Bereich des Anwendungsschaltflächenbereichs hinzu.|  
|`CMFCRibbonMainPanel::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](../Topic/CMFCRibbonMainPanel::GetCommandsFrame.md)|Gibt ein Rechteck zurück, das den Bereich des zentralen Bereich des Menübands darstellt.|  
|`CMFCRibbonMainPanel::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
  
## Hinweise  
 Das Framework wird `CMFCRibbonMainPanel` an, wenn Sie den Anwendungsbereich öffnen.  Es enthält drei Bereiche:  
  
-   Der linke Bereich enthält die Befehle, die mit Dateien, wie **Öffnen**, **Speichern**, **Drucken** und **Schließen** zugeordnet werden.  Um einen Befehl diesem Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md) auf.  
  
-   Der rechte Bereich enthält Optionen, die für den Befehl ändern, den Sie im linken Bereich auf.  Wenn Sie beispielsweise auf **Speichern unter** vom linken Bereich klicken, kann der rechten Bereich verfügbaren Dateitypen anzeigen.  Um ein Element diesem Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md) auf.  
  
-   Der untere Bereich enthält Schaltflächen, die Ihnen, die Einstellungen der Anwendung zu ändern und ermöglichen das Programm zu beenden.  Um ein Element diesem Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md) auf.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonMainPanel.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)