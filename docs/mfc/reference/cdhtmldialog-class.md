---
title: CDHtmlDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
dev_langs: C++
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a82079e43a5c4e1bfbcb9bb339663314d4ab2a49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog-Klasse
Wird verwendet, um Dialogfelder zu erstellen, verwenden HTML, statt der Dialogfeldressourcen ihre Benutzeroberfläche implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|Erstellt ein CDHtmlDialog-Objekt.|  
|[CDHtmlDialog:: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|Zerstört ein CDHtmlDialog-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Überschreibbare heißt, als einer zugriffsüberprüfung, um festzustellen, ob Skriptobjekte auf der Seite "geladen" die externen Versendung von der Website des Steuerelements zugreifen können. Überprüft, um sicherzustellen, dass die Verteilung ist, dass die für Objekte, die nicht sicher für Skripting sicher für Skripting oder der aktuellen Zone zulässt.|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable verwendet, um eine Steuerelement-Websiteinstanz zum Hosten der WebBrowser-Steuerelement auf das Dialogfeld "erstellen.|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Austausch von Daten zwischen einer Membervariablen gespeichert und der Wert der Eigenschaft für ein ActiveX-Steuerelement auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Austausch von Daten zwischen einer Membervariablen gespeichert und ein Kontrollkästchen auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Austausch von Daten zwischen einer Membervariablen gespeichert und eine HTML-Element-Eigenschaft auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Austausch von Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld.|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Ruft ab oder legt den Index eines Listenfelds auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Ruft ab oder legt den Anzeigetext für ein Feld (basierend auf den aktuellen Index) Eintrag auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Ruft ab oder legt den Wert einer im Listenfeld (basierend auf den aktuellen Index) auf einer HTML-Seite fest.|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Zerstört ein nicht modales Dialogfeld an.|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Ermöglicht nicht modale Dialogfelder.|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Können im Dialogfeld zum Filtern der Zwischenablage Datenobjekte, die vom gehosteten Browser erstellt.|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Ruft die `IDispatch` -Schnittstelle für ein ActiveX-Steuerelement im HTML-Dokument eingebettet.|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Ruft die angeforderte Eigenschaft des angegebenen ActiveX-Steuerelements ab.|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Ruft die IHTMLDocument2-Schnittstelle für die derzeit geladene HTML-Dokument ab.|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Von den enthaltenen WebBrowser-Steuerelement aufgerufen, wenn sie als Drop-Ziel verwendet wird, wird um das Dialogfeld eines alternativen zu ermöglichen [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](#getelement)|Ruft eine Schnittstelle für ein HTML-Element ab.|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Ruft die **InnerHTML** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Ruft den angeforderten Schnittstellenzeiger aus einem HTML-Element ab.|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Ruft den Wert der Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::GetElementText](#getelementtext)|Ruft die **InnerText** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::GetEvent](#getevent)|Ruft die **IHTMLEventObj** Zeiger auf das aktuelle Ereignisobjekt.|  
|[CDHtmlDialog::GetExternal](#getexternal)|Ruft den Host ab `IDispatch` Schnittstelle.|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Ruft den Host Benutzeroberflächenfunktionen ab.|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Ruft den Registrierungsschlüssel unter dem benutzereinstellungen gespeichert werden.|  
|[CDHtmlDialog::HideUI](#hideui)|Blendet die Host-Benutzeroberfläche.|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Gibt an, ob der Hosts `IDispatch` Schnittstelle für die Skripterstellung sicher ist.|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Lädt die angegebene Ressource in das WebBrowser-Steuerelement.|  
|[CDHtmlDialog::Navigate](#navigate)|Navigiert zur angegebenen URL.|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Wird vom Framework aufgerufen, bevor ein Navigationsereignis ausgelöst wird.|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Wird aufgerufen, durch das Framework um eine Anwendung zu benachrichtigen, wenn ein Dokument erreicht hat die `READYSTATE_COMPLETE` Zustand.|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert ist.|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert ist.|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Wird aufgerufen, als Antwort auf die **WM_INITDIALOG** Nachricht.|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Vom Framework aufgerufen, nachdem ein Navigationsereignis abgeschlossen ist.|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Das Objekt, das es muss sich um die Größe des Speicherplatzes Rahmen eine Warnung.|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Legt die Eigenschaft eines ActiveX-Steuerelements auf einen neuen Wert fest.|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Legt die **InnerHTML** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Legt eine Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetElementText](#setelementtext)|Legt die **InnerText** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Legt des Hosts `IDispatch` Schnittstelle.|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Der Host-UI-Flags festgelegt.|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Wird aufgerufen, wenn ein Kontextmenü angezeigt wird.|  
|[CDHtmlDialog::ShowUI](#showui)|Basiert auf der Benutzeroberfläche des Hosts.|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Wird aufgerufen, um den Prozess im Menü Tastenkombinations-menünachrichten.|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|Wird aufgerufen, um die URL zu ladenden ändern.|  
|[CDHtmlDialog::UpdateUI](#updateui)|Wird aufgerufen, um den Host zu benachrichtigen, den der Befehlsstatus geändert hat.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Gibt an, ob die Beschriftung Dialogfeld Titel der HTML-Dokuments verwendet.|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ressourcen-ID der HTML-Ressource angezeigt werden.|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Ein Zeiger auf einen Webbrowser.|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Ein Zeiger auf ein HTML-Dokument.|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Die aktuelle URL.|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Zeichenfolgenversion der HTML-Ressource-ID.|  
  
## <a name="remarks"></a>Hinweise  
 **CDHtmlDialog** den HTML-Code aus einer HTML-Ressource angezeigt werden oder eine URL laden können.  
  
 `CDHtmlDialog`auch können Daten austauschen mit HTML-Steuerelementen und Behandeln von Ereignissen aus HTML-Steuerelemente, z. B. Schaltfläche klickt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  
  
##  <a name="ddx_dhtml_helper_macros"></a>Hilfsmakros DDX_DHtml  
 Die DDX_DHtml Hilfsmakros ermöglichen einen einfachen Zugriff auf die häufig verwendeten Eigenschaften der Steuerelemente auf einer HTML-Seite.  
  
### <a name="data-exchange-macros"></a>Daten, Exchange-Makros  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft des markierten Steuerelements.|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Legt fest oder ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft den HTML-Code zwischen die Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Ruft die Ziel-URL oder den Ankerpunkt Punkt ab oder legt sie fest.|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Ruft das Zielfenster oder der Zielframe ab oder legt ihn fest.|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Legt fest oder ruft den Namen ein Bild oder eine Videoclips an, in das Dokument ab.|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Legt fest oder ruft die URL der zugeordneten Rahmen.|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL der zugeordneten Rahmen.|  
  
##  <a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal  
 Überschreibbare heißt, als einer zugriffsüberprüfung, um festzustellen, ob Skriptobjekte auf der Seite "geladen" die externen Versendung von der Website des Steuerelements zugreifen können. Überprüft, um sicherzustellen, dass die Verteilung ist, dass die für Objekte, die nicht sicher für Skripting sicher für Skripting oder der aktuellen Zone zulässt.  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog  
 Erstellt einen ressourcenbasierte dynamic HTML (Dialogfeld).  
  
```  
CDHtmlDialog();

 
CDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID,  
    CWnd *pParentWnd = NULL);

 
CDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd *pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Die Null-terminierte Zeichenfolge, die eine Dialogfeldvorlagen-Ressource im Dialogfeld heißt.  
  
 `szHtmlResID`  
 Die Null-terminierte Zeichenfolge, die den Namen des HTML-Ressource ist.  
  
 `pParentWnd`  
 Ein Zeiger auf den übergeordneten oder Besitzer-Fensterobjekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
 `nIDTemplate`  
 Enthält die ID einer Dialogfeldvorlagen-Ressource im Dialogfeld an.  
  
 `nHtmlResID`  
 Enthält die ID-Nummer, der eine HTML-Ressource an.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form des Konstruktors ermöglicht den Zugriff auf die Ressource über den Vorlagennamen. Die dritte Form des Konstruktors ermöglicht den Zugriff auf die Dialogressource über die ID der Ressourcenvorlage. In der Regel die ID beginnt mit der **IDD_** Präfix.  
  
##  <a name="_dtorcdhtmldialog"></a>CDHtmlDialog:: ~ CDHtmlDialog  
 Zerstört ein CDHtmlDialog-Objekt.  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 Die [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) Memberfunktion muss verwendet werden, um Dialogfelder ohne Modus zu zerstören, durch die erstellte [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
##  <a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite  
 Overridable verwendet, um eine Steuerelement-Websiteinstanz zum Hosten der WebBrowser-Steuerelement auf das Dialogfeld "erstellen.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT /* nID */,  
    REFCLSID /* clsid */);
```  
  
### <a name="parameters"></a>Parameter  
 `pContainer`  
 Ein Zeiger auf die [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) Objekt  
  
 `ppSite`  
 Ein Zeiger auf einen Zeiger auf eine [COleControlSite](../../mfc/reference/colecontrolsite-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion zum Zurückgeben einer Instanz eigenen Standort Steuerelementklasse überschreiben.  
  
##  <a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl  
 Austausch von Daten zwischen einer Membervariablen gespeichert und der Wert der Eigenschaft für ein ActiveX-Steuerelement auf einer HTML-Seite.  
  
```  
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    VARIANT& var);

 
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    LPCTSTR szPropName,  
    VARIANT& var);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert des ID-Parameter für das Objekttag in die HTML-Quelle für das ActiveX-Steuerelement.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft mit der exchange-Daten werden soll.  
  
 `szPropName`  
 Den Namen der Eigenschaft.  
  
 `var`  
 Die Datenmember des Typs `VARIANT`, [COleVariant](../../mfc/reference/colevariant-class.md), oder [CComVariant](../../atl/reference/ccomvariant-class.md), enthält den Wert mit dem ActiveX-Steuerelementeigenschaft ausgetauscht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox  
 Austausch von Daten zwischen einer Membervariablen gespeichert und ein Kontrollkästchen auf einer HTML-Seite.  
  
```  
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    int& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText  
 Austausch von Daten zwischen einer Membervariablen gespeichert und eine HTML-Element-Eigenschaft auf einer HTML-Seite.  
  
```  
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    CString& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    short& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    int& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    long& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    DWORD& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    float& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 *DISPID*  
 Die Dispatch-ID des HTML-Elements mit dem exchange-Daten werden soll.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
##  <a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio  
 Austausch von Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld.  
  
```  
void DDX_DHtml_Radio(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
##  <a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_SelectIndex  
 Ruft ab oder legt den Index eines Listenfelds auf einer HTML-Seite.  
  
```  
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-Id-Parameter angegeben.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
##  <a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString  
 Ruft ab oder legt den Anzeigetext für ein Feld (basierend auf den aktuellen Index) Eintrag auf einer HTML-Seite.  
  
```  
void DDX_DHtml_SelectString(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
##  <a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue  
 Ruft ab oder legt den Wert einer im Listenfeld (basierend auf den aktuellen Index) auf einer HTML-Seite fest.  
  
```  
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `szId`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert, der ausgetauscht wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless  
 Trennt ein nicht modales Dialogfeld aus der `CDHtmlDialog` Objekt und das Objekt zerstört.  
  
```  
void DestroyModeless();
```  
  
##  <a name="enablemodeless"></a>CDHtmlDialog::EnableModeless  
 Ermöglicht nicht modale Dialogfelder.  
  
```  
STDMETHOD(EnableModeless)(BOOL fEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `fEnable`  
 Finden Sie unter `fEnable` in [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject  
 Können im Dialogfeld zum Filtern der Zwischenablage Datenobjekte, die vom gehosteten Browser erstellt.  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>Parameter  
 `pDO`  
 Finden Sie unter `pDO` in [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) im Windows SDK.  
  
 `ppDORet`  
 Finden Sie unter `ppDORet` in **IDocHostUIHandler::FilterDataObject** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"S_FALSE"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch  
 Ruft die `IDispatch` -Schnittstelle für ein ActiveX-Steuerelement eingebettet wird, im HTML-Dokument zurückgegebenes [GetDHtmlDocument](#getdhtmldocument).  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die HTML-ID eines ActiveX-Steuerelements.  
  
 *ppdisp*  
 Die `IDispatch` Schnittstelle des Steuerelements Wenn auf der Webseite gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty  
 Ruft die angeforderte Eigenschaft des angegebenen ActiveX-Steuerelements ab.  
  
```  
VARIANT GetControlProperty(
    LPCTSTR szId,  
    LPCTSTR szPropName);

 
VARIANT GetControlProperty(
    LPCTSTR szId,  
    DISPID dispid);

 
VARIANT GetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die HTML-ID eines ActiveX-Steuerelements.  
  
 `szPropName`  
 Der Name einer Eigenschaft in das Standard-Gebietsschema des aktuellen Benutzers.  
  
 `pdispControl`  
 Die `IDispatch` Zeiger eines ActiveX-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID einer Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Variante, die angeforderte Eigenschaft oder eine leere Variante enthält, wenn das Steuerelement oder die Eigenschaft nicht gefunden werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Überladungen sind vom am wenigsten effiziente am oberen auf effizienteste unten aufgeführt.  
  
##  <a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl  
 Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `szUrl`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die URL zum Abrufen enthält.  
  
##  <a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument  
 Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle im derzeit geladenen HTML-Dokument.  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *\*\*pphtmlDoc*  
 Ein Zeiger auf einen Zeiger auf ein HTML-Dokument.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Gibt bei Erfolg `S_OK` zurück.  
  
##  <a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget  
 Von den enthaltenen WebBrowser-Steuerelement aufgerufen, wenn sie als Drop-Ziel verwendet wird, wird um das Dialogfeld eines alternativen zu ermöglichen [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pDropTarget`  
 Finden Sie unter `pDropTarget` in [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) im Windows SDK.  
  
 `ppDropTarget`  
 Finden Sie unter `ppDropTarget` in **IDocHostUIHandler::GetDropTarget** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getelement"></a>CDHtmlDialog::GetElement  
 Gibt eine Schnittstelle zurück, auf das angegebene HTML-Element `szElementId`.  
  
```  
HRESULT GetElement(
    LPCTSTR szElementId,  
    IDispatch** ppdisp,  
    BOOL* pbCollection = NULL);

 
HRESULT GetElement(
    LPCTSTR szElementId,  
    IHTMLElement** pphtmlElement);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 *ppdisp*  
 Ein `IDispatch` Zeiger auf das angeforderte Element oder eine Auflistung von Elementen.  
  
 *pbCollection*  
 Ein **BOOL** , der angibt, ob das Objekt szenariobeschreibungen *Ppdisp* ist ein einzelnes Element oder eine Auflistung von Elementen.  
  
 *pphtmlElement*  
 Ein **IHTMLElement** Zeiger auf das angeforderte Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Überladung, wenn Sie benötigen, um Bedingungen zu behandeln, in denen möglicherweise mehr als ein Element mit der angegebenen ID. Sie können den letzten Parameter verwenden, um herauszufinden, ob der zurückgegebene Schnittstellenzeiger auf eine Auflistung oder ein einzelnes Element ist. Wenn der Schnittstellenzeiger auf eine Auflistung befindet, können Sie Abfragen für die **IHTMLElementCollection** und seine **Element** Eigenschaft zum Verweisen auf die Elemente nach der Ordnungsposition.  
  
 Die zweite Überladung schlägt fehl, wenn mehr als ein Element mit der gleichen ID auf der Seite vorhanden ist.  
  
##  <a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml  
 Ruft die **InnerHTML** Eigenschaft des HTML-Elements identifizierten `szElementId`.  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **InnerHTML** Eigenschaft des HTML-Elements identifizierten `szElementId` oder **NULL** , wenn das Element nicht gefunden werden konnte.  
  
##  <a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface  
 Ruft den angeforderten Schnittstellenzeiger aus dem HTML-Element identifizierte `szElementId`.  
  
```  
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    Q** ppvObj);

 
HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    REFIID riid,  
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 `ppvObj`  
 Die Adresse eines Zeigers, das mit den angeforderten Schnittstellenzeiger ausgefüllt werden wird, wenn das Element gefunden wird und die Abfrage erfolgreich ausgeführt wird.  
  
 `riid`  
 Die Schnittstelle-ID (IID) der angeforderten Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty  
 Ruft den Wert der Eigenschaft identifizierten `dispid` aus dem HTML-Element identifizierte `szElementId`.  
  
```  
VARIANT GetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 `dispid`  
 Die Dispatch-ID einer Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert der Eigenschaft oder ein leerer Variant-Wert, wenn die Eigenschaft oder das Element nicht gefunden werden konnte.  
  
##  <a name="getelementtext"></a>CDHtmlDialog::GetElementText  
 Ruft die **InnerText** Eigenschaft des HTML-Elements identifizierten `szElementId`.  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **InnerText** Eigenschaft des HTML-Elements identifizierten `szElementId` oder **NULL** , wenn die Eigenschaft oder das Element nicht gefunden werden konnte.  
  
##  <a name="getevent"></a>CDHtmlDialog::GetEvent  
 Gibt die **IHTMLEventObj** Zeiger auf das aktuelle Ereignisobjekt.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEventObj`  
 Die Adresse eines Zeigers, der mit ausgefüllt werden, wird die **IHTMLEventObj** Schnittstellenzeiger auf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von innerhalb einer DHTML-Ereignishandler aufgerufen werden.  
  
##  <a name="getexternal"></a>CDHtmlDialog::GetExternal  
 Ruft den Host ab `IDispatch` Schnittstelle.  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>Parameter  
 *ppDispatch*  
 Finden Sie unter *PpDispatch* in [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg oder **E_NOTIMPL** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo  
 Ruft den Host Benutzeroberflächenfunktionen ab.  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Finden Sie unter `pInfo` in [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath  
 Ruft den Registrierungsschlüssel unter dem benutzereinstellungen gespeichert werden.  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>Parameter  
 `pchKey`  
 Finden Sie unter `pchKey` in [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) im Windows SDK.  
  
 `dw`  
 Finden Sie unter `dw` in **IDocHostUIHandler::GetOptionKeyPath** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="hideui"></a>CDHtmlDialog::HideUI  
 Blendet die Host-Benutzeroberfläche.  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe  
 Gibt an, ob der Hosts `IDispatch` Schnittstelle für die Skripterstellung sicher ist.  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"false"**.  
  
##  <a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource  
 Lädt die angegebene Ressource in das WebBrowser-Steuerelement im Dialogfeld "DHTML" an.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResource`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Ressource geladen.  
  
 `nRes`  
 Die ID der Ressource geladen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn erfolgreich; andernfalls **"false"**.  
  
##  <a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle  
 Gibt an, ob die Beschriftung Dialogfeld Titel der HTML-Dokuments verwendet.  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn **m**_ **bUseHtmlTitle** ist **"true"**, die Beschriftung Dialogfeld festgelegt ist, andernfalls gleich den Titel der HTML-Dokument, die Beschriftung in die Dialogressource wird verwendet.  
  
##  <a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID  
 Ressourcen-ID der HTML-Ressource angezeigt werden.  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp  
 Ein Zeiger auf einen Webbrowser.  
  
```  
CComPtr <IWebBrowser2> m_pBrowserApp;  
```  
  
##  <a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc  
 Ein Zeiger auf ein HTML-Dokument.  
  
```  
CComPtr<IHTMLDocument2> m_spHtmlDoc;  
```  
  
##  <a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl  
 Die aktuelle URL.  
  
```  
CString m_strCurrentUrl;  
```  
  
##  <a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID  
 Zeichenfolgenversion der HTML-Ressource-ID.  
  
```  
LPTSTR m_szHtmlResID;  
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="navigate"></a>CDHtmlDialog::Navigate  
 Navigiert zu der durch die URL, die von angegeben wird bezeichnete Ressource `lpszURL`.  
  
```  
void Navigate(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszURL`  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL, die als Ziel verwendet werden.  
  
 `dwFlags`  
 Die Flags für eine Variable, die angibt, ob die Ressource die Verlaufsliste hinzugefügt, angibt, ob in den Cache lesen oder Schreiben von aus dem Cache und angibt, ob die Ressource in einem neuen Fenster anzuzeigen. Die Variable kann eine Kombination der Werte von definiert die [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) Enumeration.  
  
 `lpszTargetFrameName`  
 Ein Zeiger auf eine Zeichenfolge, die enthält der Name des Frames, in dem die Ressource angezeigt.  
  
 `lpszHeaders`  
 Ein Zeiger auf einen Wert, der angibt, die HTTP-Header an den Server gesendet. Diese Header werden die Standard-Internet Explorer-Header hinzugefügt. Die Header können diese Informationen als die des Servers, den Typ der Daten, die auf dem Server oder einen Statuscode übergebenen erforderliche Aktion angeben. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
 `lpvPostData`  
 Ein Zeiger auf die Daten, die mit der HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten von einem HTML-Formular erhobenen verwendet. Wenn dieser Parameter keine Post-Daten **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
 `dwPostDataLen`  
 Daten, die mit der HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten von einem HTML-Formular erhobenen verwendet. Wenn dieser Parameter keine Post-Daten **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
##  <a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate  
 Vom Framework aufgerufen, die dazu führen, dass ein Ereignis ausgelöst wird, bevor eine navigiert wird.  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL zu navigieren.  
  
##  <a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete  
 Wird aufgerufen, durch das Framework um eine Anwendung zu benachrichtigen, wenn ein Dokument erreicht hat die `READYSTATE_COMPLETE` Zustand.  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL, zu der navigiert wurde.  
  
##  <a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate  
 Vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert ist.  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Finden Sie unter `fActivate` in [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird CDHtmlDialogs Durchführung des [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate  
 Vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert ist.  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Finden Sie unter `fActivate` in [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog  
 Wird aufgerufen, als Antwort auf die **WM_INITDIALOG** Nachricht.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die standardmäßige Implementierung **"true"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Nachricht wird gesendet, um das Dialogfeld während der **erstellen**, `CreateIndirect`, oder `DoModal` Aufrufe, die auftreten, unmittelbar bevor das Dialogfeld angezeigt wird.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn besondere Verarbeitung bei der Initialisierung des Dialogfelds "" ausführen müssen. In der überschriebenen Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber dessen Rückgabewert ignorieren. Normalerweise wird nun wieder **"true"** von der überschriebenen Member-Funktion.  
  
 Windows-Aufrufe der `OnInitDialog` Funktion über die globale-Standarddialogfeld Prozedur allgemeiner Dialogfelder für alle Microsoft Foundation Class Library, statt über die meldungszuordnung, daher Sie keine Meldungszuordnungseintrags für diese Memberfunktion benötigen.  
  
##  <a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete  
 Vom Framework aufgerufen, nachdem die Navigation zur angegebenen URL abgeschlossen ist.  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL, zu der navigiert wurde.  
  
##  <a name="resizeborder"></a>CDHtmlDialog::ResizeBorder  
 Das Objekt, das es muss sich um die Größe des Speicherplatzes Rahmen eine Warnung.  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>Parameter  
 `prcBorder`  
 Finden Sie unter `prcBorder` in [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) im Windows SDK.  
  
 `pUIWindow`  
 Finden Sie unter `pUIWindow` in **IDocHostUIHandler::ResizeBorder** im Windows SDK.  
  
 `fFrameWindow`  
 Finden Sie unter *fFrameWindow* in **IDocHostUIHandler::ResizeBorder** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty  
 Legt die Eigenschaft eines ActiveX-Steuerelements auf einen neuen Wert fest.  
  
```  
void SetControlProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    LPCTSTR szElementId,  
    LPCTSTR szPropName,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die HTML-ID eines ActiveX-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID, der die festzulegende Eigenschaft.  
  
 *pVar*  
 Zeiger auf eine **VARIANT** , enthält den neue Eigenschaftswert.  
  
 `pdispControl`  
 Zeiger auf ein ActiveX-Steuerelement `IDispatch` Schnittstelle.  
  
 `szPropName`  
 Eine Zeichenfolge mit den Namen der festzulegenden Eigenschaft.  
  
##  <a name="setelementhtml"></a>CDHtmlDialog::SetElementHtml  
 Legt die **InnerHTML** Eigenschaft eines HTML-Elements.  
  
```  
void SetElementHtml(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementHtml(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 `bstrText`  
 Der neue Wert für die **InnerHTML** Eigenschaft.  
  
 `punkElem`  
 Die **IUnknown** Zeiger eines HTML-Elements.  
  
##  <a name="setelementproperty"></a>CDHtmlDialog::SetElementProperty  
 Legt eine Eigenschaft eines HTML-Elements.  
  
```  
void SetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 `dispid`  
 Die Dispatch-ID, der die festzulegende Eigenschaft.  
  
 *pVar*  
 Der neue Wert der Eigenschaft.  
  
##  <a name="setelementtext"></a>CDHtmlDialog::SetElementText  
 Legt die **InnerText** Eigenschaft eines HTML-Elements.  
  
```  
void SetElementText(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementText(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
 `bstrText`  
 Der neue Wert für die **InnerText** Eigenschaft.  
  
 `punkElem`  
 Die **IUnknown** Zeiger eines HTML-Elements.  
  
##  <a name="setexternaldispatch"></a>CDHtmlDialog::SetExternalDispatch  
 Legt des Hosts `IDispatch` Schnittstelle.  
  
```  
void SetExternalDispatch(IDispatch* pdispExternal);
```  
  
### <a name="parameters"></a>Parameter  
 *pdispExternal*  
 Die neue `IDispatch` Schnittstelle.  
  
##  <a name="sethostflags"></a>CDHtmlDialog::SetHostFlags  
 Legt die UI-Flags fest.  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Mögliche Werte finden Sie unter [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) im Windows SDK.  
  
##  <a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu  
 Wird aufgerufen, wenn ein Kontextmenü angezeigt wird.  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>Parameter  
 `dwID`  
 Finden Sie unter `dwID` in [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) im Windows SDK.  
  
 `ppt`  
 Finden Sie unter `ppt` in **IDocHostUIHandler::ShowContextMenu** im Windows SDK.  
  
 `pcmdtReserved`  
 Finden Sie unter `pcmdtReserved` in **IDocHostUIHandler::ShowContextMenu** im Windows SDK.  
  
 `pdispReserved`  
 Finden Sie unter `pdispReserved` in **IDocHostUIHandler::ShowContextMenu** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"S_FALSE"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="showui"></a>CDHtmlDialog::ShowUI  
 Basiert auf der Benutzeroberfläche des Hosts.  
  
```  
STDMETHOD(ShowUI)(
    DWORD dwID,  
    IOleInPlaceActiveObject* pActiveObject,  
    IOleCommandTarget* pCommandTarget,  
    IOleInPlaceFrame* pFrame,  
    IOleInPlaceUIWindow* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 `dwID`  
 Finden Sie unter `dwID` in [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) im Windows SDK.  
  
 `pActiveObject`  
 Finden Sie unter *d pActiveObject* in **IDocHostUIHandler::ShowUI** im Windows SDK.  
  
 `pCommandTarget`  
 Finden Sie unter `pCommandTarget` in **IDocHostUIHandler::ShowUI** im Windows SDK.  
  
 `pFrame`  
 Finden Sie unter `pFrame` in **IDocHostUIHandler::ShowUI** im Windows SDK.  
  
 `pDoc`  
 Finden Sie unter `pDoc` in **IDocHostUIHandler::ShowUI** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"S_FALSE"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator  
 Wird aufgerufen, um den Prozess im Menü Tastenkombinations-menünachrichten.  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Finden Sie unter `lpMsg` in [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) im Windows SDK.  
  
 `pguidCmdGroup`  
 Finden Sie unter `pguidCmdGroup` in **IDocHostUIHandler::TranslateAccelerator** im Windows SDK.  
  
 `nCmdID`  
 Finden Sie unter `nCmdID` in **IDocHostUIHandler::TranslateAccelerator** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"S_FALSE"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="translateurl"></a>CDHtmlDialog::TranslateUrl  
 Wird aufgerufen, um die URL zu ladenden ändern.  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTranslate`  
 Finden Sie unter `dwTranslate` in [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) im Windows SDK.  
  
 `pchURLIn`  
 Finden Sie unter `pchURLIn` in **IDocHostUIHandler::TranslateUrl** im Windows SDK.  
  
 `ppchURLOut`  
 Finden Sie unter `ppchURLOut` in **IDocHostUIHandler::TranslateUrl** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"S_FALSE"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="updateui"></a>CDHtmlDialog::UpdateUI  
 Wird aufgerufen, um den Host zu benachrichtigen, den der Befehlsstatus geändert hat.  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird die Implementierung des CDHtmlDialog [IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)gemäß der Beschreibung im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DHtmlExplore](../../visual-cpp-samples.md)   
 [Hilfsmakros DDX_DHtml](#ddx_dhtml_helper_macros)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


