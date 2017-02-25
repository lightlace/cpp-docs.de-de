---
title: "CMFCToolBarDateTimeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "OnDrawOnCustomizeList"
  - "CMFCToolBarDateTimeCtrl::OnDraw"
  - "OnDraw"
  - "CMFCToolBarDateTimeCtrl.Serialize"
  - "CMFCToolBarDateTimeCtrl.OnSize"
  - "CMFCToolBarDateTimeCtrl.OnDrawOnCustomizeList"
  - "OnSize"
  - "OnCalculateSize"
  - "CMFCToolBarDateTimeCtrl"
  - "CMFCToolBarDateTimeCtrl::OnCalculateSize"
  - "SetStyle"
  - "CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList"
  - "CMFCToolBarDateTimeCtrl.OnDraw"
  - "CMFCToolBarDateTimeCtrl.SetStyle"
  - "CMFCToolBarDateTimeCtrl::SetStyle"
  - "CMFCToolBarDateTimeCtrl.OnCalculateSize"
  - "CMFCToolBarDateTimeCtrl::Serialize"
  - "CMFCToolBarDateTimeCtrl::OnSize"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarDateTimeCtrl class"
  - "OnCalculateSize method"
  - "OnDraw method"
  - "OnDrawOnCustomizeList method"
  - "OnSize method"
  - "Serialize method"
  - "SetStyle method"
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCToolBarDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Steuerelement für die Datums\- und Zeitauswahl enthält.  
  
## Syntax  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](../Topic/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl.md)|Erstellt ein `CMFCToolBarDateTimeCtrl`\-Objekt.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](../Topic/CMFCToolBarDateTimeCtrl::CanBeStretched.md)|Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung strecken kann.  \(Überschreibungen [CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md).\)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](../Topic/CMFCToolBarDateTimeCtrl::CopyFrom.md)|Kopiert die Eigenschaften einer anderen Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.  \(Überschreibungen [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Für die zukünftige Verwendung reserviert.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|Kopien Text aus der Symbolleisten\-Schaltfläche zu einem Menü.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](../Topic/CMFCToolBarDateTimeCtrl::GetByCmd.md)|Ruft das erste Objekt `CMFCToolBarDateTimeCtrl` in der Anwendung ab, die die angegebene ID besitzt Befehl|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](../Topic/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl.md)|Gibt einen Zeiger auf das Steuerelement für die Datums\- und Zeitauswahl zurück.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](../Topic/CMFCToolBarDateTimeCtrl::GetHwnd.md)|Ruft das Fensterhandle ab, das der Symbolleisten\-Schaltfläche zugeordnet ist.  \(Überschreibungen [CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md).\)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCToolBarDateTimeCtrl::GetTime](../Topic/CMFCToolBarDateTimeCtrl::GetTime.md)|Ruft die ausgewählte Zeit von einem Steuerelement für die Datums\- und Zeitauswahl ab und legt sie in eine angegebene [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)\-Struktur ein.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](../Topic/CMFCToolBarDateTimeCtrl::GetTimeAll.md)|Gibt die Zeit der ausgewählte Steuerelement für die Zeitauswahl\-Schaltfläche zurück, die eine angegebene Befehl ID besitzt|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](../Topic/CMFCToolBarDateTimeCtrl::HaveHotBorder.md)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.  \(Überschreibungen [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](../Topic/CMFCToolBarDateTimeCtrl::NotifyCommand.md)|Gibt an, ob die Schaltfläche die [Da WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](../Topic/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage.md)|Aufgerufen vom Framework, wenn die Schaltfläche zu einem Dialogfeld **Anpassen** hinzugefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Aufgerufen vom Framework, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den angedockten Zustand zu berechnen.  \(Überschreibungen [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](../Topic/CMFCToolBarDateTimeCtrl::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnClick](../Topic/CMFCToolBarDateTimeCtrl::OnClick.md)|Aufgerufen vom Framework, wenn der Benutzer auf das Steuerelement klickt.  \(Überschreibungen [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](../Topic/CMFCToolBarDateTimeCtrl::OnCtlColor.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_CTLCOLOR` Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Aufgerufen durch das Framework, um die Schaltfläche mithilfe der angegebenen Formate und der Optionen zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Aufgerufen durch das Framework, um die Schaltfläche im Bereich **Befehle** des Dialogfelds **Anpassen** zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](../Topic/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged.md)|Aufgerufen vom Framework, wenn die globale Schriftart geändert hat.  \(Überschreibungen [CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnMove](../Topic/CMFCToolBarDateTimeCtrl::OnMove.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste bewegt.  \(Überschreibungen [CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnShow](../Topic/CMFCToolBarDateTimeCtrl::OnShow.md)|Aufgerufen vom Framework, wenn die Schaltfläche sichtbar oder nicht sichtbar ist.  \(Überschreibungen [CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Aufgerufen vom Framework, wenn die Elemente Symbolleiste ändert, ihre Ursachen der Größe und der Position und dieser Änderung, die die Schaltfläche zur Änderung skalieren.  \(Überschreibungen [CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](../Topic/CMFCToolBarDateTimeCtrl::OnUpdateToolTip.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste den QuickInfo\-Text aktualisiert.  \(Überschreibungen [CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md).\)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv, \(Überschreibungen [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Legt den Stil der Symbolleisten\-Schaltfläche fest.  \(Überschreibungen [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).\)|  
|[CMFCToolBarDateTimeCtrl::SetTime](../Topic/CMFCToolBarDateTimeCtrl::SetTime.md)|Legt die Zeit und das Datum im \- Steuerelement für die Zeitauswahl fest.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](../Topic/CMFCToolBarDateTimeCtrl::SetTimeAll.md)|Legt die Zeit und das Datum in allen Instanzen des Steuerelements für die Zeitauswahl fest, die eine angegebene Befehl ID haben|  
  
## Hinweise  
 Ein Beispiel, wie ein Steuerelement für die Datums\- und Zeitauswahl, finden Sie das ToolbarDateTimePicker\-Beispiel zu projizieren verwendet.  Informationen darüber, wie Steuerschaltflächen Symbolleisten, finden Sie unter [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md) hinzugefügt wird.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbardatetimectrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)