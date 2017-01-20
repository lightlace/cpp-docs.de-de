---
title: "CMFCTabCtrl Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabCtrl class"
  - "CMFCTabCtrl constructor"
  - "CMFCTabCtrl::GetTabFromPoint method"
  - "CMFCTabCtrl::IsPtInTabArea method"
  - "CMFCTabCtrl::MoveTab method"
  - "CMFCTabCtrl::PreTranslateMessage method"
  - "CMFCTabCtrl::RecalcLayout method"
  - "CMFCTabCtrl::SwapTabs method"
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt `CMFCTabCtrl`\-Funktionalität für ein Tab\-Steuerelement bereit.  Das Tab\-Steuerelement zeigt ein andockbares Fenster mit gleichmäßige oder dreidimensionalen Registerkarten an der oberen oder unteren Rand an an.  Die Registerkarten können Text und ein Bild anzeigen und können Farbe ändern, wenn aktiv.  
  
## Syntax  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Standardkonstruktor.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](../Topic/CMFCTabCtrl::ActivateMDITab.md)|Zeigt die angegebene Registerkarte des aktuellen Tab\-Steuerelements an und legt den Fokus auf dieser Registerkarte fest.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](../Topic/CMFCTabCtrl::AllowDestroyEmptyTabbedPane.md)||  
|[CMFCTabCtrl::AutoSizeWindow](../Topic/CMFCTabCtrl::AutoSizeWindow.md)|Gibt an, ob das Framework, den Clientbereich aller Tab\-Steuerelement\-Fenster Größe ändern wenn ein Benutzeroberflächenelement der Tab\-Steuerelement\-Änderungen ist.|  
|[CMFCTabCtrl::CalcRectEdit](../Topic/CMFCTabCtrl::CalcRectEdit.md)|Entlüftet die Größe des angegebenen Registerkartenbereichs.  \(Überschreibungen `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md)|Erstellt das Tab\-Steuerelement und fügt es dem `CMFCTabCtrl`\-Objekt.|  
|`CMFCTabCtrl::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](../Topic/CMFCTabCtrl::EnableActiveTabCloseButton.md)|Zeigt an oder blendet eine Schaltfläche zum **X**\(\) auf der aktiven Registerkarte aus.|  
|[CMFCTabCtrl::EnableInPlaceEdit](../Topic/CMFCTabCtrl::EnableInPlaceEdit.md)|Aktiviert oder deaktiviert bearbeitbare Registerkartenbezeichnungen.  \(Überschreibungen [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](../Topic/CMFCTabCtrl::EnableTabDocumentsMenu.md)|Ersetzt zwei Schaltflächen, die die Fensterregisterkarten mit einer Schaltfläche wechseln, die ein Menü von Fenstern im Registerkartenformat öffnet.|  
|[CMFCTabCtrl::EnsureVisible](../Topic/CMFCTabCtrl::EnsureVisible.md)|Stellt sicher, dass eine Registerkarte sichtbar ist.|  
|[CMFCTabCtrl::GetDocumentIcon](../Topic/CMFCTabCtrl::GetDocumentIcon.md)|Ruft das Symbol ab, das einer Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCTabCtrl::GetFirstVisibleTabNum.md)|Ruft den Index der ersten Registerkarte ab, die im aktuellen Tab\-Steuerelement sichtbar ist.|  
|[CMFCTabCtrl::GetResizeMode](../Topic/CMFCTabCtrl::GetResizeMode.md)|Ruft einen Wert ab, der angibt, wie das aktuelle Tab\-Steuerelement Größe geändert werden kann.|  
|[CMFCTabCtrl::GetScrollBar](../Topic/CMFCTabCtrl::GetScrollBar.md)|Ruft einen Zeiger auf das Bildlaufleistenobjekt ab, das dem Tab\-Steuerelement zugeordnet ist.|  
|[CMFCTabCtrl::GetTabArea](../Topic/CMFCTabCtrl::GetTabArea.md)|Ruft das umschließende Rechteck des Registerkartenetikettbereichs oben oder unteren Rand des Tab\-Steuerelements ab.  \(Überschreibungen [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCTabCtrl::GetTabFromPoint`|Ruft die Registerkarte ab, die einen angegebenen Punkt enthält.  \(Überschreibungen [CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md).\)|  
|[CMFCTabCtrl::GetTabMaxWidth](../Topic/CMFCTabCtrl::GetTabMaxWidth.md)|Ruft die maximale Breite einer Registerkarte ab.|  
|[CMFCTabCtrl::GetTabsHeight](../Topic/CMFCTabCtrl::GetTabsHeight.md)|Ruft die Höhe des Registerkartenbereichs des aktuellen Tab\-Steuerelements ab.|  
|[CMFCTabCtrl::GetTabsRect](../Topic/CMFCTabCtrl::GetTabsRect.md)|Ruft ein Rechteck ab, das den Registerkartenbereich des aktuellen Tab\-Steuerelements begrenzt.  \(Überschreibungen [CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md).\)|  
|`CMFCTabCtrl::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCTabCtrl::GetWndArea](../Topic/CMFCTabCtrl::GetWndArea.md)|Ruft die Begrenzung des Clientbereichs des aktuellen Tab\-Steuerelements ab.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](../Topic/CMFCTabCtrl::HideActiveWindowHorzScrollBar.md)|Blendet die horizontale Bildlaufleiste ggf. des aktiven Fensters aus.|  
|[CMFCTabCtrl::HideInactiveWindow](../Topic/CMFCTabCtrl::HideInactiveWindow.md)|Gibt an, ob das Framework, inaktive Tab\-Steuerelement\-Fenster anzuzeigen.|  
|[CMFCTabCtrl::HideNoTabs](../Topic/CMFCTabCtrl::HideNoTabs.md)|Aktiviert oder deaktiviert das Zeichnen des Registerkartenbereichs, wenn keine sichtbaren Registerkarten gibt.|  
|[CMFCTabCtrl::HideSingleTab](../Topic/CMFCTabCtrl::HideSingleTab.md)|Aktiviert oder deaktiviert das Zeichnen einer Registerkarte, wenn es ein einzelnes Fenster im Registerkartenformat gibt.  \(Überschreibungen [CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md).\)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](../Topic/CMFCTabCtrl::IsActiveInMDITabGroup.md)|Gibt an, ob die aktuelle Registerkarte eines Tab\-Steuerelements die aktive Registerkarte in einer MDI \(Multiple Document Interface\-Registerkartengruppe ist.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](../Topic/CMFCTabCtrl::IsActiveTabBoldFont.md)|Gibt an, ob der Text der aktiven Registerkarte mit fett formatierter Schrift angezeigt wird.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](../Topic/CMFCTabCtrl::IsActiveTabCloseButton.md)|Gibt an, ob die Schaltfläche Schließen \(**X**\) auf einer aktiven Registerkarte oder der rechten oberen Ecke des Registerkartenbereichs angezeigt wird.|  
|[CMFCTabCtrl::IsDrawFrame](../Topic/CMFCTabCtrl::IsDrawFrame.md)|Gibt an, ob das Fenster im Registerkartenformat Framerechteck um eingebettete Bereiche zeichnet.|  
|[CMFCTabCtrl::IsFlatFrame](../Topic/CMFCTabCtrl::IsFlatFrame.md)|Gibt an, ob die Rahmen um den Registerkartenbereich flach oder 3D sind.|  
|[CMFCTabCtrl::IsFlatTab](../Topic/CMFCTabCtrl::IsFlatTab.md)|Gibt an, ob die Darstellung der Registerkarten im aktuellen Tab\-Steuerelement oder nicht flach ist.|  
|[CMFCTabCtrl::IsLeftRightRounded](../Topic/CMFCTabCtrl::IsLeftRightRounded.md)|Gibt an, ob die Darstellung der linken und rechten Seite einer Registerkarte im aktuellen Tab\-Steuerelement gerundet.|  
|[CMFCTabCtrl::IsMDITabGroup](../Topic/CMFCTabCtrl::IsMDITabGroup.md)|Gibt an, ob das aktuelle Tab\-Steuerelement im Clientbereich eines Multiple Document Interface\-Fensters enthalten ist.|  
|[CMFCTabCtrl::IsOneNoteStyle](../Topic/CMFCTabCtrl::IsOneNoteStyle.md)|Gibt an, ob das aktuelle Tab\-Steuerelement im Stil von Microsoft OneNote angezeigt wird.|  
|`CMFCTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb des Registerkartenbereichs ist.  \(Überschreibungen [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|[CMFCTabCtrl::IsSharedScroll](../Topic/CMFCTabCtrl::IsSharedScroll.md)|Gibt an, ob das aktuelle Tab\-Steuerelement eine Bildlaufleiste verfügt, die Registerkarten als Gruppe einen Bildlauf durchführen kann.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](../Topic/CMFCTabCtrl::IsTabDocumentsMenu.md)|Gibt an, ob das Tab\-Steuerelement Bildlaufschaltflächen oder eine Schaltfläche angezeigt wird, die ein Menü von Fenstern im Registerkartenformat anzeigt.|  
|[CMFCTabCtrl::IsVS2005Style](../Topic/CMFCTabCtrl::IsVS2005Style.md)|Gibt an, ob Registerkarten im Format Visual Studio .NET 2005. angezeigt werden.|  
|[CMFCTabCtrl::ModifyTabStyle](../Topic/CMFCTabCtrl::ModifyTabStyle.md)|Gibt die Darstellung von Registerkarten im aktuellen Tab\-Steuerelement auf.|  
|`CMFCTabCtrl::MoveTab`|Verschiebt eine Registerkarte auf eine andere Tabstoppposition.  \(Überschreibungen [CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md).\)|  
|[CMFCTabCtrl::OnDragEnter](../Topic/CMFCTabCtrl::OnDragEnter.md)|Aufgerufen vom Framework, wenn der Cursor zuerst in das Tab\-Steuerelement\-Fenster gezogen wird.|  
|[CMFCTabCtrl::OnDragOver](../Topic/CMFCTabCtrl::OnDragOver.md)|Aufgerufen vom Framework während eines Ziehvorgangs, wenn die Maus über das Ablagezielfenster bewegt wird.  \(Überschreibungen [CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md).\)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](../Topic/CMFCTabCtrl::OnShowTabDocumentsMenu.md)|Zeigt ein Popupmenü von Fenstern im Registerkartenformat, wartet, bis der Benutzer eine Registerkarte auswählt, und macht die ausgewählte Registerkarte die aktive Registerkarte.|  
|`CMFCTabCtrl::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md).\)|  
|`CMFCTabCtrl::RecalcLayout`|Berechnet das interne Layout des Tab\-Steuerelements neu.  \(Überschreibungen [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](../Topic/CMFCTabCtrl::SetActiveInMDITabGroup.md)|Legt die aktuelle Registerkarte einem Registersteuerelement wie die aktive Registerkarte in einer MDI \(Multiple Document Interface\-Registerkartengruppe fest.|  
|[CMFCTabCtrl::SetActiveTab](../Topic/CMFCTabCtrl::SetActiveTab.md)|Aktiviert eine Registerkarte.  \(Überschreibungen [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](../Topic/CMFCTabCtrl::SetActiveTabBoldFont.md)|Aktiviert oder Sperrungsgebrauch von fett formatierter Schrift auf aktiven Registerkarten.|  
|[CMFCTabCtrl::SetDrawFrame](../Topic/CMFCTabCtrl::SetDrawFrame.md)|Aktiviert oder deaktiviert drawinga Framerechteck um eine eingebettete Leiste.|  
|[CMFCTabCtrl::SetFlatFrame](../Topic/CMFCTabCtrl::SetFlatFrame.md)|Gibt an, ob eine Ebene oder 3D\-Frame um den Registerkartenbereich zeichnet.|  
|[CMFCTabCtrl::SetImageList](../Topic/CMFCTabCtrl::SetImageList.md)|Gibt eine Bildliste an.  \(Überschreibungen [CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md).\)|  
|[CMFCTabCtrl::SetResizeMode](../Topic/CMFCTabCtrl::SetResizeMode.md)|Gibt, an, wie das aktuelle Tab\-Steuerelement Größe geändert werden kann und zeigt dann das Steuerelement erneut an.|  
|[CMFCTabCtrl::SetTabMaxWidth](../Topic/CMFCTabCtrl::SetTabMaxWidth.md)|Gibt die maximale Registerkartenbreite in ein Fenster im Registerkartenformat an.|  
|[CMFCTabCtrl::StopResize](../Topic/CMFCTabCtrl::StopResize.md)|Beendet die aktuelle Größe ändern Vorgang auf dem Tab\-Steuerelement.|  
|`CMFCTabCtrl::SwapTabs`|Vertauscht ein Paar Registerkarten aus.  \(Überschreibungen [CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md).\)|  
|[CMFCTabCtrl::SynchronizeScrollBar](../Topic/CMFCTabCtrl::SynchronizeScrollBar.md)|Zeichnet eine horizontale Bildlaufleiste auf einem Tab\-Steuerelement, das flache Registerkarten anzeigt.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTabCtrl::m\_bEnableActivate](../Topic/CMFCTabCtrl::m_bEnableActivate.md)|Verhindert die aktive Ansicht an verlierendem den Fokus, wenn eine neue Registerkarte eingefügt und aktiviert ist.|  
  
## Hinweise  
 Die Klasse einzelne `CMFCTabCtrl`:  
  
-   Tab\-Steuerelement\-Formate, die 3D, Ebene und Ebene einer freigegebenen horizontalen Bildlaufleiste enthalten.  
  
-   Registerkarten oben isoliert oder den unteren Rand des Fensters.  
  
-   Registerkarten, die Text, Bilder oder Text und Bilder anzeigen.  
  
-   Registerkarten, die Farbe ändern, wenn die Registerkarte aktiv ist.  
  
-   Rahmengrößenänderungen für justierbare Registerkarten.  
  
-   Abnehmbare Fenster im Registerkartenformat.  
  
 Die `CMFCTabCtrl`\-Klasse kann mit einem Dialogfeld verwendet werden, jedoch wird für Anwendungen geeignet, die andockbare Steuerleisten wie [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] und [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] verwenden.  Weitere Informationen finden Sie unter [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).  
  
 Führen Sie folgende Schritte aus, um ein in der Größe veränderbares, Andockes Registersteuerelement in der Anwendung hinzuzufügen:  
  
1.  Erstellen Sie eine Instanz von [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Rufen Sie [CDockablePane::Create](../Topic/CDockablePane::Create.md) auf.  
  
3.  Verwenden Sie [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) oder [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md), um neue Registerkarten hinzuzufügen.  
  
4.  Rufen Sie [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) auf, damit das aktuelle andockbare Tab\-Steuerelement am Hauptrahmenfenster andocken kann.  
  
5.  Rufen Sie [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) auf, um das Fenster im Registerkartenformat am Hauptframes anzudocken.  
  
 Ein Beispiel, wie ein Fenster im Registerkartenformat als andockbare Symbolleisten, finden Sie unter [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) erstellt wird.  Um `CMFCTabCtrl` als NichtAndocken Steuerelement zu verwenden, erstellen Sie ein `CMFCTabCtrl`\-Objekt und rufen Sie dann [CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md) auf.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der `CMFCTabCtrl`\-Klasse verwendet, um ein `CMFCTabCtrl`\-Objekt zu konfigurieren.  Im Beispiel wird erläutert, wie Sie eine Registerkarte hinzufügt, die Schaltfläche Schließen auf der aktiven Registerkarte angezeigt wird, Registerkartenbezeichnungen bearbeitbare aktiviert und ein Popupmenü von Fensterbezeichnungen im Registerkartenformat anzeigt.  Dieses Beispiel ist Teil [Zustands\-Auflistungsbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_StateCollection#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StateCollection#1)]  
[!CODE [NVC_MFC_StateCollection#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StateCollection#3)]  
  
## Anforderungen  
 **Header:** afxtabctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)