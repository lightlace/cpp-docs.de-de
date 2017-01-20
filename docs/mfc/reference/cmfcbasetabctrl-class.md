---
title: "CMFCBaseTabCtrl Class"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCBaseTabCtrl class"
ms.assetid: 7270c55f-6f6e-4dd2-b0d2-291afeac3882
caps.latest.revision: 41
caps.handback.revision: "29"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Basisfunktionalität für Fenster im Registerkartenformat.  
  
## Syntax  
  
```  
class CMFCBaseTabCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCBaseTabCtrl::AddIcon](../Topic/CMFCBaseTabCtrl::AddIcon.md)||  
|[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md)|Fügt eine neue Registerkarte dem Fenster im Registerkartenformat hinzu.|  
|[CMFCBaseTabCtrl::ApplyRestoredTabInfo](../Topic/CMFCBaseTabCtrl::ApplyRestoredTabInfo.md)||  
|[CMFCBaseTabCtrl::AutoDestroyWindow](../Topic/CMFCBaseTabCtrl::AutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::CalcRectEdit](../Topic/CMFCBaseTabCtrl::CalcRectEdit.md)||  
|[CMFCBaseTabCtrl::CleanUp](../Topic/CMFCBaseTabCtrl::CleanUp.md)||  
|[CMFCBaseTabCtrl::ClearImageList](../Topic/CMFCBaseTabCtrl::ClearImageList.md)||  
|[CMFCBaseTabCtrl::DetachTab](../Topic/CMFCBaseTabCtrl::DetachTab.md)|Trennt eine Registerkarte von einem Fenster im Registerkartenformat.|  
|[CMFCBaseTabCtrl::EnableActivateLastActive](../Topic/CMFCBaseTabCtrl::EnableActivateLastActive.md)||  
|[CMFCBaseTabCtrl::EnableAutoColor](../Topic/CMFCBaseTabCtrl::EnableAutoColor.md)|Aktiviert oder deaktiviert die automatische Registerkartenfärbung.|  
|[CMFCBaseTabCtrl::EnableCustomToolTips](../Topic/CMFCBaseTabCtrl::EnableCustomToolTips.md)|Aktiviert oder deaktiviert benutzerdefinierte  QuickInfos für Registerkarten.|  
|[CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md)|Aktiviert oder deaktiviert die direkte Bearbeitung von Registerkartenbezeichnungen.|  
|[CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md)|Aktiviert lösbare Registerkarten.|  
|[CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md)|Aktiviert oder deaktiviert die Option, mit der der Benutzer die Registerkartenreihenfolge mit der Maus ändern kann.|  
|[CMFCBaseTabCtrl::EnsureVisible](../Topic/CMFCBaseTabCtrl::EnsureVisible.md)|Scrollt durch die Registerkarten, bis die angegebene Registerkarte eingeblendet wird. Diese Methode hat keine Auswirkungen, wenn die angegebene Registerkarte bereits eingeblendet wird.|  
|[CMFCBaseTabCtrl::EnterDragMode](../Topic/CMFCBaseTabCtrl::EnterDragMode.md)||  
|[CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md)|Gibt einen Bereich zurück, der einen angegebenen Punkt enthält.|  
|[CMFCBaseTabCtrl::FireChangeActiveTab](../Topic/CMFCBaseTabCtrl::FireChangeActiveTab.md)||  
|[CMFCBaseTabCtrl::FireChangingActiveTab](../Topic/CMFCBaseTabCtrl::FireChangingActiveTab.md)||  
|[CMFCBaseTabCtrl::GetActiveTab](../Topic/CMFCBaseTabCtrl::GetActiveTab.md)|Gibt den Index der aktiven Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetActiveTabColor](../Topic/CMFCBaseTabCtrl::GetActiveTabColor.md)|Gibt die Hintergrundfarbe der aktiven Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::GetActiveTabTextColor.md)|Gibt die Textfarbe der aktiven Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetActiveWnd](../Topic/CMFCBaseTabCtrl::GetActiveWnd.md)|Gibt einen Zeiger auf die aktive Seite des Registerkarten\-Steuerelements zurück.|  
|[CMFCBaseTabCtrl::GetAutoColors](../Topic/CMFCBaseTabCtrl::GetAutoColors.md)|Gibt einen Verweis auf das Array von Farben zurück, das für die automatische Färbung verwendet wird.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTab](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTab.md)|Gibt einen Zeiger auf die erste eingeblendete Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTabNum.md)||  
|[CMFCBaseTabCtrl::GetHighlightedTab](../Topic/CMFCBaseTabCtrl::GetHighlightedTab.md)|Gibt den Index der aktuell hervorgehobenen Registerkarte.|  
|[CMFCBaseTabCtrl::GetImageList](../Topic/CMFCBaseTabCtrl::GetImageList.md)||  
|[CMFCBaseTabCtrl::GetImageSize](../Topic/CMFCBaseTabCtrl::GetImageSize.md)||  
|[CMFCBaseTabCtrl::GetLastVisibleTab](../Topic/CMFCBaseTabCtrl::GetLastVisibleTab.md)||  
|[CMFCBaseTabCtrl::GetLocation](../Topic/CMFCBaseTabCtrl::GetLocation.md)|Gibt eine Variable vom Datentyp LOCATION zurück, der angibt, wo der Registerkartenbereich in Bezug auf das Registerkarten\-Steuerelement positioniert ist. Beispielsweise oben oder unten.|  
|[CMFCBaseTabCtrl::GetMaxWindowSize](../Topic/CMFCBaseTabCtrl::GetMaxWindowSize.md)||  
|[CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md)|Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück. Die Position des Registerkartenbereichs wird mithilfe von Koordinaten definiert.|  
|[CMFCBaseTabCtrl::GetTabBkColor](../Topic/CMFCBaseTabCtrl::GetTabBkColor.md)|Gibt die Hintergrundfarbe der angegebenen Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetTabBorderSize](../Topic/CMFCBaseTabCtrl::GetTabBorderSize.md)|Gibt die Größe der Registerkartenrahmen im Registerkarten\-Steuerelement zurück.|  
|[CMFCBaseTabCtrl::GetTabByID](../Topic/CMFCBaseTabCtrl::GetTabByID.md)|Gibt den Index der Registerkarte zurück, die durch eine angegebene ID bestimmt wird.|  
|[CMFCBaseTabCtrl::GetTabCloseButton](../Topic/CMFCBaseTabCtrl::GetTabCloseButton.md)||  
|[CMFCBaseTabCtrl::GetTabFromHwnd](../Topic/CMFCBaseTabCtrl::GetTabFromHwnd.md)|Gibt den Index einer Registerkarte zurück, die ein angegebenes HWND\-Objekt enthält.|  
|[CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md)|Gibt die Registerkarte zurück, die einen angegebenen Punkt enthält.|  
|[CMFCBaseTabCtrl::GetTabFullWidth](../Topic/CMFCBaseTabCtrl::GetTabFullWidth.md)||  
|[CMFCBaseTabCtrl::GetTabHicon](../Topic/CMFCBaseTabCtrl::GetTabHicon.md)|Gibt das Symbol zurück, das der angegebenen Registerkarte zugeordnet ist.|  
|[CMFCBaseTabCtrl::GetTabID](../Topic/CMFCBaseTabCtrl::GetTabID.md)|Gibt mit dem Index der Registerkarte die ID einer Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetTabIcon](../Topic/CMFCBaseTabCtrl::GetTabIcon.md)|Gibt die Symbol\-ID für eine angegebene Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetTabLabel](../Topic/CMFCBaseTabCtrl::GetTabLabel.md)|Gibt den Text einer angegebene Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetTabRect](../Topic/CMFCBaseTabCtrl::GetTabRect.md)|Ruft die Größe und Position einer angegebenen Registerkarte ab.|  
|[CMFCBaseTabCtrl::GetTabsHeight](../Topic/CMFCBaseTabCtrl::GetTabsHeight.md)||  
|[CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md)||  
|[CMFCBaseTabCtrl::GetTabTextColor](../Topic/CMFCBaseTabCtrl::GetTabTextColor.md)|Gibt die Textfarbe einer angegebenen Registerkarte zurück.|  
|[CMFCBaseTabCtrl::GetTabWnd](../Topic/CMFCBaseTabCtrl::GetTabWnd.md)|Gibt den Zeiger auf einen Bereich zurück, der sich auf einer angegebenen Registerkartenseite befindet.|  
|[CMFCBaseTabCtrl::GetTabWndNoWrapper](../Topic/CMFCBaseTabCtrl::GetTabWndNoWrapper.md)|Gibt den direkten Zeiger auf ein Steuerelement zurück, das sich auf einer angegebenen Registerkartenseite befindet, auch wenn das Steuerelement über einen Wrapper verfügt.|  
|[CMFCBaseTabCtrl::GetTabsNum](../Topic/CMFCBaseTabCtrl::GetTabsNum.md)|Gibt die Anzahl der Registerkarten im Registerkarten\-Steuerelement zurück.|  
|[CMFCBaseTabCtrl::GetToolTipCtrl](../Topic/CMFCBaseTabCtrl::GetToolTipCtrl.md)|Gibt einen Verweis auf das QuickInfo\-Steuerelement zurück, das dem `CMFCBaseTabCtrl`\-Objekt zugeordnet ist.|  
|[CMFCBaseTabCtrl::GetVisibleTabsNum](../Topic/CMFCBaseTabCtrl::GetVisibleTabsNum.md)|Gibt die Anzahl eingeblendeter Registerkarten zurück.|  
|[CMFCBaseTabCtrl::HasImage](../Topic/CMFCBaseTabCtrl::HasImage.md)||  
|[CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md)|Legt eine Option fest, mit der eine Fensterregisterkarte ausgeblendet wird. Dies geschieht jedoch nur, wenn das Fenster im Registerkartenformat nur über eine eingeblendete Registerkarte verfügt.|  
|[CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md)|Fügt eine neue Registerkarte ein.|  
|[CMFCBaseTabCtrl::InvalidateTab](../Topic/CMFCBaseTabCtrl::InvalidateTab.md)||  
|[CMFCBaseTabCtrl::IsActiveTabCloseButton](../Topic/CMFCBaseTabCtrl::IsActiveTabCloseButton.md)||  
|[CMFCBaseTabCtrl::IsAutoColor](../Topic/CMFCBaseTabCtrl::IsAutoColor.md)|Gibt einen Wert zurück, der angibt, ob die automatische Färbung für das Fenster im Registerkartenformat aktiviert ist.|  
|[CMFCBaseTabCtrl::IsAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::IsAutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::IsColored](../Topic/CMFCBaseTabCtrl::IsColored.md)||  
|[CMFCBaseTabCtrl::IsDialogControl](../Topic/CMFCBaseTabCtrl::IsDialogControl.md)||  
|[CMFCBaseTabCtrl::IsDrawNoPrefix](../Topic/CMFCBaseTabCtrl::IsDrawNoPrefix.md)||  
|[CMFCBaseTabCtrl::IsFlatFrame](../Topic/CMFCBaseTabCtrl::IsFlatFrame.md)|Gibt einen Wert zurück, der angibt, ob der Rahmen für den Registerkartenbereich flach oder dreidimensional ist.|  
|[CMFCBaseTabCtrl::IsFlatTab](../Topic/CMFCBaseTabCtrl::IsFlatTab.md)||  
|[CMFCBaseTabCtrl::IsHideSingleTab](../Topic/CMFCBaseTabCtrl::IsHideSingleTab.md)|Gibt einen Wert zurück, der angibt, ob das Registerkarten\-Steuerelement zum Ausblenden einer Registerkarte konfiguriert ist. Dies ist jedoch nur dann der Fall, wenn ein Fenster im Registerkartenformat über nur eine eingeblendete Registerkarte verfügt.|  
|[CMFCBaseTabCtrl::IsIconAdded](../Topic/CMFCBaseTabCtrl::IsIconAdded.md)||  
|[CMFCBaseTabCtrl::IsInPlaceEdit](../Topic/CMFCBaseTabCtrl::IsInPlaceEdit.md)|Gibt an, ob Benutzer die Bezeichnung auf einer Registerkarte ändern können.|  
|[CMFCBaseTabCtrl::IsLeftRightRounded](../Topic/CMFCBaseTabCtrl::IsLeftRightRounded.md)||  
|[CMFCBaseTabCtrl::IsMDITab](../Topic/CMFCBaseTabCtrl::IsMDITab.md)||  
|[CMFCBaseTabCtrl::IsOneNoteStyle](../Topic/CMFCBaseTabCtrl::IsOneNoteStyle.md)|Gibt an, ob die Registerkarten in einem Fenster im Registerkartenformat im Microsoft OneNote\-Format angezeigt werden.|  
|[CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md)|Überprüft, ob ein angegebener Punkt im Registerkartenbereich vorhanden ist.|  
|[CMFCBaseTabCtrl::IsTabCloseButtonHighlighted](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonHighlighted.md)||  
|[CMFCBaseTabCtrl::IsTabCloseButtonPressed](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonPressed.md)||  
|[CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md)|Gibt an, ob eine Registerkarte gelöst werden kann.|  
|[CMFCBaseTabCtrl::IsTabIconOnly](../Topic/CMFCBaseTabCtrl::IsTabIconOnly.md)|Gibt an, ob Symbole, und keine Bezeichnungen, auf den Registerkarten angezeigt werden sollen.|  
|[CMFCBaseTabCtrl::IsTabSwapEnabled](../Topic/CMFCBaseTabCtrl::IsTabSwapEnabled.md)|Gibt an, ob Benutzer durch Ziehen von Registerkarten ihre Position ändern können.|  
|[CMFCBaseTabCtrl::IsTabVisible](../Topic/CMFCBaseTabCtrl::IsTabVisible.md)|Gibt an, ob eine angegebene Registerkarte eingeblendet wird.|  
|[CMFCBaseTabCtrl::IsVS2005Style](../Topic/CMFCBaseTabCtrl::IsVS2005Style.md)||  
|[CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md)||  
|[CMFCBaseTabCtrl::OnChangeTabs](../Topic/CMFCBaseTabCtrl::OnChangeTabs.md)|Vom Framework aufgerufen, wenn sich die Anzahl der Registerkarten ändert.|  
|[CMFCBaseTabCtrl::OnDragEnter](../Topic/CMFCBaseTabCtrl::OnDragEnter.md)||  
|[CMFCBaseTabCtrl::OnDragLeave](../Topic/CMFCBaseTabCtrl::OnDragLeave.md)||  
|[CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md)||  
|[CMFCBaseTabCtrl::OnDrop](../Topic/CMFCBaseTabCtrl::OnDrop.md)||  
|[CMFCBaseTabCtrl::OnRenameTab](../Topic/CMFCBaseTabCtrl::OnRenameTab.md)||  
|[CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md)|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md)\-Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. \(Überschreibt [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md)|Berechnet das interne Layout eines Fensters im Registerkartenformat neu.|  
|[CMFCBaseTabCtrl::RemoveAllTabs](../Topic/CMFCBaseTabCtrl::RemoveAllTabs.md)|Entfernt alle Registerkarten aus dem Fenster im Registerkartenformat.|  
|[CMFCBaseTabCtrl::RemoveTab](../Topic/CMFCBaseTabCtrl::RemoveTab.md)|Entfernt alle Registerkarten aus einem Fenster im Registerkartenformat.|  
|[CMFCBaseTabCtrl::RenameTab](../Topic/CMFCBaseTabCtrl::RenameTab.md)||  
|[CMFCBaseTabCtrl::ResetImageList](../Topic/CMFCBaseTabCtrl::ResetImageList.md)|Setzt die Bildliste zurück, die einem Fenster im Registerkartenformat angefügt ist.|  
|[CMFCBaseTabCtrl::Serialize](../Topic/CMFCBaseTabCtrl::Serialize.md)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. \(Überschreibt [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md)|Aktiviert eine Registerkarte.|  
|[CMFCBaseTabCtrl::SetActiveTabColor](../Topic/CMFCBaseTabCtrl::SetActiveTabColor.md)|Legt die Hintergrundfarbe für die aktuelle aktive Registerkarte fest.|  
|[CMFCBaseTabCtrl::SetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::SetActiveTabTextColor.md)|Legt die Textfarbe für aktive Registerkarten fest.|  
|[CMFCBaseTabCtrl::SetAutoColors](../Topic/CMFCBaseTabCtrl::SetAutoColors.md)|Legt die anzuwendenden Farben für das Registerkarten\-Steuerelement fest, wenn automatische Färbung aktiviert ist.|  
|[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)|Legt die Wrapperklasse fest, die für nicht von der [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) abgeleitete Objekte verwendet wird.|  
|[CMFCBaseTabCtrl::SetDrawNoPrefix](../Topic/CMFCBaseTabCtrl::SetDrawNoPrefix.md)|Aktiviert und deaktiviert die Verarbeitung von Präfixzeichen, wenn die Registerkartenbezeichnungen gezeichnet werden.|  
|[CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md)|Legt die Symbolbildliste fest.|  
|[CMFCBaseTabCtrl::SetLocation](../Topic/CMFCBaseTabCtrl::SetLocation.md)||  
|[CMFCBaseTabCtrl::SetTabBkColor](../Topic/CMFCBaseTabCtrl::SetTabBkColor.md)|Legt die Hintergrundfarbe für eine angegebene Registerkarte fest.|  
|[CMFCBaseTabCtrl::SetTabBorderSize](../Topic/CMFCBaseTabCtrl::SetTabBorderSize.md)|Legt die Größe für einen neuen Registerkartenrahmen fest.|  
|[CMFCBaseTabCtrl::SetTabHicon](../Topic/CMFCBaseTabCtrl::SetTabHicon.md)|Legt ein Registerkartensymbol fest.|  
|[CMFCBaseTabCtrl::SetTabIcon](../Topic/CMFCBaseTabCtrl::SetTabIcon.md)|Legt eine Registerkartensymbol\-ID fest.|  
|[CMFCBaseTabCtrl::SetTabIconOnly](../Topic/CMFCBaseTabCtrl::SetTabIconOnly.md)|Aktiviert und deaktiviert den „Nur Symbol“\-Modus für eine angegebene Registerkarte.|  
|[CMFCBaseTabCtrl::SetTabLabel](../Topic/CMFCBaseTabCtrl::SetTabLabel.md)|Legt eine Registerkartenbezeichnung auf einen angegebenen Zeichenfolgenwert fest.|  
|[CMFCBaseTabCtrl::SetTabsHeight](../Topic/CMFCBaseTabCtrl::SetTabsHeight.md)||  
|[CMFCBaseTabCtrl::SetTabTextColor](../Topic/CMFCBaseTabCtrl::SetTabTextColor.md)|Legt die Textfarbe für eine angegebene Registerkarte fest.|  
|[CMFCBaseTabCtrl::SetTabsOrder](../Topic/CMFCBaseTabCtrl::SetTabsOrder.md)|Ordnet die Registerkarten in der angegebenen Reihenfolge an.|  
|[CMFCBaseTabCtrl::ShowTab](../Topic/CMFCBaseTabCtrl::ShowTab.md)|Blendet die angegebene Registerkarte ein oder aus.|  
|[CMFCBaseTabCtrl::StartRenameTab](../Topic/CMFCBaseTabCtrl::StartRenameTab.md)||  
|[CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md)||  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCBaseTabCtrl::CreateWrapper](../Topic/CMFCBaseTabCtrl::CreateWrapper.md)|Erstellt einen Wrapper für ein von [CWnd](../../mfc/reference/cwnd-class.md) abgeleitetes Objekt, das nicht von `CDockablePane` abgeleitet ist. Um ein `CMFCBaseTabCtrl`\-Objekt anzudocken, muss jedes eingebettete Steuerelement entweder über einen andockbaren Wrapper verfügen oder von `CDockablePane` abgeleitet sein.<br /><br /> Sie können mit `SetDockingBayWrapperRTC` die Klasse des Wrappers festlegen.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCBaseTabCtrl::m\_bActivateTabOnRightClick](../Topic/CMFCBaseTabCtrl::m_bActivateTabOnRightClick.md)|Gibt an, ob Registerkarten durch Klicken mit der linken oder rechten Maustaste ausgewählt werden.|  
|[CMFCBaseTabCtrl::m\_bAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::m_bAutoDestroyWindow.md)|Gibt an, ob die Bereiche, die auf den Registerkarten enthalten sind, automatisch entfernt werden.|  
  
## Hinweise  
 Die `CMFCBaseTabCtrl`\-Klasse stellt eine abstrakte Klasse dar. Daher kann sie nicht instanziiert werden. Um ein Fenster im Registerkartenformat zu erstellen, müssen die eine Klasse von `CMFCBaseTabCtrl` ableiten. Die MFC\-Bibliothek enthält einige Beispiele zu abgeleiteten Klassen, zu denen [CMFCTabCtrl Class](../../mfc/reference/cmfctabctrl-class.md) und [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md) zählen.  
  
 Ab [!INCLUDE[vs_dev14](../../ide/includes/vs_dev14_md.md)] unterstützt diese Klasse Microsoft Active Accessibility.  
  
## Anpassungstipps  
 Die folgenden Tipps beziehen sich auf die [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) und alle Klassen, die von dieser erben:  
  
-   Behalten Sie keine Zeiger auf Fenster im Registerkartenformat, wenn lösbare Registerkarten aktiviert sind. Diese lösbaren Registerkarten können dynamisch erstellt und entfernt werden. Daher können Zeiger ungültig werden.  
  
-   Sie können das Registerkarten\-Steuerelement so konfigurieren, dass Benutzer Registerkarten mit der Maus dynamisch auf ein Registerkarten\-Steuerelement verschieben können. Diese Funktionalität ist in der `CMFCBaseTabCtrl`\-Klasse integriert. Rufen Sie [CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md) auf, um sie zu aktivieren.  
  
-   Registerkarten sind standardmäßig lösbar, wenn Sie sie zu einem Registerkarten\-Steuerelement hinzufügen. Mit [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) können Sie auch nicht lösbare Registerkarten hinzufügen. Wenn Sie den `bDetachable`\-Parameter auf `FALSE` festlegen, wird die Registerkarte zu einer nicht lösbaren Registerkarte. Sie können auch durch Aufrufen der [CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md)\-Methode festlegen, ob die Registerkarte lösbar sein soll.  
  
-   Objekte, die von der [CWnd\-Klasse](../../mfc/reference/cwnd-class.md) abgeleitet werden, können auf einer andockbaren Symbolleiste oder Registerkarte platziert werden. Für das gesamte anzudockende Steuerelement muss das `CWnd`\-Objekt andockbar sein. Hierzu verwendet MFC eine Wrapperklasse. Diese Wrapperklasse ist die [CDockablePaneAdapter Class](../../mfc/reference/cdockablepaneadapter-class.md). Alle `CWnd`\-Objekte, die zu einer andockbaren Symbolleiste oder Registerkarte hinzugefügt werden, werden in ein `CDockablePaneAdapter`\-Objekt eingebunden. Sie können den automatischen Umbruch deaktivieren, indem Sie den `m_bEnableWrapping`\-Parameter des `CMFCBaseTablCtrl`\-Objekts auf `FALSE` festlegen. Sie können auch die Klasse, die die Anwendung als Wrapper verwendet, mit der [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)\-Methode ändern.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
## Anforderungen  
 **Header:** afxbasetabctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl Class](../../mfc/reference/cmfctabctrl-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)