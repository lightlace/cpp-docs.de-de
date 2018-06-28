---
title: COleControlSite Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61544026f559e0c45cbd81735e76203a088d2d6b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040872"
---
# <a name="colecontrolsite-class"></a>COleControlSite-Klasse
Stellt Unterstützung für benutzerdefinierte clientseitige Steuerelement-Schnittstellen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|Erstellt ein `COleControlSite`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Die Standardeigenschaft des gehosteten Steuerelements bindet an eine Datenquelle.|  
|[COleControlSite::BindProperty](#bindproperty)|Eine Eigenschaft des gehosteten Steuerelements bindet an eine Datenquelle.|  
|[COleControlSite::CreateControl](#createcontrol)|Erstellt ein gehostetes ActiveX-Steuerelement.|  
|[COleControlSite::DestroyControl](#destroycontrol)|Zerstört das gehostete Steuerelement.|  
|[COleControlSite::DoVerb](#doverb)|Führt ein bestimmtes Verb des gehosteten Steuerelements.|  
|[COleControlSite::EnableDSC](#enabledsc)|Ermöglicht die Daten, die als Quelle für eine Website des Steuerelements.|  
|[COleControlSite::EnableWindow](#enablewindow)|Können die Website des Steuerelements.|  
|[COleControlSite::FreezeEvents](#freezeevents)|Gibt an, ob die Steuerelementsite Ereignisse akzeptiert.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Ruft den Standardcode für die Schaltfläche für das gehostete Steuerelement ab.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Ruft die ID des Steuerelements ab.|  
|[COleControlSite::GetEventIID](#geteventiid)|Ruft die ID einer Ereignis-Schnittstelle für einen gehosteten Steuerelements ab.|  
|[COleControlSite::GetExStyle](#getexstyle)|Ruft die erweiterten Stile für die Website des Steuerelements ab.|  
|[COleControlSite::GetProperty](#getproperty)|Ruft eine bestimmte Eigenschaft des gehosteten Steuerelements ab.|  
|[COleControlSite::GetStyle](#getstyle)|Ruft die Stile für die Website des Steuerelements ab.|  
|[COleControlSite::GetWindowText](#getwindowtext)|Ruft den Text des gehosteten Steuerelements ab.|  
|[COleControlSite::InvokeHelper](#invokehelper)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements mit einer Liste variabler Argumente.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Bestimmt, ob das Steuerelement die Standardschaltfläche im Fenster ist.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Überprüft den Status angezeigten, der die Website des Steuerelements.|  
|[COleControlSite::ModifyStyle](#modifystyle)|Ändert die aktuelle erweiterte Formate, der die Website des Steuerelements.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Ändert die aktuelle Stile für die Website des Steuerelements an.|  
|[COleControlSite::MoveWindow](#movewindow)|Ändert die Position von der Website des Steuerelements.|  
|[COleControlSite::QuickActivate](#quickactivate)|Quick aktiviert das gehostete Steuerelement.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|Legt eine Eigenschaft oder Methode des Steuerelements ohne Wahrscheinlichkeit, dass eine Ausnahme ausgelöst.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Legt die Standardschaltfläche im Fenster an.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Ruft die ID des Steuerelements ab.|  
|[COleControlSite::SetFocus](#setfocus)|Legt den Fokus auf die Website des Steuerelements fest.|  
|[COleControlSite::SetProperty](#setproperty)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements fest.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements mit einer Liste variabler Argumente an.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|Legt die Position von der Website des Steuerelements fest.|  
|[COleControlSite::SetWindowText](#setwindowtext)|Legt den Text des gehosteten Steuerelements fest.|  
|[COleControlSite::ShowWindow](#showwindow)|Anzeigen oder Ausblenden der Website des Steuerelements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Ruft Tastaturinformationen und mnemonischen Codes des gehosteten Steuerelements ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Bestimmt, ob das gehostete Steuerelement ein fensterloses Steuerelement ist.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Enthält Informationen über die Tastatur, die für das Steuerelement behandeln.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Das Cookie des Verbindungspunkts des Steuerelements.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Die verschiedenen Status des gehosteten Steuerelements.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Die `IPropertyNotifySink` Cookie des Steuerelements.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|Die Stile des gehosteten Steuerelements.|  
|[COleControlSite::m_hWnd](#m_hwnd)|Das Handle für die Website des Steuerelements.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|Die ID der Ereignisschnittstelle des gehosteten Steuerelements.|  
|[COleControlSite::m_nID](#m_nid)|Die ID des gehosteten Steuerelements.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Ein Zeiger auf die `IOleInPlaceActiveObject` Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Der Container des gehosteten Steuerelements.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Ein Zeiger auf die `IOleInPlaceObject` Objekt des gehosteten Steuerelements.|  
|[COleControlSite::m_pObject](#m_pobject)|Ein Zeiger auf die `IOleObjectInterface` Schnittstelle des Steuerelements.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Ein Zeiger auf die `IOleInPlaceObjectWindowless` Schnittstelle des Steuerelements.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Ein Zeiger auf das Fensterobjekt des gehosteten Steuerelements.|  
|[COleControlSite::m_rect](#m_rect)|Die Dimensionen für die Website des Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Unterstützung ist das primäre Mittel, mit dem ein eingebettetes ActiveX-Steuerelement ruft Informationen über den Speicherort und den Umfang der seines Standorts anzeigen, seinen Moniker, seine Benutzeroberfläche, die ambient-Eigenschaften und anderen Ressourcen, die durch den Container bereitgestellt ab. `COleControlSite` vollständig implementiert die [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), `IBoundObjectSite`, `INotifyDBEvents`, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) Schnittstellen. Darüber hinaus wird auch die IDispatch-Schnittstelle (Bereitstellen von Unterstützung für Umgebungseigenschaften und Ereignissenken) implementiert.  
  
 Um eine Website mit ActiveX-Steuerelement erstellen `COleControlSite`, leiten Sie eine Klasse von `COleControlSite`. In Ihrem `CWnd`-abgeleitete Klasse für den Container (z. B. ein Dialogfeld) überschreiben die **CWnd::CreateControlSite** Funktion.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 Bindet das aufrufende Objekt standardmäßige einfache gebundene Eigenschaft gemäß der Markierung in der Typbibliothek, auf den zugrunde liegenden Cursor, der von der Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen-Steuerelements definiert ist.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Gibt an, die **DISPID** einer Eigenschaft in einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 *vtProp*  
 Gibt den Typ der zu bindenden Eigenschaft – z. B. **"VT_BSTR"**, **VT_VARIANT**und so weiter.  
  
 *szFieldName*  
 Gibt den Namen der Spalte, in den Cursor zur Verfügung gestellt, von dem Datenquellen-Steuerelement, an dem die Eigenschaft gebunden wird.  
  
 *pDSCWnd*  
 Ein Zeiger auf die `CWnd`-abgeleitete Objekt, das die Datenquellen-Steuerelement hostet, der die Eigenschaft gebunden werden.  
  
### <a name="remarks"></a>Hinweise  
 Die `CWnd` Objekt auf dem Sie mit dieser Funktion muss ein datengebundenes Steuerelement sein.  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 Bindet das aufrufende Objekt einfache gebundene Eigenschaft gemäß der Markierung in der Typbibliothek, auf den zugrunde liegenden Cursor, der von der Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen-Steuerelements definiert ist.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispId*  
 Gibt an, die **DISPID** einer Eigenschaft in einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.  
  
 *pWndDSC*  
 Ein Zeiger auf die `CWnd`-abgeleitete Objekt, das die Datenquellen-Steuerelement hostet, der die Eigenschaft gebunden werden.  
  
### <a name="remarks"></a>Hinweise  
 Die `CWnd` Objekt auf dem Sie mit dieser Funktion muss ein datengebundenes Steuerelement sein.  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 Erstellt ein neues `COleControlSite`-Objekt.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parameter  
 *pCtrlCont*  
 Ein Zeiger auf das Steuerelement-Container (die das Fenster, das Hosten des Steuerelements des AtiveX darstellt).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem Sie die [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) Funktion. Weitere Informationen zum Anpassen der Erstellung von Containern finden Sie unter [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
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
 *pWndCtrl*  
 Ein Zeiger auf das Window-Objekt, das das Steuerelement darstellt.  
  
 *clsid*  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 *lpszWindowName*  
 Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Eigenschaft für die Winodw Beschriftung oder den Text fest, (sofern vorhanden).  
  
 *dwStyle*  
 Windows-Formate. Die verfügbaren Formate sind aufgeführt, unter der **"Hinweise"** Abschnitt.  
  
 *Rect*  
 Gibt die Größe und Position des Steuerelements. Es kann es sich um eine `CRect` Objekt oder eine `RECT` Struktur.  
  
 *nID*  
 Gibt an, das Steuerelement untergeordnete Fenster-ID.  
  
 *pPersist*  
 Ein Zeiger auf eine `CFile` , die den dauerhaften Status für das Steuerelement enthält. Der Standardwert ist **NULL**, gibt an, dass das Steuerelement selbst initialisiert, ohne den Zustand aus dem persistenten Speicher wiederherzustellen. Wenn dies nicht der **NULL**, es muss ein Zeiger auf eine `CFile`-abgeleitetes Objekt mit persistenten Daten des Steuerelements in Form von einem Stream oder einem Speicher. Diese Daten können in einer vorherigen Aktivierung des Clients gespeichert worden sein. Die `CFile` können andere Daten enthalten, aber benötigen die Lese-/ Schreibzugriff Zeiger auf das erste Byte der Daten festgelegt werden, zum Zeitpunkt des Aufrufs von `CreateControl`.  
  
 *bStorage*  
 Gibt an, ob die Daten in *pPersist* interpretiert werden soll, als `IStorage` oder `IStream` Daten. Wenn die Daten in *pPersist* ist ein Speicher *bStorage* muss **"true"**. Wenn die Daten in *pPersist* ist ein Datenstrom *bStorage* muss **"false"**. Der Standardwert ist **"false"**.  
  
 *bstrLicKey*  
 Dies ist optional Lizenz Schlüsseldaten. Diese Daten ist erforderlich, nur für das Erstellen von Steuerelementen, die einen Laufzeit-Lizenzschlüssel erfordern. Wenn das Steuerelement Lizenzierung unterstützt, müssen Sie einen Lizenzschlüssel für die Erstellung des Steuerelements erfolgreich bereitstellen. Der Standardwert ist **NULL**.  
  
 *PPT*  
 Ein Zeiger auf eine **Punkt** Struktur, die der oberen linken Ecke des Steuerelements enthält. Die Größe des Steuerelements wird bestimmt durch den Wert des *Psize*. Die *ppt* und *Psize* Werte sind eine optionale Methode, um die Größe anzugeben, und positionieren Sie Opf des Steuerelements.  
  
 *psize*  
 Ein Zeiger auf eine **Größe** Struktur, die die Größe des Steuerelements enthält. Die oberen linken Ecke richtet sich nach dem Wert der *ppt*. Die *ppt* und *Psize* Werte sind eine optionale Methode, um die Größe anzugeben, und positionieren Sie Opf des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Teilmenge der Windows *DwStyle* Flags werden unterstützt, indem Sie `CreateControl`:  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort wie gewöhnliche Fenster sichtbar sein soll.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktivierter Fenster kann nicht vom Benutzer Eingaben zu empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.  
  
- **WS_BORDER** erstellt ein Fenster mit einem Rahmen thin-Zeile. Kann festgelegt werden, wenn Steuerelement eine Rahmenart-Eigenschaft verfügt.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen. Die Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern, indem die Richtungstasten verwenden. Alle Steuerelemente, die definiert, mit der **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Gruppe und startet die nächste Gruppe.  
  
- **WS_TABSTOP** gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Drücken die TAB-Taste den Tastaturfokus auf das nächste Steuerelement der ändert die **WS_TABSTOP** Stil.  
  
 Verwenden Sie die zweite Überladung, um die Standardgröße Steuerelemente zu erstellen.  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 Zerstört das `COleControlSite`-Objekt.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sobald Sie abgeschlossen ist, wird das Objekt aus dem Arbeitsspeicher freigegeben, und alle Verweise auf das Objekt nicht mehr gültig sind.  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 Führt das angegebene Verb.  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nVerb*  
 Gibt das Verb ausgeführt. Sie können eine der folgenden enthalten:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|-1|Sekundäre verb|(Keine)|  
|1|Zeigt das Objekt zur Bearbeitung.|`OLEIVERB_SHOW`|  
|-2|Das Element in einem separaten Fenster bearbeitet wird.|`OLEIVERB_OPEN`|  
|-3|Blendet das Objekt aus.|`OLEIVERB_HIDE`|  
|-4|Aktiviert ein Steuerelement platzieren.|`OLEIVERB_UIACTIVATE`|  
|-5|Aktiviert eine Steuerelement direkt ohne zusätzliche Elemente der Benutzeroberfläche.|`OLEIVERB_INPLACEACTIVATE`|  
|-7|Anzeigen der Eigenschaften des Steuerelements an.|`OLEIVERB_PROPERTIES`|  
  
 *lpMsg*  
 Ein Zeiger auf die Nachricht, die zu aktivierenden Elements verursacht hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist direkt über des Steuerelements ruft `IOleObject` Schnittstelle, um das angegebene Verb ausführen. Wenn eine Ausnahme, als Ergebnis dieses Aufrufs Funktion ausgelöst wird eine `HRESULT` Fehlercode zurückgegeben.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 Ermöglicht die Daten, die als Quelle für die Website des Steuerelements.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird aufgerufen, durch das Framework zu aktivieren und initialisieren Sie die Daten, die als Quelle für die Website des Steuerelements. Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten bereitzustellen.  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 Aktiviert oder deaktiviert die Maus- und Tastatureingaben auf die Website des Steuerelements.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *bAktivieren*  
 Gibt an, ob aktivieren oder deaktivieren das Fenster: **"true"** wenn Fenster Eingabe verwendet wird, andernfalls aktiviert werden **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Fenster zuvor deaktiviert war, andernfalls 0.  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 Gibt an, ob die Website des Steuerelements behandeln oder ignorieren die Ereignisse, die von einem Steuerelement ausgelöst wird.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parameter  
 *bFreeze*  
 Gibt an, ob die Steuerelementsite das Akzeptieren von Ereignissen beenden möchte. Wert ungleich NULL, wenn das Steuerelement keine Ereignisse akzeptiert; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bFreeze* ist **"true"**, die Website des Steuerelements fordert das Steuerelement Fring Ereignisse zu beenden. Wenn *bFreeze* ist **"false"**, die Website des Steuerelements fordert das Steuerelement zum Auslösen von Ereignissen fortgesetzt.  
  
> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um die Ereignisse auslösen, wenn von der Website des Steuerelements angefordert beendet. Auslösen von Ereignissen fortgesetzt werden kann, jedoch alle nachfolgenden Ereignisse durch die Website des Steuerelements ignoriert werden.  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 Ruft Informationen zu mnemonisches und Tastaturverhalten des Steuerelements ab.  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen werden gespeichert, [COleControlSite::m_ctlInfo](#m_ctlinfo).  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 Bestimmt, ob das Steuerelement eine Standardschaltfläche ist.  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Kann einer der folgenden Werte sein:  
  
- **DLGC_DEFPUSHBUTTON** Steuerelement ist die Standardschaltfläche im Dialogfeld "".  
  
- **DLGC_UNDEFPUSHBUTTON** Steuerelement ist nicht die Standardschaltfläche im Dialogfeld "".  
  
- **0** -Steuerelement ist nicht mit einer Schaltfläche.  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 Ruft die ID des Steuerelements ab.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Dialogfeld-Element-ID des Steuerelements.  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 Ruft einen Zeiger auf das Steuerelement Ereignis Standardschnittstelle ab.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 *piid*  
 Ein Zeiger auf eine Schnittstellen-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0. Im Erfolgsfall *Piid* enthält die Schnittstellen-ID für das Steuerelement Standardschnittstelle-Ereignis.  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 Ruft die erweiterten Fensterstile ab.  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fenster des Steuerelements des Stile erweitert.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Abrufen der regulären Stile [COleControlSite::GetStyle](#getstyle).  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 Ruft die Steuerelementeigenschaft gemäß *DwDispID*.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft, finden Sie auf das Steuerelement standardmäßig `IDispatch` Schnittstelle abgerufen werden sollen.  
  
 *vtProp*  
 Gibt den Typ der Eigenschaft abgerufen werden sollen. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvProp*  
 Die Adresse der Variablen, die den Wert der Eigenschaft zugewiesen wird. Mit den vom angegebenen Typ übereinstimmen muss *VtProp*.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird zurückgegeben, durch *PvProp*.  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 Ruft die Stile für die Website des Steuerelements ab.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fenster Stile.  
  
### <a name="remarks"></a>Hinweise  
 Eine Liste der möglichen Werte finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Um die erweiterten Stile für die Website des Steuerelements abzurufen, rufen Sie [COleControlSite::GetExStyle](#getexstyle).  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 Ruft den aktuellen Text des Steuerelements ab.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *str*  
 Ein Verweis auf ein `CString` Objekt, das den aktuellen Text des Steuerelements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement die vordefinierte Caption-Eigenschaft unterstützt, wird dieser Wert zurückgegeben. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird der Wert für die Text-Eigenschaft zurückgegeben.  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 Ruft die Methode oder Eigenschaft gemäß *DwDispID*, in dem durch angegebenen Kontext *wFlags*.  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, um aufgerufen werden.  
  
 *wFlags*  
 Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben. Nach möglichen *wFlags* -Werte finden Sie in `IDispatch::Invoke` im Windows SDK.  
  
 *vtRet*  
 Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Mit den vom angegebenen Typ übereinstimmen muss *VtRet*.  
  
 *pbParamInfo*  
 Zeiger auf eine Null-terminierte Zeichenfolge von Bytes, die die Typen der folgenden Parameter angeben *PbParamInfo*. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Variable Parameterliste, der in der angegebenen Typen *PbParamInfo*.  
  
### <a name="remarks"></a>Hinweise  
 Die *PbParamInfo* Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter. Die Variable Argumentliste wird in der Deklaration Syntax... durch dargestellt.  
  
 Diese Funktion konvertiert die Parameter für **VARIANTARG** Werte und ruft anschließend die `IDispatch::Invoke` Methode für das Steuerelement. Wenn der Aufruf von `IDispatch::Invoke` ein Fehler auftritt, wird diese Funktion eine Ausnahme ausgelöst. Wenn der zurückgegebene Statuscode von `IDispatch::Invoke` ist `DISP_E_EXCEPTION`, diese Funktion löst eine `COleDispatchException` Objekt ist, andernfalls löst eine `COleException`.  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 Ruft die Methode oder Eigenschaft gemäß *DwDispID*, in dem durch angegebenen Kontext *wFlags*.  
  
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
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, um aufgerufen werden.  
  
 *wFlags*  
 Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben.  
  
 *vtRet*  
 Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Mit den vom angegebenen Typ übereinstimmen muss *VtRet*.  
  
 *pbParamInfo*  
 Zeiger auf eine Null-terminierte Zeichenfolge von Bytes, die die Typen der folgenden Parameter angeben *PbParamInfo*. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Ein Zeiger auf eine Variable Argumentliste.  
  
### <a name="remarks"></a>Hinweise  
 Die *PbParamInfo* Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter. Zusätzliche Parameter für die Methode oder Eigenschaft aufgerufen können übergeben werden, mithilfe der *Va_list* Parameter.  
  
 In der Regel wird diese Funktion aufgerufen, indem `COleControlSite::InvokeHelper`.  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 Bestimmt, ob das Steuerelement die Standardschaltfläche ist.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement die Standardschaltfläche für das Fenster, andernfalls 0 (null).  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 Bestimmt, ob die Website des Steuerelements aktiviert ist.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement aktiviert ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird aus der Systemeigenschaft für das Steuerelement aktiviert abgerufen.  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 Bestimmt, ob das Objekt ein fensterloses Steuerelement ist.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ungleich NULL, wenn das Steuerelement kein Fenster hat, andernfalls 0.  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 Informationen zum wie Tastatureingaben vom Steuerelement behandelt wird.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen werden gespeichert, einem [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) Struktur.  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 Der Verbindungspunkt-Cookie aus der Ereignissenke für das Steuerelement enthält.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 Enthält verschiedene Informationen über das Steuerelement an.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)im Windows SDK.  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 Enthält die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Cookie.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 Enthält die Fensterstile des Steuerelements an.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 Enthält die `HWND` des Steuerelements oder **NULL** Wenn das Steuerelement fensterlose ist.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 Enthält die Schnittstellen-ID des Steuerelements Standard Ereignissenken-Schnittstelle.  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 Enthält das Steuerelement Dialogfeld-ID auf.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 Enthält die [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) Schnittstelle des Steuerelements.  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 Enthält das Steuerelement-Container (das Formular darstellt).  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 Enthält die `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) Schnittstelle des Steuerelements.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 Enthält die **IOleObjectInterface** Schnittstelle des Steuerelements.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 Enthält die `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) Schnittstelle des Steuerelements.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 Enthält einen Zeiger auf die `CWnd` -Objekt, das das Steuerelement selbst darstellt.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 Enthält die Grenzen des Steuerelements relativ zum Fenster des Containers an.  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle  
 Ändert die Stile des Steuerelements an.  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwRemove*  
 Die Formate aus der aktuellen Fensterstile entfernt werden soll.  
  
 *dwAdd*  
 Die Formate aus der aktuellen Fensterstile hinzugefügt werden.  
  
 *nFlags*  
 Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte finden Sie unter der [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Funktion im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Stile geändert werden, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement Stock Enabled-Eigenschaft wird entsprechend der Einstellung für modifiziert **WS_DISABLED**. Stock Border-Style-Eigenschaft des Steuerelements wird entsprechend die angeforderte Einstellung für modifiziert `WS_BORDER`. Alle anderen Formate werden direkt an das Steuerelement Fensterhandle angewendet, sofern eins vorhanden ist.  
  
 Ändert die Fensterstile des Steuerelements an. Stile hinzugefügt oder entfernt werden soll, können mit den bitweisen OR-Operator kombiniert werden ( &#124; ) Operator. Finden Sie unter der [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) -Funktion in das Windows SDK für Informationen zu den verfügbaren Fensterstile.  
  
 Wenn *nFlags* ungleich NULL ist `ModifyStyle` Ruft die Win32-Funktion `SetWindowPos`, und zeichnet das Fenster kombinierten *nFlags* mit den folgenden vier Flags:  
  
- `SWP_NOSIZE` Behält die aktuelle Größe an.  
  
- `SWP_NOMOVE` Behält die aktuelle Position.  
  
- `SWP_NOZORDER` Behält den aktuelle Z-Reihenfolge an.  
  
- `SWP_NOACTIVATE` Das Fenster aktiviert nicht.  
  
 So ändern Sie ein Fenster des erweiterten Stile, rufen Sie [ModifyStyleEx](#modifystyleex).  
  
##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx  
 Ändert die erweiterten Stile des Steuerelements an.  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwRemove*  
 Die erweiterten Stile aus der aktuellen Fensterstile entfernt werden soll.  
  
 *dwAdd*  
 Die erweiterten Stile aus dem aktuellen Fensterstile hinzugefügt werden.  
  
 *nFlags*  
 Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte finden Sie unter der [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Funktion im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Stile geändert werden, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement Systemeigenschaft Darstellung wird entsprechend der Einstellung für modifiziert **WS_EX_CLIENTEDGE**. Alle anderen erweiterten Fensterstile werden direkt an das Fensterhandle des Steuerelements angewendet, sofern eins vorhanden ist.  
  
 Ändert das Fenster Stile des Steuerelementobjekts Standort erweitert. Stile hinzugefügt oder entfernt werden soll, können mit den bitweisen OR-Operator kombiniert werden ( &#124; ) Operator. Finden Sie unter der [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) -Funktion in das Windows SDK für Informationen zu den verfügbaren Fensterstile.  
  
 Wenn *nFlags* ungleich NULL ist `ModifyStyleEx` Ruft die Win32-Funktion `SetWindowPos`, und zeichnet das Fenster kombinierten *nFlags* mit den folgenden vier Flags:  
  
- `SWP_NOSIZE` Behält die aktuelle Größe an.  
  
- `SWP_NOMOVE` Behält die aktuelle Position.  
  
- `SWP_NOZORDER` Behält den aktuelle Z-Reihenfolge an.  
  
- `SWP_NOACTIVATE` Das Fenster aktiviert nicht.  
  
 So ändern Sie ein Fenster des erweiterten Stile, rufen Sie [ModifyStyle](#modifystyle).  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 Ändert die Position des Steuerelements.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die neue Position der linken Seite des Fensters.  
  
 *y*  
 Die neue Position des oberen Rand des Fensters.  
  
 *nWidth*  
 Die neue Breite des Fensters  
  
 *nHeight*  
 Die neue Höhe des Fensters.  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 Quick aktiviert das enthaltene Steuerelement.  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Website des Steuerelements aktiviert wurde, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, nur dann, wenn der Benutzer den Erstellungsprozess des Steuerelements außer Kraft gesetzt wird.  
  
 Die `IPersist*::Load` und `IPersist*::InitNew` Methoden aufgerufen werden, nachdem unverzügliche Aktivierung erfolgt. Das Steuerelement sollte dessen Verbindungen zu senken des Containers während unverzügliche Aktivierung herstellen. Diese Verbindungen sind jedoch nicht live bis `IPersist*::Load` oder `IPersist*::InitNew` aufgerufen wurde.  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 Legt die Steuerelementeigenschaft gemäß *DwDispID*.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, um festgelegt werden.  
  
 *vtProp*  
 Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Einen einzelnen Parameter des Typs gemäß *VtProp*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Im Gegensatz zu `SetProperty` und `SetPropertyV`, wenn ein Fehler aufgetreten ist (z. B. versucht, eine nicht vorhandene Eigenschaft festzulegen.), wird keine Ausnahme ausgelöst.  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 Legt das Steuerelement als Standardschaltfläche an.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>Parameter  
 *bStandardstufe*  
 Wert ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden sollte; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement benötigen die **OLEMISC_ACTSLIKEBUTTON** Status-Bit festgelegt ist.  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 Ändert den Wert der Dialogfeld-Element-ID des Steuerelements.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der neue Bezeichnerwert.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall Element im vorherige Dialogfeld Bezeichner des Fensters; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 Legt den Fokus auf das Steuerelement.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>Parameter  
 *lpmsg*  
 Ein Zeiger auf eine [MSG-Struktur](../../mfc/reference/msg-structure1.md). Diese Struktur enthält das Windows-Meldung Auslösen der `SetFocus` Anforderung für das Steuerelement in die aktuelle Website des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Fenster, das zuvor den Fokus hat.  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 Legt die Steuerelementeigenschaft gemäß *DwDispID*.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, um festgelegt werden.  
  
 *vtProp*  
 Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Einen einzelnen Parameter des Typs gemäß *VtProp*.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetProperty` prüfpunkterstellung einen Fehler erkennt, wird eine Ausnahme ausgelöst.  
  
 Der Typ der Ausnahme richtet sich nach den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, `COleDispatchExcpetion` ausgelöst wird andernfalls eine `COleException`.  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 Legt die Steuerelementeigenschaft gemäß *DwDispID*.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDispID*  
 Identifiziert die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, um festgelegt werden.  
  
 *vtProp*  
 Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Zeiger auf die Liste der Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Zusätzliche Parameter für die Methode oder Eigenschaft, die aufgerufen wird, können Passeed werden mithilfe der *Arg_list* Parameter. Wenn `SetProperty` prüfpunkterstellung einen Fehler erkennt, wird eine Ausnahme ausgelöst.  
  
 Der Typ der Ausnahme richtet sich nach den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, `COleDispatchExcpetion` ausgelöst wird andernfalls eine `COleException`.  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 Legt die Größe, Position und Z-Reihenfolge von der Website des Steuerelements.  
  
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
 *pWndInsertAfter*  
 Ein Zeiger auf das Fenster.  
  
 *w*  
 Die neue Position der linken Seite des Fensters.  
  
 *y*  
 Die neue Position des oberen Rand des Fensters.  
  
 *CX*  
 Die neue Breite des Fensters  
  
 *CY*  
 Die neue Höhe des Fensters.  
  
 *nFlags*  
 Gibt an, das Fenster größenanpassung und Positionierung von Flags. Mögliche Werte finden Sie im Abschnitt "Hinweise" [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich, andernfalls 0.  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 Legt den Text für die Website des Steuerelements fest.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszString*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge als den neuen Text für Titel oder Steuerelement verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion versucht zunächst, die vordefinierte Caption-Eigenschaft festgelegt. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird stattdessen die Text-Eigenschaft festgelegt.  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 Legt das Fenster Anzeigestatus fest.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Parameter  
 *nCmdShow*  
 Gibt an, wie die Website des Steuerelements angezeigt werden. Es muss eine der folgenden Werte sein:  
  
- **SW_HIDE** Blendet das Fenster aus und übergibt die Aktivierung zu einem anderen Fenster.  
  
- **SW_MINIMIZE** minimiert das Fenster, und die Fenster das obersten Ebene in der Liste für das System aktiviert.  
  
- **SW_RESTORE** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, wird es von Windows zu seiner ursprünglichen Größe und Position wiederhergestellt.  
  
- **SW_SHOW** aktiviert das Fenster, und zeigt es in seiner aktuellen Größe und Position.  
  
- **SW_SHOWMAXIMIZED** aktiviert das Fenster, und zeigt ihn als eines maximierten Fensters.  
  
- **SW_SHOWMINIMIZED** aktiviert das Fenster, und zeigt ihn als ein Symbol.  
  
- **SW_SHOWMINNOACTIVE** zeigt das Fenster als Symbol an. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNA** zeigt das Fenster in seinem aktuellen Status an. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNOACTIVATE** zeigt das Fenster in ihrer aktuellen Größe und Position. Das Fenster, das derzeit aktiv ist, bleibt aktiv.  
  
- **SW_SHOWNORMAL** aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, wird es von Windows zu seiner ursprünglichen Größe und Position wiederhergestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Fenster bereits sichtbar war; 0, wenn das Fenster bereits ausgeblendet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)
