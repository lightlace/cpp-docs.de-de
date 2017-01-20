---
title: "CHtmlView-Klasse"
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
  - "CHtmlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Browser, MFC-Unterstützung für"
  - "CHtmlView-Klasse"
  - "WebBrowser-Steuerelement"
  - "WebBrowser-Steuerelement, MFC-Unterstützung"
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlView-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des WebBrowser\-Steuerelements im Kontext der MFC\-Dokument\-\/Ansichtarchitektur bereit.  
  
## Syntax  
  
```  
class CHtmlView : public CFormView  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHtmlView::Create](../Topic/CHtmlView::Create.md)|Erstellt das WebBrowser\-Steuerelement.|  
|[CHtmlView::CreateControlSite](../Topic/CHtmlView::CreateControlSite.md)|Überschreibbar. Verwendet, um eine Steuerelement\-Websiteinstanz zum Hosten eines Steuerelements auf dem Formular zu erstellen.|  
|[CHtmlView::ExecFormsCommand](../Topic/CHtmlView::ExecFormsCommand.md)|Führt den angegebenen Befehl mithilfe der Methode `IOleCommandTarget::Exec` aus.|  
|[CHtmlView::ExecWB](../Topic/CHtmlView::ExecWB.md)|Führt einen Befehl aus.|  
|[CHtmlView::GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)|Bestimmt, ob die Adressleiste des Internet Explorer\-Objekts angezeigt wird. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::GetApplication](../Topic/CHtmlView::GetApplication.md)|Ruft ein Anwendungsobjekt ab, das die Anwendung darstellt, die die aktuelle Instanz der Internet Explorer\-Anwendung enthält.|  
|[CHtmlView::GetBusy](../Topic/CHtmlView::GetBusy.md)|Ruft einen Wert ab, der angibt, ob aktuell noch ein Download oder eine andere Aktivität ausgeführt wird.|  
|[CHtmlView::GetContainer](../Topic/CHtmlView::GetContainer.md)|Ruft den Container des WebBrowser\-Steuerelements ab.|  
|[CHtmlView::GetFullName](../Topic/CHtmlView::GetFullName.md)|Ruft den vollständigen Namen, einschließlich Pfad, der im Webbrowser angezeigten Ressource ab. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::GetFullScreen](../Topic/CHtmlView::GetFullScreen.md)|Gibt an, ob das WebBrowser\-Steuerelement im Vollbildmodus oder im normalen Modus ausgeführt wird.|  
|[CHtmlView::GetHeight](../Topic/CHtmlView::GetHeight.md)|Ruft die Höhe des Internet Explorer\-Hauptfensters ab.|  
|[CHtmlView::GetHtmlDocument](../Topic/CHtmlView::GetHtmlDocument.md)|Ruft das aktive HTML\-Dokument ab.|  
|[CHtmlView::GetLeft](../Topic/CHtmlView::GetLeft.md)|Ruft die Bildschirmkoordinate der linken Kante des Internet Explorer\-Hauptfensters ab.|  
|[CHtmlView::GetLocationName](../Topic/CHtmlView::GetLocationName.md)|Ruft den Namen der Ressource ab, die aktuell im WebBrowser angezeigt wird|  
|[CHtmlView::GetLocationURL](../Topic/CHtmlView::GetLocationURL.md)|Ruft die URL der Ressource ab, die aktuell im WebBrowser angezeigt wird.|  
|[CHtmlView::GetMenuBar](../Topic/CHtmlView::GetMenuBar.md)|Ruft einen Wert ab, der bestimmt, ob die Menüleiste angezeigt wird.|  
|[CHtmlView::GetOffline](../Topic/CHtmlView::GetOffline.md)|Ruft einen Wert ab, der bestimmt, ob das Steuerelement offline ist.|  
|[CHtmlView::GetParentBrowser](../Topic/CHtmlView::GetParentBrowser.md)|Ruft einen Zeiger auf die `IDispatch`\-Schnittstelle ab. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](assetId:///0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](../Topic/CHtmlView::GetProperty.md)|Ruft den aktuellen Wert einer Eigenschaft ab, die dem angegebenen Objekt zugeordnet ist.|  
|[CHtmlView::GetReadyState](../Topic/CHtmlView::GetReadyState.md)|Ruft den Bereitschaftsstatus des Webbrowserobjekts ab.|  
|[CHtmlView::GetRegisterAsBrowser](../Topic/CHtmlView::GetRegisterAsBrowser.md)|Gibt an, ob das WebBrowser\-Steuerelement als Browser der obersten Ebene für die Zielnamenauflösung registriert ist.|  
|[CHtmlView::GetRegisterAsDropTarget](../Topic/CHtmlView::GetRegisterAsDropTarget.md)|Gibt an, ob das WebBrowser\-Steuerelement als Ablageziel für die Navigation registriert ist.|  
|[CHtmlView::GetSilent](../Topic/CHtmlView::GetSilent.md)|Gibt an, ob Dialogfelder angezeigt werden können.|  
|[CHtmlView::GetSource](../Topic/CHtmlView::GetSource.md)|Der HTML\-Quellcode der Webseite.|  
|[CHtmlView::GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)|Gibt an, ob die Statusleiste von Internet Explorer angezeigt wird. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::GetTheaterMode](../Topic/CHtmlView::GetTheaterMode.md)|Gibt an, ob das WebBrowser\-Steuerelement im Kinomodus ausgeführt wird.|  
|[CHtmlView::GetToolBar](../Topic/CHtmlView::GetToolBar.md)|Ruft einen Wert ab, der bestimmt, ob die Symbolleiste angezeigt wird.|  
|[CHtmlView::GetTop](../Topic/CHtmlView::GetTop.md)|Ruft die Bildschirmkoordinate der oberen Kante des Internet Explorer\-Hauptfensters ab.|  
|[CHtmlView::GetTopLevelContainer](../Topic/CHtmlView::GetTopLevelContainer.md)|Ruft einen Wert ab, der angibt, ob das aktuelle Objekt den Container der obersten Ebene des WebBrowser\-Steuerelements darstellt.|  
|[CHtmlView::GetType](../Topic/CHtmlView::GetType.md)|Ruft den Typnamen des Dokumentobjekts ab.|  
|[CHtmlView::GetVisible](../Topic/CHtmlView::GetVisible.md)|Ruft einen Wert ab, der angibt, ob das Objekt sichtbar oder ausgeblendet ist.|  
|[CHtmlView::GetWidth](../Topic/CHtmlView::GetWidth.md)|Ruft die Breite des Internet Explorer\-Hauptfensters ab.|  
|[CHtmlView::GoBack](../Topic/CHtmlView::GoBack.md)|Navigiert zum vorherigen Element in der Verlaufsliste.|  
|[CHtmlView::GoForward](../Topic/CHtmlView::GoForward.md)|Navigiert zum nächsten Element in der Verlaufsliste.|  
|[CHtmlView::GoHome](../Topic/CHtmlView::GoHome.md)|Navigiert zur aktuellen Homepage oder Startseite.|  
|[CHtmlView::GoSearch](../Topic/CHtmlView::GoSearch.md)|Navigiert zur aktuellen Suchseite.|  
|[CHtmlView::LoadFromResource](../Topic/CHtmlView::LoadFromResource.md)|Lädt eine Ressource im WebBrowser\-Steuerelement.|  
|[CHtmlView::Navigate](../Topic/CHtmlView::Navigate.md)|Navigiert zu der durch eine URL bezeichnete Ressource.|  
|[CHtmlView::Navigate2](../Topic/CHtmlView::Navigate2.md)|Navigiert zu der durch eine URL bezeichnete Ressource oder zu der durch einen vollständigen Pfad angegebenen Datei.|  
|[CHtmlView::OnBeforeNavigate2](../Topic/CHtmlView::OnBeforeNavigate2.md)|Wird aufgerufen, bevor ein Navigationsvorgang im vorhandenen WebBrowser \(entweder in einem Fenster\- oder in einem Frameset\-Element\) ausgeführt wird.|  
|[CHtmlView::OnCommandStateChange](../Topic/CHtmlView::OnCommandStateChange.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der aktivierte Zustand eines Webbrowserbefehls geändert wurde.|  
|[CHtmlView::OnDocumentComplete](../Topic/CHtmlView::OnDocumentComplete.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass ein Dokument den Zustand `READYSTATE_COMPLETE` erreicht hat.|  
|[CHtmlView::OnDocWindowActivate](../Topic/CHtmlView::OnDocWindowActivate.md)|Wird von der Implementierung von [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) von Internet Explorer oder MSHTML aufgerufen, die das aktive direkte Objekt benachrichtigt, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird.|  
|[CHtmlView::OnDownloadBegin](../Topic/CHtmlView::OnDownloadBegin.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass ein Navigationsvorgang beginnt.|  
|[CHtmlView::OnDownloadComplete](../Topic/CHtmlView::OnDownloadComplete.md)|Wird aufgerufen, wenn ein Navigationsvorgang beendet oder angehalten wurde bzw. wenn ein Fehler aufgetreten ist.|  
|[CHtmlView::OnEnableModeless](../Topic/CHtmlView::OnEnableModeless.md)|Wird aufgerufen, um Dialogfelder ohne Modus zu aktivieren oder deaktivieren, wenn der Container ein modales Dialogfeld erstellt oder entfernt.|  
|[CHtmlView::OnFilterDataObject](../Topic/CHtmlView::OnFilterDataObject.md)|Wird auf dem Host von Internet Explorer oder MSHTML aufgerufen, um dem Host das Ersetzen des Datenobjekts von Internet Explorer oder MSHTML zu ermöglichen.|  
|[CHtmlView::OnFrameWindowActivate](../Topic/CHtmlView::OnFrameWindowActivate.md)|Wird von [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) aufgerufen, um das Objekt zu benachrichtigen, wenn das Rahmenfenster der obersten Ebene des Containers aktiviert oder deaktiviert wird.|  
|[CHtmlView::OnFullScreen](../Topic/CHtmlView::OnFullScreen.md)|Wird aufgerufen, wenn die FullScreen\-Eigenschaft geändert wurde.|  
|[CHtmlView::OnGetDropTarget](../Topic/CHtmlView::OnGetDropTarget.md)|Wird von Internet Explorer oder MSHTML bei der Verwendung als Ablageziel aufgerufen, um dem Host die Bereitstellung eines alternativen [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) zu ermöglichen.|  
|[CHtmlView::OnGetExternal](../Topic/CHtmlView::OnGetExternal.md)|Wird von Internet Explorer oder MSHTML aufgerufen, um die `IDispatch`\-Schnittstelle des Hosts zu erhalten.|  
|[CHtmlView::OnGetHostInfo](../Topic/CHtmlView::OnGetHostInfo.md)|Ruft die UI\-Fähigkeiten des Internet Explorer\- oder MSHTML\-Hosts ab.|  
|[CHtmlView::OnGetOptionKeyPath](../Topic/CHtmlView::OnGetOptionKeyPath.md)|Gibt den Registrierungsschlüssel zurück, unter dem Internet Explorer oder MSHTML Benutzereinstellungen speichert.|  
|[CHtmlView::OnHideUI](../Topic/CHtmlView::OnHideUI.md)|Wird aufgerufen, wenn Internet Explorer oder MSHTML seine Menüs und Symbolleisten entfernt.|  
|[CHtmlView::OnMenuBar](../Topic/CHtmlView::OnMenuBar.md)|Wird aufgerufen, wenn die MenuBar\-Eigenschaft geändert wurde.|  
|[CHtmlView::OnNavigateComplete2](../Topic/CHtmlView::OnNavigateComplete2.md)|Wird aufgerufen, nachdem die Navigation zu einem Link abgeschlossen wurde \(in einem Fenster\- oder FrameSet\-Element\).|  
|[CHtmlView::OnNavigateError](../Topic/CHtmlView::OnNavigateError.md)|Wird vom Framework aufgerufen, wenn ein Fehler bei der Navigation zu einem Link auftritt.|  
|[CHtmlView::OnNewWindow2](../Topic/CHtmlView::OnNewWindow2.md)|Wird aufgerufen, wenn ein neues Fenster erstellt wird, um eine Ressource anzuzeigen.|  
|[CHtmlView::OnProgressChange](../Topic/CHtmlView::OnProgressChange.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der Status eines Downloadvorgangs aktualisiert wurde.|  
|[CHtmlView::OnPropertyChange](../Topic/CHtmlView::OnPropertyChange.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass die [PutProperty](../Topic/CHtmlView::PutProperty.md)\-Methode den Wert einer Eigenschaft geändert hat.|  
|[CHtmlView::OnQuit](../Topic/CHtmlView::OnQuit.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass die Internet Explorer\-Anwendung beendet werden kann. \(Betrifft nur Internet Explorer\)|  
|[CHtmlView::OnResizeBorder](../Topic/CHtmlView::OnResizeBorder.md)|Wird von der Implementierung von [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053) in Internet Explorer oder MSHTML aufgerufen, die das Objekt benachrichtigt, dass es die Größe seines Rahmenbereichs ändern muss.|  
|[CHtmlView::OnShowContextMenu](../Topic/CHtmlView::OnShowContextMenu.md)|Wird von Internet Explorer oder MSHTML aufgerufen, wenn die Anzeige des Kontextmenüs bevorsteht.|  
|[CHtmlView::OnShowUI](../Topic/CHtmlView::OnShowUI.md)|Wird aufgerufen, wenn die Anzeige von Menüs und Symbolleisten in Internet Explorer oder MSHTML bevorsteht.|  
|[CHtmlView::OnStatusBar](../Topic/CHtmlView::OnStatusBar.md)|Wird aufgerufen, wenn die StatusBar\-Eigenschaft geändert wurde.|  
|[CHtmlView::OnStatusTextChange](../Topic/CHtmlView::OnStatusTextChange.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der Text in der Statusleiste des WebBrowser\-Steuerelements geändert wurde.|  
|[CHtmlView::OnTheaterMode](../Topic/CHtmlView::OnTheaterMode.md)|Wird aufgerufen, wenn die TheaterMode\-Eigenschaft geändert wird.|  
|[CHtmlView::OnTitleChange](../Topic/CHtmlView::OnTitleChange.md)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, wenn der Titel eines Dokuments im WebBrowser\-Steuerelement verfügbar ist oder geändert wird.|  
|[CHtmlView::OnToolBar](../Topic/CHtmlView::OnToolBar.md)|Wird aufgerufen, wenn sich die ToolBar\-Eigenschaft geändert hat.|  
|[CHtmlView::OnTranslateAccelerator](../Topic/CHtmlView::OnTranslateAccelerator.md)|Wird von Internet Explorer oder MSHTML aufgerufen, wenn [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) oder [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) aufgerufen wird, um Tastenkombinations\-Menünachrichten aus der Nachrichtenwarteschlange des Containers zu verarbeiten.|  
|[CHtmlView::OnTranslateUrl](../Topic/CHtmlView::OnTranslateUrl.md)|Wird von Internet Explorer oder MSHTML aufgerufen, um dem Host die Möglichkeit zu geben, die zu ladende URL zu ändern.|  
|[CHtmlView::OnUpdateUI](../Topic/CHtmlView::OnUpdateUI.md)|Benachrichtigt den Host, dass sich der Befehlsstatus geändert hat.|  
|[CHtmlView::OnVisible](../Topic/CHtmlView::OnVisible.md)|Wird aufgerufen, wenn das Fenster für das WebBrowser\-Steuerelement ein\- oder ausgeblendet werden soll.|  
|[CHtmlView::PutProperty](../Topic/CHtmlView::PutProperty.md)|Legt den Wert einer Eigenschaft fest, die dem angegebenen Objekt zugeordnet ist.|  
|[CHtmlView::QueryFormsCommand](../Topic/CHtmlView::QueryFormsCommand.md)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|  
|[CHtmlView::QueryStatusWB](../Topic/CHtmlView::QueryStatusWB.md)|Fragt den Status eines Befehls ab, der vom WebBrowser\-Steuerelement verarbeitet wird.|  
|[CHtmlView::Refresh](../Topic/CHtmlView::Refresh.md)|Lädt die aktuelle Seite erneut.|  
|[CHtmlView::Refresh2](../Topic/CHtmlView::Refresh2.md)|Lädt die aktuelle Datei und verhindert optional das Senden der `pragma:nocache`\-Header.|  
|[CHtmlView::SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)|Blendet die Adressleiste des Internet Explorer\-Objekts ein oder aus. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)|Legt einen Wert fest, um zu bestimmen, ob das Steuerelement im Vollbildmodus oder im normalen Fenstermodus ausgeführt wird \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::SetHeight](../Topic/CHtmlView::SetHeight.md)|Legt die Höhe des Internet Explorer\-Hauptfensters fest.|  
|[CHtmlView::SetLeft](../Topic/CHtmlView::SetLeft.md)|Legt die horizontale Position des Internet Explorer\-Hauptfensters fest.|  
|[CHtmlView::SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)|Legt einen Wert fest, der bestimmt, ob die Menüleiste des Steuerelements angezeigt wird. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::SetOffline](../Topic/CHtmlView::SetOffline.md)|Legt einen Wert fest, der bestimmt, ob das Steuerelement offline ist.|  
|[CHtmlView::SetRegisterAsBrowser](../Topic/CHtmlView::SetRegisterAsBrowser.md)|Legt einen Wert fest, der angibt, ob das WebBrowser\-Steuerelement als Browser der obersten Ebene für die Zielnamenauflösung registriert ist.|  
|[CHtmlView::SetRegisterAsDropTarget](../Topic/CHtmlView::SetRegisterAsDropTarget.md)|Legt einen Wert fest, der angibt, ob das WebBrowser\-Steuerelement als Ablageziel für die Navigation registriert ist.|  
|[CHtmlView::SetSilent](../Topic/CHtmlView::SetSilent.md)|Legt einen Wert fest, der angibt, ob das Steuerelement Dialogfelder anzeigt.|  
|[CHtmlView::SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)|Legt einen Wert fest, der angibt, ob die Statusleiste von Internet Explorer angezeigt wird. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::SetTheaterMode](../Topic/CHtmlView::SetTheaterMode.md)|Legt einen Wert fest, der angibt, ob das WebBrowser\-Steuerelement im Kinomodus ausgeführt wird.|  
|[CHtmlView::SetToolBar](../Topic/CHtmlView::SetToolBar.md)|Legt einen Wert fest, der bestimmt, ob die Symbolleiste des Steuerelements angezeigt wird. \(Vom WebBrowser\-Steuerelement ignoriert; nur Internet Explorer.\)|  
|[CHtmlView::SetTop](../Topic/CHtmlView::SetTop.md)|Legt die vertikale Position des Internet Explorer\-Hauptfensters fest.|  
|[CHtmlView::SetVisible](../Topic/CHtmlView::SetVisible.md)|Legt einen Wert fest, der angibt, ob das Objekt sichtbar oder ausgeblendet ist.|  
|[CHtmlView::SetWidth](../Topic/CHtmlView::SetWidth.md)|Legt die Breite des Internet Explorer\-Hauptfensters fest.|  
|[CHtmlView::Stop](../Topic/CHtmlView::Stop.md)|Bricht das Öffnen einer Datei ab.|  
  
## Hinweise  
 Das WebBrowser\-Steuerelement ist ein Fenster, in dem der Benutzer zu Websites im World Wide Web sowie zu Ordnern im lokalen Dateisystem und in einem Netzwerk navigieren kann. Das WebBrowser\-Steuerelement unterstützt die Navigation mithilfe von Hyperlinks und URLs \(Uniform Resource Locator\) und unterhält eine Verlaufsliste.  
  
## Verwenden der CHtmlView\-Klasse in einer MFC\-Anwendung  
 In der standardmäßigen MFC\-Frameworkanwendung \(entweder auf SDI oder auf MDI basierend\) wird das Ansichtsobjekt üblicherweise aus einem spezialisierten Satz Klassen abgeleitet. Diese Klassen, die alle aus `CView` abgeleitet sind, bieten spezielle Funktionen über den von `CView` bereitgestellten Rahmen hinaus.  
  
 Die Ableitung der Ansichtsklasse der Anwendung aus `CHtmlView` stellt der Ansicht das WebBrowser\-Steuerelement bereit. Dadurch wird die Anwendung praktisch zu einem Webbrowser. Die bevorzugte Methode zum Erstellen einer Anwendung im Stil eines Webbrowsers besteht in der Verwendung des MFC\-Anwendungs\-Assistenten und dem Angeben von `CHtmlView` als Ansichtsklasse. Weitere Informationen zum Implementieren und Verwenden des WebBrowser\-Steuerelements in MFC\-Anwendungen finden Sie unter [Erstellen eines Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  Das WebBrowser\-ActiveX\-Steuerelement \(und daher `CHtmlView`\) ist nur für Programme verfügbar, die unter den Windows NT\-Versions 4.0 oder höher ausgeführt werden, auf denen Internet Explorer 4.0 oder höher installiert wurde.  
  
 `CHtmlView` ist für Anwendungen ausgelegt, die auf das Web \(und\/oder HTML\-Dokumente\) zugreifen. Die folgenden `CHtmlView`\-Memberfunktionen betreffen nur die Internet Explorer\-Anwendung. Diese Funktionen können im WebBrowser\-Steuerelement erfolgreich ausgeführt werden, sie haben aber keine sichtbare Auswirkung.  
  
-   [GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)  
  
-   [GetFullName](../Topic/CHtmlView::GetFullName.md)  
  
-   [GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)  
  
-   [GetAddressBar](../Topic/CHtmlView::SetAddressBar.md)  
  
-   [SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)  
  
-   [SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)  
  
-   [SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)  
  
-   [SetToolBar](../Topic/CHtmlView::SetToolBar.md)  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## Anforderungen  
 **Header:** afxhtml.h  
  
## Siehe auch  
 [MFC\-Beispiel\-MFCIE](../../top/visual-cpp-samples.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)