---
title: "CToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl class"
  - "data tips [C++]"
  - "QuickInfos [C++], tool tip controls"
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Funktionalität eines ToolTip\-Steuerelements "," ein kleines Popupfenster, das eine einzelne Textzeile den Zweck eines Tools in einer Anwendung aussagekräftig anzeigt.  
  
## Syntax  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](../Topic/CToolTipCtrl::CToolTipCtrl.md)|Erstellt ein `CToolTipCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](../Topic/CToolTipCtrl::Activate.md)|Aktiviert und deaktiviert das ToolTip\-Steuerelement.|  
|[CToolTipCtrl::AddTool](../Topic/CToolTipCtrl::AddTool.md)|Registriert ein Tool mit dem ToolTip\-Steuerelement.|  
|[CToolTipCtrl::AdjustRect](../Topic/CToolTipCtrl::AdjustRect.md)|Wird zwischen Text\-Anzeigenrechteck eines ToolTip\-Steuerelements und seinem Fensterrechteck.|  
|[CToolTipCtrl::Create](../Topic/CToolTipCtrl::Create.md)|Erstellt ein QuickInfo\-Steuerelement und fügt es zu einem `CToolTipCtrl`\-Objekt.|  
|[CToolTipCtrl::CreateEx](../Topic/CToolTipCtrl::CreateEx.md)|Erstellt ein QuickInfo\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CToolTipCtrl`\-Objekt.|  
|[CToolTipCtrl::DelTool](../Topic/CToolTipCtrl::DelTool.md)|Entfernt ein Tool vom ToolTip\-Steuerelement.|  
|[CToolTipCtrl::GetBubbleSize](../Topic/CToolTipCtrl::GetBubbleSize.md)|Ruft die Größe der QuickInfo ab.|  
|[CToolTipCtrl::GetCurrentTool](../Topic/CToolTipCtrl::GetCurrentTool.md)|Ruft Informationen, wie die Größe, Position und der Text, des QuickInfofensters ab, das das aktuelle QuickInfosteuerelement anzeigt.|  
|[CToolTipCtrl::GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md)|Ruft die ursprüngliche, das Popup und die reshow Dauer ab, die derzeit für ein QuickInfo\-Steuerelement festgelegt werden.|  
|[CToolTipCtrl::GetMargin](../Topic/CToolTipCtrl::GetMargin.md)|Ruft den oberen Rand ab, linken, unteren und Rechtränder, die für ein QuickInfo\-Fenster festgelegt werden.|  
|[CToolTipCtrl::GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md)|Ruft die maximale Breite für ein QuickInfo\-Fenster ab.|  
|[CToolTipCtrl::GetText](../Topic/CToolTipCtrl::GetText.md)|Ruft den Text ab, den ein QuickInfo\-Steuerelement für ein Tool beibehält.|  
|[CToolTipCtrl::GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md)|Ruft die Hintergrundfarbe in einem QuickInfo\-Fenster ab.|  
|[CToolTipCtrl::GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md)|Ruft die Textfarbe in einem QuickInfo\-Fenster ab.|  
|[CToolTipCtrl::GetTitle](../Topic/CToolTipCtrl::GetTitle.md)|Ruft den Titel des aktuellen QuickInfosteuerelements ab.|  
|[CToolTipCtrl::GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md)|Ruft die Anzahl der Tools ab, die durch ein QuickInfo\-Steuerelement verwaltet werden.|  
|[CToolTipCtrl::GetToolInfo](../Topic/CToolTipCtrl::GetToolInfo.md)|Ruft die Informationen ab, die ein QuickInfo\-Steuerelement über ein Tool beibehält.|  
|[CToolTipCtrl::HitTest](../Topic/CToolTipCtrl::HitTest.md)|Testet einen Punkt, um zu bestimmen, ob er innerhalb des umgebenden Rechtecks des angegebenen Tools ist.  In diesem Fall ruft Informationen über das Tool ab.|  
|[CToolTipCtrl::Pop](../Topic/CToolTipCtrl::Pop.md)|Entfernt ein angezeigtes QuickInfo\-Fenster aus der Ansicht.|  
|[CToolTipCtrl::Popup](../Topic/CToolTipCtrl::Popup.md)|Veranlasst das aktuelle QuickInfosteuerelement, bei Koordinaten der letzten Mausmeldung anzuzeigen.|  
|[CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md)|Leitet eine Mausmeldung an ein QuickInfo\-Steuerelement für die Verarbeitung weiter.|  
|[CToolTipCtrl::SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md)|Legt die ursprüngliche, das Popup und die reshow Dauer für ein QuickInfo\-Steuerelement fest.|  
|[CToolTipCtrl::SetMargin](../Topic/CToolTipCtrl::SetMargin.md)|Legt die Spitze fest, linken, unteren und Rechtränder für ein QuickInfo\-Fenster.|  
|[CToolTipCtrl::SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md)|Legt die maximale Breite für ein QuickInfo\-Fenster fest.|  
|[CToolTipCtrl::SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md)|Legt die Hintergrundfarbe in einem QuickInfo\-Fenster fest.|  
|[CToolTipCtrl::SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md)|Legt die Textfarbe in einem QuickInfo\-Fenster fest.|  
|[CToolTipCtrl::SetTitle](../Topic/CToolTipCtrl::SetTitle.md)|Fügt eine Standardsymbol\- und Namezeichenfolge einer QuickInfo hinzu.|  
|[CToolTipCtrl::SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md)|Legt die Informationen fest, die eine QuickInfo für ein Tool beibehält.|  
|[CToolTipCtrl::SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md)|Legt ein neues umschließendes Rechteck für ein Tool fest.|  
|[CToolTipCtrl::SetWindowTheme](../Topic/CToolTipCtrl::SetWindowTheme.md)|Legt den Stil des QuickInfo\-Fensters fest.|  
|[CToolTipCtrl::Update](../Topic/CToolTipCtrl::Update.md)|Erzwingt das aktuelle neu gezeichnet werden Tool.|  
|[CToolTipCtrl::UpdateTipText](../Topic/CToolTipCtrl::UpdateTipText.md)|Legt den QuickInfo\-Text für ein Tool fest.|  
  
## Hinweise  
 Ein Tool "Tool" ist entweder ein Fenster, wie ein untergeordnetes Fenster oder Steuerelement oder ein anwendungsdefinierter rechteckiger Bereich innerhalb eines Clientbereichs des Fensters.  Eine QuickInfo ist i ausgeblendet und wird nur angezeigt, wenn der Benutzer den Cursor auf ein Tool und legt ihn dort für ungefähr halb zweites können.  Die QuickInfo wird neben dem Cursor und ausgeblendet, wenn der Benutzer auf eine Maustaste klickt oder den Cursor aus dem Tool verschoben wird.  
  
 `CToolTipCtrl` stellt Funktionalität bereit, um die ursprüngliche Zeit und Dauer zu steuern, die QuickInfo, der Randbreiten, die den QuickInfo\-Text umfassen, der Breite des QuickInfo\-Fensters selbst und des Hintergrunds und der Textfarbe der QuickInfo.  Ein einzelnes ToolTip\-Steuerelement kann Informationen für mehr als ein Tool bereitstellen.  
  
 Die `CToolTipCtrl`\-Klasse stellt Funktionen des allgemeinen ToolTip\-Steuerelements Windows.  Dieses Steuerelement \(und daher die `CToolTipCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher ausgeführt werden.  
  
 Weitere Informationen zum Aktivieren von QuickInfos, finden Sie unter [QuickInfo in Windows wird nicht von abgeleitet CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Weitere Informationen zur Verwendung von `CToolTipCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)