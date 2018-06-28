---
title: COleControlContainer Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
dev_langs:
- C++
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b59a1ef4d1a70063c15b7de41963abc60dd341a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041928"
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer-Klasse
Dient als Steuerelementcontainer für ActiveX-Steuerelemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Erstellt ein `COleControlContainer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Erstellt eine Steuerelement-Website, von dem Container gehostet wird.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Informiert alle gehosteten Steuerelemente, die Ambiente-Eigenschaft geändert wurde.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Ändert den angegebenen Schaltflächen-Steuerelement.|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Wählt das angegebene Optionsfeld einer Gruppe an.|  
|[COleControlContainer::CreateControl](#createcontrol)|Erstellt ein gehostetes ActiveX-Steuerelement.|  
|[COleControlContainer::CreateOleFont](#createolefont)|Erstellt eine OLE-Schriftart.|  
|[COleControlContainer::FindItem](#finditem)|Gibt die benutzerdefinierte Website des angegebenen Steuerelements zurück.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Bestimmt, ob die Steuerelementsite Ereignisse akzeptiert.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Ruft die angegebene ambient-Eigenschaft ab.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Ruft das angegebene Dialogfeldsteuerelement ab.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Ruft den Wert des Steuerelements angegebenen Dialogfeld ab.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Ruft die Beschriftung des Steuerelements angegebenen Dialogfeld ab.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Bestimmt, ob der Container WM_SETFOCUS Nachrichten verarbeitet.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Verarbeitet die Nachrichten an ein fensterloses Steuerelement gesendet.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Bestimmt den Status der angegebenen Schaltfläche.|  
|[COleControlContainer::OnPaint](#onpaint)|Wird aufgerufen, um einen Teil des Containers neu gezeichnet werden.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Wird aufgerufen, wenn ein Steuerelement handelt, direktes aktiviert werden soll.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Wird aufgerufen, wenn ein Steuerelement ist deaktiviert werden soll.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Vom Framework aufgerufen, wenn von einem untergeordneten Fenster Scroll Nachrichten empfangen werden.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Sendet eine Nachricht an das angegebene Steuerelement.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Legt den Wert des angegebenen Steuerelements.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Legt den Text des angegebenen Steuerelements fest.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Die Hintergrundfarbe des Containers.|  
|[COleControlContainer::m_crFore](#m_crfore)|Die Vordergrundfarbe des Containers.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Eine Liste der unterstützten Steuerelement Standorte.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Die Anzahl der gehosteten Fensterlose Steuerelemente.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Ein Zeiger auf die OLE-Schriftart für die Website des benutzerdefinierten Steuerelements.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Ein Zeiger auf die Website des Capture-Steuerelements.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Ein Zeiger auf das Steuerelement, das aktuell den Eingabefokus besitzt.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Ein Zeiger auf das Steuerelement, das derzeit aktiviert ist.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Ein Zeiger auf das Fenster, den Steuerelementcontainer implementieren.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Der Siteübersicht.|  
  
## <a name="remarks"></a>Hinweise  
 Dies erfolgt durch die Unterstützung für einen oder mehrere ActiveX-Steuerelement-Standorte (durch implementiert `COleControlSite`). `COleControlContainer` vollständig implementiert die [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) und [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) Schnittstellen, sodass enthaltenen ActiveX-Steuerelementen zur Erfüllung ihrer Qualifikationen als direktes Elemente.  
  
 Diese Klasse dient in der Regel in Verbindung mit `COccManager` und `COleControlSite` zum Implementieren eines benutzerdefinierten ActiveX-Steuerelementcontainers mit benutzerdefinierten Websites für ein oder mehrere ActiveX-Steuerelemente.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite  
 Wird aufgerufen, durch das Framework zum Erstellen und Anfügen von einer Website des Steuerelements.  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pWnd*  
 Ein Zeiger auf eine `CWnd` Objekt.  
  
 *nIDC*  
 Die ID des Steuerelements angefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie, um diesen Prozess anzupassen möchten.  
  
> [!NOTE]
>  Verwenden Sie die erste Form dieser Funktion, wenn Sie die MFC-Bibliothek statisch verknüpfen möchten. Verwenden Sie das zweite Format, wenn Sie dynamisch mit MFC-Bibliothek verknüpfen.  
  
##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange  
 Informiert alle gehosteten Steuerelemente, die Ambiente-Eigenschaft geändert wurde.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die Dispatch-ID der ambient-Eigenschaft geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen, wenn eine Ambiente-Eigenschaft den Wert geändert wurde. Überschreiben Sie diese Funktion, um dieses Verhalten anzupassen.  
  
##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton  
 Ändert den aktuellen Zustand der Schaltfläche.  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDButton*  
 Die ID der Schaltfläche geändert werden.  
  
 *nPrüfen*  
 Gibt den Status der Schaltfläche. Einer der folgenden Werte ist möglich:  
  
- **BST_CHECKED** legt den Zustand der Schaltfläche für die aktivierten auf.  
  
- **BST_INDETERMINATE** legt den Zustand der Schaltfläche auf grau dargestellt, der angibt, eines unbestimmten Zustands fest. Verwenden Sie diesen Wert nur, wenn die Schaltfläche "" hat die **BS_3STATE** oder **BS_AUTO3STATE** Stil.  
  
- **BST_UNCHECKED** legt den Zustand der Schaltfläche auf geleerten fest.  
  
##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton  
 Wählt eine angegebene Optionsfeld in einer Gruppe aus, und löscht die verbleibenden Schaltflächen in der Gruppe.  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDFirstButton*  
 Gibt den Bezeichner der das erste Optionsfeld in der Gruppe an.  
  
 *nIDLastButton*  
 Gibt den Bezeichner des letzten Optionsfelds in der Gruppe an.  
  
 *nIDCheckButton*  
 Gibt den Bezeichner des Optionsfelds überprüft werden soll.  
  
##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer  
 Erstellt ein `COleControlContainer`-Objekt.  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pWnd*  
 Ein Zeiger auf das übergeordnete Fenster eines dem Steuerelementcontainer.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem das Objekt erfolgreich erstellt wurde, fügen Sie einen benutzerdefiniertes Steuerelement Standort mit einem Aufruf von `AttachControlSite`.  
  
##  <a name="createcontrol"></a>  COleControlContainer::CreateControl  
 Erstellt ein ActiveX-Steuerelement, durch das angegebene gehostete `COleControlSite` Objekt.  
  
```  
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);

 
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndCtrl*  
 Ein Zeiger auf das Window-Objekt, das das Steuerelement darstellt.  
  
 *clsid*  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 *lpszWindowName*  
 Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Beschriftung oder Text-Eigenschaft des Steuerelements fest, (sofern vorhanden). Wenn **NULL**, Titel oder Text-Eigenschaft des Steuerelements wird nicht geändert.  
  
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
  
 *ppNewSite*  
 Ein Zeiger auf die vorhandene Website des Steuerelements, die als host das Steuerelement erstellt wird. Der Standardwert ist **NULL**, gibt an, dass eine neue Website des Steuerelements automatisch erstellt und an das neue Steuerelement angefügt werden.  
  
 *PPT*  
 Ein Zeiger auf eine **Punkt** Struktur, die der oberen linken Ecke des Steuerelements enthält. Die Größe des Steuerelements wird bestimmt durch den Wert des *Psize*. Die *ppt* und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.  
  
 *psize*  
 Ein Zeiger auf eine **Größe** Struktur, die die Größe des Steuerelements enthält. Die oberen linken Ecke richtet sich nach dem Wert der *ppt*. Die *ppt* und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Teilmenge der Windows *DwStyle* Flags werden unterstützt, indem Sie `CreateControl`:  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort wie gewöhnliche Fenster sichtbar sein soll.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktivierter Fenster kann nicht vom Benutzer Eingaben zu empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.  
  
- **WS_BORDER** erstellt ein Fenster mit einem Rahmen thin-Zeile. Kann festgelegt werden, wenn Steuerelement eine Rahmenart-Eigenschaft verfügt.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen. Die Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern, indem die Richtungstasten verwenden. Alle Steuerelemente, die definiert, mit der **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Gruppe und startet die nächste Gruppe.  
  
- **WS_TABSTOP** gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Drücken die TAB-Taste den Tastaturfokus auf das nächste Steuerelement der ändert die **WS_TABSTOP** Stil.  
  
 Verwenden Sie die zweite Überladung, um die Standardgröße Steuerelemente zu erstellen.  
  
##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont  
 Erstellt eine OLE-Schriftart.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pFont*  
 Ein Zeiger auf die Schriftart, die von der Control-Container verwendet werden.  
  
##  <a name="finditem"></a>  COleControlContainer::FindItem  
 Sucht die benutzerdefinierte Website, die das angegebene Element hostet.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des Elements gefunden werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die benutzerdefinierte Website des angegebenen Elements.  
  
##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents  
 Bestimmt, ob der Container wird Ereignisse von den Standorten angefügtes Steuerelement ignorieren oder haben akzeptiert.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parameter  
 *bFreeze*  
 Wert ungleich NULL, wenn Ereignisse verarbeitet werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um die Ereignisse auslösen, wenn von dem Steuerelementcontainer angefordert beendet. Auslösen von Ereignissen fortgesetzt werden kann, jedoch alle nachfolgenden Ereignisse werden von dem Steuerelementcontainer ignoriert.  
  
##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp  
 Ruft den Wert einer angegebenen ambient-Eigenschaft.  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>Parameter  
 *pSite*  
 Ein Zeiger auf eine Website des Steuerelements aus der die Ambiente-Eigenschaft abgerufen wird.  
  
 *DISPID*  
 Die Dispatch-ID der gewünschten ambient-Eigenschaft.  
  
 *pVarResult*  
 Ein Zeiger auf den Wert der ambient-Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem  
 Ruft einen Zeiger auf das angegebene Steuerelement oder ein untergeordnetes Fenster in einem Dialogfeld oder andere Fenster ab.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des abzurufenden Elements Dialogfeld.  
  
 *phWnd*  
 Ein Zeiger auf das Handle für das angegebene Dialog-Element-Fensterobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dialogfeldelement Fenster.  
  
##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt  
 Ruft den Wert der übersetzte Text des Steuerelements ab.  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des Steuerelements.  
  
 *lpTrans*  
 Zeiger auf eine boolesche Variable, die einen Erfolg/Fehler Funktionswert empfängt ( **"true"** zeigt "Erfolg", " **" false "** weisen auf Fehler hin).  
  
 *bSigned*  
 Gibt an, ob die Funktion sollte untersuchen Sie den Text für ein Minuszeichen (-) am Anfang und eine Ganzzahl mit Vorzeichen zurück, wenn ein solches gefunden. Wenn die *bSigned* Parameter ist **"true"**, angeben, dass der Wert abgerufen werden soll eine Ganzzahl mit Vorzeichen, umgewandelt den Rückgabewert in einer **Int** Typ. Um erweiterte Fehlerinformationen abzurufen, rufen [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die Variable auf verweist *LpTrans* festgelegt ist, um **"true"**, und der Rückgabewert ist den übersetzten Wert, der den Steuerelementtext.  
  
 Wenn die Funktion fehlschlägt, die Variable verweist, zu *LpTrans* festgelegt ist, um **"false"**, und der Rückgabewert ist 0 (null). Beachten Sie, dass, da 0 (null) ein möglicher Wert für die übersetzten ist, ein Rückgabewert von 0 (null) nicht allein Fehler angegeben ist.  
  
 Wenn *LpTrans* ist **NULL**, die Funktion gibt keine Informationen zum Erfolg oder Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion übersetzt den abgerufenen Text durch zusätzlichen Leerzeichen am Anfang des Texts zu entfernen und anschließend der Typ der Dezimalstellen. Die Funktion beendet das Übersetzen von beim Erreichen des Endes des Texts oder einen nicht numerischen Zeichen auftritt.  
  
 Diese Funktion gibt 0 (null) zurück, wenn der übersetzte Wert übersteigt **INT_MAX** (für signierte Nummern) oder **UINT_MAX** (für unsignierte Zahlen).  
  
##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText  
 Ruft den Text des Steuerelements ab.  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des Steuerelements.  
  
 *lpStr*  
 Zeiger auf den Text des Steuerelements.  
  
 *nMaxCount*  
 Gibt die maximale Länge in Zeichen der Zeichenfolge, die in den Puffer verweist, zu kopierenden *LpStr*. Wenn die Länge der Zeichenfolge das Limit überschreitet, wird die Zeichenfolge abgeschnitten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, gibt der zurückgegebene Wert die Anzahl der Zeichen, die in den Puffer, nicht einschließlich des abschließenden Null-Zeichens kopiert.  
  
 Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, rufen [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus  
 Bestimmt, ob der Container WM_SETFOCUS Nachrichten verarbeitet.  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Container WM_SETFOCUS Nachrichten behandelt; andernfalls 0 (null).  
  
##  <a name="handlewindowlessmessage"></a>  COleControlContainer::HandleWindowlessMessage  
 Verarbeitet Windows-Meldungen für fensterlose Steuerelemente.  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Parameter  
 *message*  
 Der Bezeichner für die fenstermeldung von Windows bereitgestellt.  
  
 *wParam*  
 Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche Nachricht-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der *Nachricht* Parameter.  
  
 *lParam*  
 Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche Nachricht-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der *Nachricht* Parameter.  
  
 *plResult*  
 Windows-Ergebniscode. Gibt das Ergebnis der Verarbeitung der Nachricht und hängt von der gesendeten Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Behandlung von fensterloses Steuerelement Nachrichten anzupassen.  
  
##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked  
 Bestimmt den Status der angegebenen Schaltfläche.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIDButton*  
 Der Bezeichner des Schaltflächen-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert eine Schaltfläche erstellt, mit der **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, oder **BS_3STATE** Stil. Einer der folgenden Werte ist möglich:  
  
- **BST_CHECKED** Schaltfläche aktiviert ist.  
  
- **BST_INDETERMINATE** Schaltfläche ist abgeblendet, der angibt, eines unbestimmten Zustands (gilt nur, wenn die Schaltfläche "" hat die **BS_3STATE** oder **BS_AUTO3STATE** Stil).  
  
- **BST_UNCHECKED** Schaltfläche deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche "" eines drei-Status-Steuerelements ist, die Memberfunktion bestimmt, ob sie dieses Kontrollkästchen aktiviert, abgeblendet ist, oder keines von beiden.  
  
##  <a name="m_crback"></a>  COleControlContainer::m_crBack  
 Die Hintergrundfarbe des Containers.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>  COleControlContainer::m_crFore  
 Die Vordergrundfarbe des Containers.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds  
 Eine Liste der Steuerelement Websites aufgeführt, die vom Container gehostet.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls  
 Die Anzahl der fensterlose Steuerelemente, die von dem Steuerelementcontainer gehostet wird.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont  
 Ein Zeiger auf die OLE-Schriftart für die Website des benutzerdefinierten Steuerelements.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture  
 Ein Zeiger auf die Website des Capture-Steuerelements.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus  
 Ein Zeiger auf die Website des Steuerelements, die aktuell den Eingabefokus besitzt.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive  
 Ein Zeiger auf die Website des Steuerelements, die direkten aktiviert ist.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd  
 Ein Zeiger auf die dem Container zugeordnete Fensterobjekt.  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap  
 Der Siteübersicht.  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="onpaint"></a>  COleControlContainer::OnPaint  
 Vom Framework aufgerufen, WM_PAINT-Anforderungen zu verarbeiten.  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Ein Zeiger auf den Gerätekontext, der vom Container verwendeten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Meldung verarbeitet wurde; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Anpassen der Zeichenprozess.  
  
##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate  
 Vom Framework aufgerufen, wenn die Website des Steuerelements verweist *pSite*, werden direkte aktiviert.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pSite*  
 Ein Zeiger auf die Website des Steuerelements, direktes aktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Direkte Aktivierung bedeutet, dass der Container-Hauptmenü ein direktes zusammengesetzten Menü ersetzt wird.  
  
##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate  
 Vom Framework aufgerufen, wenn die Website des Steuerelements verweist *pSite*, deaktiviert werden soll.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pSite*  
 Ein Zeiger auf die Website des Steuerelements deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Bei Empfang dieser Benachrichtigung ist, sollte der Container seine Benutzeroberfläche installieren und den Fokus.  
  
##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren  
 Vom Framework aufgerufen, wenn von einem untergeordneten Fenster Scroll Nachrichten empfangen werden.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Parameter  
 *DX*  
 Die Menge des Bildlaufs entlang der x-Achse in Pixel.  
  
 *dy*  
 Die Menge des Bildlaufs entlang der y-Achse in Pixel.  
  
##  <a name="senddlgitemmessage"></a>  COleControlContainer::SendDlgItemMessage  
 Sendet eine Nachricht an das angegebene Steuerelement.  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Gibt den Bezeichner des Steuerelements, das die Nachricht empfängt.  
  
 *message*  
 Gibt die Meldung gesendet werden.  
  
 *wParam*  
 Gibt zusätzliche Nachricht-spezifische Informationen.  
  
 *lParam*  
 Gibt zusätzliche Nachricht-spezifische Informationen.  
  
##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt  
 Legt den Text eines Steuerelements in einem Dialogfeld auf die angegebene Zeichenfolgendarstellung einer angegebenen ganzzahligen Wert fest.  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des Steuerelements.  
  
 *nWert*  
 Der ganzzahlige Wert, der angezeigt werden.  
  
 *bSigned*  
 Gibt an, ob die *nWert* Parameter ist mit oder ohne Vorzeichen. Wenn dieser Parameter ist **"true"**, *nWert* signiert ist. Wenn dieser Parameter ist **"true"** und *nWert* ist kleiner als 0 (null), ein Minuszeichen Anmeldung vor die erste Ziffer in der Zeichenfolge befindet. Wenn dieser Parameter ist **"false"**, *nWert* ist nicht signiert.  
  
##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText  
 Legt den Text des angegebenen Steuerelements, mit dem Text, der in enthaltenen *LpszString*.  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Der Bezeichner des Steuerelements.  
  
 *lpszString*  
 Zeiger auf den Text des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager-Klasse](../../mfc/reference/coccmanager-class.md)
