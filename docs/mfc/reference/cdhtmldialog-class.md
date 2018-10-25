---
title: CDHtmlDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d42f0a62f552b09d06300c393efdb1cfbf2335e9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075618"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog-Klasse

Wird verwendet, um Dialogfelder zu erstellen, verwenden HTML, statt der Dialogfeldressourcen ihre Benutzeroberfläche zu implementieren.

## <a name="syntax"></a>Syntax

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|Erstellt ein CDHtmlDialog-Objekt.|
|[CDHtmlDialog:: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|Zerstört ein CDHtmlDialog-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Überschreibbare heißt, die als eine zugriffsprüfung, um festzustellen, ob Skriptobjekte auf der Seite geladen, die externe Verteilung der Site für das Steuerelement zugreifen können. Überprüft, stellen Sie sicher, dass die Verteilung ist, dass entweder der sicher für Skripting oder der aktuellen Zone ermöglicht, für Objekte, die nicht für die Skripterstellung sicher sind.|
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable, die zum Erstellen einer Steuerelement-Websiteinstanz zum Hosten des WebBrowser-Steuerelements im Dialogfeld verwendet werden.|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Datenaustausch zwischen einer Membervariablen gespeichert und der Wert der Eigenschaft für ein ActiveX-Steuerelement auf einer HTML-Seite.|
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Tauscht Daten zwischen einer Membervariablen gespeichert und ein Kontrollkästchen auf einer HTML-Seite.|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Datenaustausch zwischen einer Membervariablen gespeichert und eine HTML-Element-Eigenschaft auf eine HTML-Seite.|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Datenaustausch zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld.|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Übernimmt oder bestimmt den Index eines Listenfelds auf einer HTML-Seite.|
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Übernimmt oder bestimmt den Anzeigetext eines Listeneintrags-Feld (basierend auf den aktuellen Index) auf einer HTML-Seite.|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Ruft ab oder legt den Wert eines Listeneintrags-Feld (basierend auf den aktuellen Index) für eine HTML-Seite.|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Zerstört ein nicht modales Dialogfeld an.|
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Ermöglicht Dialogfelder ohne Modus.|
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Können das Dialogfeld zum Filtern des Zwischenablage-Datenobjekte, die vom Browser gehosteten erstellt.|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Ruft die `IDispatch` Schnittstelle für ein ActiveX-Steuerelement im HTML-Dokument eingebettet.|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Ruft die angeforderte Eigenschaft des angegebenen ActiveX-Steuerelements ab.|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Ruft die IHTMLDocument2-Schnittstelle für das derzeit geladene HTML-Dokument ab.|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Vom WebBrowser-Steuerelement enthaltene aufgerufen wird, wenn es um das Dialogfeld eines alternativen zu ermöglichen als Drop-Ziel verwendet wird [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[CDHtmlDialog::GetElement](#getelement)|Ruft eine Schnittstelle für ein HTML-Element ab.|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Ruft die `innerHTML` Eigenschaft eines HTML-Elements.|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Ruft den angeforderten Schnittstellenzeiger aus einem HTML-Element ab.|
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Ruft den Wert der Eigenschaft eines HTML-Elements ab.|
|[CDHtmlDialog::GetElementText](#getelementtext)|Ruft die `innerText` Eigenschaft eines HTML-Elements.|
|[CDHtmlDialog::GetEvent](#getevent)|Ruft die `IHTMLEventObj` Zeiger auf das aktuelle Ereignisobjekt.|
|[CDHtmlDialog::GetExternal](#getexternal)|Ruft des Hosts des `IDispatch` Schnittstelle.|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Ruft Funktionen des Hosts ab.|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Ruft den Registrierungsschlüssel, unter dem benutzereinstellungen gespeichert werden.|
|[CDHtmlDialog::HideUI](#hideui)|Blendet die Host Benutzeroberfläche.|
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Gibt an, ob der Hosts des `IDispatch` Schnittstelle für die Skripterstellung sicher ist.|
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Lädt die angegebene Ressource in das WebBrowser-Steuerelement.|
|[CDHtmlDialog::Navigate](#navigate)|Navigiert zur angegebenen URL.|
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Wird von Framework aufgerufen, bevor ein Navigationsereignis ausgelöst wird.|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, wenn ein Dokument mit den READYSTATE_COMPLETE-Zustand erreicht hat.|
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert ist.|
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Wird vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert ist.|
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Wird aufgerufen, als Reaktion auf die WM_INITDIALOG-Meldung.|
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Vom Framework aufgerufen, nachdem ein Navigationsereignis abgeschlossen ist.|
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Benachrichtigt das Objekt, das die Größe seines Rahmenbereichs ändern muss.|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Legt die Eigenschaft eines ActiveX-Steuerelements in einen neuen Wert fest.|
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Legt die `innerHTML` Eigenschaft eines HTML-Elements.|
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Legt eine Eigenschaft eines HTML-Elements.|
|[CDHtmlDialog::SetElementText](#setelementtext)|Legt die `innerText` Eigenschaft eines HTML-Elements.|
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Legt der Hosts `IDispatch` Schnittstelle.|
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Legt die Benutzeroberfläche Flags des Hosts fest.|
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Wird aufgerufen, wenn ein Kontextmenü angezeigt wird.|
|[CDHtmlDialog::ShowUI](#showui)|Zeigt die Host Benutzeroberfläche.|
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Wird aufgerufen, um den Prozess Tastenkombinations-menünachrichten.|
|[CDHtmlDialog::TranslateUrl](#translateurl)|Wird aufgerufen, um die URL zu ladenden ändern.|
|[CDHtmlDialog::UpdateUI](#updateui)|Wird aufgerufen, um den Host zu benachrichtigen, den der Befehlsstatus geändert hat.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Gibt an, ob die dialogfeldbeschriftung Titel des HTML-Dokuments verwendet werden soll.|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ressourcen-ID von HTML-Ressource, die angezeigt werden soll.|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Ein Zeiger auf eine Web-Browser-Anwendung.|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Ein Zeiger auf ein HTML-Dokument.|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Die aktuelle URL.|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Zeichenfolgenversion der HTML-Ressourcen-ID.|

## <a name="remarks"></a>Hinweise

`CDHtmlDialog` der HTML-Code, der aus einer HTML-Ressource angezeigt werden oder eine URL kann geladen werden.

`CDHtmlDialog` Außerdem Daten tauschen Sie mit HTML-Steuerelementen und Behandeln von Ereignissen aus HTML-Steuerelemente, z. B. die Schaltfläche klickt.

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

##  <a name="ddx_dhtml_helper_macros"></a>  DDX_DHtml-Hilfsmakros

DDX_DHtml-Hilfsmakros ermöglichen einen einfachen Zugriff auf die häufig verwendeten Eigenschaften von Steuerelementen auf einer HTML-Seite.

### <a name="data-exchange-macros"></a>Registrierungsdatenaustausch-Makros

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft aus dem ausgewählten Steuerelement.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab, oder legt diesen fest.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft Sie den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Legt fest oder ruft ab, der Ziel-URL oder den Ankerpunkt Punkt.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Ruft das Zielfenster oder den Zielframe ab, ab oder legt diesen fest.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Legt fest oder ruft den Namen ein Bild oder einen Videoclip in das Dokument ab.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Legt fest oder ruft die URL des zugeordneten Frames ab.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL des zugeordneten Frames ab.|

##  <a name="canaccessexternal"></a>  CDHtmlDialog::CanAccessExternal

Überschreibbare heißt, die als eine zugriffsprüfung, um festzustellen, ob Skriptobjekte auf der Seite geladen, die externe Verteilung der Site für das Steuerelement zugreifen können. Überprüft, stellen Sie sicher, dass die Verteilung ist, dass entweder der sicher für Skripting oder der aktuellen Zone ermöglicht, für Objekte, die nicht für die Skripterstellung sicher sind.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="cdhtmldialog"></a>  CDHtmlDialog::CDHtmlDialog

Erstellt ein ressourcenbasierte dynamische HTML-Dialogfeld.

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

*lpszTemplateName*<br/>
Die Null-terminierte Zeichenfolge mit dem Namen von einer Ressource im Dialogfeld.

*szHtmlResID*<br/>
Die Null-terminierte Zeichenfolge, die den Namen der eine HTML-Ressource ist.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.

*nIDTemplate*<br/>
Enthält die ID einer Ressource im Dialogfeld an.

*nHtmlResID*<br/>
Enthält die ID-Nummer, der eine HTML-Ressource.

### <a name="remarks"></a>Hinweise

Die zweite Form des Konstruktors ermöglicht den Zugriff auf die Ressource anhand des Namens der Vorlage. Die dritte Form des Konstruktors ermöglicht den Zugriff auf die Ressource durch die ID der Ressourcenvorlage. Die ID beginnt gewöhnlich mit den **IDD_** Präfix.

##  <a name="_dtorcdhtmldialog"></a>  CDHtmlDialog:: ~ CDHtmlDialog

Zerstört ein CDHtmlDialog-Objekt.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Hinweise

Die [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) Memberfunktion muss verwendet werden, um nicht modale Dialogfelder zu zerstören, die vom erstellten [CDialog::Create](../../mfc/reference/cdialog-class.md#create).

##  <a name="createcontrolsite"></a>  CDHtmlDialog::CreateControlSite

Overridable, die zum Erstellen einer Steuerelement-Websiteinstanz zum Hosten des WebBrowser-Steuerelements im Dialogfeld verwendet werden.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Parameter

*pContainer*<br/>
Ein Zeiger auf die [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) Objekt

*ppSite*<br/>
Ein Zeiger auf einen Zeiger auf eine [COleControlSite](../../mfc/reference/colecontrolsite-class.md).

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie können diese Memberfunktion zum Zurückgeben einer Instanz der Website eine eigene Klasse überschreiben.

##  <a name="ddx_dhtml_axcontrol"></a>  CDHtmlDialog::DDX_DHtml_AxControl

Datenaustausch zwischen einer Membervariablen gespeichert und der Wert der Eigenschaft für ein ActiveX-Steuerelement auf einer HTML-Seite.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert des Object-Tag-ID-Parameter in der HTML-Quelle für das ActiveX-Steuerelement.

*DISPID*<br/>
Die Dispatch-ID der Eigenschaft mit der Sie die Daten austauschen möchten.

*szPropName*<br/>
Den Namen der Eigenschaft.

*var*<br/>
Der Datenmember vom Typ VARIANT, [COleVariant](../../mfc/reference/colevariant-class.md), oder [CComVariant](../../atl/reference/ccomvariant-class.md), enthält den Wert, der mit der Eigenschaft des ActiveX-Steuerelements ausgetauscht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

##  <a name="ddx_dhtml_checkbox"></a>  CDHtmlDialog::DDX_DHtml_CheckBox

Tauscht Daten zwischen einer Membervariablen gespeichert und ein Kontrollkästchen auf einer HTML-Seite.

```
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

##  <a name="ddx_dhtml_elementtext"></a>  CDHtmlDialog::DDX_DHtml_ElementText

Datenaustausch zwischen einer Membervariablen gespeichert und eine HTML-Element-Eigenschaft auf eine HTML-Seite.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*DISPID*<br/>
Die Dispatch-ID des HTML-Elements mit dem Sie die Daten austauschen möchten.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

##  <a name="ddx_dhtml_radio"></a>  CDHtmlDialog::DDX_DHtml_Radio

Datenaustausch zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld.

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

##  <a name="ddx_dhtml_selectindex"></a>  CDHtmlDialog::DDX_DHtml_SelectIndex

Übernimmt oder bestimmt den Index eines Listenfelds auf einer HTML-Seite.

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-Id-Parameter angegeben.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

##  <a name="ddx_dhtml_selectstring"></a>  CDHtmlDialog::DDX_DHtml_SelectString

Übernimmt oder bestimmt den Anzeigetext eines Listeneintrags-Feld (basierend auf den aktuellen Index) auf einer HTML-Seite.

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

##  <a name="ddx_dhtml_selectvalue"></a>  CDHtmlDialog::DDX_DHtml_SelectValue

Ruft ab oder legt den Wert eines Listeneintrags-Feld (basierend auf den aktuellen Index) für eine HTML-Seite.

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*szId*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*Wert*<br/>
Der Wert, die ausgetauscht werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

##  <a name="destroymodeless"></a>  CDHtmlDialog::DestroyModeless

Trennt ein nicht modales Dialogfeld aus der `CDHtmlDialog` Objekt und das Objekt zerstört.

```
void DestroyModeless();
```

##  <a name="enablemodeless"></a>  CDHtmlDialog::EnableModeless

Ermöglicht Dialogfelder ohne Modus.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Parameter

*fEnable*<br/>
Finden Sie unter *fEnable* in [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx), wie im Windows SDK beschrieben.

##  <a name="filterdataobject"></a>  CDHtmlDialog::FilterDataObject

Können das Dialogfeld zum Filtern des Zwischenablage-Datenobjekte, die vom Browser gehosteten erstellt.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Parameter

*pDO*<br/>
Finden Sie unter *pDO* in [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) im Windows SDK.

*ppDORet*<br/>
Finden Sie unter *PpDORet* in `IDocHostUIHandler::FilterDataObject` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_FALSE zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx), wie im Windows SDK beschrieben.

##  <a name="getcontroldispatch"></a>  CDHtmlDialog::GetControlDispatch

Ruft die `IDispatch` Schnittstelle für ein ActiveX-Steuerelement eingebettet wird, in das HTML-Dokument, das von zurückgegebene [GetDHtmlDocument](#getdhtmldocument).

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Parameter

*szId*<br/>
Die HTML-ID eines ActiveX-Steuerelements.

*ppdisp*<br/>
Die `IDispatch` Schnittstelle des Steuerelements Wenn finden Sie auf der Webseite.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="getcontrolproperty"></a>  CDHtmlDialog::GetControlProperty

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

*szId*<br/>
Die HTML-ID eines ActiveX-Steuerelements.

*szPropName*<br/>
Der Name einer Eigenschaft in das Standardgebietsschema des aktuellen Benutzers.

*pdispControl*<br/>
Die `IDispatch` Zeiger eines ActiveX-Steuerelements.

*DISPID*<br/>
Die Dispatch-ID einer Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Eine Variante, die angeforderte Eigenschaft oder eine leere Variante enthält, wenn das Steuerelement oder die Eigenschaft nicht gefunden werden kann.

### <a name="remarks"></a>Hinweise

Überladungen sind von oben am wenigsten effiziente bis am unteren Rand am effizientesten aufgelistet.

##  <a name="getcurrenturl"></a>  CDHtmlDialog::GetCurrentUrl

Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Parameter

*szUrl*<br/>
Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, enthält die URL zum Abrufen.

##  <a name="getdhtmldocument"></a>  CDHtmlDialog::GetDHtmlDocument

Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das derzeit geladene HTML-Dokument.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Parameter

*\*\*PphtmlDoc* ein Zeiger auf einen Zeiger auf ein HTML-Dokument.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT. Gibt S_OK zurück, wenn erfolgreich.

##  <a name="getdroptarget"></a>  CDHtmlDialog::GetDropTarget

Vom WebBrowser-Steuerelement enthaltene aufgerufen wird, wenn es um das Dialogfeld eines alternativen zu ermöglichen als Drop-Ziel verwendet wird [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Parameter

*pDropTarget*<br/>
Finden Sie unter *pDropTarget* in [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) im Windows SDK.

*ppDropTarget*<br/>
Finden Sie unter *PpDropTarget* in `IDocHostUIHandler::GetDropTarget` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx), wie im Windows SDK beschrieben.

##  <a name="getelement"></a>  CDHtmlDialog::GetElement

Gibt eine Schnittstelle zurück, auf das HTML-Element, das vom angegebenen *SzElementId*.

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

*szElementId*<br/>
Die ID eines HTML-Elements.

*ppdisp*<br/>
Ein `IDispatch` Zeiger auf das angeforderte Element oder eine Auflistung von Elementen.

*pbCollection*<br/>
Ein boolescher Wert, der angibt, ob das Objekt durch dargestellt *Ppdisp* ist ein einzelnes Element oder eine Auflistung von Elementen.

*pphtmlElement*<br/>
Ein `IHTMLElement` Zeiger auf das angeforderte Element.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Verwenden Sie die erste Überladung, wenn Sie benötigen, um Bedingungen zu behandeln, in denen möglicherweise mehr als ein Element mit der angegebenen ID. Sie können den letzten Parameter verwenden, um herauszufinden, ob der zurückgegebene Schnittstellenzeiger auf eine Auflistung oder ein einzelnes Element ist. Wenn der Schnittstellenzeiger auf eine Auflistung ist, können Sie Abfragen für die `IHTMLElementCollection` und verwenden Sie die `item` Eigenschaft zum Verweisen auf die Elemente nach Ordnungsposition.

Die zweite Überladung schlägt fehl, wenn mehr als ein Element mit der gleichen ID auf der Seite vorhanden ist.

##  <a name="getelementhtml"></a>  CDHtmlDialog::GetElementHtml

Ruft die `innerHTML` -Eigenschaft des HTML-Elements identifizierte *SzElementId*.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

### <a name="return-value"></a>Rückgabewert

Die `innerHTML` -Eigenschaft des HTML-Elements identifizierte *SzElementId* oder NULL, wenn das Element nicht gefunden werden konnte.

##  <a name="getelementinterface"></a>  CDHtmlDialog::GetElementInterface

Ruft den angeforderten Schnittstellenzeiger aus dem HTML-Element identifizierte *SzElementId*.

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

*szElementId*<br/>
Die ID eines HTML-Elements.

*ppvObj*<br/>
Adresse von einem Zeiger, der mit den angeforderten Schnittstellenzeiger gefüllt wird, wenn das Element gefunden wird und die Abfrage erfolgreich ausgeführt wird.

*riid*<br/>
Die ID (IID) der angeforderten Schnittstelle-Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

##  <a name="getelementproperty"></a>  CDHtmlDialog::GetElementProperty

Ruft den Wert der Eigenschaft identifizierte *Dispid* aus dem HTML-Element identifizierte *SzElementId*.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispid);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

*DISPID*<br/>
Die Dispatch-ID einer Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Der Wert der Eigenschaft oder eine leere Variante, wenn die Eigenschaft oder das Element nicht gefunden werden kann.

##  <a name="getelementtext"></a>  CDHtmlDialog::GetElementText

Ruft die `innerText` -Eigenschaft des HTML-Elements identifizierte *SzElementId*.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

### <a name="return-value"></a>Rückgabewert

Die `innerText` -Eigenschaft des HTML-Elements identifizierte *SzElementId* oder NULL, wenn die Eigenschaft oder das Element nicht gefunden werden konnte.

##  <a name="getevent"></a>  CDHtmlDialog::GetEvent

Gibt die `IHTMLEventObj` Zeiger auf das aktuelle Ereignisobjekt.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Parameter

*ppEventObj*<br/>
Adresse eines Zeigers, der mit gefüllt werden soll, wird die `IHTMLEventObj` Schnittstellenzeiger auf.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur von innerhalb einer DHTML-Ereignishandler aufgerufen werden.

##  <a name="getexternal"></a>  CDHtmlDialog::GetExternal

Ruft des Hosts des `IDispatch` Schnittstelle.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Parameter

*ppDispatch*<br/>
Finden Sie unter *PpDispatch* in [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder E_NOTIMPL zurück, bei einem Fehler.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx), wie im Windows SDK beschrieben.

##  <a name="gethostinfo"></a>  CDHtmlDialog::GetHostInfo

Ruft Funktionen des Hosts ab.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Parameter

*"pInfo"*<br/>
Finden Sie unter *"pInfo"* in [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx), wie im Windows SDK beschrieben.

##  <a name="getoptionkeypath"></a>  CDHtmlDialog::GetOptionKeyPath

Ruft den Registrierungsschlüssel, unter dem benutzereinstellungen gespeichert werden.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Parameter

*pchKey*<br/>
Finden Sie unter *PchKey* in [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) im Windows SDK.

*Data Warehouse*<br/>
Finden Sie unter *dw* in `IDocHostUIHandler::GetOptionKeyPath` in das Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx), wie im Windows SDK beschrieben.

##  <a name="hideui"></a>  CDHtmlDialog::HideUI

Blendet die Host Benutzeroberfläche.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx), wie im Windows SDK beschrieben.

##  <a name="isexternaldispatchsafe"></a>  CDHtmlDialog::IsExternalDispatchSafe

Gibt an, ob der Hosts des `IDispatch` Schnittstelle für die Skripterstellung sicher ist.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Rückgabewert

Gibt FALSE zurück.

##  <a name="loadfromresource"></a>  CDHtmlDialog::LoadFromResource

Lädt die angegebene Ressource in das WebBrowser-Steuerelement im Dialogfeld für die DHTML an.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Parameter

*lpszResource*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Ressource, die geladen werden.

*nRes*<br/>
Die ID der Ressource geladen werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

##  <a name="m_busehtmltitle"></a>  CDHtmlDialog::m_bUseHtmlTitle

Gibt an, ob die dialogfeldbeschriftung Titel des HTML-Dokuments verwendet werden soll.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Hinweise

Wenn **m**_ **bUseHtmlTitle** ist "true", die dialogfeldbeschriftung auf den Titel der HTML-Dokument festgelegt; andernfalls wird die Beschriftung für die Ressource verwendet wird.

##  <a name="m_nhtmlresid"></a>  CDHtmlDialog::m_nHtmlResID

Ressourcen-ID von HTML-Ressource, die angezeigt werden soll.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

##  <a name="m_pbrowserapp"></a>  CDHtmlDialog::m_pBrowserApp

Ein Zeiger auf eine Web-Browser-Anwendung.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

##  <a name="m_sphtmldoc"></a>  CDHtmlDialog::m_spHtmlDoc

Ein Zeiger auf ein HTML-Dokument.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

##  <a name="m_strcurrenturl"></a>  CDHtmlDialog::m_strCurrentUrl

Die aktuelle URL.

```
CString m_strCurrentUrl;
```

##  <a name="m_szhtmlresid"></a>  CDHtmlDialog::m_szHtmlResID

Zeichenfolgenversion der HTML-Ressourcen-ID.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

##  <a name="navigate"></a>  CDHtmlDialog::Navigate

Navigiert zu die durch die URL, die angegebenen identifizierte Ressource *LpszURL*.

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

*lpszURL*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit der URL bereitgestellt werden soll.

*dwFlags*<br/>
Die Flags, der eine Variable, die angibt, ob die Ressource der Verlaufsliste hinzu, an, ob in den Cache lesen oder Schreiben von aus dem Cache und angibt, ob die Ressource in einem neuen Fenster angezeigt werden soll. Die Variable werden eine Kombination der Werte von definiert die [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) Enumeration.

*lpszTargetFrameName*<br/>
Ein Zeiger auf eine Zeichenfolge, die enthält der Name des Frames, in dem die Ressource angezeigt werden soll.

*lpszHeaders*<br/>
Ein Zeiger auf einen Wert, der angibt, die HTTP-Header an den Server gesendet werden soll. Diese Header werden in die Standard-Internet Explorer-Header hinzugefügt. Die Header können solche Informationen als die des Servers, den Typ der Daten, die mit dem Server oder einen Statuscode übergebenen erforderliche Aktion angeben. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.

*lpvPostData*<br/>
Ein Zeiger auf Daten, die mit der HTTP POST-Transaktion zu senden. Beispielsweise wird die POST-Transaktion verwendet, zum Senden von Daten, die von einem HTML-Formular gesammelt wurden. Wenn dieser Parameter keine Post-Daten angibt `Navigate` gibt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.

*dwPostDataLen*<br/>
Daten, die mit der HTTP POST-Transaktion zu senden. Beispielsweise wird die POST-Transaktion verwendet, zum Senden von Daten, die von einem HTML-Formular gesammelt wurden. Wenn dieser Parameter keine Post-Daten angibt `Navigate` gibt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.

##  <a name="onbeforenavigate"></a>  CDHtmlDialog::OnBeforeNavigate

Vom Framework aufgerufen, die dazu führen, dass ein Ereignis ausgelöst wird, bevor eine Navigation.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
Ein Zeiger auf ein `IDispatch` -Objekt.

*szUrl*<br/>
Ein Zeiger auf eine Zeichenfolge, enthält die URL zu navigieren.

##  <a name="ondocumentcomplete"></a>  CDHtmlDialog::OnDocumentComplete

Wird aufgerufen, durch das Framework eine Anwendung zu benachrichtigen, wenn ein Dokument den READYSTATE_COMPLETE-Zustand erreicht hat.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
Ein Zeiger auf ein `IDispatch` -Objekt.

*szUrl*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit der URL, zu dem navigiert wurde.

##  <a name="ondocwindowactivate"></a>  CDHtmlDialog::OnDocWindowActivate

Vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert ist.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parameter

*fActivate*<br/>
Finden Sie unter *fActivate* in [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird CDHtmlDialogs gesammelte von [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx), wie im Windows SDK beschrieben.

##  <a name="onframewindowactivate"></a>  CDHtmlDialog::OnFrameWindowActivate

Wird vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert ist.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parameter

*fActivate*<br/>
Finden Sie unter *fActivate* in [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx), wie im Windows SDK beschrieben.

##  <a name="oninitdialog"></a>  CDHtmlDialog::OnInitDialog

Wird aufgerufen, als Reaktion auf die WM_INITDIALOG-Meldung.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Nachricht wird gesendet, um das Dialogfeld während der `Create`, `CreateIndirect`, oder `DoModal` -Aufrufe, die auftreten, unmittelbar bevor das Dialogfeld angezeigt wird.

Überschreiben Sie diese Memberfunktion auf, wenn müssen Sie durchführen, besondere Bearbeitung, wenn das Dialogfeld initialisiert wird. In der außer Kraft gesetzte Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber ignorieren Sie den Rückgabewert. Sie werden normalerweise von Ihrer Funktion überschriebenen Member "true" zurückgeben.

Windows ruft die `OnInitDialog` Funktion über die globale-Standarddialogfeld-Prozedur, die für alle Microsoft Foundation Class Library-Dialogfelder, anstatt über die meldungszuordnung, also eine Meldungszuordnungseintrags für diese Memberfunktion keine man.

##  <a name="onnavigatecomplete"></a>  CDHtmlDialog::OnNavigateComplete

Vom Framework aufgerufen, nachdem die Navigation zur angegebenen URL abgeschlossen ist.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
Ein Zeiger auf ein `IDispatch` -Objekt.

*szUrl*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit der URL, zu dem navigiert wurde.

##  <a name="resizeborder"></a>  CDHtmlDialog::ResizeBorder

Benachrichtigt das Objekt, das die Größe seines Rahmenbereichs ändern muss.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Parameter

*prcBorder*<br/>
Finden Sie unter *PrcBorder* in [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) im Windows SDK.

*pUIWindow*<br/>
Finden Sie unter *pUIWindow* in `IDocHostUIHandler::ResizeBorder` im Windows SDK.

*fFrameWindow*<br/>
Finden Sie unter *fFrameWindow* in `IDocHostUIHandler::ResizeBorder` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

##  <a name="setcontrolproperty"></a>  CDHtmlDialog::SetControlProperty

Legt die Eigenschaft eines ActiveX-Steuerelements in einen neuen Wert fest.

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

*szElementId*<br/>
Die HTML-ID eines ActiveX-Steuerelements.

*DISPID*<br/>
Die Dispatch-ID der festzulegenden Eigenschaft.

*pVar*<br/>
Zeiger auf eine Variante, die den neue Eigenschaftswert enthält.

*pdispControl*<br/>
Zeiger auf ein ActiveX-Steuerelements `IDispatch` Schnittstelle.

*szPropName*<br/>
Eine Zeichenfolge mit dem Namen der festzulegenden Eigenschaft.

##  <a name="setelementhtml"></a>  CDHtmlDialog::SetElementHtml

Legt die `innerHTML` Eigenschaft eines HTML-Elements.

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

*bstrText*<br/>
Der neue Wert der `innerHTML`-Eigenschaft.

*punkElem*<br/>
Die `IUnknown` Zeiger eines HTML-Elements.

##  <a name="setelementproperty"></a>  CDHtmlDialog::SetElementProperty

Legt eine Eigenschaft eines HTML-Elements.

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispid,
    VARIANT* pVar);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

*DISPID*<br/>
Die Dispatch-ID der festzulegenden Eigenschaft.

*pVar*<br/>
Der neue Wert der Eigenschaft.

##  <a name="setelementtext"></a>  CDHtmlDialog::SetElementText

Legt die `innerText` Eigenschaft eines HTML-Elements.

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parameter

*szElementId*<br/>
Die ID eines HTML-Elements.

*bstrText*<br/>
Der neue Wert der `innerText`-Eigenschaft.

*punkElem*<br/>
Die `IUnknown` Zeiger eines HTML-Elements.

##  <a name="setexternaldispatch"></a>  CDHtmlDialog::SetExternalDispatch

Legt der Hosts `IDispatch` Schnittstelle.

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Parameter

*pdispExternal*<br/>
Die neue `IDispatch` Schnittstelle.

##  <a name="sethostflags"></a>  CDHtmlDialog::SetHostFlags

Legt den Host-UI-Flags fest.

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Mögliche Werte finden Sie unter [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) im Windows SDK.

##  <a name="showcontextmenu"></a>  CDHtmlDialog::ShowContextMenu

Wird aufgerufen, wenn ein Kontextmenü angezeigt wird.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Parameter

*dwID*<br/>
Finden Sie unter *DwID* in [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) im Windows SDK.

*PPT*<br/>
Finden Sie unter *ppt* in `IDocHostUIHandler::ShowContextMenu` in das Windows SDK.

*pcmdtReserved*<br/>
Finden Sie unter *PcmdtReserved* in `IDocHostUIHandler::ShowContextMenu` im Windows SDK.

*pdispReserved*<br/>
Finden Sie unter *PdispReserved* in `IDocHostUIHandler::ShowContextMenu` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_FALSE zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx), wie im Windows SDK beschrieben.

##  <a name="showui"></a>  CDHtmlDialog::ShowUI

Zeigt die Host Benutzeroberfläche.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>Parameter

*dwID*<br/>
Finden Sie unter *DwID* in [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) im Windows SDK.

*pActiveObject*<br/>
Finden Sie unter *d pActiveObject* in `IDocHostUIHandler::ShowUI` im Windows SDK.

*pCommandTarget*<br/>
Finden Sie unter *pCommandTarget* in `IDocHostUIHandler::ShowUI` im Windows SDK.

*pFrame*<br/>
Finden Sie unter *pFrame* in `IDocHostUIHandler::ShowUI` im Windows SDK.

*pDoc*<br/>
Finden Sie unter *pDoc* in `IDocHostUIHandler::ShowUI` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_FALSE zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx), wie im Windows SDK beschrieben.

##  <a name="translateaccelerator"></a>  CDHtmlDialog::TranslateAccelerator

Wird aufgerufen, um den Prozess Tastenkombinations-menünachrichten.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Parameter

*lpMsg*<br/>
Finden Sie unter *LpMsg* in [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) im Windows SDK.

*pguidCmdGroup*<br/>
Finden Sie unter *PguidCmdGroup* in `IDocHostUIHandler::TranslateAccelerator` im Windows SDK.

*nCmdID*<br/>
Finden Sie unter *nCmdID* in `IDocHostUIHandler::TranslateAccelerator` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_FALSE zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx), wie im Windows SDK beschrieben.

##  <a name="translateurl"></a>  CDHtmlDialog::TranslateUrl

Wird aufgerufen, um die URL zu ladenden ändern.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Parameter

*dwTranslate*<br/>
Finden Sie unter *DwTranslate* in [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) im Windows SDK.

*pchURLIn*<br/>
Finden Sie unter *PchURLIn* in `IDocHostUIHandler::TranslateUrl` im Windows SDK.

*ppchURLOut*<br/>
Finden Sie unter *PpchURLOut* in `IDocHostUIHandler::TranslateUrl` im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_FALSE zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx), wie im Windows SDK beschrieben.

##  <a name="updateui"></a>  CDHtmlDialog::UpdateUI

Wird aufgerufen, um den Host zu benachrichtigen, den der Befehlsstatus geändert hat.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist CDHtmlDialogs-Implementierung von [IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx), wie im Windows SDK beschrieben.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DHtmlExplore](../../visual-cpp-samples.md)<br/>
[DDX_DHtml-Hilfsmakros](#ddx_dhtml_helper_macros)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

