---
title: "CMFCOutlookBar-Klasse"
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
  - "CMFCOutlookBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBar-Klasse"
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBar-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Seite im Registerformat mit dem Aussehen **Navigationsbereich** in Microsoft Outlook 2000 oder in Outlook 2003.  Das `CMFCOutlookBar`\-Objekt enthält ein [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)\-Objekt und von Registerkarten.  Die Registerkarten können entweder [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)\-Objekte oder `CWnd` sein abgeleitete Objekte.  Wenn Benutzer wird die Outlook\-Leiste als eine Reihe von Schaltflächen und Anzeigebereich.  Wenn der Benutzer auf eine Schaltfläche klickt, wird der entsprechende Steuerelement\- oder Schaltflächenbereich angezeigt.  
  
## Syntax  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Standardkonstruktor.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](../Topic/CMFCOutlookBar::AllowDestroyEmptyTabbedPane.md)|Gibt an, ob eine leere Seite im Registerformat zerstört werden kann.  \(Überschreibungen [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md).\)|  
|[CMFCOutlookBar::CanAcceptPane](../Topic/CMFCOutlookBar::CanAcceptPane.md)|Bestimmt, ob ein anderer Bereich zum Outlook\-Leistebereich angedockt werden kann.  \(Überschreibungen CDockablePane::CanAcceptPane.\)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](../Topic/CMFCOutlookBar::CanSetCaptionTextToTabName.md)|Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text wie die aktive Registerkarte angezeigt wird.  \(Überschreibungen [CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md).\)|  
|[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)|Erstellt das Outlook\-Leistensteuerelement.|  
|[CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md)|Erstellt eine benutzerdefinierte Outlook\-Leisteregisterkarte.|  
|`CMFCOutlookBar::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](../Topic/CMFCOutlookBar::DoesAllowDynInsertBefore.md)|Bestimmt, ob ein Benutzer eine Steuerleiste an den äußeren Rand der Outlook\-Leiste andocken kann.|  
|[CMFCOutlookBar::FloatTab](../Topic/CMFCOutlookBar::FloatTab.md)|Schwimmt einen Bereich, jedoch nur, wenn der Bereich sich gegenwärtig in einer abnehmbaren Registerkarte befindet.  \(Überschreibungen [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CMFCOutlookBar::GetButtonsFont](../Topic/CMFCOutlookBar::GetButtonsFont.md)|Gibt die Schriftart des Textes in den Schaltflächen der Outlook\-Leiste zurück.|  
|[CMFCOutlookBar::GetTabArea](../Topic/CMFCOutlookBar::GetTabArea.md)|Gibt die Größe und Position der Registerkartenbereiche auf der Outlook\-Leiste zurück.  \(Überschreibungen [CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md).\)|  
|`CMFCOutlookBar::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBar::IsMode2003](../Topic/CMFCOutlookBar::IsMode2003.md)|Bestimmt ob das Verhalten der Outlook\-Leistenachahmer, die von Microsoft Office Outlook 2003 \(siehe Hinweise\).|  
|[CMFCOutlookBar::OnAfterAnimation](../Topic/CMFCOutlookBar::OnAfterAnimation.md)|Aufgerufen durch [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) nach der aktiven Registerkarte kann mithilfe der Animation festgelegt.|  
|[CMFCOutlookBar::OnBeforeAnimation](../Topic/CMFCOutlookBar::OnBeforeAnimation.md)|Aufgerufen durch [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md), bevor eine Registerkarte als aktuelle Registerkarte mithilfe der Animation festgelegt ist.|  
|[CMFCOutlookBar::OnScroll](../Topic/CMFCOutlookBar::OnScroll.md)|Aufgerufen vom Framework, wenn die Outlook\-Leiste oben oder unten durch.|  
|[CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md)|Entfernt eine benutzerdefinierte Outlook\-Leisteregisterkarte.|  
|[CMFCOutlookBar::SetButtonsFont](../Topic/CMFCOutlookBar::SetButtonsFont.md)|Legt die Schriftart des Textes in den Schaltflächen der Outlook\-Leiste fest.|  
|[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md)|Gibt ob das Verhalten der Outlook\-Leistenachahmer an, die von Outlook 2003 \(siehe Hinweise\).|  
  
## Hinweise  
 Ein Beispiel einer Outlook\-Leiste, finden Sie unter [OutlookDemo\-Beispiel: MFC\-OutlookDemo\-Anwendung](../../top/visual-cpp-samples.md).  
  
## Implementieren der Outlook\-Leiste  
 Um das `CMFCOutlookBar`\-Steuerelement in der Anwendung zu verwenden, führen Sie folgende Schritte aus:  
  
1.  Betten Sie ein `CMFCOutlookBar`\-Objekt in die Hauptrahmenfensterklasse ein.  
  
    ```  
    class CMainFrame : public CMDIFrameWnd  
     { ...  
         CMFCOutlookBar         m_wndOutlookBar;  
         CMFCOutlookBarPane     m_wndOutlookPane;  
    ... };  
    ```  
  
2.  Wenn Sie die `WM_CREATE` Meldung im Hauptframes verarbeiten, rufen Sie die [CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)\-Methode auf, um das Outlook\-Leistetab\-steuerelement zu erstellen.  
  
    ```  
    m_wndOutlookBar.Create (_T("Shortcuts"), this, CRect (0, 0, 100, 100), ID_VIEW_OUTLOOKBAR, WS_CHILD | WS_VISIBLE | CBRS_LEFT);  
    ```  
  
3.  Abrufen eines Zeigers auf zugrunde liegenden `CMFCOutlookBarTabCtrl`, indem er [CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md) verwendet.  
  
    ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();  
    ```  
  
4.  Erstellen Sie ein [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)\-Objekt für jede Registerkarte, die Schaltflächen enthält.  
  
    ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar, AFX_DEFAULT_TOOLBAR_STYLE, ID_OUTLOOK_PANE_GENERAL, AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  
    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);  
    // add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About", ID_APP_ABOUT);  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open", ID_FILE_OPEN);  
    ```  
  
5.  Rufen Sie [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) auf, um jede neue Registerkarte hinzuzufügen.  Legen Sie den `bDetachable`\-Parameter zu `FALSE` fest, um eine Seite nicht\-abnehmbar auszuführen.  Oder, Verwendung [CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md), abnehmbare Seiten hinzuzufügen.  
  
    ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);   
    ```  
  
6.  So `CWnd` hinzufügen von abgeleitetes Steuerelement \(beispielsweise, [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)\) als Registerkarte, erstellen das Steuerelement und den Aufruf [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md), um es der Outlook\-Leiste hinzuzufügen.  
  
> [!NOTE]
>  Sie sollten eindeutige Steuer\-IDs für jedes Objekt [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) und für jedes `CWnd` verwenden von abgeleitetes Objekt.  
  
 So fügen Sie neue Seiten, verwendet [CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md) und [CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md) dynamisch zur Laufzeit hinzufügen oder löschen.  
  
## Outlook 2003\-Modus  
 In Outlook 2003\-Modus werden die Registerkartenschaltflächen am unteren Rand des Outlook\-Leistebereich positioniert.  Wenn nicht genügend Platz, die Schaltflächen anzuzeigen, werden sie als Symbole in einem Symbolleiste ähnlichen Bereich entlang dem unteren Rand des Bereichs angezeigt.  
  
 Verwendung [CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md), Outlook 2003\-Modus zu aktivieren.  Verwenden Sie [CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md), um die Bitmap festzulegen, die die Symbole enthält, die an der Unterkante der Outlook\-Leiste angezeigt werden.  Die Symbole in der Bitmap müssen durch Registerkartenindex sortiert werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## Anforderungen  
 **Header:** afxoutlookbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane\-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)