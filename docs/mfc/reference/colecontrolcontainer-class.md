---
title: "COleControlContainer Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlContainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++], control site"
  - "COleControlContainer class"
  - "Benutzerdefinierte Steuerelemente [MFC], sites"
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleControlContainer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fungiert als Steuerelementcontainer für ActiveX\-Steuerelemente auf.  
  
## Syntax  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](../Topic/COleControlContainer::COleControlContainer.md)|Erstellt ein `COleControlContainer`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](../Topic/COleControlContainer::AttachControlSite.md)|Stellt Steuerungssite erstellt, gehostet vom Container.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](../Topic/COleControlContainer::BroadcastAmbientPropertyChange.md)|Informiert alle gehosteten Steuerelemente, dass eine Ambient\-Eigenschaft geändert hat.|  
|[COleControlContainer::CheckDlgButton](../Topic/COleControlContainer::CheckDlgButton.md)|Ändert das angegebene Schaltflächen\-Steuerelement.|  
|[COleControlContainer::CheckRadioButton](../Topic/COleControlContainer::CheckRadioButton.md)|Wählt das angegebene Optionsfeld einer Gruppe aus.|  
|[COleControlContainer::CreateControl](../Topic/COleControlContainer::CreateControl.md)|Erstellt ein gehostetes ActiveX\-Steuerelement.|  
|[COleControlContainer::CreateOleFont](../Topic/COleControlContainer::CreateOleFont.md)|Erstellt eine OLE\-Schriftart.|  
|[COleControlContainer::FindItem](../Topic/COleControlContainer::FindItem.md)|Gibt die benutzerdefinierte Site des angegebenen Steuerelements zurück.|  
|[COleControlContainer::FreezeAllEvents](../Topic/COleControlContainer::FreezeAllEvents.md)|Bestimmt, ob die Ereignisse Steuerungssite akzeptieren.|  
|[COleControlContainer::GetAmbientProp](../Topic/COleControlContainer::GetAmbientProp.md)|Ruft die angegebene Ambient\-Eigenschaft ab.|  
|[COleControlContainer::GetDlgItem](../Topic/COleControlContainer::GetDlgItem.md)|Ruft das angegebene Dialogfeld\-Steuerelement ab.|  
|[COleControlContainer::GetDlgItemInt](../Topic/COleControlContainer::GetDlgItemInt.md)|Ruft den Wert des angegebenen Dialogfeldsteuerelements ab.|  
|[COleControlContainer::GetDlgItemText](../Topic/COleControlContainer::GetDlgItemText.md)|Ruft die Beschriftung des angegebenen Dialogfeldsteuerelements ab.|  
|[COleControlContainer::HandleSetFocus](../Topic/COleControlContainer::HandleSetFocus.md)|Bestimmt, ob der Container `WM_SETFOCUS` Meldungen behandelt.|  
|[COleControlContainer::HandleWindowlessMessage](../Topic/COleControlContainer::HandleWindowlessMessage.md)|Bearbeitet die Meldungen, die einem Steuerelement fensterlose gesendet werden.|  
|[COleControlContainer::IsDlgButtonChecked](../Topic/COleControlContainer::IsDlgButtonChecked.md)|Bestimmt den Zustand der angegebenen Schaltfläche.|  
|[COleControlContainer::OnPaint](../Topic/COleControlContainer::OnPaint.md)|Aufgerufen, um einen Teil des Containers neu zu zeichnen.|  
|[COleControlContainer::OnUIActivate](../Topic/COleControlContainer::OnUIActivate.md)|Aufgerufen, wenn ein Steuerelement über, direkt zu sein aktiviert ist.|  
|[COleControlContainer::OnUIDeactivate](../Topic/COleControlContainer::OnUIDeactivate.md)|Aufgerufen, wenn ein Steuerelement im Begriff ist deaktiviert werden.|  
|[COleControlContainer::ScrollChildren](../Topic/COleControlContainer::ScrollChildren.md)|Aufgerufen vom Framework, wenn Bildlaufmeldungen von einem untergeordneten Fenster empfangen werden.|  
|[COleControlContainer::SendDlgItemMessage](../Topic/COleControlContainer::SendDlgItemMessage.md)|Sendet eine Meldung an das angegebene Steuerelement.|  
|[COleControlContainer::SetDlgItemInt](../Topic/COleControlContainer::SetDlgItemInt.md)|Legt den Wert des angegebenen Steuerelements fest.|  
|[COleControlContainer::SetDlgItemText](../Topic/COleControlContainer::SetDlgItemText.md)|Legt den Text des angegebenen Steuerelements fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlContainer::m\_crBack](../Topic/COleControlContainer::m_crBack.md)|Die Hintergrundfarbe des Containers.|  
|[COleControlContainer::m\_crFore](../Topic/COleControlContainer::m_crFore.md)|Die Vordergrundfarbe des Containers.|  
|[COleControlContainer::m\_listSitesOrWnds](../Topic/COleControlContainer::m_listSitesOrWnds.md)|Eine Liste der unterstützten Steuerungssite.|  
|[COleControlContainer::m\_nWindowlessControls](../Topic/COleControlContainer::m_nWindowlessControls.md)|Die Anzahl der gehosteten fensterlose Steuerelemente.|  
|[COleControlContainer::m\_pOleFont](../Topic/COleControlContainer::m_pOleFont.md)|Ein Zeiger auf die OLE\-Schriftart der Site des benutzerdefinierten Steuerelements.|  
|[COleControlContainer::m\_pSiteCapture](../Topic/COleControlContainer::m_pSiteCapture.md)|Zeiger auf Erfassungssteuerungssiten.|  
|[COleControlContainer::m\_pSiteFocus](../Topic/COleControlContainer::m_pSiteFocus.md)|Zeiger auf das Steuerelement, das gerade Eingabefokus hat.|  
|[COleControlContainer::m\_pSiteUIActive](../Topic/COleControlContainer::m_pSiteUIActive.md)|Zeiger auf das Steuerelement, das direkt ist derzeit aktiviert.|  
|[COleControlContainer::m\_pWnd](../Topic/COleControlContainer::m_pWnd.md)|Zeiger auf das Fenster den Steuerelementcontainer zu implementieren.|  
|[COleControlContainer::m\_siteMap](../Topic/COleControlContainer::m_siteMap.md)|Die Siteübersicht.|  
  
## Hinweise  
 Dies wird durchgeführt, indem Unterstützung für eine oder mehrere ActiveX\-Steuerelement\-Sites bietet \(implementiert durch `COleControlSite`\).  `COleControlContainer` vollständig implementiert die [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) und [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103)\-Schnittstellen und ermöglicht den enthaltenen ActiveX\-Steuerelemente, um ihre const\-volatile\-Qualifizierungen als direkte Elemente zu erfüllen.  
  
 Häufig wird diese Klasse in Verbindung mit `COccManager` und `COleControlSite` verwendet, um einen benutzerdefinierten ActiveX\-Steuerelementcontainer, mit benutzerdefinierten Sites für eine oder mehrere ActiveX\-Steuerelemente zu implementieren.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## Anforderungen  
 **Header:** afxocc.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager Class](../../mfc/reference/coccmanager-class.md)