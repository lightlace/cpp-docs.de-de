---
title: COleControlSite Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
dev_langs:
- C++
helpviewer_keywords:
- COleControlSite class
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
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
ms.openlocfilehash: 9bae18342fe5f6aeac939c854f578cf47636fa63
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolsite-class"></a>COleControlSite-Klasse
Stellt Unterstützung für benutzerdefinierte clientseitige Steuerelement-Schnittstellen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|Erstellt ein `COleControlSite`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Die Standardeigenschaft des gehosteten Steuerelements bindet an eine Datenquelle.|  
|[COleControlSite::BindProperty](#bindproperty)|Eine Eigenschaft des gehosteten Steuerelements bindet an eine Datenquelle.|  
|[COleControlSite::CreateControl](#createcontrol)|Erstellt ein gehosteten ActiveX-Steuerelement.|  
|[COleControlSite::DestroyControl](#destroycontrol)|Zerstört das gehostete Steuerelement.|  
|[COleControlSite::DoVerb](#doverb)|Führt ein bestimmtes Verb des gehosteten Steuerelements.|  
|[COleControlSite::EnableDSC](#enabledsc)|Ermöglicht die Quelle für eine Website des Steuerelements darstellt.|  
|[COleControlSite::EnableWindow](#enablewindow)|Können die Website des Steuerelements.|  
|[COleControlSite::FreezeEvents](#freezeevents)|Gibt an, ob die Steuerelementsite Ereignisse akzeptiert.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Ruft den Standardcode für die Schaltfläche für das gehostete Steuerelement ab.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Ruft den Bezeichner des Steuerelements ab.|  
|[COleControlSite::GetEventIID](#geteventiid)|Ruft die ID einer Ereignis-Schnittstelle für ein gehostetes Steuerelement ab.|  
|[COleControlSite::GetExStyle](#getexstyle)|Ruft die erweiterten Stile, der die Website des Steuerelements ab.|  
|[COleControlSite::GetProperty](#getproperty)|Ruft eine bestimmte Eigenschaft des gehosteten Steuerelements ab.|  
|[COleControlSite::GetStyle](#getstyle)|Ruft die Formatvorlagen der Site für das Steuerelement ab.|  
|[COleControlSite::GetWindowText](#getwindowtext)|Ruft den Text des gehosteten Steuerelements ab.|  
|[COleControlSite::InvokeHelper](#invokehelper)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements mit einer Variable Argumentliste.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Bestimmt, ob das Steuerelement die Standardschaltfläche im Fenster ist.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Überprüft den Sichtbarkeitsstatus der Site für das Steuerelement.|  
|[COleControlSite::ModifyStyle](#modifystyle)|Ändert die aktuelle erweiterte Stile der Site für das Steuerelement.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Ändert die aktuelle Stile der Site für das Steuerelement.|  
|[COleControlSite::MoveWindow](#movewindow)|Ändert die Position der Site für das Steuerelement.|  
|[COleControlSite::QuickActivate](#quickactivate)|Quick aktiviert das gehostete Steuerelement.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|Legt eine Eigenschaft oder Methode des Steuerelements ohne Wahrscheinlichkeit eine Ausnahme ausgelöst.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Legt die Standardschaltfläche im Fenster fest.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Ruft den Bezeichner des Steuerelements ab.|  
|[COleControlSite::SetFocus](#setfocus)|Legt den Fokus auf die Website des Steuerelements fest.|  
|[COleControlSite::SetProperty](#setproperty)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements mit einer Variable Argumentliste.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|Legt die Position der Site für das Steuerelement fest.|  
|[COleControlSite::SetWindowText](#setwindowtext)|Legt den Text des gehosteten Steuerelements.|  
|[COleControlSite::ShowWindow](#showwindow)|Anzeigen oder Ausblenden der Website des Steuerelements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Ruft Tastaturinformationen und Zugriffstasten für das gehostete Steuerelement ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Bestimmt, ob das gehostete Steuerelement ein fensterloses Steuerelement ist.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Enthält Informationen über die Tastatur, die für das Steuerelement behandeln.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Das Cookie des Verbindungspunkts des Steuerelements.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Die verschiedenen Status für das gehostete Steuerelement.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Die `IPropertyNotifySink` Cookie des Steuerelements.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|Die Stile des gehosteten Steuerelements.|  
|[COleControlSite::m_hWnd](#m_hwnd)|Das Handle der Site für das Steuerelement.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|Die ID der Ereignisschnittstelle für das gehostete Steuerelement.|  
|[COleControlSite::m_nID](#m_nid)|Die ID des gehosteten Steuerelements.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Ein Zeiger auf die `IOleInPlaceActiveObject` Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Der Container des gehosteten Steuerelements.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Ein Zeiger auf die `IOleInPlaceObject` Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m_pObject](#m_pobject)|Ein Zeiger auf die `IOleObjectInterface` Schnittstelle des Steuerelements.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Ein Zeiger auf die `IOleInPlaceObjectWindowless` Schnittstelle des Steuerelements.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Ein Zeiger auf das Window-Objekt für das gehostete Steuerelement.|  
|[COleControlSite::m_rect](#m_rect)|Die Dimensionen von der Website des Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Unterstützung ist das primäre Mittel, durch die ein eingebettetes ActiveX-Steuerelement Informationen über den Speicherort und Größe seiner Anzeigeseite, seinen Moniker, seine Benutzeroberfläche, die ambient-Eigenschaften und andere Ressourcen, die von seinem Container bereitgestellt erhält. `COleControlSite`vollständig implementiert die [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), **IBoundObjectSite**, **INotifyDBEvents**, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) Schnittstellen. Darüber hinaus wird auch die IDispatch-Schnittstelle (Unterstützung für Umgebungseigenschaften und Ereignissenken) implementiert.  
  
 Um eine Website mit ActiveX-Steuerelement erstellen `COleControlSite`, leiten Sie eine Klasse von `COleControlSite`. In der `CWnd`-abgeleiteten Klasse für den Container (z. B. ein Dialogfeld) überschreiben die **CWnd::CreateControlSite** Funktion.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>COleControlSite::BindDefaultProperty  
 Bindet das aufrufende Objekt einfach gebundenen Standardeigenschaft, als markierte in der Typbibliothek auf den zugrunde liegenden Cursor, der von der Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen-Steuerelements definiert wird.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Gibt die **DISPID** einer Eigenschaft für ein datengebundenes Steuerelement, das an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft, die gebunden werden, z. B. `VT_BSTR`, **VT_VARIANT**und so weiter.  
  
 `szFieldName`  
 Gibt den Namen der Spalte im Cursor zur Verfügung gestellt, von dem Datenquellen-Steuerelement, zu dem die Eigenschaft gebunden wird.  
  
 `pDSCWnd`  
 Ein Zeiger auf die `CWnd`-abgeleiteten Objekt, das Datenquellen Steuerelement hostet, zu dem die Eigenschaft gebunden werden.  
  
### <a name="remarks"></a>Hinweise  
 Das `CWnd` Objekt, auf dem Sie diese Funktion aufrufen, muss ein datengebundenes Steuerelement.  
  
##  <a name="bindproperty"></a>COleControlSite::BindProperty  
 Bindet das aufrufende Objekt einfach gebundenen Eigenschaft als markierte in der Typbibliothek, auf den zugrunde liegenden Cursor, der von der Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen-Steuerelements definiert wird.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispId*  
 Gibt die **DISPID** einer Eigenschaft für ein datengebundenes Steuerelement, das an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 `pWndDSC`  
 Ein Zeiger auf die `CWnd`-abgeleiteten Objekt, das Datenquellen Steuerelement hostet, zu dem die Eigenschaft gebunden werden.  
  
### <a name="remarks"></a>Hinweise  
 Das `CWnd` Objekt, auf dem Sie diese Funktion aufrufen, muss ein datengebundenes Steuerelement.  
  
##  <a name="colecontrolsite"></a>COleControlSite::COleControlSite  
 Erstellt ein neues `COleControlSite`-Objekt.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parameter  
 `pCtrlCont`  
 Ein Zeiger auf das Steuerelement-Container (das Fenster mit dem AtiveX Steuerelement darstellt).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem die [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) Funktion. Weitere Informationen zum Anpassen der Erstellung von Containern finden Sie unter [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).  
  
##  <a name="createcontrol"></a>COleControlSite::CreateControl  
 Erstellt ein ActiveX-Steuerelement gehostet wird, durch die `COleControlSite` Objekt.  
  
```  
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndCtrl`  
 Ein Zeiger auf das Steuerelement darstellt.  
  
 `clsid`  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 `lpszWindowName`  
 Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Winodw Beschriftung oder Text-Eigenschaft fest, (sofern vorhanden).  
  
 `dwStyle`  
 Fensterstile. Die verfügbaren Formate finden Sie unter der **Hinweise** Abschnitt.  
  
 `rect`  
 Gibt die Größe und Position des Steuerelements. Es kann entweder eine `CRect` Objekt oder eine `RECT` Struktur.  
  
 `nID`  
 Gibt an, der ID des Steuerelements untergeordnete Fenster  
  
 `pPersist`  
 Ein Zeiger auf eine `CFile` , die den Zustand für das Steuerelement enthält. Der Standardwert ist **NULL**, gibt an, dass das Steuerelement selbst ohne seinen Zustand wiederherzustellen, aus dem alle permanenten Speicher initialisiert. Wenn dies nicht **NULL**, wird ein Zeiger auf eine `CFile`-abgeleitetes Objekt mit persistenten Daten des Steuerelements in Form von einem Stream oder ein Speicherkonto. Diese Daten können in einer vorherigen Aktivierung des Clients gespeichert worden sein. Die `CFile` können andere Daten, muss jedoch seinen Schreib-Lese-Zeiger auf das erste Byte der Daten dauerhaft festgelegt werden, zum Zeitpunkt des Aufrufs von `CreateControl`.  
  
 `bStorage`  
 Gibt an, ob die Daten in `pPersist` interpretiert werden soll, als `IStorage` oder `IStream` Daten. Wenn die Daten in `pPersist` ist ein Speicher `bStorage` sollte **TRUE**. Wenn die Daten in `pPersist` ist ein Stream `bStorage` sollte **FALSE**. Der Standardwert ist **FALSE**.  
  
 `bstrLicKey`  
 Optionale Lizenz Schlüsseldaten. Diese Daten ist erforderlich, nur zum Erstellen von Steuerelementen, die zur Laufzeit Lizenzschlüssel erforderlich. Wenn das Steuerelement unterstützt die Lizenzierung, benötigt einen Lizenzschlüssel für die Erstellung des Steuerelements erfolgreich ausgeführt werden kann. Der Standardwert ist **NULL**.  
  
 `ppt`  
 Ein Zeiger auf eine **Punkt** Struktur, die die linke obere Ecke des Steuerelements enthält. Die Größe des Steuerelements wird bestimmt durch den Wert der *Psize*. Die `ppt` und *Psize* Werte sind eine optionale Methode dar, um die Größe und position Opf des Steuerelements.  
  
 *psize*  
 Ein Zeiger auf eine **Größe** Struktur, die die Größe des Steuerelements enthält. Die linke obere Ecke wird bestimmt durch den Wert des `ppt`. Die `ppt` und *Psize* Werte sind eine optionale Methode dar, um die Größe und position Opf des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Teilmenge der Windows `dwStyle` Flags werden von unterstützt `CreateControl`:  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort, wie gewöhnliche Fenster angezeigt werden soll.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktiviertes Fenster kann keine Eingabe vom Benutzer empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.  
  
- `WS_BORDER`Erstellt ein Fenster mit einem Rahmen thin-Zeile. Kann festgelegt werden, wenn Steuerelement eine BorderStyle-Eigenschaft besitzt.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen. Der Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern mithilfe der Richtung. Alle Steuerelemente, die mit definiert die **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Gruppe und startet die nächste Gruppe.  
  
- **WS_TABSTOP** gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Drücken die TAB-Taste den Tastaturfokus auf das nächste Steuerelement der ändert die **WS_TABSTOP** Stil.  
  
 Verwenden Sie die zweite Überladung zum Erstellen von Steuerelementen mit Standardgröße.  
  
##  <a name="destroycontrol"></a>COleControlSite::DestroyControl  
 Zerstört das `COleControlSite`-Objekt.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nach der abgeschlossen ist, wird das Objekt aus dem Speicher freigegeben, und alle Verweise auf das Objekt nicht mehr gültig sind.  
  
##  <a name="doverb"></a>COleControlSite::DoVerb  
 Führt das angegebene Verb.  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nVerb`  
 Gibt das Verb ausführen. Sie können eine der folgenden enthalten:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|-1|Sekundäre verb|(Keine)|  
|1|Zeigt das Objekt zur Bearbeitung.|`OLEIVERB_SHOW`|  
|-2|Bearbeitet das Element in einem separaten Fenster.|`OLEIVERB_OPEN`|  
|-3|Blendet das Objekt aus.|`OLEIVERB_HIDE`|  
|-4|Aktiviert eine-Steuerelement direkt.|`OLEIVERB_UIACTIVATE`|  
|-5|Aktiviert eine-Steuerelement direkt, ohne zusätzliche Elemente der Benutzeroberfläche.|**OLEIVERB_INPLACEACTIVATE**|  
|-7|Zeigen Sie die Eigenschaften des Steuerelements.|**OLEIVERB_PROPERTIES**|  
  
 `lpMsg`  
 Ein Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft direkt über des Steuerelements `IOleObject` Schnittstelle für das angegebene Verb aufzurufen. Wenn eine Ausnahme, als Ergebnis dieses Funktionsaufrufs ausgelöst wird ein `HRESULT` Fehlercode zurückgegeben.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="enabledsc"></a>COleControlSite::EnableDSC  
 Ermöglicht die Quelle für die Website des Steuerelements darstellt.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Hinweise  
 Vom Framework aufgerufen wird, aktivieren und initialisieren Sie Daten, die als Quelle für die Website des Steuerelements. Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten bereitzustellen.  
  
##  <a name="enablewindow"></a>COleControlSite::EnableWindow  
 Aktiviert oder deaktiviert die Maus- und Tastatureingaben an die Website des Steuerelements.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob zum Aktivieren oder deaktivieren das Fenster: **TRUE** ist Fenster Eingabe aktiviert ist, andernfalls werden **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Fenster zuvor deaktiviert war, andernfalls 0.  
  
##  <a name="freezeevents"></a>COleControlSite::FreezeEvents  
 Gibt an, ob die Steuerelementsite behandeln oder ignorieren von Ereignissen, die von einem Steuerelement ausgelöst wird.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parameter  
 `bFreeze`  
 Gibt an, ob die Steuerelementsite das Akzeptieren von Ereignissen beenden möchte. Wert ungleich NULL, wenn das Steuerelement keine Ereignisse akzeptiert; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bFreeze` ist **TRUE**, die Website des Steuerelements fordert das Steuerelement Fring Ereignisse zu beenden. Wenn `bFreeze` ist **FALSE**, die Website des Steuerelements fordert das Steuerelement zum Auslösen von Ereignissen fortgesetzt.  
  
> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, beendet das Auslösen von Ereignissen wird von der Website des Steuerelements angefordert. Auslösen von Ereignissen fortgesetzt werden kann, jedoch alle nachfolgenden Ereignisse durch die Website des Steuerelements ignoriert werden.  
  
##  <a name="getcontrolinfo"></a>COleControlSite::GetControlInfo  
 Ruft Informationen über mnemonisches und Tastaturverhalten eines Steuerelements.  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen werden gespeichert [COleControlSite::m_ctlInfo](#m_ctlinfo).  
  
##  <a name="getdefbtncode"></a>COleControlSite::GetDefBtnCode  
 Bestimmt, ob das Steuerelement eine Standardschaltfläche ist.  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Kann einer der folgenden Werte sein:  
  
- **DLGC_DEFPUSHBUTTON** -Steuerelement ist die Standardschaltfläche im Dialogfeld.  
  
- **DLGC_UNDEFPUSHBUTTON** Steuerelement ist nicht die Standardschaltfläche im Dialogfeld.  
  
- **0** Steuerelement ist keine Schaltfläche.  
  
##  <a name="getdlgctrlid"></a>COleControlSite::GetDlgCtrlID  
 Ruft den Bezeichner des Steuerelements ab.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Dialogfeld Element-ID des Steuerelements.  
  
##  <a name="geteventiid"></a>COleControlSite::GetEventIID  
 Ruft einen Zeiger auf das Steuerelement Standardschnittstelle Ereignis ab.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 `piid`  
 Ein Zeiger auf ein Schnittstellen-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0. Im Erfolgsfall `piid` die Schnittstellen-ID für die Standard-Ereignisschnittstelle des Steuerelements enthält.  
  
##  <a name="getexstyle"></a>COleControlSite::GetExStyle  
 Ruft die erweiterten Fensterstile.  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Steuerelementfenster des Stile erweitert.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Abrufen der regulären Stile [COleControlSite::GetStyle](#getstyle).  
  
##  <a name="getproperty"></a>COleControlSite::GetProperty  
 Ruft die durch angegebene Steuerelementeigenschaft `dwDispID`.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft, auf das Steuerelement standardmäßig gefunden `IDispatch` Schnittstelle abgerufen werden sollen.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft abgerufen werden soll. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvProp`  
 Die Adresse der Variablen, die den Wert der Eigenschaft angezeigt wird. Mit den vom angegebenen Typ übereinstimmen muss `vtProp`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird zurückgegeben, über `pvProp`.  
  
##  <a name="getstyle"></a>COleControlSite::GetStyle  
 Ruft die Formatvorlagen der Site für das Steuerelement ab.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fenster Stile.  
  
### <a name="remarks"></a>Hinweise  
 Eine Liste der möglichen Werte finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md). Um die erweiterten Stile, der die Website des Steuerelements abzurufen, rufen [COleControlSite::GetExStyle](#getexstyle).  
  
##  <a name="getwindowtext"></a>COleControlSite::GetWindowText  
 Ruft den aktuellen Text des Steuerelements ab.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Ein Verweis auf ein `CString` -Objekt, das den aktuellen Text des Steuerelements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement die vordefinierte Caption-Eigenschaft unterstützt, wird dieser Wert zurückgegeben. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird der Wert für die Text-Eigenschaft zurückgegeben.  
  
##  <a name="invokehelper"></a>COleControlSite::InvokeHelper  
 Ruft die Methode oder Eigenschaft, die durch angegebene `dwDispID`, in dem vom angegebenen Kontext `wFlags`.  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf des Steuerelements gefunden `IDispatch` Schnittstelle aufgerufen werden.  
  
 `wFlags`  
 Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben. Nach möglichen `wFlags` Werte finden Sie unter `IDispatch::Invoke` in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `vtRet`  
 Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Sie muss mit dem durch `vtRet`angegebenen Typ übereinstimmen.  
  
 `pbParamInfo`  
 Zeiger auf eine NULL-terminierte Zeichenfolge aus Bytes, die die Typen der Parameter angeben, die auf `pbParamInfo`folgen. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Variable Parameterliste aus den in `pbParamInfo`angegebenen Typen.  
  
### <a name="remarks"></a>Hinweise  
 Der `pbParamInfo` -Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter an. Die Variable Liste mit Argumenten wird durch... in der Syntax-Deklaration dargestellt.  
  
 Diese Funktion konvertiert die Parameter **VARIANTARG** Werte, und ruft anschließend die **IDispatch:: Invoke** -Methode des Steuerelements. Wenn der Aufruf von **IDispatch:: Invoke** fehlschlägt, wird diese Funktion eine Ausnahme ausgelöst. Wenn durch der Statuscode zurückgegeben **IDispatch:: Invoke** ist `DISP_E_EXCEPTION`, löst diese Funktion eine **COleDispatchException** Objekt ist, andernfalls löst eine `COleException`.  
  
##  <a name="invokehelperv"></a>COleControlSite::InvokeHelperV  
 Ruft die Methode oder Eigenschaft, die durch angegebene `dwDispID`, in dem vom angegebenen Kontext `wFlags`.  
  
```  
virtual void InvokeHelperV(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
    va_list argList);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf des Steuerelements gefunden `IDispatch` Schnittstelle aufgerufen werden.  
  
 `wFlags`  
 Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben.  
  
 `vtRet`  
 Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Sie muss mit dem durch `vtRet`angegebenen Typ übereinstimmen.  
  
 `pbParamInfo`  
 Zeiger auf eine NULL-terminierte Zeichenfolge aus Bytes, die die Typen der Parameter angeben, die auf `pbParamInfo`folgen. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `argList`  
 Ein Zeiger auf eine Variable Argumentliste.  
  
### <a name="remarks"></a>Hinweise  
 Der `pbParamInfo` -Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter an. Zusätzliche Parameter für die Methode oder Eigenschaft aufgerufene mit übergeben werden können der *Va_list* Parameter.  
  
 Diese Funktion wird in der Regel aufgerufen, durch `COleControlSite::InvokeHelper`.  
  
##  <a name="isdefaultbutton"></a>COleControlSite::IsDefaultButton  
 Bestimmt, ob das Steuerelement die Standardschaltfläche ist.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement die Standardschaltfläche für das Fenster, andernfalls&0; (null).  
  
##  <a name="iswindowenabled"></a>COleControlSite::IsWindowEnabled  
 Bestimmt, ob die Website des Steuerelements aktiviert ist.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement aktiviert ist, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird aus vordefinierten des Steuerelements Enabled-Eigenschaft abgerufen.  
  
##  <a name="m_biswindowless"></a>COleControlSite::m_bIsWindowless  
 Bestimmt, ob das Objekt ein fensterloses Steuerelement ist.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ungleich NULL, wenn das Steuerelement kein Fenster besitzt, andernfalls&0; (null).  
  
##  <a name="m_ctlinfo"></a>COleControlSite::m_ctlInfo  
 Informationen wie Tastatureingaben vom Steuerelement behandelt wird.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen werden gespeichert, einem [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) Struktur.  
  
##  <a name="m_dweventsink"></a>COleControlSite::m_dwEventSink  
 Der Verbindungspunkt Cookie aus der Ereignissenke für das Steuerelement enthält.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>COleControlSite::m_dwMiscStatus  
 Enthält verschiedene Informationen über das Steuerelement.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_dwpropnotifysink"></a>COleControlSite::m_dwPropNotifySink  
 Enthält die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Cookie.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>COleControlSite::m_dwStyle  
 Enthält die Fensterstile des Steuerelements.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>COleControlSite::m_hWnd  
 Enthält die `HWND` des Steuerelements oder **NULL** Wenn das Steuerelement fensterlose ist.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>COleControlSite::m_iidEvents  
 Enthält die Schnittstellen-ID des Steuerelements Standard Ereignissenken-Schnittstelle.  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>COleControlSite::m_nID  
 Enthält das Steuerelement Dialogfeld Element-ID.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>COleControlSite::m_pActiveObject  
 Enthält die [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) Schnittstelle des Steuerelements.  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>COleControlSite::m_pCtrlCont  
 Enthält der Container des Steuerelements (des Formulars darstellt).  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>COleControlSite::m_pInPlaceObject  
 Enthält die `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) Schnittstelle des Steuerelements.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>COleControlSite::m_pObject  
 Enthält die **IOleObjectInterface** Schnittstelle des Steuerelements.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>COleControlSite::m_pWindowlessObject  
 Enthält die `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) Schnittstelle des Steuerelements.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>COleControlSite::m_pWndCtrl  
 Enthält einen Zeiger auf das `CWnd` -Objekt, das Steuerelement selbst darstellt.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>COleControlSite::m_rect  
 Enthält die Grenzen des Steuerelements relativ zum Fenster des Containers.  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>COleControlSite::ModifyStyle  
 Ändert die Formatvorlagen des Steuerelements.  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwRemove`  
 Die Formate aus der aktuellen Fensterstile entfernt werden soll.  
  
 `dwAdd`  
 Die Formate aus der aktuellen Fensterstile hinzugefügt werden.  
  
 `nFlags`  
 Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte finden Sie unter der [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Stile geändert werden, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement Stock Enabled-Eigenschaft wird entsprechend die Einstellung für geändert **WS_DISABLED**. Vordefinierte Rahmenart-Eigenschaft des Steuerelements wird entsprechend die angeforderten Einstellung für modifiziert `WS_BORDER`. Alle anderen Formate werden direkt an das Fensterhandle des Steuerelements angewendet, sofern vorhanden.  
  
 Ändert die Fensterstile des Steuerelements. Stile hinzugefügt oder entfernt werden können kombiniert werden, mit dem bitweisen OR-Operator (|). Finden Sie unter der [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Informationen zu den verfügbaren Fenster.  
  
 Wenn `nFlags` ungleich NULL ist, `ModifyStyle` wird die Win32-Funktion `SetWindowPos`, und zeichnet das Fenster durch Kombinieren von `nFlags` mit den folgenden vier Flags:  
  
- `SWP_NOSIZE`Behält die aktuelle Größe.  
  
- `SWP_NOMOVE`Behält die aktuelle Position.  
  
- `SWP_NOZORDER`Behält den aktuelle Z-Reihenfolge.  
  
- `SWP_NOACTIVATE`Das Fenster wird nicht aktiviert werden.  
  
 So ändern Sie ein Fenster des erweiterten Stile, rufen Sie [ModifyStyleEx](#modifystyleex).  
  
##  <a name="modifystyleex"></a>COleControlSite::ModifyStyleEx  
 Ändert die erweiterten Stile des Steuerelements.  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwRemove`  
 Die erweiterten Stile aus der aktuellen Fensterstile entfernt werden soll.  
  
 `dwAdd`  
 Die erweiterten Stile aus dem aktuellen Fensterstile hinzugefügt werden.  
  
 `nFlags`  
 Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte finden Sie unter der [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Stile geändert werden, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Vordefinierte Appearance-Eigenschaft des Steuerelements wird entsprechend die Einstellung für modifiziert **WS_EX_CLIENTEDGE**. Alle anderen erweiterten Fensterstile werden direkt auf Fensterhandle des Steuerelements angewendet, sofern vorhanden.  
  
 Ändert das Fenster Erweiterte Stile des Website-Steuerelements. Stile hinzugefügt oder entfernt werden können kombiniert werden, mit dem bitweisen OR-Operator (|). Finden Sie unter der [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Informationen zu den verfügbaren Fenster.  
  
 Wenn `nFlags` ungleich NULL ist, `ModifyStyleEx` wird die Win32-Funktion `SetWindowPos`, und zeichnet das Fenster durch Kombinieren von `nFlags` mit den folgenden vier Flags:  
  
- `SWP_NOSIZE`Behält die aktuelle Größe.  
  
- `SWP_NOMOVE`Behält die aktuelle Position.  
  
- `SWP_NOZORDER`Behält den aktuelle Z-Reihenfolge.  
  
- `SWP_NOACTIVATE`Das Fenster wird nicht aktiviert werden.  
  
 So ändern Sie ein Fenster des erweiterten Stile, rufen Sie [ModifyStyle](#modifystyle).  
  
##  <a name="movewindow"></a>COleControlSite::MoveWindow  
 Ändert die Position des Steuerelements.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die neue Position der linken Seite des Fensters.  
  
 *y*  
 Die neue Position des oberen Rand des Fensters.  
  
 `nWidth`  
 Die neue Breite des Fensters  
  
 `nHeight`  
 Die neue Höhe des Fensters.  
  
##  <a name="quickactivate"></a>COleControlSite::QuickActivate  
 Schnelle aktiviert das enthaltene Steuerelement.  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Website des Steuerelements aktiviert wurde, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, nur, wenn der Benutzer den Erstellungsprozess des Steuerelements außer Kraft gesetzt wird.  
  
 Die `IPersist*::Load` und `IPersist*::InitNew` Methoden aufgerufen werden, nachdem schnelle Aktivierung erfolgt. Das Steuerelement sollte alle Verbindungen zu senken des Containers während schnelle Aktivierung herstellen. Diese Verbindungen sind jedoch nicht live bis `IPersist*::Load` oder `IPersist*::InitNew` aufgerufen wurde.  
  
##  <a name="safesetproperty"></a>COleControlSite::SafeSetProperty  
 Legt die Steuerelementeigenschaft, die durch angegebene `dwDispID`.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf des Steuerelements gefunden `IDispatch` Schnittstelle festgelegt werden.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft festgelegt werden. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Ein einzelner Parameter des durch `vtProp`angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Im Gegensatz zu `SetProperty` und `SetPropertyV`, wenn ein Fehler auftritt (z. B. versucht, eine nicht vorhandene Eigenschaft festzulegen), wird keine Ausnahme ausgelöst.  
  
##  <a name="setdefaultbutton"></a>COleControlSite::SetDefaultButton  
 Legt das Steuerelement als Standardschaltfläche an.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `bDefault`  
 Wert ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden sollen; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement muss verfügen die **OLEMISC_ACTSLIKEBUTTON** Status-Bit festgelegt.  
  
##  <a name="setdlgctrlid"></a>COleControlSite::SetDlgCtrlID  
 Ändert den Wert der Dialogfeld-Element-ID des Steuerelements.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der neue Bezeichnerwert.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall item im vorherige Dialogfeld Bezeichner des Fensters; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfocus"></a>COleControlSite::SetFocus  
 Setzt den Fokus auf das Steuerelement.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>Parameter  
 *lpmsg*  
 Ein Zeiger auf eine [MSG-Struktur](../../mfc/reference/msg-structure1.md). Diese Struktur enthält das Windows-Meldung Auslösen der `SetFocus` Anforderung für das Steuerelement in die Site für das aktuelle Steuerelement enthalten sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Fenster, das zuvor den Fokus hatte.  
  
##  <a name="setproperty"></a>COleControlSite::SetProperty  
 Legt die Steuerelementeigenschaft, die durch angegebene `dwDispID`.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf des Steuerelements gefunden `IDispatch` Schnittstelle festgelegt werden.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft festgelegt werden. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Ein einzelner Parameter des durch `vtProp`angegebenen Typs.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetProperty` einen Fehler erkennt, wird eine Ausnahme ausgelöst.  
  
 Der Typ der Ausnahme wird durch den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode bestimmt. Wenn der Rückgabewert `DISP_E_EXCEPTION`, **COleDispatchExcpetion** ausgelöst wird; andernfalls eine `COleException`.  
  
##  <a name="setpropertyv"></a>COleControlSite::SetPropertyV  
 Legt die Steuerelementeigenschaft, die durch angegebene `dwDispID`.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf des Steuerelements gefunden `IDispatch` Schnittstelle festgelegt werden.  
  
 `vtProp`  
 Gibt den Typ der Eigenschaft festgelegt werden. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `argList`  
 Zeiger auf die Liste der Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Zusätzliche Parameter für die Methode oder Eigenschaft, die aufgerufen wird, können Passeed werden mithilfe der *Arg_list* Parameter. Wenn `SetProperty` einen Fehler erkennt, wird eine Ausnahme ausgelöst.  
  
 Der Typ der Ausnahme wird durch den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode bestimmt. Wenn der Rückgabewert `DISP_E_EXCEPTION`, **COleDispatchExcpetion** ausgelöst wird; andernfalls eine `COleException`.  
  
##  <a name="setwindowpos"></a>COleControlSite::SetWindowPos  
 Legt die Größe, Position und Z-Reihenfolge der Site für das Steuerelement.  
  
```  
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndInsertAfter`  
 Ein Zeiger auf das Fenster.  
  
 *x*  
 Die neue Position der linken Seite des Fensters.  
  
 *y*  
 Die neue Position des oberen Rand des Fensters.  
  
 `cx`  
 Die neue Breite des Fensters  
  
 `cy`  
 Die neue Höhe des Fensters.  
  
 `nFlags`  
 Gibt das Fenster Größe und Position von Flags. Mögliche Werte finden Sie im Abschnitt "Hinweise" [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich, andernfalls&0; (null).  
  
##  <a name="setwindowtext"></a>COleControlSite::SetWindowText  
 Legt den Text für die Website des Steuerelements fest.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die als den neuen Text für Titel oder Steuerelement verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion versucht zunächst, die vordefinierte Caption-Eigenschaft festgelegt. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird stattdessen die Text-Eigenschaft festgelegt.  
  
##  <a name="showwindow"></a>COleControlSite::ShowWindow  
 Legt Anzeigezustand des Fensters fest.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdShow`  
 Gibt an, wie die Website des Steuerelements angezeigt werden. Es muss einer der folgenden Werte sein:  
  
- **SW_HIDE** Blendet das Fenster aus und übergibt die Aktivierung zu einem anderen Fenster.  
  
- **SW_MINIMIZE** minimiert das Fenster, und das Fenster das obersten Ebene in der Liste des Systems aktiviert.  
  
- **SW_RESTORE** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert wird, wird es von Windows in ihrer ursprünglichen Größe und Position wiederhergestellt.  
  
- **SW_SHOW** wird das Fenster aktiviert und in seiner aktuellen Größe und Position angezeigt.  
  
- **SW_SHOWMAXIMIZED** wird das Fenster aktiviert und wird in Form eines maximierten Fensters angezeigt.  
  
- **SW_SHOWMINIMIZED** wird das Fenster aktiviert und wird als Symbol angezeigt.  
  
- **SW_SHOWMINNOACTIVE** zeigt das Fenster als Symbol an. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNA** zeigt das Fenster im aktuellen Zustand an. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNOACTIVATE** zeigt das Fenster in der letzten Größe und Position. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNORMAL** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert wird, wird es von Windows in ihrer ursprünglichen Größe und Position wiederhergestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Fenster bereits sichtbar war; 0, wenn zuvor Fenster ausgeblendetes.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)

