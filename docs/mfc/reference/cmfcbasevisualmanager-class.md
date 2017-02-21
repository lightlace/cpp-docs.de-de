---
title: "CMFCBaseVisualManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseVisualManager"
  - "CMFCBaseVisualManager.~CMFCBaseVisualManager"
  - "~CMFCBaseVisualManager"
  - "CMFCBaseVisualManager::~CMFCBaseVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseVisualManager destructor"
  - "CMFCBaseVisualManager class"
  - "CMFCBaseVisualManager class, Destruktor"
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCBaseVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Ebene zwischen abgeleiteten visuellen Managern und dem Windows\-Design APIs.  
  
 `CMFCBaseVisualManager` lädt UxTheme.dll, wenn verfügbar, und verwaltet Zugriff auf die Methoden Windows\-Designs APIs.  
  
 Diese Klasse ist nur für die interne Verwendung.  
  
## Syntax  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](../Topic/CMFCBaseVisualManager::CMFCBaseVisualManager.md)|erstellt und initialisiert ein `CMFCBaseVisualManager`\-Objekt.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::DrawCheckBox](../Topic/CMFCBaseVisualManager::DrawCheckBox.md)|Zeichnet ein Kontrollkästchen\-Steuerelement mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::DrawComboBorder](../Topic/CMFCBaseVisualManager::DrawComboBorder.md)|Zeichnet einen Kombinationsfeldrahmen mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::DrawComboDropButton](../Topic/CMFCBaseVisualManager::DrawComboDropButton.md)|Zeichnet eine Kombinationsfelddropdownschaltfläche mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::DrawPushButton](../Topic/CMFCBaseVisualManager::DrawPushButton.md)|Zeichnet eine Schaltfläche mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::DrawRadioButton](../Topic/CMFCBaseVisualManager::DrawRadioButton.md)|Zeichnet ein Optionsfeld\-Steuerelement mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](../Topic/CMFCBaseVisualManager::DrawStatusBarProgress.md)|Zeichnet eine Statusanzeige auf einem StatusBar\-Steuerelement \([CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)\) mithilfe des Designs der aktiven Fenster.|  
|[CMFCBaseVisualManager::FillReBarPane](../Topic/CMFCBaseVisualManager::FillReBarPane.md)|Füllt den Hintergrund des Infoleiste\-Steuerelements mithilfe des Designs der aktiven Fenster aus.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](../Topic/CMFCBaseVisualManager::GetStandardWindowsTheme.md)|Ruft das Design der aktiven Fenster ab.|  
  
### Geschützte Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::CleanUpThemes](../Topic/CMFCBaseVisualManager::CleanUpThemes.md)|Ruft `CloseThemeData` für alle Handles abgerufenen in `UpdateSystemColors` auf.|  
|[CMFCBaseVisualManager::UpdateSystemColors](../Topic/CMFCBaseVisualManager::UpdateSystemColors.md)|Aufrufe `OpenThemeData`, Typ\- Handles zum Zeichnen verschiedener Steuerelemente: Fenster, Symbolleisten, Schaltflächen, u. a.|  
  
## Hinweise  
 Sie müssen Objekte dieser Klasse nicht direkt instanziieren.  
  
 Da es eine Basisklasse für alle visuellen Manager ist, können Sie [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md) nur aufrufen, erhalten Sie einen Zeiger auf das aktuelle visuellen Manager und greifen auf die Methoden für `CMFCBaseVisualManager` mit diesem Zeiger auf.  Wenn Sie jedoch ein Steuerelement anzeigen müssen, indem Sie das Design der aktiven Fenster verwenden, ist es besser, die `CMFCVisualManagerWindows`\-Schnittstelle zu verwenden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## Anforderungen  
 **Header:** afxvisualmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)