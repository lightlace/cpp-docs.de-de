---
title: CDHtmlDialog Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CDHtmlDialog class
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: adf3664da1ecd1bdde9a1bd13e5b43ab7695e4d7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog-Klasse
Wird verwendet, um Dialogfelder zu erstellen, verwenden HTML, statt der Dialogfeldressourcen ihre Benutzeroberfläche implementiert.  
  
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
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Überschreibbare heißt, als ein Zugriff überprüfen können, ob scripting Objekte auf der Seite geladen, die externe Verteilung der Site für das Steuerelement zugreifen können. Stellen Sie sicher, dass die Verteilung ermöglicht die für scripting sicher sind oder der aktuellen Zone für Objekte, die nicht sicher für Skripting überprüft.|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable verwendet, um eine Instanz eines Steuerelements Website zum Hosten der WebBrowser-Steuerelement im Dialogfeld erstellen.|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Tauscht Daten zwischen einer Membervariablen und den Wert der Eigenschaft eines ActiveX-Steuerelements auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Tauscht Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite das Kontrollkästchen.|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Tauscht Daten zwischen einer Membervariablen und eine HTML-Element-Eigenschaft einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Tauscht Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld aus.|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Ruft ab oder legt den Index eines Listenfelds auf einer HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Ruft ab den Anzeigetext ein (basierend auf den aktuellen Index) im Listenfeld eine HTML-Seite.|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Ruft ab oder legt den Wert einer im Listenfeld (basierend auf den aktuellen Index) eine HTML-Seite fest.|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Zerstört ein nicht modales Dialogfeld.|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Ermöglicht nicht modale Dialogfelder.|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Können das Dialogfeld zum Filtern der Zwischenablage Datenobjekte, die vom Browser gehosteten erstellt.|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Ruft die `IDispatch` Schnittstelle für ein ActiveX-Steuerelement in das HTML-Dokument eingebettet.|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Ruft die angeforderte Eigenschaft des angegebenen ActiveX-Steuerelements ab.|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Ruft die IHTMLDocument2-Schnittstelle für die derzeit geladenen HTML-Dokument ab.|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Von enthaltenen WebBrowser-Steuerelement aufgerufen, wenn sie im Dialogfeld, um eine Alternative angeben können als Ablageziel verwendet wird [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](#getelement)|Ruft eine Schnittstelle auf ein HTML-Element.|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Ruft die **InnerHTML** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Ruft den angeforderten Schnittstellenzeiger aus einem HTML-Element ab.|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Ruft den Wert der Eigenschaft eines HTML-Elements ab.|  
|[CDHtmlDialog::GetElementText](#getelementtext)|Ruft die **InnerText** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::GetEvent](#getevent)|Ruft die **IHTMLEventObj** Zeiger auf das aktuelle Ereignisobjekt.|  
|[CDHtmlDialog::GetExternal](#getexternal)|Ruft den Host ab `IDispatch` Schnittstelle.|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Ruft den Host Benutzeroberflächenfunktionen ab.|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Ruft den Registrierungsschlüssel unter dem Voreinstellungen des Benutzers gespeichert sind.|  
|[CDHtmlDialog::HideUI](#hideui)|Blendet die Host-Benutzeroberfläche.|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Gibt an, ob der Hosts `IDispatch` Schnittstelle ist sicher für Skripting.|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Lädt die angegebene Ressource in das WebBrowser-Steuerelement.|  
|[CDHtmlDialog::Navigate](#navigate)|Navigiert zur angegebenen URL.|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Vom Framework aufgerufen, bevor ein Navigationsereignis ausgelöst wird.|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Aufgerufen, um eine Anwendung zu benachrichtigen, wenn ein Dokument erreicht hat die `READYSTATE_COMPLETE` Zustand.|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Wird vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert wird.|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Wird vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert wird.|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Als Reaktion auf die **WM_INITDIALOG** Nachricht.|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Wird vom Framework aufgerufen, nachdem ein Navigationsereignis abgeschlossen ist.|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Das Objekt, das Größe des Speicherplatzes Rahmen muss eine Warnung.|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Legt die Eigenschaft eines ActiveX-Steuerelements in einen neuen Wert fest.|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Legt die **InnerHTML** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Legt eine Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetElementText](#setelementtext)|Legt die **InnerText** Eigenschaft eines HTML-Elements.|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Legt des Hosts `IDispatch` Schnittstelle.|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Der Host UI-Flags festgelegt.|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Wird aufgerufen, wenn ein Kontextmenü angezeigt werden soll.|  
|[CDHtmlDialog::ShowUI](#showui)|Zeigt die Benutzeroberfläche des Hosts.|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Menü-Zugriffstaste Nachrichten bezeichnet.|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|Aufgerufen, um die URL zu ladenden ändern.|  
|[CDHtmlDialog::UpdateUI](#updateui)|Wird aufgerufen, um den Host zu benachrichtigen, den dass der Befehlsstatus geändert hat.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Gibt an, ob als Dialogfeld Titel den Titel der HTML verwenden.|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ressourcen-ID der HTML-Ressource angezeigt werden.|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Ein Zeiger auf eine Web-Browser-Anwendung.|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Ein Zeiger auf ein HTML-Dokument.|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Die aktuelle URL.|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Zeichenfolgenversion der HTML-Ressource-ID.|  
  
## <a name="remarks"></a>Hinweise  
 **CDHtmlDialog** können den HTML-Code aus einer HTML-Ressource angezeigt werden oder eine URL laden.  
  
 `CDHtmlDialog`Außerdem Daten Austausch mit HTML-Steuerelementen und Behandeln von Ereignissen aus HTML-Steuerelemente, wie z. B. Schaltflächenklicks.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Die DDX_DHtml Hilfsmakros ermöglichen einen einfachen Zugriff auf die am häufigsten verwendeten Eigenschaften von Steuerelementen auf einer HTML-Seite.  
  
### <a name="data-exchange-macros"></a>Data Exchange-Makros  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft des ausgewählten Steuerelements.|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Legt fest oder ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Legt fest oder ruft den Ziel-URL oder den Ankerpunkt Punkt.|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Legt fest oder ruft das Zielfenster oder der Zielframe.|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Legt fest oder ruft den Namen der ein Bild oder einen Videoclip in das Dokument.|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Legt fest oder ruft die URL des zugeordneten Rahmen.|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL des zugeordneten Rahmen.|  
  
##  <a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal  
 Überschreibbare heißt, als ein Zugriff überprüfen können, ob scripting Objekte auf der Seite geladen, die externe Verteilung der Site für das Steuerelement zugreifen können. Stellen Sie sicher, dass die Verteilung ermöglicht die für scripting sicher sind oder der aktuellen Zone für Objekte, die nicht sicher für Skripting überprüft.  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog  
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
 `lpszTemplateName`  
 Die auf Null endende Zeichenfolge, die den Namen des eine Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `szHtmlResID`  
 Die auf Null endende Zeichenfolge, die den Namen der HTML-Ressource ist.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Element oder Besitzer (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `nHtmlResID`  
 Enthält die ID-Nummer, der eine HTML-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form des Konstruktors ermöglicht den Zugriff auf die Ressource über den Vorlagennamen. Die dritte Form des Konstruktors ermöglicht den Zugriff auf die Ressource über die ID der Ressourcenvorlage für. Die ID beginnt gewöhnlich mit der **IDD_** Präfix.  
  
##  <a name="_dtorcdhtmldialog"></a>CDHtmlDialog:: ~ CDHtmlDialog  
 Zerstört ein CDHtmlDialog-Objekt.  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 Die [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) Member-Funktion muss verwendet werden, um nicht modale Dialogfelder zerstören durch die erstellte [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
##  <a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite  
 Overridable verwendet, um eine Instanz eines Steuerelements Website zum Hosten der WebBrowser-Steuerelement im Dialogfeld erstellen.  
  
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
 Sie können diese Memberfunktion zum Zurückgeben einer Instanz von eine eigene Website-Klasse überschreiben.  
  
##  <a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl  
 Tauscht Daten zwischen einer Membervariablen und den Wert der Eigenschaft eines ActiveX-Steuerelements auf einer HTML-Seite.  
  
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
 Der Wert des ID-Parameter für das Object-Tag im HTML-Quelle für das ActiveX-Steuerelement.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, mit der Sie Daten austauschen möchten.  
  
 `szPropName`  
 Der Name der Eigenschaft.  
  
 `var`  
 Der Datenmember vom Typ `VARIANT`, [COleVariant](../../mfc/reference/colevariant-class.md), oder [CComVariant](../../atl/reference/ccomvariant-class.md), enthält den Wert, der mit der Eigenschaft des ActiveX-Steuerelements ausgetauscht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&#1;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox  
 Tauscht Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite das Kontrollkästchen.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&#2;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText  
 Tauscht Daten zwischen einer Membervariablen und eine HTML-Element-Eigenschaft einer HTML-Seite.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 *DISPID*  
 Die Dispatch-ID des HTML-Elements, mit denen Sie Daten austauschen möchten.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
##  <a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio  
 Tauscht Daten zwischen einer Membervariablen gespeichert und auf einer HTML-Seite ein Optionsfeld aus.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-Id-Parameter angegeben.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
##  <a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString  
 Ruft ab den Anzeigetext ein (basierend auf den aktuellen Index) im Listenfeld eine HTML-Seite.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
##  <a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue  
 Ruft ab oder legt den Wert einer im Listenfeld (basierend auf den aktuellen Index) eine HTML-Seite fest.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 *value*  
 Der Wert ausgetauscht werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&3;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless  
 Ein nicht modales Dialogfeld aus trennt die `CDHtmlDialog` -Objekt und das Objekt zerstört.  
  
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
 Finden Sie unter `fEnable` in [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject  
 Können das Dialogfeld zum Filtern der Zwischenablage Datenobjekte, die vom Browser gehosteten erstellt.  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>Parameter  
 `pDO`  
 Finden Sie unter `pDO` in [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDORet`  
 Finden Sie unter `ppDORet` in **IDocHostUIHandler::FilterDataObject** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **S_FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch  
 Ruft die `IDispatch` Schnittstelle für ein ActiveX-Steuerelement eingebettet im HTML-Dokument zurückgegebene [GetDHtmlDocument](#getdhtmldocument).  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>Parameter  
 `szId`  
 Die HTML-ID eines ActiveX-Steuerelements.  
  
 *ppdisp*  
 Die `IDispatch` Schnittstelle Wenn auf der Webseite gefunden.  
  
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
 Der Name einer Eigenschaft in das Standardgebietsschema des aktuellen Benutzers.  
  
 `pdispControl`  
 Die `IDispatch` Zeiger eines ActiveX-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID einer Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Variante, die mit der angeforderten Eigenschaft oder ein leerer Variant-Wert, wenn das Steuerelement oder die Eigenschaft nicht gefunden werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Überladungen werden von oben am wenigsten effiziente auf effizienteste unten aufgelistet.  
  
##  <a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl  
 Ruft den Uniform Resource Locator (URL), die das aktuelle Dokument zugeordnet ist.  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `szUrl`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit der URL abzurufen.  
  
##  <a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument  
 Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das derzeit geladene HTML-Dokument.  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *\*\*pphtmlDoc*  
 Ein Zeiger auf einen Zeiger auf ein HTML-Dokument.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Gibt bei Erfolg `S_OK` zurück.  
  
##  <a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget  
 Von enthaltenen WebBrowser-Steuerelement aufgerufen, wenn sie im Dialogfeld, um eine Alternative angeben können als Ablageziel verwendet wird [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pDropTarget`  
 Finden Sie unter `pDropTarget` in [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDropTarget`  
 Finden Sie unter `ppDropTarget` in **IDocHostUIHandler::GetDropTarget** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 Ein **BOOL** , der angibt, ob das Objekt durch dargestellt *Ppdisp* ist ein einzelnes Element oder eine Auflistung von Elementen.  
  
 *pphtmlElement*  
 Ein **IHTMLElement** Zeiger auf das angeforderte Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Überladung, wenn Sie müssen zum Verarbeiten in der möglicherweise mehr als ein Element mit der angegebenen ID. Den letzten Parameter können Sie feststellen, ob der zurückgegebene Schnittstellenzeiger auf eine Auflistung oder ein einzelnes Element handelt. Wenn der Schnittstellenzeiger auf eine Auflistung ist, können Sie Abfragen der **IHTMLElementCollection** und seine **Element** -Eigenschaft zum Verweisen auf die Elemente nach der Ordnungsposition.  
  
 Die zweite Überladung schlägt fehl, wenn mehr als ein Element mit der gleichen ID auf der Seite vorhanden ist.  
  
##  <a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml  
 Ruft die **InnerHTML** -Eigenschaft des HTML-Elements identifizierten `szElementId`.  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **InnerHTML** -Eigenschaft des HTML-Elements identifizierten `szElementId` oder **NULL** , wenn das Element nicht gefunden werden konnte.  
  
##  <a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface  
 Ruft den angeforderten-Schnittstellenzeiger aus dem HTML-Element identifizierten `szElementId`.  
  
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
 Adresse des ein Zeiger, der die angeforderte Schnittstellenzeiger gefüllt werden, wenn das Element gefunden wird und die Abfrage erfolgreich ausgeführt wird.  
  
 `riid`  
 Die Schnittstelle-ID (IID) der angeforderten Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&4;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty  
 Ruft den Wert der Eigenschaft identifizierten `dispid` aus dem HTML-Element identifizierten `szElementId`.  
  
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
 Der Wert der Eigenschaft oder ein leerer Variant-Wert, wenn die Eigenschaft oder ein Element nicht gefunden werden konnte.  
  
##  <a name="getelementtext"></a>CDHtmlDialog::GetElementText  
 Ruft die **InnerText** -Eigenschaft des HTML-Elements identifizierten `szElementId`.  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Parameter  
 `szElementId`  
 Die ID eines HTML-Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **InnerText** -Eigenschaft des HTML-Elements identifizierten `szElementId` oder **NULL** , wenn die Eigenschaft oder ein Element nicht gefunden werden konnte.  
  
##  <a name="getevent"></a>CDHtmlDialog::GetEvent  
 Gibt die **IHTMLEventObj** Zeiger auf das aktuelle Ereignisobjekt.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEventObj`  
 Die Adresse eines Zeigers, der mit gefüllt werden die **IHTMLEventObj** -Schnittstellenzeiger.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur von einem DHTML-Ereignishandler aufgerufen werden.  
  
##  <a name="getexternal"></a>CDHtmlDialog::GetExternal  
 Ruft den Host ab `IDispatch` Schnittstelle.  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>Parameter  
 *ppDispatch*  
 Finden Sie unter *PpDispatch* in [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg oder **E_NOTIMPL** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo  
 Ruft den Host Benutzeroberflächenfunktionen ab.  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Finden Sie unter `pInfo` in [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath  
 Ruft den Registrierungsschlüssel unter dem Voreinstellungen des Benutzers gespeichert sind.  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>Parameter  
 `pchKey`  
 Finden Sie unter `pchKey` in [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dw`  
 Finden Sie unter `dw` in **IDocHostUIHandler::GetOptionKeyPath** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="hideui"></a>CDHtmlDialog::HideUI  
 Blendet die Host-Benutzeroberfläche.  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe  
 Gibt an, ob der Hosts `IDispatch` Schnittstelle ist sicher für Skripting.  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **FALSE**.  
  
##  <a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource  
 Lädt die angegebene Ressource in das WebBrowser-Steuerelement im Dialogfeld DHTML.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResource`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Ressource zu laden.  
  
 `nRes`  
 Die ID der Ressource geladen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
##  <a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle  
 Gibt an, ob als Dialogfeld Titel den Titel der HTML verwenden.  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn **m**_ **bUseHtmlTitle** ist **true**, Dialogfeld Beschriftung den Titel des HTML-Dokuments entspricht; andernfalls festgelegt ist, wird die Beschriftung für die Ressource verwendet.  
  
##  <a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID  
 Ressourcen-ID der HTML-Ressource angezeigt werden.  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCHtmlHttp&5;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp  
 Ein Zeiger auf eine Web-Browser-Anwendung.  
  
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
 [!code-cpp[NVC_MFCHtmlHttp&6;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="navigate"></a>CDHtmlDialog::Navigate  
 Navigiert zu der Ressource identifiziert, die durch die URL, die durch angegeben wird `lpszURL`.  
  
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
 Ein Zeiger auf eine Zeichenfolge mit der URL als Ziel angegeben werden.  
  
 `dwFlags`  
 Die Flags einer Variablen, der angibt, ob die Ressource die Verlaufsliste hinzugefügt, ob der Cache lesen oder Schreiben aus dem Cache und angibt, ob die Ressource in einem neuen Fenster anzuzeigen. Die Variable kann eine Kombination der Werte von definiert die [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) Enumeration.  
  
 `lpszTargetFrameName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Frames, in dem die Ressource angezeigt.  
  
 `lpszHeaders`  
 Ein Zeiger auf einen Wert, der angibt, die HTTP-Header an den Server gesendet. Diese Header werden die Standard-Internet Explorer-Header hinzugefügt. Die Header können solche Informationen als die des Servers, den Typ der Daten an den Server oder einen Statuscode erforderliche Aktion angeben. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
 `lpvPostData`  
 Ein Zeiger auf die Daten, die mit der HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten, die durch ein HTML-Formular verwendet. Wenn dieser Parameter keine Post-Daten angegeben wird **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
 `dwPostDataLen`  
 Daten, die HTTP POST-Transaktion gesendet. Beispielsweise wird die POST-Transaktion zum Senden von Daten, die durch ein HTML-Formular verwendet. Wenn dieser Parameter keine Post-Daten angegeben wird **navigieren** stellt eine HTTP GET-Transaktion. Dieser Parameter wird ignoriert, wenn die URL nicht über eine HTTP-URL ist.  
  
##  <a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate  
 Vom Framework aufgerufen wird, bewirken, dass ein Ereignis ausgelöst, bevor eine Navigation.  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge mit der URL zu navigieren.  
  
##  <a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete  
 Aufgerufen, um eine Anwendung zu benachrichtigen, wenn ein Dokument erreicht hat die `READYSTATE_COMPLETE` Zustand.  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge mit der URL, zu der navigiert wurde.  
  
##  <a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate  
 Wird vom Framework aufgerufen, wenn das Dokumentfenster aktiviert oder deaktiviert wird.  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Finden Sie unter `fActivate` in [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialogs Durchführung des [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate  
 Wird vom Framework aufgerufen, wenn das Rahmenfenster aktiviert oder deaktiviert wird.  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `fActivate`  
 Finden Sie unter `fActivate` in [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog  
 Als Reaktion auf die **WM_INITDIALOG** Nachricht.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt **TRUE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Nachricht wird gesendet, um das Dialogfeld während der **erstellen**, `CreateIndirect`, oder `DoModal` Funktionsaufrufe, die auftreten, unmittelbar bevor das Dialogfeld angezeigt wird.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn zur speziellen Verarbeitung bei der Initialisierung des Dialogfelds müssen. In der überschriebenen Version, rufen Sie zunächst die Basisklasse `OnInitDialog` aber ihren Rückgabewert ignorieren. Normalerweise wird nun wieder **TRUE** Ihrer überschriebene Member-Funktion.  
  
 Windows ruft die `OnInitDialog` -Funktion über die globale-Standarddialogfeld-Prozedur, die für alle Microsoft Foundation Class Library-Dialogfelder, anstatt über Ihre Zuordnung Nachricht also eine Meldungszuordnungseintrags für diese Memberfunktion Sie brauchen.  
  
##  <a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete  
 Nach Abschluss der Navigation zur angegebenen URL vom Framework aufgerufen.  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Ein Zeiger auf ein `IDispatch` -Objekt.  
  
 `szUrl`  
 Ein Zeiger auf eine Zeichenfolge mit der URL, zu der navigiert wurde.  
  
##  <a name="resizeborder"></a>CDHtmlDialog::ResizeBorder  
 Das Objekt, das Größe des Speicherplatzes Rahmen muss eine Warnung.  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>Parameter  
 `prcBorder`  
 Finden Sie unter `prcBorder` in [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pUIWindow`  
 Finden Sie unter `pUIWindow` in **IDocHostUIHandler::ResizeBorder** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `fFrameWindow`  
 Finden Sie unter *fFrameWindow* in **IDocHostUIHandler::ResizeBorder** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty  
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
 `szElementId`  
 Die HTML-ID eines ActiveX-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID der festzulegenden Eigenschaft.  
  
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
 Der neue Wert, der die **InnerHTML** Eigenschaft.  
  
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
 Die Dispatch-ID der festzulegenden Eigenschaft.  
  
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
 Der neue Wert, der die **InnerText** Eigenschaft.  
  
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
 Der Host festgelegt UI-Flags.  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Mögliche Werte finden Sie unter [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu  
 Wird aufgerufen, wenn ein Kontextmenü angezeigt werden soll.  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>Parameter  
 `dwID`  
 Finden Sie unter `dwID` in [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppt`  
 Finden Sie unter `ppt` in **IDocHostUIHandler::ShowContextMenu** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pcmdtReserved`  
 Finden Sie unter `pcmdtReserved` in **IDocHostUIHandler::ShowContextMenu** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pdispReserved`  
 Finden Sie unter `pdispReserved` in **IDocHostUIHandler::ShowContextMenu** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **S_FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="showui"></a>CDHtmlDialog::ShowUI  
 Zeigt die Benutzeroberfläche des Hosts.  
  
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
 Finden Sie unter `dwID` in [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pActiveObject`  
 Finden Sie unter *d pActiveObject* in **IDocHostUIHandler::ShowUI** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pCommandTarget`  
 Finden Sie unter `pCommandTarget` in **IDocHostUIHandler::ShowUI** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pFrame`  
 Finden Sie unter `pFrame` in **IDocHostUIHandler::ShowUI** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pDoc`  
 Finden Sie unter `pDoc` in **IDocHostUIHandler::ShowUI** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **S_FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator  
 Menü-Zugriffstaste Nachrichten bezeichnet.  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Finden Sie unter `lpMsg` in [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pguidCmdGroup`  
 Finden Sie unter `pguidCmdGroup` in **IDocHostUIHandler::TranslateAccelerator** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nCmdID`  
 Finden Sie unter `nCmdID` in **IDocHostUIHandler::TranslateAccelerator** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **S_FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="translateurl"></a>CDHtmlDialog::TranslateUrl  
 Aufgerufen, um die URL zu ladenden ändern.  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTranslate`  
 Finden Sie unter `dwTranslate` in [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pchURLIn`  
 Finden Sie unter `pchURLIn` in **IDocHostUIHandler::TranslateUrl** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppchURLOut`  
 Finden Sie unter `ppchURLOut` in **IDocHostUIHandler::TranslateUrl** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **S_FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="updateui"></a>CDHtmlDialog::UpdateUI  
 Wird aufgerufen, um den Host zu benachrichtigen, den dass der Befehlsstatus geändert hat.  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist CDHtmlDialog Implementierung von [IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DHtmlExplore](../../visual-cpp-samples.md)   
 [Hilfsmakros DDX_DHtml](#ddx_dhtml_helper_macros)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



