---
title: "CMDIChildWndEx-Klasse"
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
  - "CMDIChildWndEx"
  - "GetThisClass"
  - "CMDIChildWndEx::PreTranslateMessage"
  - "CMDIChildWndEx::ActivateFrame"
  - "CMDIChildWndEx.GetThisClass"
  - "CMDIChildWndEx::AddDockSite"
  - "CMDIChildWndEx.CreateObject"
  - "CMDIChildWndEx::CreateObject"
  - "CMDIChildWndEx.ActivateFrame"
  - "CMDIChildWndEx::GetThisClass"
  - "CMDIChildWndEx.PreTranslateMessage"
  - "PreTranslateMessage"
  - "ActivateFrame"
  - "CreateObject"
  - "CMDIChildWndEx.AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIChildWndEx-Klasse"
  - "ActivateFrame-Methode"
  - "PreTranslateMessage-Methode"
  - "GetThisClass-Methode"
  - "CreateObject-Methode"
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# CMDIChildWndEx-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMDIChildWndEx`\-Klasse stellt Funktionalität eines untergeordneten Windows\-MultipleDocument Interface \(MDI\)\-Fensters.  Sie erweitert die Funktionalität von [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md).  Das Framework benötigt diese Klasse, wenn eine MDI\-Anwendung bestimmte MFC\-Klassen verwendet.  
  
## Syntax  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](../Topic/CMDIChildWndEx::ActivateTopLevelFrame.md)|Intern aufgerufen über das Framework, um Frames der obersten Ebene zu aktivieren, wenn die Anwendung von einer Taskleistenregisterkarte aktiviert werden sollte.|  
|`CMDIChildWndEx::AddDockSite`|Diese Methode wird nicht verwendet oder implementiert.|  
|[CMDIChildWndEx::AddPane](../Topic/CMDIChildWndEx::AddPane.md)|Fügt einen Bereich hinzu.|  
|[CMDIChildWndEx::AddTabbedPane](../Topic/CMDIChildWndEx::AddTabbedPane.md)|Fügt eine Seite im Registerformat hinzu.|  
|[CMDIChildWndEx::AdjustDockingLayout](../Topic/CMDIChildWndEx::AdjustDockingLayout.md)|Passt das andockbare Layout.|  
|[CMDIChildWndEx::CanShowOnMDITabs](../Topic/CMDIChildWndEx::CanShowOnMDITabs.md)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](../Topic/CMDIChildWndEx::CanShowOnTaskBarTabs.md)|Teilt das Framework mit, ob dieses untergeordnete MDI\-Fenster auf Windows 7\-Taskleistenregisterkarten angezeigt werden kann.|  
|[CMDIChildWndEx::CanShowOnWindowsList](../Topic/CMDIChildWndEx::CanShowOnWindowsList.md)|Gibt `TRUE` zurück, wenn der Name des untergeordneten MDI\-Fensters [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) im Dialogfeld angezeigt werden kann.  Andernfalls wird `FALSE` zurückgegeben.|  
|`CMDIChildWndEx::CreateObject`|Aufgerufen durch das Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMDIChildWndEx::DockPane](../Topic/CMDIChildWndEx::DockPane.md)|Dockt einen Bereich an.|  
|[CMDIChildWndEx::DockPaneLeftOf](../Topic/CMDIChildWndEx::DockPaneLeftOf.md)|wird ein Bereich auf der linken Seite eines anderen Bereichs.|  
|[CMDIChildWndEx::EnableAutoHidePanes](../Topic/CMDIChildWndEx::EnableAutoHidePanes.md)|Aktiviert Modus "Automatisches Ausblenden" für Bereiche, wenn sie mit den angegebenen Seiten des Fensters angedockt werden.|  
|[CMDIChildWndEx::EnableDocking](../Topic/CMDIChildWndEx::EnableDocking.md)|Aktiviert Andocken des untergeordneten MDI\-Fensters zum Großrechner.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::EnableTaskbarThumbnailClipRect.md)|Lässt oder deaktiviert automatische Auswahl eines Teils Clientbereichs eines Fensters, um als Miniaturansicht des Fensters in der Taskleiste anzuzeigen.|  
|[CMDIChildWndEx::GetDockingManager](../Topic/CMDIChildWndEx::GetDockingManager.md)||  
|[CMDIChildWndEx::GetDocumentName](../Topic/CMDIChildWndEx::GetDocumentName.md)|Gibt den Namen des Dokuments zurück, das im untergeordneten MDI\-Fenster angezeigt wird.|  
|[CMDIChildWndEx::GetFrameIcon](../Topic/CMDIChildWndEx::GetFrameIcon.md)|Aufgerufen vom Framework, um das Symbol des untergeordneten MDI\-Fensters abzurufen.|  
|[CMDIChildWndEx::GetFrameText](../Topic/CMDIChildWndEx::GetFrameText.md)|Aufgerufen vom Framework, um den Text für das untergeordnete MDI\-Fenster abzurufen.|  
|[CMDIChildWndEx::GetPane](../Topic/CMDIChildWndEx::GetPane.md)|Sucht einen Bereich von der angegebenen Steuerelement\-ID|  
|[CMDIChildWndEx::GetRelatedTabGroup](../Topic/CMDIChildWndEx::GetRelatedTabGroup.md)||  
|[CMDIChildWndEx::GetTabbedPane](../Topic/CMDIChildWndEx::GetTabbedPane.md)|Gibt einen Zeiger auf einen eingebetteten Hauptandockbereich zurück, der zu einem Dokument im Registerkartenformat konvertiert wurde.|  
|[CMDIChildWndEx::GetTabProxyWnd](../Topic/CMDIChildWndEx::GetTabProxyWnd.md)|EINGABETASTEregisterkarten\-Proxyfenster tatsächlich registriert mit Windows 7\-Taskleistenregisterkarten.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](../Topic/CMDIChildWndEx::GetTaskbarPreviewWnd.md)|Aufgerufen vom Framework, wenn erhalten muss ein auf Windows 7\-Taskleistenregisterkartenminiaturansicht angezeigt werden untergeordnetes Fenster \(normalerweise eine Ansicht oder ein Splitterfenster\).|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::GetTaskbarThumbnailClipRect.md)|Aufgerufen vom Framework, wenn sie einen Teil Clientbereich eines Fensters auswählen muss, um als Miniaturansicht des Fensters in der Taskleiste anzuzeigen.|  
|`CMDIChildWndEx::GetThisClass`|Aufgerufen vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](../Topic/CMDIChildWndEx::GetToolbarButtonToolTipText.md)|Aufgerufen vom Framework, um eine QuickInfo für eine Symbolleisten\-Schaltfläche abzurufen.|  
|[CMDIChildWndEx::InsertPane](../Topic/CMDIChildWndEx::InsertPane.md)|Registriert den angegebenen Bereich mit dem Andocken Manager.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](../Topic/CMDIChildWndEx::InvalidateIconicBitmaps.md)|Macht Symbolbit\-übersichtsdarstellung des untergeordneten MDI\-Fensters ungültig.|  
|[CMDIChildWndEx::IsPointNearDockSite](../Topic/CMDIChildWndEx::IsPointNearDockSite.md)|Bestimmt, ob ein bestimmter Punkt neben der Docksite ist.|  
|[CMDIChildWndEx::IsReadOnly](../Topic/CMDIChildWndEx::IsReadOnly.md)|Gibt `TRUE` zurück, wenn das Dokument, das im untergeordneten Fenster angezeigt wird, schreibgeschützt ist.  Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](../Topic/CMDIChildWndEx::IsRegisteredWithTaskbarTabs.md)|Gibt RICHTET aus, wenn untergeordnetes MDI\-Fenster erfolgreich mit Windows 7\-Taskleistenregisterkarten registriert wurde.|  
|[CMDIChildWndEx::IsTabbedPane](../Topic/CMDIChildWndEx::IsTabbedPane.md)|Gibt `TRUE` zurück, wenn das untergeordnete MDI\-Fenster einen Hauptandockbereich enthält.  Andernfalls wird `FALSE` zurückgegeben.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](../Topic/CMDIChildWndEx::IsTaskbarTabsSupportEnabled.md)|Teilt mit, ob das untergeordnete MDI\-Fenster auf Windows 7\-Taskleistenregisterkarten angezeigt werden kann.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](../Topic/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled.md)|Teilt mit, ob automatische Auswahl eines Teils Clientbereichs eines Fensters zur Anzeige als Miniaturansicht des Fensters in der Taskleiste aktiviert oder deaktiviert wird.|  
|[CMDIChildWndEx::m\_dwDefaultTaskbarTabPropertyFlags](../Topic/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags.md)|Eine Kombination von Flags, die vom Framework zur SetTaskbarTabProperties\-Methode übergeben wird, wenn eine Registerkarte \(untergeordnetes MDI\-Fenster\) mit Windows 7\-Taskleistenregisterkarten registriert wird.  Die standardmäßige Kombination ist STPF\_USEAPPTHUMBNAILWHENACTIVE &#124; STPF\_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](../Topic/CMDIChildWndEx::OnGetIconicLivePreviewBitmap.md)|Aufgerufen vom Framework, wenn abrufen muss eine Bitmap für Livevorschau des untergeordneten MDI\-Fensters.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](../Topic/CMDIChildWndEx::OnGetIconicThumbnail.md)|Aufgerufen vom Framework, wenn abrufen muss eine Bitmap für ikonenhafte Miniaturansicht des untergeordneten MDI\-Fensters.|  
|[CMDIChildWndEx::OnMoveMiniFrame](../Topic/CMDIChildWndEx::OnMoveMiniFrame.md)|Aufgerufen vom Framework, um ein Minirahmenfenster zu verschieben.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](../Topic/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton.md)|Aufgerufen vom Framework, wenn der Benutzer Schaltfläche Schließen auf Taskleistenregisterkartenminiaturansicht. drückt.|  
|[CMDIChildWndEx::OnSetPreviewMode](../Topic/CMDIChildWndEx::OnSetPreviewMode.md)|Aufgerufen durch das Framework, um Seitenansichtsmodus einzugeben oder zu beenden.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailActivate.md)|Aufgerufen vom Framework, wenn die Taskleistenregisterkartenminiaturansicht WM\_ACTIVATE\-Meldung verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate.md)|Aufgerufen vom Framework, wenn die Taskleistenregisterkartenminiaturansicht WM\_MOUSEACTIVATE\-Meldung verarbeiten soll.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailStretch.md)|Aufgerufen vom Framework, wenn sie eine Bitmap für Windows 7\-Taskleistenregisterkarten\-Miniaturansichtsvorschau des untergeordneten MDI\-Fensters strecken muss.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](../Topic/CMDIChildWndEx::OnUpdateFrameTitle.md)|Aufgerufen vom Framework, um den Rahmens zu aktualisieren.  \(Überschreibungen `CMDIChildWnd::OnUpdateFrameTitle`.\)|  
|[CMDIChildWndEx::PaneFromPoint](../Topic/CMDIChildWndEx::PaneFromPoint.md)|Gibt den Bereich zurück, der den angegebenen Punkt enthält.|  
|`CMDIChildWndEx::PreTranslateMessage`|Wird von Klasse [CWinApp](../../mfc/reference/cwinapp-class.md), um Fenstermeldungen zu übersetzen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMDIChildWndEx::RecalcLayout](../Topic/CMDIChildWndEx::RecalcLayout.md)|Berechnet das Layout des Fensters neu.|  
|[CMDIChildWndEx::RegisterTaskbarTab](../Topic/CMDIChildWndEx::RegisterTaskbarTab.md)|Register\-untergeordnetes MDI\-Element mit Windows 7\-Taskleistenregisterkarten.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](../Topic/CMDIChildWndEx::RemovePaneFromDockManager.md)|Entfernt einen Bereich von Andocken Manager.|  
|[CMDIChildWndEx::SetRelatedTabGroup](../Topic/CMDIChildWndEx::SetRelatedTabGroup.md)||  
|[CMDIChildWndEx::SetTaskbarTabActive](../Topic/CMDIChildWndEx::SetTaskbarTabActive.md)|Aktiviert entsprechende Windows 7\-Taskleistenregisterkarte.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](../Topic/CMDIChildWndEx::SetTaskbarTabOrder.md)|Einfügungs\-untergeordnetesMDI\-Element vor dem angegebenen Fenster auf Windows 7\-Taskleistenregisterkarten.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](../Topic/CMDIChildWndEx::SetTaskbarTabProperties.md)|Legt die Eigenschaften für eine Windows 7\-Taskleistenregisterkarte fest.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::SetTaskbarThumbnailClipRect.md)|Intern aufgerufen über das Framework, um Ausschneiderechteck festzulegen, um einen Teil Clientbereich eines Fensters auszuwählen, die als Miniaturansicht des Fensters in der Taskleiste anzuzeigen.|  
|[CMDIChildWndEx::ShowPane](../Topic/CMDIChildWndEx::ShowPane.md)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](../Topic/CMDIChildWndEx::UnregisterTaskbarTab.md)|Entfernt untergeordnetes MDI\-Fenster von Windows 7\-Taskleistenregisterkarten.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](../Topic/CMDIChildWndEx::UpdateTaskbarTabIcon.md)|Update\-Windows 7\-Taskleistenregisterkartensymbol.|  
  
## Hinweise  
 Um erweiterte andockbare Funktionen in MDI\-Anwendungen zu nutzen, leiten Sie die Klasse des untergeordneten MDI\-Fensters der Anwendung von `CMDIChildWndEx` anstelle [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Klasse von `CMDIChildWndEx`.  Dieser Codeausschnitt stammt [VisualStudioDemo\-Beispiel: MFC\-Anwendung Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#3)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## Anforderungen  
 **Header:** afxMDIChildWndEx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md)