---
title: "CMFCToolBarEditBoxButton Class"
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
  - "OnDrawOnCustomizeList"
  - "OnDraw"
  - "CMFCToolBarEditBoxButton::OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton.SetACCData"
  - "CMFCToolBarEditBoxButton::OnDraw"
  - "OnCalculateSize"
  - "SetACCData"
  - "CMFCToolBarEditBoxButton"
  - "CMFCToolBarEditBoxButton::SetACCData"
  - "CMFCToolBarEditBoxButton::Serialize"
  - "CMFCToolBarEditBoxButton.OnDraw"
  - "CMFCToolBarEditBoxButton.OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton::OnCalculateSize"
  - "Serialize"
  - "CMFCToolBarEditBoxButton.Serialize"
  - "CMFCToolBarEditBoxButton.OnCalculateSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarEditBoxButton class"
  - "OnCalculateSize method"
  - "OnDraw method"
  - "OnDrawOnCustomizeList method"
  - "Serialize method"
  - "SetACCData method"
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarEditBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleistenschaltfläche, die ein Bearbeitungssteuerelement \([CEdit Class](../../mfc/reference/cedit-class.md)\) enthält.  
  
## Syntax  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](../Topic/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton.md)|Erstellt ein `CMFCToolBarEditBoxButton`\-Objekt.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](../Topic/CMFCToolBarEditBoxButton::CanBeStretched.md)|Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung strecken kann.  \(Überschreibungen [CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md).\)|  
|[CMFCToolBarEditBoxButton::CopyFrom](../Topic/CMFCToolBarEditBoxButton::CopyFrom.md)|Kopiert die Eigenschaften einer anderen Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.  \(Überschreibungen [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](../Topic/CMFCToolBarEditBoxButton::CreateEdit.md)|Erstellt ein neues Bearbeitungssteuerelement in der Schaltfläche.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarEditBoxButton::GetByCmd](../Topic/CMFCToolBarEditBoxButton::GetByCmd.md)|Ruft das erste Objekt `CMFCToolBarEditBoxButton` in der Anwendung ab, die die angegebene ID besitzt Befehl|  
|[CMFCToolBarEditBoxButton::GetContentsAll](../Topic/CMFCToolBarEditBoxButton::GetContentsAll.md)|Ruft den Text des ersten Eingabefeldsymbolleisten\-steuerelements ab, das über die angegebene ID besitzt Befehl|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](../Topic/CMFCToolBarEditBoxButton::GetContextMenuID.md)|Ruft das Ressourcen\-ID des Kontextmenüs ab, das mit der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](../Topic/CMFCToolBarEditBoxButton::GetEditBorder.md)|Ruft das umschließende Rechteck des Bearbeitungsteils der Eingabefeldschaltfläche ab.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](../Topic/CMFCToolBarEditBoxButton::GetEditBox.md)|Gibt einen Zeiger auf das Bearbeitungssteuerelement zurück, das in der Schaltfläche eingebettet ist.|  
|[CMFCToolBarEditBoxButton::GetHwnd](../Topic/CMFCToolBarEditBoxButton::GetHwnd.md)|Ruft das Fensterhandle ab, das der Symbolleisten\-Schaltfläche zugeordnet ist.  \(Überschreibungen [CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md).\)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](../Topic/CMFCToolBarEditBoxButton::GetInvalidateRect.md)|Ruft den des Innenbereichs der Schaltfläche ab, die neu gezeichnet werden muss.  \(Überschreibungen [CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md).\)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](../Topic/CMFCToolBarEditBoxButton::HaveHotBorder.md)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt.  \(Überschreibungen [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](../Topic/CMFCToolBarEditBoxButton::IsFlatMode.md)|Bestimmt, ob Eingabefeldschaltflächen ein gedrehtes Format haben.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](../Topic/CMFCToolBarEditBoxButton::NotifyCommand.md)|Gibt an, ob die Schaltfläche die [Da WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md).\)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](../Topic/CMFCToolBarEditBoxButton::OnAddToCustomizePage.md)|Aufgerufen vom Framework, wenn die Schaltfläche zu einem Dialogfeld **Anpassen** hinzugefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md).\)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Aufgerufen vom Framework, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den angedockten Zustand zu berechnen.  \(Überschreibungen [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](../Topic/CMFCToolBarEditBoxButton::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.  \(Überschreibungen [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarEditBoxButton::OnClick](../Topic/CMFCToolBarEditBoxButton::OnClick.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Maustaste klickt.  \(Überschreibungen [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](../Topic/CMFCToolBarEditBoxButton::OnCtlColor.md)|Aufgerufen vom Framework, wenn die Elemente eine Symbolleiste `WM_CTLCOLOR` Meldung verarbeitet.  \(Überschreibungen [CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md).\)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Aufgerufen durch das Framework, um die Schaltfläche mithilfe der angegebenen Formate und der Optionen zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Aufgerufen durch das Framework, um die Schaltfläche im Bereich **Befehle** des Dialogfelds **Anpassen** zu zeichnen.  \(Überschreibungen [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](../Topic/CMFCToolBarEditBoxButton::OnGlobalFontsChanged.md)|Aufgerufen vom Framework, wenn die globale Schriftart geändert hat.  \(Überschreibungen [CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md).\)|  
|[CMFCToolBarEditBoxButton::OnMove](../Topic/CMFCToolBarEditBoxButton::OnMove.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste bewegt.  \(Überschreibungen [CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md).\)|  
|[CMFCToolBarEditBoxButton::OnShow](../Topic/CMFCToolBarEditBoxButton::OnShow.md)|Aufgerufen vom Framework, wenn die Schaltfläche sichtbar oder nicht sichtbar ist.  \(Überschreibungen [CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md).\)|  
|[CMFCToolBarEditBoxButton::OnSize](../Topic/CMFCToolBarEditBoxButton::OnSize.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste ändert, ihre Ursachen der Größe und der Position und dieser Änderung, die die Schaltfläche zur Änderung skalieren.  \(Überschreibungen [CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](../Topic/CMFCToolBarEditBoxButton::OnUpdateToolTip.md)|Aufgerufen vom Framework, wenn die Elemente Symbolleiste den QuickInfo\-Text aktualisiert.  \(Überschreibungen [CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md).\)|  
|`CMFCToolBarEditBoxButton::Serialize`|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv.  \(Überschreibungen [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Füllt das bereitgestellte `CAccessibilityData`\-Objekt mit Barrierefreiheitsdaten von der Symbolleisten\-Schaltfläche auf.  \(Überschreibungen [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](../Topic/CMFCToolBarEditBoxButton::SetContents.md)|Legt den Text im Bearbeitungssteuerelement der Schaltfläche fest.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](../Topic/CMFCToolBarEditBoxButton::SetContentsAll.md)|Sucht die Bearbeitungssteuerelementschaltfläche, die eine angegebene Befehls\-ID verfügt, und der Text im Bearbeitungssteuerelement dieser Schaltfläche fest.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](../Topic/CMFCToolBarEditBoxButton::SetContextMenuID.md)|Gibt das Ressourcen\-ID des Kontextmenüs an, das mit der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](../Topic/CMFCToolBarEditBoxButton::SetFlatMode.md)|Gibt die flache Darstellung von Eingabefeldschaltflächen in der Anwendung.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](../Topic/CMFCToolBarEditBoxButton::SetStyle.md)|Gibt das Format der Schaltfläche an.  \(Überschreibungen [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).\)|  
  
## Hinweise  
 Um eine Eingabefeldschaltfläche einer Symbolleiste hinzuzufügen, führen Sie folgende Schritte aus:  
  
 1.  Reservieren Sie ein blindes Ressourcen\-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2.  Konstruieren Sie ein `CMFCToolBarEditBoxButton`\-Objekt.  
  
 3.  Im Meldungshandler, der die `AFX_WM_RESETTOOLBAR` Meldung verarbeitet, ersetzen Sie die blinde Schaltfläche durch die neue Kombinationsfeldschaltfläche, indem Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) verwenden.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCToolBarEditBoxButton` verwendet.  Im Beispiel wird gezeigt, wie, dass ein Benutzer die Schaltfläche während der Anpassung strecken, angeben kann, dass ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt, den Text im Textfeld\-Steuerelement festgelegt hat, die flache Darstellung von Eingabefeldschaltflächen in der Anwendung an und das Format eines Symbolleisteneingabefeldsteuerelements angibt.  
  
 [!CODE [NVC_MFC_RibbonApp#40](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#40)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbareditboxbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)