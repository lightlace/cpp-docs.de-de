---
title: Klasse CHtmlView-| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlView
dev_langs:
- C++
helpviewer_keywords:
- browsers, MFC support for
- CHtmlView class
- WebBrowser control
- WebBrowser control, MFC support
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9d96ab02a0c49a2ece12c933f5d550a46204a39
ms.lasthandoff: 02/24/2017

---
# <a name="chtmlview-class"></a>CHtmlView-Klasse
Stellt die Funktionalität des WebBrowser-Steuerelements im Kontext der MFC-Dokument-/Ansichtarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHtmlView : public CFormView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlView::Create](#create)|Erstellt das WebBrowser-Steuerelement.|  
|[CHtmlView::CreateControlSite](#createcontrolsite)|Überschreibbar. Verwendet, um eine Steuerelement-Websiteinstanz zum Hosten eines Steuerelements auf dem Formular zu erstellen.|  
|[CHtmlView::ExecFormsCommand](#execformscommand)|Führt den angegebenen Befehl mithilfe der Methode `IOleCommandTarget::Exec` aus.|  
|[CHtmlView::ExecWB](#execwb)|Führt einen Befehl aus.|  
|[CHtmlView::GetAddressBar](#getaddressbar)|Bestimmt, ob die Adressleiste des Internet Explorer-Objekts angezeigt wird. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::GetApplication](#getapplication)|Ruft ein Anwendungsobjekt ab, das die Anwendung darstellt, die die aktuelle Instanz der Internet Explorer-Anwendung enthält.|  
|[CHtmlView::GetBusy](#getbusy)|Ruft einen Wert ab, der angibt, ob aktuell noch ein Download oder eine andere Aktivität ausgeführt wird.|  
|[CHtmlView::GetContainer](#getcontainer)|Ruft den Container des WebBrowser-Steuerelements ab.|  
|[CHtmlView::GetFullName](#getfullname)|Ruft den vollständigen Namen, einschließlich Pfad, der im Webbrowser angezeigten Ressource ab. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::GetFullScreen](#getfullscreen)|Gibt an, ob das WebBrowser-Steuerelement im Vollbildmodus oder im normalen Modus ausgeführt wird.|  
|[CHtmlView::GetHeight](#getheight)|Ruft die Höhe des Internet Explorer-Hauptfensters ab.|  
|[CHtmlView::GetHtmlDocument](#gethtmldocument)|Ruft das aktive HTML-Dokument ab.|  
|[CHtmlView::GetLeft](#getleft)|Ruft die Bildschirmkoordinate der linken Kante des Internet Explorer-Hauptfensters ab.|  
|[CHtmlView::GetLocationName](#getlocationname)|Ruft den Namen der Ressource ab, die aktuell im WebBrowser angezeigt wird|  
|[CHtmlView::GetLocationURL](#getlocationurl)|Ruft die URL der Ressource ab, die aktuell im WebBrowser angezeigt wird.|  
|[CHtmlView::GetMenuBar](#getmenubar)|Ruft einen Wert ab, der bestimmt, ob die Menüleiste angezeigt wird.|  
|[CHtmlView::GetOffline](#getoffline)|Ruft einen Wert ab, der bestimmt, ob das Steuerelement offline ist.|  
|[CHtmlView::GetParentBrowser](#getparentbrowser)|Ruft einen Zeiger auf die `IDispatch` -Schnittstelle ab. Weitere Informationen finden Sie unter [die IDispatch-Schnittstelle implementieren](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](#getproperty)|Ruft den aktuellen Wert einer Eigenschaft ab, die dem angegebenen Objekt zugeordnet ist.|  
|[CHtmlView::GetReadyState](#getreadystate)|Ruft den Bereitschaftsstatus des Webbrowserobjekts ab.|  
|[CHtmlView::GetRegisterAsBrowser](#getregisterasbrowser)|Gibt an, ob das WebBrowser-Steuerelement als Browser der obersten Ebene für die Zielnamenauflösung registriert ist.|  
|[CHtmlView::GetRegisterAsDropTarget](#getregisterasdroptarget)|Gibt an, ob das WebBrowser-Steuerelement als Ablageziel für die Navigation registriert ist.|  
|[CHtmlView::GetSilent](#getsilent)|Gibt an, ob Dialogfelder angezeigt werden können.|  
|[CHtmlView::GetSource](#getsource)|Der HTML-Quellcode der Webseite.|  
|[CHtmlView::GetStatusBar](#getstatusbar)|Gibt an, ob die Statusleiste von Internet Explorer angezeigt wird. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::GetTheaterMode](#gettheatermode)|Gibt an, ob das WebBrowser-Steuerelement im Kinomodus ausgeführt wird.|  
|[CHtmlView::GetToolBar](#gettoolbar)|Ruft einen Wert ab, der bestimmt, ob die Symbolleiste angezeigt wird.|  
|[CHtmlView::GetTop](#gettop)|Ruft die Bildschirmkoordinate der oberen Kante des Internet Explorer-Hauptfensters ab.|  
|[CHtmlView::GetTopLevelContainer](#gettoplevelcontainer)|Ruft einen Wert ab, der angibt, ob das aktuelle Objekt den Container der obersten Ebene des WebBrowser-Steuerelements darstellt.|  
|[CHtmlView::GetType](#gettype)|Ruft den Typnamen des Dokumentobjekts ab.|  
|[CHtmlView::GetVisible](#getvisible)|Ruft einen Wert ab, der angibt, ob das Objekt sichtbar oder ausgeblendet ist.|  
|[CHtmlView::GetWidth](#getwidth)|Ruft die Breite des Internet Explorer-Hauptfensters ab.|  
|[CHtmlView::GoBack](#goback)|Navigiert zum vorherigen Element in der Verlaufsliste.|  
|[CHtmlView::GoForward](#goforward)|Navigiert zum nächsten Element in der Verlaufsliste.|  
|[CHtmlView::GoHome](#gohome)|Navigiert zur aktuellen Homepage oder Startseite.|  
|[CHtmlView::GoSearch](#gosearch)|Navigiert zur aktuellen Suchseite.|  
|[CHtmlView::LoadFromResource](#loadfromresource)|Lädt eine Ressource im WebBrowser-Steuerelement.|  
|[CHtmlView::Navigate](#navigate)|Navigiert zu der durch eine URL bezeichnete Ressource.|  
|[CHtmlView::Navigate2](#navigate2)|Navigiert zu der durch eine URL bezeichnete Ressource oder zu der durch einen vollständigen Pfad angegebenen Datei.|  
|[CHtmlView::OnBeforeNavigate2](#onbeforenavigate2)|Wird aufgerufen, bevor ein Navigationsvorgang im vorhandenen WebBrowser (entweder in einem Fenster- oder in einem Frameset-Element) ausgeführt wird.|  
|[CHtmlView::OnCommandStateChange](#oncommandstatechange)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der aktivierte Zustand eines Webbrowserbefehls geändert wurde.|  
|[CHtmlView::OnDocumentComplete](#ondocumentcomplete)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass ein Dokument den Zustand `READYSTATE_COMPLETE` erreicht hat.|  
|[CHtmlView::OnDocWindowActivate](#ondocwindowactivate)|Aufgerufen von der Internet Explorer oder MSHTML-Implementierung des [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), wird das aktive in-Place-Objekt, wenn der Container-Dokumentfenster aktiviert oder deaktiviert wird.|  
|[CHtmlView::OnDownloadBegin](#ondownloadbegin)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass ein Navigationsvorgang beginnt.|  
|[CHtmlView::OnDownloadComplete](#ondownloadcomplete)|Wird aufgerufen, wenn ein Navigationsvorgang beendet oder angehalten wurde bzw. wenn ein Fehler aufgetreten ist.|  
|[CHtmlView::OnEnableModeless](#onenablemodeless)|Wird aufgerufen, um Dialogfelder ohne Modus zu aktivieren oder deaktivieren, wenn der Container ein modales Dialogfeld erstellt oder entfernt.|  
|[CHtmlView::OnFilterDataObject](#onfilterdataobject)|Wird auf dem Host von Internet Explorer oder MSHTML aufgerufen, um dem Host das Ersetzen des Datenobjekts von Internet Explorer oder MSHTML zu ermöglichen.|  
|[CHtmlView::OnFrameWindowActivate](#onframewindowactivate)|Aufgerufen von [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) , um das Objekt zu benachrichtigen, wenn der Container der obersten Ebene-Rahmenfenster aktiviert bzw. deaktiviert wird.|  
|[CHtmlView::OnFullScreen](#onfullscreen)|Wird aufgerufen, wenn die FullScreen-Eigenschaft geändert wurde.|  
|[CHtmlView::OnGetDropTarget](#ongetdroptarget)|Von Internet Explorer oder MSHTML aufgerufen wird, wenn es als Ablageziel verwendet wird, wird um den Host Geben Sie eine Alternative ermöglichen [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CHtmlView::OnGetExternal](#ongetexternal)|Wird von Internet Explorer oder MSHTML aufgerufen, um die `IDispatch` -Schnittstelle des Hosts zu erhalten.|  
|[CHtmlView::OnGetHostInfo](#ongethostinfo)|Ruft die UI-Fähigkeiten des Internet Explorer- oder MSHTML-Hosts ab.|  
|[CHtmlView::OnGetOptionKeyPath](#ongetoptionkeypath)|Gibt den Registrierungsschlüssel zurück, unter dem Internet Explorer oder MSHTML Benutzereinstellungen speichert.|  
|[CHtmlView::OnHideUI](#onhideui)|Wird aufgerufen, wenn Internet Explorer oder MSHTML seine Menüs und Symbolleisten entfernt.|  
|[CHtmlView::OnMenuBar](#onmenubar)|Wird aufgerufen, wenn die MenuBar-Eigenschaft geändert wurde.|  
|[CHtmlView::OnNavigateComplete2](#onnavigatecomplete2)|Wird aufgerufen, nachdem die Navigation zu einem Link abgeschlossen wurde (in einem Fenster- oder FrameSet-Element).|  
|[CHtmlView::OnNavigateError](#onnavigateerror)|Wird vom Framework aufgerufen, wenn ein Fehler bei der Navigation zu einem Link auftritt.|  
|[CHtmlView::OnNewWindow2](#onnewwindow2)|Wird aufgerufen, wenn ein neues Fenster erstellt wird, um eine Ressource anzuzeigen.|  
|[CHtmlView::OnProgressChange](#onprogresschange)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der Status eines Downloadvorgangs aktualisiert wurde.|  
|[CHtmlView::OnPropertyChange](#onpropertychange)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, die die [PutProperty](#putproperty) Methode den Wert einer Eigenschaft geändert hat.|  
|[CHtmlView::OnQuit](#onquit)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass die Internet Explorer-Anwendung beendet werden kann. (Betrifft nur Internet Explorer)|  
|[CHtmlView::OnResizeBorder](#onresizeborder)|Aufgerufen von der Internet Explorer oder MSHTML-Implementierung von [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), die das Objekt, die Größe des Speicherplatzes Rahmen muss benachrichtigt.|  
|[CHtmlView::OnShowContextMenu](#onshowcontextmenu)|Wird von Internet Explorer oder MSHTML aufgerufen, wenn die Anzeige des Kontextmenüs bevorsteht.|  
|[CHtmlView::OnShowUI](#onshowui)|Wird aufgerufen, wenn die Anzeige von Menüs und Symbolleisten in Internet Explorer oder MSHTML bevorsteht.|  
|[CHtmlView::OnStatusBar](#onstatusbar)|Wird aufgerufen, wenn die StatusBar-Eigenschaft geändert wurde.|  
|[CHtmlView::OnStatusTextChange](#onstatustextchange)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, dass der Text in der Statusleiste des WebBrowser-Steuerelements geändert wurde.|  
|[CHtmlView::OnTheaterMode](#ontheatermode)|Wird aufgerufen, wenn die TheaterMode-Eigenschaft geändert wird.|  
|[CHtmlView::OnTitleChange](#ontitlechange)|Wird aufgerufen, um eine Anwendung zu benachrichtigen, wenn der Titel eines Dokuments im WebBrowser-Steuerelement verfügbar ist oder geändert wird.|  
|[CHtmlView::OnToolBar](#ontoolbar)|Wird aufgerufen, wenn sich die ToolBar-Eigenschaft geändert hat.|  
|[CHtmlView::OnTranslateAccelerator](#ontranslateaccelerator)|Von Internet Explorer oder MSHTML aufgerufen, wenn [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) oder [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) wird aufgerufen, um die Verarbeitung der Nachrichten im Menü Zugriffstaste Nachrichtenwarteschlange des Containers.|  
|[CHtmlView::OnTranslateUrl](#ontranslateurl)|Wird von Internet Explorer oder MSHTML aufgerufen, um dem Host die Möglichkeit zu geben, die zu ladende URL zu ändern.|  
|[CHtmlView::OnUpdateUI](#onupdateui)|Benachrichtigt den Host, dass sich der Befehlsstatus geändert hat.|  
|[CHtmlView::OnVisible](#onvisible)|Wird aufgerufen, wenn das Fenster für das WebBrowser-Steuerelement ein- oder ausgeblendet werden soll.|  
|[CHtmlView::PutProperty](#putproperty)|Legt den Wert einer Eigenschaft fest, die dem angegebenen Objekt zugeordnet ist.|  
|[CHtmlView::QueryFormsCommand](#queryformscommand)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|  
|[CHtmlView::QueryStatusWB](#querystatuswb)|Fragt den Status eines Befehls ab, der vom WebBrowser-Steuerelement verarbeitet wird.|  
|[CHtmlView::Refresh](#refresh)|Lädt die aktuelle Seite erneut.|  
|[CHtmlView::Refresh2](#refresh2)|Lädt die aktuelle Datei und verhindert optional das Senden der `pragma:nocache` -Header.|  
|[CHtmlView::SetAddressBar](#setaddressbar)|Blendet die Adressleiste des Internet Explorer-Objekts ein oder aus. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::SetFullScreen](#setfullscreen)|Legt einen Wert fest, um zu bestimmen, ob das Steuerelement im Vollbildmodus oder im normalen Fenstermodus ausgeführt wird (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::SetHeight](#setheight)|Legt die Höhe des Internet Explorer-Hauptfensters fest.|  
|[CHtmlView::SetLeft](#setleft)|Legt die horizontale Position des Internet Explorer-Hauptfensters fest.|  
|[CHtmlView::SetMenuBar](#setmenubar)|Legt einen Wert fest, der bestimmt, ob die Menüleiste des Steuerelements angezeigt wird. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::SetOffline](#setoffline)|Legt einen Wert fest, der bestimmt, ob das Steuerelement offline ist.|  
|[CHtmlView::SetRegisterAsBrowser](#setregisterasbrowser)|Legt einen Wert fest, der angibt, ob das WebBrowser-Steuerelement als Browser der obersten Ebene für die Zielnamenauflösung registriert ist.|  
|[CHtmlView::SetRegisterAsDropTarget](#setregisterasdroptarget)|Legt einen Wert fest, der angibt, ob das WebBrowser-Steuerelement als Ablageziel für die Navigation registriert ist.|  
|[CHtmlView::SetSilent](#setsilent)|Legt einen Wert fest, der angibt, ob das Steuerelement Dialogfelder anzeigt.|  
|[CHtmlView::SetStatusBar](#setstatusbar)|Legt einen Wert fest, der angibt, ob die Statusleiste von Internet Explorer angezeigt wird. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::SetTheaterMode](#settheatermode)|Legt einen Wert fest, der angibt, ob das WebBrowser-Steuerelement im Kinomodus ausgeführt wird.|  
|[CHtmlView::SetToolBar](#settoolbar)|Legt einen Wert fest, der bestimmt, ob die Symbolleiste des Steuerelements angezeigt wird. (Vom WebBrowser-Steuerelement ignoriert; nur Internet Explorer.)|  
|[CHtmlView::SetTop](#settop)|Legt die vertikale Position des Internet Explorer-Hauptfensters fest.|  
|[CHtmlView::SetVisible](#setvisible)|Legt einen Wert fest, der angibt, ob das Objekt sichtbar oder ausgeblendet ist.|  
|[CHtmlView::SetWidth](#setwidth)|Legt die Breite des Internet Explorer-Hauptfensters fest.|  
|[CHtmlView::Stop](#stop)|Bricht das Öffnen einer Datei ab.|  
  
## <a name="remarks"></a>Hinweise  
 Das WebBrowser-Steuerelement ist ein Fenster, in dem der Benutzer zu Websites im World Wide Web sowie zu Ordnern im lokalen Dateisystem und in einem Netzwerk navigieren kann. Das WebBrowser-Steuerelement unterstützt die Navigation mithilfe von Hyperlinks und URLs (Uniform Resource Locator) und unterhält eine Verlaufsliste.  
  
## <a name="using-the-chtmlview-class-in-an-mfc-application"></a>Verwenden der CHtmlView-Klasse in einer MFC-Anwendung  
 In der standardmäßigen MFC-Frameworkanwendung (entweder auf SDI oder auf MDI basierend) wird das Ansichtsobjekt üblicherweise aus einem spezialisierten Satz Klassen abgeleitet. Diese Klassen, die alle aus `CView`abgeleitet sind, bieten spezielle Funktionen über den von `CView`bereitgestellten Rahmen hinaus.  
  
 Die Ableitung der Ansichtsklasse der Anwendung aus `CHtmlView` stellt der Ansicht das WebBrowser-Steuerelement bereit. Dadurch wird die Anwendung praktisch zu einem Webbrowser. Die bevorzugte Methode zum Erstellen einer Anwendung im Stil eines Webbrowsers besteht in der Verwendung des MFC-Anwendungs-Assistenten und dem Angeben von `CHtmlView` als Ansichtsklasse. Weitere Informationen zum Implementieren und verwenden das WebBrowser-Steuerelement in MFC-Anwendung finden Sie unter [Erstellen einer Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  Das WebBrowser-ActiveX-Steuerelement (und daher `CHtmlView`) ist nur für Programme verfügbar, die unter den Windows NT-Versions 4.0 oder höher ausgeführt werden, auf denen Internet Explorer 4.0 oder höher installiert wurde.  
  
 `CHtmlView`Dient zur Anwendung, die Zugriff auf das Web (bzw. HTML-Dokumente). Die folgenden `CHtmlView` -Memberfunktionen betreffen nur die Internet Explorer-Anwendung. Diese Funktionen können im WebBrowser-Steuerelement erfolgreich ausgeführt werden, sie haben aber keine sichtbare Auswirkung.  
  
- [GetAddressBar](#getaddressbar)  
  
- [GetFullName](#getfullname)  
  
- [GetStatusBar](#getstatusbar)  
  
- [SetAddressBar](#setaddressbar)  
  
- [SetFullScreen](#setfullscreen)  
  
- [SetMenuBar](#setmenubar)  
  
- [SetStatusBar](#setstatusbar)  
  
- [SetToolBar](#settoolbar)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="a-namecreatea--chtmlviewcreate"></a><a name="create"></a>CHtmlView::Create  
 Rufen Sie diese Memberfunktion, um ein WebBrowser-Steuerelement oder ein Container für den Internet Explorer ausführbare Datei zu erstellen.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Windows-Klasse bezeichnet. Der Name der Klasse kann einen beliebigen Namen registriert die [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) globale Funktion oder die **RegisterClass** Windows-Funktion. Wenn **NULL**, verwendet die vordefinierte [CFrameWnd](../../mfc/reference/cframewnd-class.md) Attribute.  
  
 `lpszWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters darstellt.  
  
 `dwStyle`  
 Gibt die Stilattribute Fenster an. In der Standardeinstellung die **WS_VISIBLE** und **WS_CHILD** Fensterstile festgelegt sind.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters angibt. Die `rectDefault` Wert ermöglicht es Windows, um die Größe und Position des neuen Fensters festzulegen.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Steuerelements.  
  
 `nID`  
 Die ID der Ansicht. Legen Sie in der Standardeinstellung auf **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md). **NULL** standardmäßig.  
  
##  <a name="a-namecreatecontrolsitea--chtmlviewcreatecontrolsite"></a><a name="createcontrolsite"></a>CHtmlView::CreateControlSite  
 Überschreibbar. Verwendet, um eine Steuerelement-Websiteinstanz zum Hosten eines Steuerelements auf dem Formular zu erstellen.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT nID,  
    REFCLSID clsid);
```  
  
### <a name="parameters"></a>Parameter  
 `pContainer`  
 Ein Zeiger auf eine [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) -Objekt, das das Steuerelement enthält.  
  
 `ppSite`  
 Ein Zeiger auf einen Zeiger auf eine [COleControlSite](../../mfc/reference/colecontrolsite-class.md) -Objekt, für das Steuerelement die Website bereitstellen.  
  
 `nID`  
 Der Bezeichner für das Steuerelement gehostet werden.  
  
 `clsid`  
 Die CLSID des Steuerelements gehostet werden  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion zum Zurückgeben einer Instanz von eine eigene Website-Klasse überschreiben.  
  
##  <a name="a-nameexecformscommanda--chtmlviewexecformscommand"></a><a name="execformscommand"></a>CHtmlView::ExecFormsCommand  
 Führt den angegebenen Befehl mithilfe der Methode `IOleCommandTarget::Exec` aus.  
  
```  
HRESULT ExecFormsCommand(
    DWORD dwCommandID,  
    VARIANT* pVarIn,  
    VARIANT* pVarOut);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCommandID`  
 Der Befehl, der ausgeführt werden soll. Dieser Befehl muss gehören zu den **CMDSETID3_Forms3** Gruppe.  
  
 *pVarIn*  
 Zeiger auf eine **VARIANT** Struktur, die Eingabeargumente enthält. Kann **NULL**.  
  
 *pVarOut*  
 Zeiger auf eine **VARIANT** Struktur, um die Ausgabe des Befehls zu erhalten. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Eine vollständige Liste der möglichen Werte finden Sie unter [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 **ExecFormsCommand** die das Verhalten der [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) Methode.  
  
##  <a name="a-nameexecwba--chtmlviewexecwb"></a><a name="execwb"></a>CHtmlView::ExecWB  
 Rufen Sie diese Memberfunktion zum Ausführen eines Befehls im WebBrowser oder Internet Explorer.  
  
```  
void ExecWB(
    OLECMDID cmdID,  
    OLECMDEXECOPT cmdexecopt,  
    VARIANT* pvaIn,  
    VARIANT* pvaOut);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Der auszuführende Befehl.  
  
 *cmdexecopt*  
 Die Optionen für die Ausführung des Befehls.  
  
 `pvaIn`  
 Eine Variante, die Eingabeargumente des Befehls angegeben.  
  
 *pvaOut*  
 Eine Variante, die zur Angabe von Argumenten Ausgabe.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IWebBrowser2::ExecWB](https://msdn.microsoft.com/library/aa752117.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetaddressbara--chtmlviewgetaddressbar"></a><a name="getaddressbar"></a>CHtmlView::GetAddressBar  
 Rufen Sie diese Memberfunktion zum Abrufen von Internet Explorer Adressleiste ein.  
  
```  
BOOL GetAddressBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Adressleiste angezeigt wird; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namegetapplicationa--chtmlviewgetapplication"></a><a name="getapplication"></a>CHtmlView::GetApplication  
 Rufen Sie diese Memberfunktion zum Abrufen der Automation-Objekts unterstützt, die von der Anwendung, die das WebBrowser-Steuerelement enthält.  
  
```  
LPDISPATCH GetApplication() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDispatch` Schnittstelle des active Document-Objekts. Weitere Informationen finden Sie unter [die IDispatch-Schnittstelle implementieren](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetbusya--chtmlviewgetbusy"></a><a name="getbusy"></a>CHtmlView::GetBusy  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das WebBrowser-Steuerelement in einer Navigation oder downloadingvorgangs aktiviert ist.  
  
```  
BOOL GetBusy() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Webbrowser ausgelastet ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetcontainera--chtmlviewgetcontainer"></a><a name="getcontainer"></a>CHtmlView::GetContainer  
 Rufen Sie diese Memberfunktion zum Abrufen eines Objekts, das den Container des Webbrowsers ergibt.  
  
```  
LPDISPATCH GetContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDispatch` Schnittstelle des active Document-Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetfullnamea--chtmlviewgetfullname"></a><a name="getfullname"></a>CHtmlView::GetFullName  
 Rufen Sie diese Memberfunktion um den vollständigen Pfad der Datei abzurufen, die Internet Explorer derzeit angezeigt wird.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den Pfad und Namen der aktuell angezeigten Datei enthält. Wenn kein Pfad und Dateiname vorhanden, `GetFullName` gibt ein leeres `CString`.  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namegetfullscreena--chtmlviewgetfullscreen"></a><a name="getfullscreen"></a>CHtmlView::GetFullScreen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das WebBrowser-Steuerelement im Vollbildmodus oder im normalen Modus betrieben wird.  
  
```  
BOOL GetFullScreen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der WebBrowser im Vollbildmodus ausgeführt wird; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 In den Vollbildmodus main Internet Explorer-Fenster wird maximiert und die Statusleiste, die Symbolleiste, die Menüleiste und die Titelleiste werden ausgeblendet.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetheighta--chtmlviewgetheight"></a><a name="getheight"></a>CHtmlView::GetHeight  
 Rufen Sie diese Memberfunktion rufen die Höhe des Rahmenfensters des WebBrowser-Steuerelements in Pixel.  
  
```  
long GetHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Steuerelements Frame Fenster, in Pixel.  
  
##  <a name="a-namegethtmldocumenta--chtmlviewgethtmldocument"></a><a name="gethtmldocument"></a>CHtmlView::GetHtmlDocument  
 Rufen Sie diese Memberfunktion, um das HTML-Dokument für das aktive Dokument abzurufen.  
  
```  
LPDISPATCH GetHtmlDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDispatch` Schnittstelle des active Document-Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetlefta--chtmlviewgetleft"></a><a name="getleft"></a>CHtmlView::GetLeft  
 Rufen Sie diese Memberfunktion um den Abstand zwischen dem inneren linken Rand des WebBrowser-Steuerelements und dem linken Rand des Containers abzurufen.  
  
```  
long GetLeft() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abstand des linken Fensterrands in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetlocationnamea--chtmlviewgetlocationname"></a><a name="getlocationname"></a>CHtmlView::GetLocationName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Ressource, die in den WebBrowser angezeigt.  
  
```  
CString GetLocationName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt mit dem Namen der Ressource, die momentan in der WebBrowser angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Ressource eine HTML-Seite im World Wide Web ist, ist der Name der Titel der Seite. Wenn die Ressource einen Ordner oder eine Datei auf dem lokalen Computer oder im Netzwerk befindet, ist der Name der UNC-Namen oder den vollständigen Pfad des Ordners oder der Datei.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetlocationurla--chtmlviewgetlocationurl"></a><a name="getlocationurl"></a>CHtmlView::GetLocationURL  
 Rufen Sie diese Memberfunktion, um die URL der Ressource abzurufen, die das WebBrowser-Steuerelement gerade angezeigt wird.  
  
```  
CString GetLocationURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit der URL der Ressource, die momentan in der WebBrowser angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Ressource einen Ordner oder eine Datei auf dem lokalen Computer oder im Netzwerk befindet, ist der Name der UNC-Namen oder den vollständigen Pfad des Ordners oder der Datei.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetmenubara--chtmlviewgetmenubar"></a><a name="getmenubar"></a>CHtmlView::GetMenuBar  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Menüleiste angezeigt wird.  
  
```  
BOOL GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Menüleiste angezeigt wird; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetofflinea--chtmlviewgetoffline"></a><a name="getoffline"></a>CHtmlView::GetOffline  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der Webbrowser offline ausgeführt wird.  
  
```  
BOOL GetOffline() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Webbrowser gerade offline ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetparentbrowsera--chtmlviewgetparentbrowser"></a><a name="getparentbrowser"></a>CHtmlView::GetParentBrowser  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf das übergeordnete Objekt des WebBrowser-Steuerelements abzurufen.  
  
```  
LPDISPATCH GetParentBrowser() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `IDispatch` -Schnittstelle des Objekts, das das übergeordnete Element des WebBrowser-Steuerelements ist.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetpropertya--chtmlviewgetproperty"></a><a name="getproperty"></a>CHtmlView::GetProperty  
 Rufen Sie diese Memberfunktion um den Wert der Eigenschaft, die derzeit mit dem Steuerelement verknüpfte abzurufen.  
  
```  
BOOL GetProperty(
    LPCTSTR lpszProperty,  
    CString& strValue);  
  
COleVariant GetProperty(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProperty`  
 Ein Zeiger auf eine Zeichenfolge, die die Eigenschaft abgerufen.  
  
 `strValue`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den aktuellen Wert der Eigenschaft empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Version, einen Wert ungleich NULL, wenn erfolgreich abgeschlossen wurde; andernfalls&0; (null). In der zweiten Version eine [COleVariant](../../mfc/reference/colevariant-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetreadystatea--chtmlviewgetreadystate"></a><a name="getreadystate"></a>CHtmlView::GetReadyState  
 Rufen Sie diese Memberfunktion zum Abrufen des Status des WebBrowser-Objekts bereit.  
  
```  
READYSTATE GetReadyState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) -Wert fest, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetregisterasbrowsera--chtmlviewgetregisterasbrowser"></a><a name="getregisterasbrowser"></a>CHtmlView::GetRegisterAsBrowser  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das WebBrowser-Objekt der obersten Ebene Browser für die Auflösung des Ziel-Namen registriert ist.  
  
```  
BOOL GetRegisterAsBrowser() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Browser auf der obersten Ebene Browser registriert ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetregisterasdroptargeta--chtmlviewgetregisterasdroptarget"></a><a name="getregisterasdroptarget"></a>CHtmlView::GetRegisterAsDropTarget  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das WebBrowser-Steuerelement als Ablageziel für die Navigation registriert ist.  
  
```  
BOOL GetRegisterAsDropTarget() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Browser als Dropziel registriert ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetsilenta--chtmlviewgetsilent"></a><a name="getsilent"></a>CHtmlView::GetSilent  
 Rufen Sie diese Memberfunktion, um festzustellen, ob alle Dialogfelder in das WebBrowser-Steuerelement angezeigt werden können.  
  
```  
BOOL GetSilent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Dialogfelder aus dem WebBrowser-Steuerelement angezeigt werden können; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetsourcea--chtmlviewgetsource"></a><a name="getsource"></a>CHtmlView::GetSource  
 Rufen Sie diese Memberfunktion zum Abrufen der HTML-Quellcode für die Webseite ein.  
  
```  
BOOL GetSource(CString& strRef);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="parameters"></a>Parameter  
 `refString`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die den Quellcode enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist äquivalent zum Befehl "Quelltext anzeigen" in Internet Explorer, mit der Ausnahme, dass der Quellcode in zurückgegeben wird ein `CString`.  
  
##  <a name="a-namegetstatusbara--chtmlviewgetstatusbar"></a><a name="getstatusbar"></a>CHtmlView::GetStatusBar  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das WebBrowser-Steuerelement eine Statusleiste angezeigt.  
  
```  
BOOL GetStatusBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Statusleiste angezeigt werden kann; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namegettheatermodea--chtmlviewgettheatermode"></a><a name="gettheatermode"></a>CHtmlView::GetTheaterMode  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der Webbrowser im Theater-Modus befindet.  
  
```  
BOOL GetTheaterMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Webbrowser im Theater-Modus ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Webbrowser im Theater-Modus befindet, im Browser Hauptfenster den gesamten Bildschirm einnimmt, wird eine Symbolleiste mit einem minimalen Satz von Navigationstools angezeigt und die Statusleiste wird angezeigt, in der oberen rechten Ecke des Bildschirms.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegettoolbara--chtmlviewgettoolbar"></a><a name="gettoolbar"></a>CHtmlView::GetToolBar  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Symbolleiste sichtbar ist.  
  
```  
int GetToolBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, ob die Symbolleiste sichtbar ist. Wert ungleich NULL, wenn die Symbolleiste sichtbar ist; andernfalls&0; (null).  
  
##  <a name="a-namegettopa--chtmlviewgettop"></a><a name="gettop"></a>CHtmlView::GetTop  
 Rufen Sie diese Memberfunktion zum Abrufen der Bildschirmkoordinate des oberen Rands des Hauptfensters des WebBrowser-Steuerelements.  
  
```  
long GetTop() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Adresse einer Variablen, die die Bildschirmkoordinate des oberen Randes des Hauptfensters empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegettoplevelcontainera--chtmlviewgettoplevelcontainer"></a><a name="gettoplevelcontainer"></a>CHtmlView::GetTopLevelContainer  
 Rufen Sie diese Memberfunktion, um festzustellen, ob Internet Explorer den Container der obersten Ebene des WebBrowser-Steuerelements ist.  
  
```  
BOOL GetTopLevelContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Container ist ungleich NULL ist der Container der obersten Ebene; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegettypea--chtmlviewgettype"></a><a name="gettype"></a>CHtmlView::GetType  
 Rufen Sie diese Memberfunktion, um den Namen des aktiven Dokuments enthaltene abrufen.  
  
```  
CString GetType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit dem Namen des Datentyps des aktiven Dokuments enthaltene Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetvisiblea--chtmlviewgetvisible"></a><a name="getvisible"></a>CHtmlView::GetVisible  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das enthaltene Objekt sichtbar ist.  
  
```  
BOOL GetVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt sichtbar ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegetwidtha--chtmlviewgetwidth"></a><a name="getwidth"></a>CHtmlView::GetWidth  
 Ruft die Breite des Internet Explorer-Hauptfensters ab.  
  
```  
long GetWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Breite des Fensters in Pixel.  
  
##  <a name="a-namegobacka--chtmlviewgoback"></a><a name="goback"></a>CHtmlView::GoBack  
 Navigiert rückwärts ein Element in der Verlaufsliste.  
  
```  
void GoBack();
```  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegoforwarda--chtmlviewgoforward"></a><a name="goforward"></a>CHtmlView::GoForward  
 Navigiert vorwärts ein Element in der Verlaufsliste.  
  
```  
void GoForward();
```  
  
##  <a name="a-namegohomea--chtmlviewgohome"></a><a name="gohome"></a>CHtmlView::GoHome  
 Navigiert zur aktuellen Homepage oder Startseite, die im Dialogfeld „Internetoptionen“ von Internet Explorer oder im Dialogfeld „Interneteigenschaften“ beim Zugriff aus der Systemsteuerung festgelegt ist.  
  
```  
void GoHome();
```  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namegosearcha--chtmlviewgosearch"></a><a name="gosearch"></a>CHtmlView::GoSearch  
 Navigiert zu der aktuellen Suchseite wie angegeben in das Dialogfeld Internetoptionen von Internet Explorer oder das Dialogfeld Eigenschaften von Internet zugegriffen wird, in der Systemsteuerung.  
  
```  
void GoSearch();
```  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-nameloadfromresourcea--chtmlviewloadfromresource"></a><a name="loadfromresource"></a>CHtmlView::LoadFromResource  
 Rufen Sie diese Memberfunktion, um die angegebene Ressource in das WebBrowser-Steuerelement zu laden.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResource`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Ressource zu laden.  
  
 `nRes`  
 Die ID des Puffers, der mit dem Namen der Ressource geladen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namenavigatea--chtmlviewnavigate"></a><a name="navigate"></a>CHtmlView::Navigate  
 Rufen Sie diese Memberfunktion auf, auf die Ressource identifiziert, die durch eine URL zu navigieren.  
  
```  
void Navigate(
    LPCTSTR URL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *URL*  
 Ein vom Aufrufer reservierte Zeichenfolge mit der URL zu navigieren oder den vollständigen Pfad der Datei angezeigt.  
  
 `dwFlags`  
 Die Flags einer Variablen, der angibt, ob die Ressource die Verlaufsliste hinzugefügt, ob zum Lesen oder Schreiben aus dem Cache und angibt, ob die Ressource in einem neuen Fenster anzuzeigen. Die Variable kann eine Kombination der Werte von definiert die [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) Enumeration.  
  
 `lpszTargetFrameName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Frames, in dem die Ressource angezeigt.  
  
 `lpszHeaders`  
 Ein Zeiger auf einen Wert, der angibt, die HTTP-Header an den Server gesendet. Diese Header werden die Standard-Internet Explorer-Header hinzugefügt. Die Header können u. a. als die des Servers, den Typ der Daten an den Server oder einen Statuscode erforderliche Aktion angeben. Dieser Parameter wird ignoriert, wenn *URL* ist keine HTTP-URL.  
  
 `lpvPostData`  
 Ein Zeiger auf die Daten, die mit der HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten, die durch ein HTML-Formular verwendet. Wenn dieser Parameter keine Post-Daten angegeben wird **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn *URL* ist keine HTTP-URL.  
  
 `dwPostDataLen`  
 Daten, die HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten, die durch ein HTML-Formular verwendet. Wenn dieser Parameter keine Post-Daten angegeben wird **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn *URL* ist keine HTTP-URL.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namenavigate2a--chtmlviewnavigate2"></a><a name="navigate2"></a>CHtmlView::Navigate2  
 Rufen Sie diese Memberfunktion auf, auf die Ressource durch eine URL identifiziert, oder der Datei, die einen vollständigen Pfad identifizierten zu navigieren.  
  
```  
void Navigate2(
    LPITEMIDLIST pIDL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags,  
    CByteArray& baPostedData,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeader = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pIDL*  
 Ein Zeiger auf eine [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) Struktur.  
  
 `dwFlags`  
 Die Flags einer Variablen, der angibt, ob die Ressource die Verlaufsliste hinzugefügt, ob zum Lesen oder Schreiben aus dem Cache und angibt, ob die Ressource in einem neuen Fenster anzuzeigen. Die Variable kann eine Kombination der Werte von definiert die [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) Enumeration.  
  
 `lpszTargetFrameName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Frames, in dem die Ressource angezeigt.  
  
 `lpszURL`  
 Ein Zeiger auf eine Zeichenfolge mit der URL.  
  
 `lpvPostData`  
 Daten, die HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten, die durch ein HTML-Formular verwendet. Wenn dieser Parameter keine Post-Daten angegeben wird `Navigate2` stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn *URL* ist kein HTTP oder HTTPS-URL.  
  
 `dwPostDataLen`  
 Die Länge in Bytes der Daten auf den die `lpvPostData` Parameter.  
  
 `lpszHeaders`  
 Ein Zeiger auf einen Wert, der angibt, die HTTP- oder HTTPS-Header an den Server gesendet. Diese Header werden die Standard-Internet Explorer-Header hinzugefügt. Die Header können u. a. als die des Servers, den Typ der Daten an den Server oder einen Statuscode erforderliche Aktion angeben. Dieser Parameter wird ignoriert, wenn *URL* ist kein HTTP oder HTTPS-URL.  
  
 `baPostedData`  
 Ein Verweis auf eine [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion erweitert die **navigieren** Member-Funktion, durch die Unterstützung der Suchvorgänge auf besondere Ordner, z. B. Desktop- und Arbeitsplatz, die vom Parameter dargestellt werden *pIDL*.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&#7;](../../mfc/reference/codesnippet/cpp/chtmlview-class_1.cpp)]  
  
##  <a name="a-nameonbeforenavigate2a--chtmlviewonbeforenavigate2"></a><a name="onbeforenavigate2"></a>CHtmlView::OnBeforeNavigate2  
 Diese Memberfunktion wird von dem Framework dazu führen, dass ein Ereignis ausgelöst, bevor eine Navigation im Webbrowser wird aufgerufen.  
  
```  
virtual void OnBeforeNavigate2(
    LPCTSTR lpszURL,  
    DWORD nFlags,  
    LPCTSTR lpszTargetFrameName,  
    CByteArray& baPostedData,  
    LPCTSTR lpszHeaders,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Ein Zeiger auf eine Zeichenfolge mit der URL zu navigieren.  
  
 `nFlags`  
 Für zukünftige Verwendung reserviert.  
  
 `lpszTargetFrameName`  
 Eine Zeichenfolge mit dem Namen des Frames, in dem die Ressource angezeigt oder **NULL** Wenn keine benannte Frame für die Ressource bestimmt wird.  
  
 `baPostedData`  
 Ein Verweis auf ein `CByteArray` Objekt mit Daten, die an den Server gesendet werden soll, wenn die HTTP POST-Transaktion verwendet wird.  
  
 `lpszHeaders`  
 Ein Zeiger auf eine Zeichenfolge mit zusätzlichen HTTP-Headern zum Senden an den Server (nur für HTTP-URLs). Die Header können u. a. als die des Servers, den Typ der Daten an den Server oder einen Statuscode erforderliche Aktion angeben.  
  
 `pbCancel`  
 Ein Zeiger auf ein Flag "Abbrechen". Eine Anwendung lassen sich dieser Parameter auf einen Wert ungleich NULL, um die Navigation abzubrechen oder NULL zulassen, um den Vorgang fortzusetzen.  
  
##  <a name="a-nameoncommandstatechangea--chtmlviewoncommandstatechange"></a><a name="oncommandstatechange"></a>CHtmlView::OnCommandStateChange  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, die dass der Aktivierungsstatus für einen Web-Browser-Befehl geändert hat.  
  
```  
virtual void OnCommandStateChange(
    long nCommand,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *%nbefehl*  
 Der Bezeichner des Befehls, dessen Aktivierungsstatus geändert hat.  
  
 `bEnable`  
 Aktivierten Status. Dieser Parameter ist ungleich NULL, wenn der Befehl aktiviert ist, oder&0; (null), wenn er deaktiviert ist.  
  
##  <a name="a-nameondocumentcompletea--chtmlviewondocumentcomplete"></a><a name="ondocumentcomplete"></a>CHtmlView::OnDocumentComplete  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, die ein Dokument erreicht hat die `READYSTATE_COMPLETE` Zustand.  
  
```  
virtual void OnDocumentComplete(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Ein Zeiger auf eine Zeichenfolge, die die UNC-URL ergibt Datei Name oder eine PIDL (einen Zeiger auf eine Liste der Bezeichner), zu der navigiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Nicht jedes Einzelbild löst dieses Ereignis, aber jeder Frame, der ausgelöst wird ein [OnDownloadBegin](#ondownloadbegin) Ereignis wird ausgelöst, eine entsprechende `OnDocumentComplete` Ereignis.  
  
 Durch die URL angegebene `lpszURL` kann die URL, die dem Browser, navigieren mitgeteilt wurde, da diese URL der kanonisierten und qualifizierte URL unterscheidet. Wenn eine Anwendung in einem Aufruf an eine URL "www.Microsoft.com" gibt z. B. [navigieren](#navigate) oder [Navigate2](#navigate2), übergeben von `OnNavigateComplete2` werden "http://www.microsoft.com/". Auch wenn der Server den Browser zu einer anderen URL umgeleitet, wird die umgeleitete URL hier berücksichtigt.  
  
##  <a name="a-nameondocwindowactivatea--chtmlviewondocwindowactivate"></a><a name="ondocwindowactivate"></a>CHtmlView::OnDocWindowActivate  
 Wird von der Implementierung von **IOleInPlaceActiveObject::OnDocWindowActivate**von Internet Explorer oder MSHTML aufgerufen, die das aktive direkte Objekt benachrichtigt, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird.  
  
```  
virtual HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Gibt den Status des Dokumentfensters angezeigt. Wenn dieser Wert ungleich NULL ist, wird das Fenster aktiviert wird. Wenn dieser Wert&0; (null) ist, wird das Fenster deaktiviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnDocWindowActivate` an die `OnDocWindowActivate` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameondownloadbegina--chtmlviewondownloadbegin"></a><a name="ondownloadbegin"></a>CHtmlView::OnDownloadBegin  
 Diese Memberfunktion heißt vom Framework mit dem ein Dokument herunterladen beginnen.  
  
```  
virtual void OnDownloadBegin();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Ereignis wird ausgelöst, kurz nach der [OnBeforeNavigate2](#onbeforenavigate2) Ereignis, wenn die Navigation nicht abgebrochen wird. Dieses Ereignis sollte Animationen oder "ausgelastet" festgestellt, dass die Anzeige der Container muss verbunden sein.  
  
##  <a name="a-nameondownloadcompletea--chtmlviewondownloadcomplete"></a><a name="ondownloadcomplete"></a>CHtmlView::OnDownloadComplete  
 Diese Member-Funktion wird aufgerufen, durch das Framework an, dass ein Navigationsvorgang abgeschlossen ist, angehalten wurde oder fehlgeschlagen ist.  
  
```  
virtual void OnDownloadComplete();
```  
  
##  <a name="a-nameonenablemodelessa--chtmlviewonenablemodeless"></a><a name="onenablemodeless"></a>CHtmlView::OnEnableModeless  
 Wird aufgerufen, wenn Internet Explorer oder MSHTML modale Benutzeroberfläche anzeigt.  
  
```  
virtual HRESULT OnEnableModeless(BOOL fEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `fEnable`  
 Gibt an, ob der Host nicht modale Dialogfelder aktiviert oder deaktiviert werden. Wenn dieser Wert ungleich NULL ist, werden nicht modale Dialogfelder aktiviert. Wenn dieser Wert&0; (null) ist, werden nicht modale Dialogfelder deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Aktiviert oder deaktiviert nicht modale Dialogfelder, wenn der Container erstellt oder ein modales Dialogfeld zerstört. Überschreiben `OnEnableModeless` an die `EnableModeless` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonfilterdataobjecta--chtmlviewonfilterdataobject"></a><a name="onfilterdataobject"></a>CHtmlView::OnFilterDataObject  
 Wird auf dem Host von Internet Explorer oder MSHTML aufgerufen, um dem Host das Ersetzen des Datenobjekts von Internet Explorer oder MSHTML zu ermöglichen.  
  
```  
virtual HRESULT OnFilterDataObject(
    LPDATAOBJECT pDataObject,  
    LPDATAOBJECT* ppDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Adresse der [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Schnittstelle, die von Internet Explorer oder MSHTML bereitgestellt wird.  
  
 *ppDataObject*  
 Adresse, die empfängt die `IDataObject` vom Host bereitgestellten Schnittstellenzeiger. Der Inhalt dieses Parameters sollte immer auf initialisiert werden **NULL**, auch wenn die Methode fehlschlägt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn das Objekt ersetzt wird, **S_FALSE** Wenn das Objekt nicht ersetzt wird, oder ein OLE definierter Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnFilterDataObject` an die `FilterDataObject` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonframewindowactivatea--chtmlviewonframewindowactivate"></a><a name="onframewindowactivate"></a>CHtmlView::OnFrameWindowActivate  
 Aufgerufen von [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) , um das Objekt zu benachrichtigen, wenn der Container der obersten Ebene-Rahmenfenster aktiviert bzw. deaktiviert wird.  
  
```  
virtual HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Gibt den Zustand des Containers auf oberster Ebene Rahmenfenster. Wenn dieser Wert ungleich NULL ist, wird das Fenster aktiviert wird. Wenn dieser Wert&0; (null) ist, wird das Fenster deaktiviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnFrameWindowActivate` an die `OnFrameWindowActivate` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonfullscreena--chtmlviewonfullscreen"></a><a name="onfullscreen"></a>CHtmlView::OnFullScreen  
 Diese Member-Funktion wird vom Framework aufgerufen wenn der [Vollbild](https://msdn.microsoft.com/library/aa752119.aspx) -Eigenschaft geändert hat.  
  
```  
virtual void OnFullScreen(BOOL bFullScreen);
```  
  
### <a name="parameters"></a>Parameter  
 *bFullScreen*  
 Wert ungleich NULL, wenn Internet Explorer im Vollbildmodus ausgeführt wird; andernfalls NULL.  
  
##  <a name="a-nameongetdroptargeta--chtmlviewongetdroptarget"></a><a name="ongetdroptarget"></a>CHtmlView::OnGetDropTarget  
 Wird von Internet Explorer oder MSHTML bei der Verwendung als Ablageziel aufgerufen, um dem Host die Bereitstellung eines alternativen `IDropTarget`.  
  
```  
virtual HRESULT OnGetDropTarget(
    LPDROPTARGET pDropTarget,  
    LPDROPTARGET* ppDropTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pDropTarget`  
 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) will, dass Internet Explorer oder MSHTML verwenden.  
  
 `ppDropTarget`  
 Adresse der `IDropTarget` , empfängt die `IDropTarget` Schnittstellenzeiger auf der Host bereitstellen möchte.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der Rückgabecodes.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnGetDropTarget` an die `GetDropTarget` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameongetexternala--chtmlviewongetexternal"></a><a name="ongetexternal"></a>CHtmlView::OnGetExternal  
 Wird von Internet Explorer oder MSHTML aufgerufen, um die `IDispatch` -Schnittstelle des Hosts zu erhalten.  
  
```  
virtual HRESULT OnGetExternal(LPDISPATCH* lppDispatch);
```  
  
### <a name="parameters"></a>Parameter  
 *lppDispatch*  
 Ein Zeiger auf die Adresse, die empfängt die `IDispatch` -Schnittstellenzeiger, der Host-Anwendung. Wenn der Host eine Automatisierungsschnittstelle verfügbar macht, können sie einen Verweis auf Internet Explorer oder MSHTML über diesen Parameter bereitzustellen. Der Inhalt dieses Parameters sollte immer auf initialisiert werden **NULL**, auch wenn die Methode fehlschlägt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnGetExternal` an die `GetExternal` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameongethostinfoa--chtmlviewongethostinfo"></a><a name="ongethostinfo"></a>CHtmlView::OnGetHostInfo  
 Ruft die UI-Fähigkeiten des Internet Explorer- oder MSHTML-Hosts ab.  
  
```  
virtual HRESULT OnGetHostInfo(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Adresse einer [DOCHOSTUIINFO](https://msdn.microsoft.com/library/aa770044.aspx) -Struktur, die Funktionen für den Host empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnGetHostInfo` an die `GetHostInfo` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameongetoptionkeypatha--chtmlviewongetoptionkeypath"></a><a name="ongetoptionkeypath"></a>CHtmlView::OnGetOptionKeyPath  
 Rufen Sie diese Memberfunktion um den Registrierungsschlüssel zu erhalten, unter dem Internet Explorer oder MSHTML-Voreinstellungen des Benutzers gespeichert.  
  
```  
virtual HRESULT OnGetOptionKeyPath(
    LPOLESTR* pchKey,  
    DWORD dwReserved);
```  
  
### <a name="parameters"></a>Parameter  
 `pchKey`  
 Adresse einer `LPOLESTR` , empfängt die Unterschlüssel Registrierungszeichenfolge, in dem der Host die Standardoptionen speichert. Dieser Unterschlüssel werden unter dem Schlüssel HKEY_CURRENT_USER. Dieser Speicher mithilfe [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727). Die aufrufende Anwendung ist verantwortlich für das Freigeben von Arbeitsspeicher verwenden [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722). Dieser Parameter sollte immer initialisiert werden, um **NULL**, auch wenn die Methode fehlschlägt.  
  
 `dwReserved`  
 Für zukünftige Verwendung reserviert. Zurzeit nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Im Erfolgsfall oder **S_FALSE** andernfalls. Wenn **S_FALSE**, Internet Explorer oder MSHTML wird standardmäßig eine eigene Benutzeroptionen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnGetOptionKeyPath` an die `GetOptionKeyPath` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonhideuia--chtmlviewonhideui"></a><a name="onhideui"></a>CHtmlView::OnHideUI  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn Internet Explorer oder MSHTML Menüs und Symbolleisten werden entfernt.  
  
```  
virtual HRESULT OnHideUI();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnHideUI` an die `HideUI` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonmenubara--chtmlviewonmenubar"></a><a name="onmenubar"></a>CHtmlView::OnMenuBar  
 Diese Member-Funktion wird vom Framework aufgerufen wenn der [MenuBar](https://msdn.microsoft.com/library/aa752131.aspx) -Eigenschaft geändert hat.  
  
```  
virtual void OnMenuBar(BOOL bMenuBar);
```  
  
### <a name="parameters"></a>Parameter  
 *bMenuBar*  
 Wert ungleich NULL, wenn der Internet Explorer-Menüleiste angezeigt wird; andernfalls NULL.  
  
##  <a name="a-nameonnavigatecomplete2a--chtmlviewonnavigatecomplete2"></a><a name="onnavigatecomplete2"></a>CHtmlView::OnNavigateComplete2  
 Diese Memberfunktion wird vom Framework aufgerufen, nach Abschluss eine Navigation zu einem Hyperlink (in einem Fenster- oder Frameset-Element).  
  
```  
virtual void OnNavigateComplete2(LPCTSTR strURL);
```  
  
### <a name="parameters"></a>Parameter  
 *strURL*  
 Ein Zeichenfolgenausdruck, der die URL ergibt UNC-Namen, oder PIDL (einen Zeiger auf eine Liste der Bezeichner), zu der navigiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der URL-Parameter kann eine PIDL im Falle einer Shell Name Space-Entität für die keine Entsprechung für die URL vorhanden ist.  
  
 Beachten Sie, die in die URL enthalten *StrURL* kann die URL, die dem Browser, navigieren mitgeteilt wurde, da diese URL der kanonisierten und qualifizierte URL unterscheidet. Wenn eine Anwendung in einem Aufruf an eine URL "www.Microsoft.com" gibt z. B. [navigieren](#navigate) oder [Navigate2](#navigate2), übergeben von `OnNavigateComplete2` werden "http://www.microsoft.com/". Auch wenn der Server den Browser zu einer anderen URL umgeleitet, wird die umgeleitete URL hier berücksichtigt.  
  
##  <a name="a-nameonnavigateerrora--chtmlviewonnavigateerror"></a><a name="onnavigateerror"></a>CHtmlView::OnNavigateError  
 Wird vom Framework aufgerufen, wenn ein Fehler bei der Navigation zu einem Link auftritt.  
  
```  
virtual void OnNavigateError(
    LPCTSTR lpszURL,  
    LPCTSTR lpszFrame,  
    DWORD dwError,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Die URL für die Navigation fehlgeschlagen ist.  
  
 *lpszFrame*  
 Der Name des Frames, in der die Ressource ist, werden Sie angezeigt werden, oder NULL, wenn keine benannten Frame für die Ressource zugewiesen wurde.  
  
 `dwError`  
 Status der Fehlercode, falls verfügbar. Eine Liste der möglichen HRESULT und HTTP-Statuscodes finden Sie unter [NavigateError Ereignis Statuscodes.](https://msdn.microsoft.com/library/aa768365.aspx)  
  
 `pbCancel`  
 Gibt an, ob die Navigation zu einer Fehlerseite oder weiteren automatische Suche abgebrochen werden soll. Wenn **TRUE** (Standard), Navigation zu einer Fehlerseite oder die automatische Suche; fort, wenn **FALSE**, Navigation, eine Fehlerseite oder die automatische Suche abbrechen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Fehlerbehandlung für die benutzerdefinierte Navigation bereitstellen.  
  
 Weitere Informationen finden Sie unter [DWebBrowserEvents2::NavigateError](https://msdn.microsoft.com/library/aa768286.aspx)  
  
##  <a name="a-nameonnewwindow2a--chtmlviewonnewwindow2"></a><a name="onnewwindow2"></a>CHtmlView::OnNewWindow2  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn ein neues Fenster wird für eine Ressource anzuzeigen.  
  
```  
virtual void OnNewWindow2(
    LPDISPATCH* ppDisp,  
    BOOL* Cancel);
```  
  
### <a name="parameters"></a>Parameter  
 `ppDisp`  
 Ein Zeiger auf einen Schnittstellenzeiger, der optional ist, empfängt die `IDispatch` -Schnittstellenzeiger eines neuen WebBrowser oder Internet Explorer-Objekts.  
  
 `Cancel`  
 Ein Zeiger auf ein Flag "Abbrechen". Eine Anwendung lassen sich dieser Parameter auf einen Wert ungleich NULL, um die Navigation abzubrechen oder NULL zulassen, um den Vorgang fortzusetzen.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Ereignis steht vor der Erstellung eines neuen Fensters aus in den WebBrowser.  
  
##  <a name="a-nameonprogresschangea--chtmlviewonprogresschange"></a><a name="onprogresschange"></a>CHtmlView::OnProgressChange  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, dass der Status eines Downloadvorgangs aktualisiert wurde.  
  
```  
virtual void OnProgressChange(
    long nProgress,  
    long nProgressMax);
```  
  
### <a name="parameters"></a>Parameter  
 *nProgress*  
 Die Menge des Gesamtstatus zum Anzeigen oder -1, wenn der Vorgang abgeschlossen ist.  
  
 *nProgressMax*  
 Maximale Fortschrittswert.  
  
### <a name="remarks"></a>Hinweise  
 Container können die Angaben, die von diesem Ereignis, um die Anzahl der bisher heruntergeladenen Bytes anzuzeigen oder um eine Statusanzeige zu aktualisieren.  
  
##  <a name="a-nameonpropertychangea--chtmlviewonpropertychange"></a><a name="onpropertychange"></a>CHtmlView::OnPropertyChange  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, [PutProperty](#putproperty) den Wert einer Eigenschaft geändert hat.  
  
```  
virtual void OnPropertyChange(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProperty`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der Eigenschaft enthält.  
  
##  <a name="a-nameonquita--chtmlviewonquit"></a><a name="onquit"></a>CHtmlView::OnQuit  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, die dass die Internet Explorer-Anwendung beendet ist.  
  
```  
virtual void OnQuit();
```  
  
##  <a name="a-nameonresizebordera--chtmlviewonresizeborder"></a><a name="onresizeborder"></a>CHtmlView::OnResizeBorder  
 Aufgerufen von der Internet Explorer oder MSHTML-Implementierung von [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), die das Objekt, die Größe des Speicherplatzes Rahmen muss benachrichtigt.  
  
```  
virtual HRESULT OnResizeBorder(
    LPCRECT prcBorder,  
    LPOLEINPLACEUIWINDOW pUIWindow,  
    BOOL fFrameWindow);
```  
  
### <a name="parameters"></a>Parameter  
 `prcBorder`  
 Neue äußere Rechteck Rahmen Speicherplatz.  
  
 `pUIWindow`  
 Ein Zeiger auf die Schnittstelle für das Frame oder das Dokumentfenster Window-Objekt, dessen Rahmen geändert hat.  
  
 `fFrameWindow`  
 **True,** beim Aufrufen des Rahmenfensters [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), andernfalls **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnResizeBorder` an die `ResizeBorder` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonshowcontextmenua--chtmlviewonshowcontextmenu"></a><a name="onshowcontextmenu"></a>CHtmlView::OnShowContextMenu  
 Wird von Internet Explorer oder MSHTML aufgerufen, wenn die Anzeige des Kontextmenüs bevorsteht.  
  
```  
virtual HRESULT OnShowContextMenu(
    DWORD dwID,  
    LPPOINT ppt,  
    LPUNKNOWN pcmdtReserved,  
    LPDISPATCH pdispReserved);
```  
  
### <a name="parameters"></a>Parameter  
 `dwID`  
 Der Bezeichner des Kontextmenüs angezeigt werden. Finden Sie unter **IDocHostUIHandler::ShowContextMenu** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
 `ppt`  
 Bildschirmkoordinaten für das Menü.  
  
 `pcmdtReserved`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) verwendete Schnittstelle zum Befehlsstatus Abfragen und Befehle für dieses Objekt ausführen.  
  
 `pdispReserved`  
 IDispatch-Schnittstelle des Objekts an den Bildschirmkoordinaten. Dies ermöglicht es einem Host zur Unterscheidung von bestimmter Objekten um spezifischere Kontext bereitzustellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnShowContextMenu` an die `ShowContextMenu` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonshowuia--chtmlviewonshowui"></a><a name="onshowui"></a>CHtmlView::OnShowUI  
 Wird aufgerufen, wenn die Anzeige von Menüs und Symbolleisten in Internet Explorer oder MSHTML bevorsteht.  
  
```  
virtual HRESULT OnShowUI(
    DWORD dwID,  
    LPOLEINPLACEACTIVEOBJECT pActiveObject,  
    LPOLECOMMANDTARGET pCommandTarget,  
    LPOLEINPLACEFRAME pFrame,  
    LPOLEINPLACEUIWINDOW pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `dwID`  
 Für zukünftige Verwendung reserviert.  
  
 `pActiveObject`  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) Schnittstelle das aktive Objekt.  
  
 `pCommandTarget`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) -Schnittstelle des Objekts.  
  
 `pFrame`  
 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) -Schnittstelle des Objekts. Dies ist für Menüs und Symbolleisten erforderlich.  
  
 `pDoc`  
 [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) Schnittstelle für das Objekt. Dies ist für Symbolleisten erforderlich.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnShowUI` an die `ShowUI` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonstatusbara--chtmlviewonstatusbar"></a><a name="onstatusbar"></a>CHtmlView::OnStatusBar  
 Diese Member-Funktion wird vom Framework aufgerufen wenn der [StatusBar](https://msdn.microsoft.com/library/aa768270.aspx) -Eigenschaft geändert hat.  
  
```  
virtual void OnStatusBar(BOOL bStatusBar);
```  
  
### <a name="parameters"></a>Parameter  
 *bStatusBar*  
 Ungleich NULL, wenn Internet Explorer Statusleiste sichtbar ist, oder andernfalls NULL.  
  
##  <a name="a-nameonstatustextchangea--chtmlviewonstatustextchange"></a><a name="onstatustextchange"></a>CHtmlView::OnStatusTextChange  
 Diese Member-Funktion wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, dass der Text der Statusleiste mit dem WebBrowser-Steuerelement geändert hat.  
  
```  
virtual void OnStatusTextChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Eine Zeichenfolge, die den neuen Statusleistentext enthält.  
  
##  <a name="a-nameontheatermodea--chtmlviewontheatermode"></a><a name="ontheatermode"></a>CHtmlView::OnTheaterMode  
 Diese Member-Funktion wird vom Framework aufgerufen wenn der [TheaterMode](https://msdn.microsoft.com/library/aa768273.aspx) -Eigenschaft geändert hat.  
  
```  
virtual void OnTheaterMode(BOOL bTheaterMode);
```  
  
### <a name="parameters"></a>Parameter  
 *bTheaterMode*  
 Wert ungleich NULL, wenn Internet Explorer im Theater-Modus ist; andernfalls NULL.  
  
##  <a name="a-nameontitlechangea--chtmlviewontitlechange"></a><a name="ontitlechange"></a>CHtmlView::OnTitleChange  
 Diese Member-Funktion wird vom Framework, um eine Anwendung zu benachrichtigen, wenn der Titel eines Dokuments in das WebBrowser-Steuerelement verfügbar wird oder der Änderungen aufgerufen.  
  
```  
virtual void OnTitleChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Titel.  
  
### <a name="remarks"></a>Hinweise  
 HTML-Code kann der Titel ändern; Während HTML weiterhin heruntergeladen wird, wird die URL des Dokuments als Titel festgelegt. Nach der tatsächliche Titel (sofern vorhanden) von der HTML-Code analysiert wird, wird der Titel entsprechend den Titel geändert.  
  
##  <a name="a-nameontoolbara--chtmlviewontoolbar"></a><a name="ontoolbar"></a>CHtmlView::OnToolBar  
 Diese Member-Funktion wird vom Framework aufgerufen wenn der [Symbolleiste](https://msdn.microsoft.com/library/aa768274.aspx) -Eigenschaft geändert hat.  
  
```  
virtual void OnToolBar(BOOL bToolBar);
```  
  
### <a name="parameters"></a>Parameter  
 *bToolBar*  
 Ungleich NULL, wenn Internet Explorer Symbolleiste sichtbar ist, oder andernfalls NULL.  
  
##  <a name="a-nameontranslateacceleratora--chtmlviewontranslateaccelerator"></a><a name="ontranslateaccelerator"></a>CHtmlView::OnTranslateAccelerator  
 Von Internet Explorer oder MSHTML aufgerufen, wenn [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) oder [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) wird aufgerufen, um die Verarbeitung der Nachrichten im Menü Zugriffstaste Nachrichtenwarteschlange des Containers.  
  
```  
virtual HRESULT OnTranslateAccelerator(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Verweist auf die Nachricht, die übersetzt werden müssen.  
  
 `pguidCmdGroup`  
 Gruppen-ID-Befehl.  
  
 `nCmdID`  
 Befehls-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Im Erfolgsfall oder **S_FALSE** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnTranslateAccelerator` an die `TranslateAccelerator` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameontranslateurla--chtmlviewontranslateurl"></a><a name="ontranslateurl"></a>CHtmlView::OnTranslateUrl  
 Wird von Internet Explorer oder MSHTML aufgerufen, um dem Host die Möglichkeit zu geben, die zu ladende URL zu ändern.  
  
```  
virtual HRESULT OnTranslateUrl(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTranslate`  
 Für zukünftige Verwendung reserviert.  
  
 `pchURLIn`  
 Die Adresse einer Zeichenfolge, die vom Internet Explorer oder MSHTML an, die die URL zu übersetzende darstellt.  
  
 `ppchURLOut`  
 Adresse eines Zeichenfolgenzeigers, die die Adresse der übersetzten URL empfängt. Der Host weist den Puffer mit der Speicherbelegungsfunktion Aufgaben. Der Inhalt dieses Parameters sollte immer auf initialisiert werden **NULL**, auch wenn die URL nicht übersetzt wird oder die Methode fehlschlägt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die URL übersetzt wurde, **S_FALSE** , wenn die URL nicht übersetzt wurde, oder ein OLE definierter Fehlercode, wenn ein Fehler aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben `OnTranslateUrl` an die `TranslateUrl` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement. Finden Sie unter [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameonupdateuia--chtmlviewonupdateui"></a><a name="onupdateui"></a>CHtmlView::OnUpdateUI  
 Benachrichtigt den Host, dass sich der Befehlsstatus geändert hat.  
  
```  
virtual HRESULT OnUpdateUI();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein OLE definierter Fehlercode andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Der Host sollte den Status von Symbolleisten-Schaltflächen aktualisieren. Diese Methode wird aufgerufen, unabhängig von der Rückgabewert von `ShowUI`. Überschreiben `OnUpdateUI` an die `UpdateUI` -Benachrichtigung vom Microsoft Webbrowser-Steuerelement.  
  
##  <a name="a-nameonvisiblea--chtmlviewonvisible"></a><a name="onvisible"></a>CHtmlView::OnVisible  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn das Fenster für den WebBrowser angezeigt oder ausgeblendet werden soll.  
  
```  
virtual void OnVisible(BOOL bVisible);
```  
  
### <a name="parameters"></a>Parameter  
 `bVisible`  
 Ungleich NULL, wenn das Objekt sichtbar ist, oder andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird das Objekt Steuerelement Hostfenster an dasselbe Verhalten würde das Verhalten von Internet Explorer-Fenster.  
  
##  <a name="a-nameputpropertya--chtmlviewputproperty"></a><a name="putproperty"></a>CHtmlView::PutProperty  
 Rufen Sie diese Memberfunktion zum Festlegen der Eigenschaft mit einem angegebenen Objekt verknüpft ist.  
  
```  
void PutProperty(
    LPCTSTR lpszProperty,  
    const VARIANT& vtValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    double dValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    long lValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    LPCTSTR lpszValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    short nValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProperty`  
 Eine Zeichenfolge, die die Eigenschaft festgelegt.  
  
 *vtValue*  
 Der neue Wert der Eigenschaft, die durch angegebene `lpszProperty`.  
  
 *lpszPropertyName*  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der festzulegenden Eigenschaft.  
  
 *dValue*  
 Der neue Wert der Eigenschaft.  
  
 `lValue`  
 Der neue Wert der Eigenschaft.  
  
 `lpszValue`  
 Ein Zeiger auf eine Zeichenfolge, die den neuen Wert der Eigenschaft enthält.  
  
 `nValue`  
 Der neue Wert der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namequeryformscommanda--chtmlviewqueryformscommand"></a><a name="queryformscommand"></a>CHtmlView::QueryFormsCommand  
 Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.  
  
```  
HRESULT QueryFormsCommand(
    DWORD dwCommandID,  
    BOOL* pbSupported,  
    BOOL* pbEnabled,  
    BOOL* pbChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCommandID`  
 Der Bezeichner des Befehls abgefragt wird.  
  
 *pbSupported*  
 Ein Zeiger auf eine **BOOL** Angabe If Befehls (identifizierten `dwCommandID`) wird unterstützt. Wenn TRUE, wird der Befehl unterstützt. andernfalls FALSE.  
  
 `pbEnabled`  
 Ein Zeiger auf eine **BOOL** Angabe If Befehls (identifizierten `dwCommandID`) aktiviert ist. Wenn TRUE, wird der Befehl unterstützt. andernfalls FALSE.  
  
 *pbChecked*  
 Ein Zeiger auf eine **BOOL** Angabe If Befehls (identifizierten `dwCommandID`) aktiviert ist. Wenn TRUE, wird der Befehl unterstützt. andernfalls FALSE.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Eine vollständige Liste der möglichen Werte finden Sie unter [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 `QueryFormsCommand`implementiert das Verhalten der [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Methode.  
  
##  <a name="a-namequerystatuswba--chtmlviewquerystatuswb"></a><a name="querystatuswb"></a>CHtmlView::QueryStatusWB  
 Rufen Sie diese Memberfunktion zum Befehlsstatus abzufragen.  
  
```  
OLECMDF QueryStatusWB(OLECMDID cmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die [OLECMDID](http://msdn.microsoft.com/library/windows/desktop/ms691264) Wert des Befehls, für die der Aufrufer Statusinformationen benötigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse der [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) -Wert, der den Status des Befehls empfängt.  
  
### <a name="remarks"></a>Hinweise  
 `QueryStatusWB`implementiert das Verhalten der [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Methode.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namerefresha--chtmlviewrefresh"></a><a name="refresh"></a>CHtmlView::Refresh  
 Lädt die URL oder die Datei, die der Webbrowser gerade angezeigt wird.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Hinweise  
 **Aktualisieren Sie** enthält keine Parameter zum Festlegen der Ebene aktualisieren.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namerefresh2a--chtmlviewrefresh2"></a><a name="refresh2"></a>CHtmlView::Refresh2  
 Lädt die Datei, die Internet Explorer derzeit angezeigt wird.  
  
```  
void Refresh2(int nLevel);
```  
  
### <a name="parameters"></a>Parameter  
 `nLevel`  
 Die Adresse der Variablen dabei die Aktualisierung. Die möglichen Variablen werden in definiert [RefreshConstants](https://msdn.microsoft.com/library/aa768363.aspx)in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [aktualisieren](#refresh), `Refresh2` enthält einen Parameter, der die Aktualisierung angibt.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetaddressbara--chtmlviewsetaddressbar"></a><a name="setaddressbar"></a>CHtmlView::SetAddressBar  
 Rufen Sie diese Memberfunktion zum ein- oder Ausblenden des Objekts der Internet Explorer-Adressleiste ein.  
  
```  
void SetAddressBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Ungleich-Adressleiste angezeigt; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namesetfullscreena--chtmlviewsetfullscreen"></a><a name="setfullscreen"></a>CHtmlView::SetFullScreen  
 Rufen Sie diese Memberfunktion zum Internet Explorer entweder Vollbildmodus oder das normale Modus festgelegt.  
  
```  
void SetFullScreen(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Ungleich NULL für den Vollbildmodus; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 In den Vollbildmodus main Internet Explorer-Fenster wird maximiert und die Statusleiste, die Symbolleiste, die Menüleiste und die Titelleiste werden ausgeblendet.  
  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namesetheighta--chtmlviewsetheight"></a><a name="setheight"></a>CHtmlView::SetHeight  
 Rufen Sie diese Memberfunktion, um die Höhe des Hauptfensters von Internet Explorer festgelegt.  
  
```  
void SetHeight(long nNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewValue`  
 Die Höhe in Pixel des Hauptfensters.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetlefta--chtmlviewsetleft"></a><a name="setleft"></a>CHtmlView::SetLeft  
 Legt die horizontale Position des Internet Explorer-Hauptfensters fest.  
  
```  
void SetLeft(long nNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewValue`  
 Die Bildschirmkoordinate des linken Rands des Hauptfensters.  
  
##  <a name="a-namesetmenubara--chtmlviewsetmenubar"></a><a name="setmenubar"></a>CHtmlView::SetMenuBar  
 Rufen Sie diese Memberfunktion zum ein- oder Ausblenden der Menüleiste von Internet Explorer.  
  
```  
void SetMenuBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Ungleich NULL Menüleiste anzeigen; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namesetofflinea--chtmlviewsetoffline"></a><a name="setoffline"></a>CHtmlView::SetOffline  
 Rufen Sie diese Memberfunktion zum legen Sie einen Wert, der angibt, ob das WebBrowser-Steuerelement im Offlinemodus ausgeführt wird.  
  
```  
void SetOffline(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wert ungleich NULL aus dem lokalen Cache gelesen werden; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Im Offlinemodus befindet liest der Browser HTML-Seiten, aus dem lokalen Cache anstatt aus dem Quelldokument.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetregisterasbrowsera--chtmlviewsetregisterasbrowser"></a><a name="setregisterasbrowser"></a>CHtmlView::SetRegisterAsBrowser  
 Rufen Sie diese Memberfunktion zum legen Sie einen Wert, der angibt, ob das WebBrowser-Steuerelement der obersten Ebene Browser für die Auflösung des Ziel-Namen registriert ist.  
  
```  
void SetRegisterAsBrowser(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bestimmt, ob Internet Explorer als der obersten Ebene Browser registriert ist. Ein Wert ungleich NULL Webbrowser auf oberster Ebene Browser registriert ist; Wenn&0; (null), ist es nicht über einen Browser auf der obersten Ebene. Der Standardwert ist&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Ein der obersten Ebene Browser ist der Browser in der Registrierung als Standardbrowser festlegen.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetregisterasdroptargeta--chtmlviewsetregisterasdroptarget"></a><a name="setregisterasdroptarget"></a>CHtmlView::SetRegisterAsDropTarget  
 Rufen Sie diese Memberfunktion zum legen Sie einen Wert an, ob das WebBrowser-Steuerelement als Ablageziel für die Navigation registriert ist.  
  
```  
void SetRegisterAsDropTarget(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Bestimmt, ob das WebBrowser-Steuerelement als Ablageziel für die Navigation registriert ist. Wenn ungleich NULL ist, wird das Objekt als Dropziel registriert; Wenn der Wert&0; ist, ist es kein Ablageziel.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetsilenta--chtmlviewsetsilent"></a><a name="setsilent"></a>CHtmlView::SetSilent  
 Rufen Sie diese Memberfunktion zum legen Sie einen Wert an, ob alle Dialogfelder angezeigt werden können.  
  
```  
void SetSilent(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Ein Wert ungleich Null werden Dialogfelder nicht angezeigt werden. Wenn der Wert&0; ist, werden Dialogfelder angezeigt werden. Der Standardwert ist&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetstatusbara--chtmlviewsetstatusbar"></a><a name="setstatusbar"></a>CHtmlView::SetStatusBar  
 Rufen Sie diese Memberfunktion zum Anzeigen der Statusleiste.  
  
```  
void SetStatusBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wert ungleich NULL, wenn die Statusleiste sichtbar ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namesettheatermodea--chtmlviewsettheatermode"></a><a name="settheatermode"></a>CHtmlView::SetTheaterMode  
 Rufen Sie diese Memberfunktion zum legen Sie einen Wert, der angibt, ob das WebBrowser-Steuerelement im Theater-Modus befindet.  
  
```  
void SetTheaterMode(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Ungleich NULL für das WebBrowser-Steuerelement festzulegen, Theater Modus; andernfalls&0; (null). Der Standardwert ist&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Webbrowser im Theater-Modus befindet, im Browser Hauptfenster den gesamten Bildschirm einnimmt, wird eine Symbolleiste mit einem minimalen Satz von Navigationstools angezeigt und die Statusleiste wird angezeigt, in der oberen rechten Ecke des Bildschirms.  
  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesettoolbara--chtmlviewsettoolbar"></a><a name="settoolbar"></a>CHtmlView::SetToolBar  
 Rufen Sie diese Memberfunktion zum ein- oder Ausblenden der Symbolleiste von Internet Explorer.  
  
```  
void SetToolBar(int nNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewValue`  
 Gibt an, ob die Symbolleiste angezeigt werden soll. Wert ungleich NULL, wenn die Symbolleiste angezeigt werden; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Gilt für InternetExplorer. Wenn Sie diesen Aufruf mit einem WebBrowser-Steuerelement verwenden, wird kein Fehler zurückgegeben, aber es wird dieser Aufruf ignorieren.  
  
##  <a name="a-namesettopa--chtmlviewsettop"></a><a name="settop"></a>CHtmlView::SetTop  
 Rufen Sie diese Memberfunktion, um den Abstand zwischen dem inneren oberen Rand des WebBrowser-Steuerelements und dem oberen Rand des Containers festzulegen  
  
```  
void SetTop(long nNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewValue`  
 Die Bildschirmkoordinate des oberen Rands des Hauptfensters.  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetvisiblea--chtmlviewsetvisible"></a><a name="setvisible"></a>CHtmlView::SetVisible  
 Rufen Sie diese Memberfunktion um den Sichtbarkeitsstatus des WebBrowser-Steuerelements festlegen.  
  
```  
void SetVisible(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bNewValue`  
 Wert ungleich NULL, wenn das Steuerelement sichtbar ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
##  <a name="a-namesetwidtha--chtmlviewsetwidth"></a><a name="setwidth"></a>CHtmlView::SetWidth  
 Legt die Breite des Internet Explorer-Hauptfensters fest.  
  
```  
void SetWidth(long nNewValue);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewValue`  
 Die Breite in Pixel der Internet Explorer-Hauptfenster.  
  
##  <a name="a-namestopa--chtmlviewstop"></a><a name="stop"></a>CHtmlView::Stop  
 Rufen Sie diese Memberfunktion, um eine unvollständige Navigation abbrechen oder Downloadvorgang und beendet dynamische Seitenelemente wie Hintergrundsound und Animationen.  
  
```  
void Stop();
```  
  
### <a name="remarks"></a>Hinweise  
 Betrifft Internet Explorer und WebBrowser.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCIE](../../visual-cpp-samples.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)


