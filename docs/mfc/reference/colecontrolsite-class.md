---
title: "COleControlSite Class"
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
  - "COleControlSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlSite class"
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleControlSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet Unterstützung für benutzerdefinierte clientseitige Antriebssteuerungen.  
  
## Syntax  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](../Topic/COleControlSite::COleControlSite.md)|Erstellt ein `COleControlSite`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](../Topic/COleControlSite::BindDefaultProperty.md)|Bindet die Standardeigenschaft des gehosteten Steuerelements an eine Datenquelle.|  
|[COleControlSite::BindProperty](../Topic/COleControlSite::BindProperty.md)|Bindet eine Eigenschaft des gehosteten Steuerelements an eine Datenquelle.|  
|[COleControlSite::CreateControl](../Topic/COleControlSite::CreateControl.md)|Erstellt ein gehostetes ActiveX\-Steuerelement.|  
|[COleControlSite::DestroyControl](../Topic/COleControlSite::DestroyControl.md)|Zerstört das gehostete Steuerelement.|  
|[COleControlSite::DoVerb](../Topic/COleControlSite::DoVerb.md)|Führt ein bestimmtes Verb des gehosteten Steuerelements aus.|  
|[COleControlSite::EnableDSC](../Topic/COleControlSite::EnableDSC.md)|Ermöglicht Datenauftreten für Steuerungssite.|  
|[COleControlSite::EnableWindow](../Topic/COleControlSite::EnableWindow.md)|Aktiviert die Steuerungssite.|  
|[COleControlSite::FreezeEvents](../Topic/COleControlSite::FreezeEvents.md)|Gibt an, ob die Ereignisse Steuerungssite akzeptieren.|  
|[COleControlSite::GetDefBtnCode](../Topic/COleControlSite::GetDefBtnCode.md)|Ruft den Standardschaltflächencode für das gehostete Steuerelement.|  
|[COleControlSite::GetDlgCtrlID](../Topic/COleControlSite::GetDlgCtrlID.md)|Ruft den Bezeichner des Steuerelements ab.|  
|[COleControlSite::GetEventIID](../Topic/COleControlSite::GetEventIID.md)|Ruft die ID einer Ereignisschnittstelle für ein gehostetes Steuerelement ab.|  
|[COleControlSite::GetExStyle](../Topic/COleControlSite::GetExStyle.md)|Ruft die erweiterten Formate der Steuerungssite ab.|  
|[COleControlSite::GetProperty](../Topic/COleControlSite::GetProperty.md)|Ruft eine bestimmte Eigenschaft des gehosteten Steuerelements ab.|  
|[COleControlSite::GetStyle](../Topic/COleControlSite::GetStyle.md)|Ruft die Formate der Steuerungssite ab.|  
|[COleControlSite::GetWindowText](../Topic/COleControlSite::GetWindowText.md)|Ruft den Text des gehosteten Steuerelements ab.|  
|[COleControlSite::InvokeHelper](../Topic/COleControlSite::InvokeHelper.md)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements.|  
|[COleControlSite::InvokeHelperV](../Topic/COleControlSite::InvokeHelperV.md)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements mit einer Liste von variablen Argumenten auf.|  
|[COleControlSite::IsDefaultButton](../Topic/COleControlSite::IsDefaultButton.md)|Bestimmt, ob das Steuerelement die Standardschaltfläche im ist.|  
|[COleControlSite::IsWindowEnabled](../Topic/COleControlSite::IsWindowEnabled.md)|Überprüft den sichtbaren Zustand der Steuerungssite.|  
|[COleControlSite::ModifyStyle](../Topic/COleControlSite::ModifyStyle.md)|Ändert die aktuellen erweiterten Formate der Steuerungssite.|  
|[COleControlSite::ModifyStyleEx](../Topic/COleControlSite::ModifyStyleEx.md)|Ändert die aktuellen Formate der Steuerungssite.|  
|[COleControlSite::MoveWindow](../Topic/COleControlSite::MoveWindow.md)|Ändert die Position der Steuerungssite.|  
|[COleControlSite::QuickActivate](../Topic/COleControlSite::QuickActivate.md)|Quick aktiviert das gehostete Steuerelement.|  
|[COleControlSite::SafeSetProperty](../Topic/COleControlSite::SafeSetProperty.md)|Legt eine Eigenschaft oder eine Methode des Steuerelements ohne Möglichkeit des Auslösens einer Ausnahme fest.|  
|[COleControlSite::SetDefaultButton](../Topic/COleControlSite::SetDefaultButton.md)|Legt die Standardschaltfläche im fest.|  
|[COleControlSite::SetDlgCtrlID](../Topic/COleControlSite::SetDlgCtrlID.md)|Ruft den Bezeichner des Steuerelements ab.|  
|[COleControlSite::SetFocus](../Topic/COleControlSite::SetFocus.md)|Legt den Fokus auf den Steuerungssiten fest.|  
|[COleControlSite::SetProperty](../Topic/COleControlSite::SetProperty.md)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements fest.|  
|[COleControlSite::SetPropertyV](../Topic/COleControlSite::SetPropertyV.md)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements mit einer variablen Liste von Argumenten fest.|  
|[COleControlSite::SetWindowPos](../Topic/COleControlSite::SetWindowPos.md)|Legt die Position der Steuerungssite fest.|  
|[COleControlSite::SetWindowText](../Topic/COleControlSite::SetWindowText.md)|Legt den Text des gehosteten Steuerelements fest.|  
|[COleControlSite::ShowWindow](../Topic/COleControlSite::ShowWindow.md)|Zeigt die Steuerungssite oder aus.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](../Topic/COleControlSite::GetControlInfo.md)|Ruft Tastaturinformationen und \-mnemotechnik für das gehostete Steuerelement.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleControlSite::m\_bIsWindowless](../Topic/COleControlSite::m_bIsWindowless.md)|Bestimmt, ob das gehostete Steuerelement ein fensterloses Steuerelement ist.|  
|[COleControlSite::m\_ctlInfo](../Topic/COleControlSite::m_ctlInfo.md)|Enthält Informationen über Tastatureingaben für das Steuerelement.|  
|[COleControlSite::m\_dwEventSink](../Topic/COleControlSite::m_dwEventSink.md)|Das Cookie des Verbindungspunkts des Steuerelements.|  
|[COleControlSite::m\_dwMiscStatus](../Topic/COleControlSite::m_dwMiscStatus.md)|Die verschiedenen Zustände für das gehostete Steuerelement.|  
|[COleControlSite::m\_dwPropNotifySink](../Topic/COleControlSite::m_dwPropNotifySink.md)|Das `IPropertyNotifySink` Cookie des Steuerelements.|  
|[COleControlSite::m\_dwStyle](../Topic/COleControlSite::m_dwStyle.md)|Die Stile des gehosteten Steuerelements.|  
|[COleControlSite::m\_hWnd](../Topic/COleControlSite::m_hWnd.md)|Das Handle der Steuerungssite.|  
|[COleControlSite::m\_iidEvents](../Topic/COleControlSite::m_iidEvents.md)|Die ID der Ereignisschnittstelle für das gehostete Steuerelement.|  
|[COleControlSite::m\_nID](../Topic/COleControlSite::m_nID.md)|Die ID des gehosteten Steuerelements.|  
|[COleControlSite::m\_pActiveObject](../Topic/COleControlSite::m_pActiveObject.md)|Ein Zeiger auf `IOleInPlaceActiveObject`\-Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m\_pCtrlCont](../Topic/COleControlSite::m_pCtrlCont.md)|Der Container des gehosteten Steuerelements.|  
|[COleControlSite::m\_pInPlaceObject](../Topic/COleControlSite::m_pInPlaceObject.md)|Ein Zeiger auf `IOleInPlaceObject`\-Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m\_pObject](../Topic/COleControlSite::m_pObject.md)|Ein Zeiger auf die `IOleObjectInterface` Oberfläche des Steuerelements.|  
|[COleControlSite::m\_pWindowlessObject](../Topic/COleControlSite::m_pWindowlessObject.md)|Ein Zeiger auf die `IOleInPlaceObjectWindowless` Oberfläche des Steuerelements.|  
|[COleControlSite::m\_pWndCtrl](../Topic/COleControlSite::m_pWndCtrl.md)|Ein Zeiger auf Fensterobjekt für das gehostete Steuerelement.|  
|[COleControlSite::m\_rect](../Topic/COleControlSite::m_rect.md)|Die Dimensionen der Steuerungssite.|  
  
## Hinweise  
 Diese Unterstützung ist das primäre Mittel, durch die ein eingebettetes ActiveX\-Steuerelement Informationen über den Speicherort und den Umfang der Anzeigensite, des Monikers, der Benutzeroberfläche, der Ambient\-Eigenschaften und einer anderen Ressourcen, die vom Container bereitgestellt sein.  `COleControlSite` implementiert vollständig [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), **IBoundObjectSite**, **INotifyDBEvents**, [IRowSetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)\-Schnittstellen.  Außerdem wird die IDispatch\-Schnittstelle \(Unterstützung für Ambient\-Eigenschaften und Ereignissenken eingefügt\) auch implementiert.  
  
 Um eine ActiveX\-Steuerelement\-Site mithilfe `COleControlSite` zu erstellen, leiten Sie eine Klasse von `COleControlSite`.  In dem `CWnd` von abgeleitete Klasse für die Überschreibung des Containers \(beispielsweise, das Dialogfeld\) die **CWnd::CreateControlSite**\-Funktion.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## Anforderungen  
 **Header:** afxocc.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)