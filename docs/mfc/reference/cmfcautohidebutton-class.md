---
title: "CMFCAutoHideButton Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCAutoHideButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideButton class"
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Schaltfläche, die eine [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) anzeigt oder ausblendet \(vorausgesetzt, die Klasse ist so konfiguriert, dass sie ausgeblendet werden kann\).  
  
## Syntax  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAutoHideButton::BringToTop](../Topic/CMFCAutoHideButton::BringToTop.md)||  
|[CMFCAutoHideButton::Create](../Topic/CMFCAutoHideButton::Create.md)|Erstellt und initialisiert die Schaltfläche zum automatischen Ausblenden.|  
|[CMFCAutoHideButton::GetAlignment](../Topic/CMFCAutoHideButton::GetAlignment.md)|Ruft die Ausrichtung der Schaltfläche zum automatischen Ausblenden ab.|  
|[CMFCAutoHideButton::GetAutoHideWindow](../Topic/CMFCAutoHideButton::GetAutoHideWindow.md)|Gibt das der Schaltfläche zum automatischen Ausblenden zugeordnete [CDockablePane](../../mfc/reference/cdockablepane-class.md)\-Objekt zurück.|  
|[CMFCAutoHideButton::GetParentToolBar](../Topic/CMFCAutoHideButton::GetParentToolBar.md)||  
|[CMFCAutoHideButton::GetRect](../Topic/CMFCAutoHideButton::GetRect.md)||  
|[CMFCAutoHideButton::GetSize](../Topic/CMFCAutoHideButton::GetSize.md)|Legt die Größe der Schaltfläche zum automatischen Ausblenden fest.|  
|[CMFCAutoHideButton::GetTextSize](../Topic/CMFCAutoHideButton::GetTextSize.md)|Gibt die Größe der Textbeschriftung für die Schaltfläche zum automatischen Ausblenden zurück.|  
|[CMFCAutoHideButton::HighlightButton](../Topic/CMFCAutoHideButton::HighlightButton.md)|Hebt die Schaltfläche zum automatischen Ausblenden hervor.|  
|[CMFCAutoHideButton::IsActive](../Topic/CMFCAutoHideButton::IsActive.md)|Gibt an, ob die Schaltfläche zum automatischen Ausblenden aktiv ist.|  
|[CMFCAutoHideButton::IsHighlighted](../Topic/CMFCAutoHideButton::IsHighlighted.md)|Gibt den Hervorhebestatus der Schaltfläche zum automatischen Ausblenden zurück.|  
|[CMFCAutoHideButton::IsHorizontal](../Topic/CMFCAutoHideButton::IsHorizontal.md)|Bestimmt, ob die Schaltfläche zum automatischen Ausblenden horizontal oder vertikal ist.|  
|[CMFCAutoHideButton::IsTop](../Topic/CMFCAutoHideButton::IsTop.md)||  
|[CMFCAutoHideButton::IsVisible](../Topic/CMFCAutoHideButton::IsVisible.md)|Gibt an, ob die Schaltfläche sichtbar ist.|  
|[CMFCAutoHideButton::Move](../Topic/CMFCAutoHideButton::Move.md)||  
|[CMFCAutoHideButton::OnDraw](../Topic/CMFCAutoHideButton::OnDraw.md)|Das Framework ruft diese Methode auf, wenn es die Schaltfläche zum automatischen Ausblenden zeichnet.|  
|[CMFCAutoHideButton::OnDrawBorder](../Topic/CMFCAutoHideButton::OnDrawBorder.md)|Das Framework ruft diese Methode auf, wenn es den Rahmen einer Schaltfläche zum automatischen Ausblenden zeichnet.|  
|[CMFCAutoHideButton::OnFillBackground](../Topic/CMFCAutoHideButton::OnFillBackground.md)|Das Framework ruft diese Methode auf, wenn es den Hintergrund einer Schaltfläche zum automatischen Ausblenden füllt.|  
|[CMFCAutoHideButton::ReplacePane](../Topic/CMFCAutoHideButton::ReplacePane.md)||  
|[CMFCAutoHideButton::ShowAttachedWindow](../Topic/CMFCAutoHideButton::ShowAttachedWindow.md)|Blendet die zugeordnete [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) ein oder aus.|  
|[CMFCAutoHideButton::ShowButton](../Topic/CMFCAutoHideButton::ShowButton.md)|Blendet die Schaltfläche zum automatischen Ausblenden ein oder aus.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](../Topic/CMFCAutoHideButton::UnSetAutoHideMode.md)||  
  
## Hinweise  
 Bei der Erstellung wird das `CMFCAutoHideButton`\-Objekt an eine [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) angefügt.  Das `CDockablePane`\-Objekt wird ausgeblendet oder angezeigt, wenn der Benutzer mit dem `CMFCAutoHideButton`\-Objekt interagiert.  
  
 Standardmäßig erstellt das Framework automatisch eine `CMFCAutoHideButton`, wenn der Benutzer das automatische Ausblenden aktiviert.  Das Framework kann ein Element einer benutzerdefinierten Benutzeroberflächenklasse erstellen, anstatt der `CMFCAutoHideButton`\-Klasse.  Um festzulegen, welche benutzerdefinierte Benutzeroberflächenklasse das Framework verwenden soll, legen Sie die statische Membervariable `CMFCAutoHideBar::m_pAutoHideButtonRTS` auf den gleichen Wert wie die benutzerdefinierte Benutzeroberflächenklasse fest.  Standardmäßig ist diese Variable auf `CMFCAutoHideButton` festgelegt.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAutoHideButton`\-Objekts, und die Verwendung verschiedener Methoden in der `CMFCAutoHideButton`\-Klasse.  Das Beispiel veranschaulicht, wie Sie ein `CMFCAutoHideButton`\-Objekt mithilfe seiner `Create`\-Methode initialisieren, die zugeordnete `CDockablePane`\-Klasse anzeigen und die Schaltfläche zum automatischen Ausblenden anzeigen.  
  
 [!CODE [NVC_MFC_RibbonApp#32](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#32)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)  
  
## Anforderungen  
 **Header:** afxautohidebutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)