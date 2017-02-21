---
title: "CStatusBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl class"
  - "status bar controls"
  - "Windows common controls [C++], CStatusBarCtrl"
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStatusBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des Windows\-Common\-StatusBar\-Steuerelements bereit.  
  
## Syntax  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](../Topic/CStatusBarCtrl::CStatusBarCtrl.md)|Erstellt ein `CStatusBarCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](../Topic/CStatusBarCtrl::Create.md)|Erstellt ein und fügt es StatusBar\-Steuerelement zu einem `CStatusBarCtrl`\-Objekt.|  
|[CStatusBarCtrl::CreateEx](../Topic/CStatusBarCtrl::CreateEx.md)|Erstellt ein StatusBar\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CStatusBarCtrl`\-Objekt.|  
|[CStatusBarCtrl::DrawItem](../Topic/CStatusBarCtrl::DrawItem.md)|Aufgerufen, wenn ein visueller Aspekt eines Ownerdrawnstatusbar\-steuerelements ändert.|  
|[CStatusBarCtrl::GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)|Ruft die aktuellen Breiten der horizontalen und vertikalen Rahmen eines StatusBar\-Steuerelements ab.|  
|[CStatusBarCtrl::GetIcon](../Topic/CStatusBarCtrl::GetIcon.md)|Ruft das Symbol für einen Teil \(auch als Bereich\) im Leistesteuerelement des aktuellen Status ab.|  
|[CStatusBarCtrl::GetParts](../Topic/CStatusBarCtrl::GetParts.md)|Ruft die Anzahl der Teile in einem StatusBar\-Steuerelement ab.|  
|[CStatusBarCtrl::GetRect](../Topic/CStatusBarCtrl::GetRect.md)|Ruft das umgebende Rechteck eines Teils in einem StatusBar\-Steuerelement ab.|  
|[CStatusBarCtrl::GetText](../Topic/CStatusBarCtrl::GetText.md)|Ruft den Text aus dem angegebenen Teil eines StatusBar\-Steuerelements ab.|  
|[CStatusBarCtrl::GetTextLength](../Topic/CStatusBarCtrl::GetTextLength.md)|Rufen Sie die Länge, in Zeichen, Text aus dem angegebenen Teil eines StatusBar\-Steuerelements ab.|  
|[CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)|Ruft den QuickInfo\-Text für einen Bereich in einer Statusleiste ab.|  
|[CStatusBarCtrl::IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)|Überprüft ein Statusfenstersteuerelement, um zu bestimmen, wenn es im einfachen Modus ist.|  
|[CStatusBarCtrl::SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)|Legt die Hintergrundfarbe in einer Statusleiste fest.|  
|[CStatusBarCtrl::SetIcon](../Topic/CStatusBarCtrl::SetIcon.md)|Legt das Symbol für einen Bereich in einer Statusleiste fest.|  
|[CStatusBarCtrl::SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)|Legt die Mindesthöhe Zeichnungsbereich eines Statusleistensteuer fest.|  
|[CStatusBarCtrl::SetParts](../Topic/CStatusBarCtrl::SetParts.md)|Legt die Anzahl von Teilen in einem StatusBar\-Steuerelement und die Koordinate des rechten Rands jedes Teils fest.|  
|[CStatusBarCtrl::SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)|Gibt ob ein einfacher Text der StatusBar\-Steuerelement\-Statusanzeigen an oder zeigt alle Steuerteile an, die von einem früheren Aufruf `SetParts` festgelegt werden.|  
|[CStatusBarCtrl::SetText](../Topic/CStatusBarCtrl::SetText.md)|Legt den Text im angegebenen Teil eines StatusBar\-Steuerelements fest.|  
|[CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md)|Legt den QuickInfo\-Text für einen Bereich in einer Statusleiste fest.|  
  
## Hinweise  
 Ein StatusBar\-Steuerelement "" ist ein horizontales Fenster angezeigt, normalerweise am unteren Rand ein übergeordnetes Fenster, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann.  Das StatusBar\-Steuerelement kann in Bereiche unterteilt werden, um mehr als einen Typ Informationen anzuzeigen.  
  
 Dieses Steuerelement \(und daher die `CStatusBarCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Weitere Informationen zur Verwendung von `CStatusBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)