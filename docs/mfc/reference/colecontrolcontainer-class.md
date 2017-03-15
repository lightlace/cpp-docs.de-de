---
title: Klasse COleControlContainer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlContainer
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COleControlContainer class
- ActiveX control containers [C++], control site
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
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
ms.openlocfilehash: 764583d28bf71319eac5b7e51e0915ae786261a7
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolcontainer-class"></a>COleControlContainer-Klasse
Dient als Steuerelementcontainer für ActiveX-Steuerelemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Erstellt ein `COleControlContainer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Erstellt eine-Steuerelement-Website, die vom Container gehostet.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Dass alle gehostete Steuerelementen, die eine Ambiente-Eigenschaft geändert wurde.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Ändert den angegebenen Schaltflächen-Steuerelement.|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Wählt das angegebene Optionsfeld einer Gruppe.|  
|[COleControlContainer::CreateControl](#createcontrol)|Erstellt ein gehosteten ActiveX-Steuerelement.|  
|[COleControlContainer::CreateOleFont](#createolefont)|Erstellt eine OLE-Schriftart.|  
|[COleControlContainer::FindItem](#finditem)|Gibt die benutzerdefinierte Website für das angegebene Steuerelement zurück.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Bestimmt, ob die Steuerelementsite Ereignisse akzeptiert.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Ruft die angegebene ambient-Eigenschaft ab.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Ruft das angegebene Steuerelement ab.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Ruft den Wert des angegebenen Dialog-Steuerelements ab.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Ruft die Beschriftung des angegebenen Dialog-Steuerelements ab.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Bestimmt, ob der Container verwaltet `WM_SETFOCUS` Nachrichten.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Verarbeitet die Nachrichten an ein fensterloses Steuerelement gesendet.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Der Status der angegebenen Schaltfläche bestimmt.|  
|[COleControlContainer::OnPaint](#onpaint)|Wird aufgerufen, um einen Teil des Containers zu aktualisieren.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Wird aufgerufen, wenn ein Steuerelement ist, direkte aktiviert werden soll.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Wird aufgerufen, wenn ein Steuerelement deaktiviert werden soll.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Führen Sie einen Bildlauf in einem untergeordneten Fenster Nachrichten vom Framework aufgerufen.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Sendet eine Nachricht an das angegebene Steuerelement.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Legt den Wert des angegebenen Steuerelements.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Legt den Text des angegebenen Steuerelements.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Die Hintergrundfarbe des Containers.|  
|[COleControlContainer::m_crFore](#m_crfore)|Die Vordergrundfarbe des Containers.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Eine Liste der unterstützten Steuerelement Websites.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Die Anzahl der gehosteten Fensterlose Steuerelemente.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Ein Zeiger auf die OLE-Schriftart der Site für das benutzerdefinierte Steuerelement.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Ein Zeiger auf die Website des Steuerelements erfassen.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Ein Zeiger auf das Steuerelement, das aktuell den Eingabefokus besitzt.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Ein Zeiger auf das Steuerelement, das derzeit aktiviert ist.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Ein Zeiger auf das Fenster des Steuerelementcontainers implementieren.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Der Siteübersicht.|  
  
## <a name="remarks"></a>Hinweise  
 Dies erfolgt durch die Unterstützung für einen oder mehrere ActiveX-Steuerelement-Standorte (durch implementiert `COleControlSite`). `COleControlContainer`vollständig implementiert die [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) und [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) Schnittstellen, sodass enthaltenen ActiveX-Steuerelemente, um ihre Qualifikationen als direktes Elemente zu erfüllen.  
  
 Diese Klasse dient in der Regel in Verbindung mit `COccManager` und `COleControlSite` zum Implementieren eines benutzerdefinierten ActiveX-Steuerelementcontainers mit benutzerdefinierten Websites für eine oder mehrere ActiveX-Steuerelemente.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="a-nameattachcontrolsitea--colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite  
 Vom Framework erstellen und Anfügen einer Website des Steuerelements aufgerufen.  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf ein `CWnd` Objekt.  
  
 `nIDC`  
 Die ID des Steuerelements angefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie diesen Prozess anpassen möchten.  
  
> [!NOTE]
>  Verwenden Sie die erste Form dieser Funktion, wenn Sie statisch mit der MFC-Bibliothek verknüpfen. Verwenden Sie das zweite Formular, wenn Sie dynamisch mit der MFC-Bibliothek verknüpfen.  
  
##  <a name="a-namebroadcastambientpropertychangea--colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange  
 Dass alle gehostete Steuerelementen, die eine Ambiente-Eigenschaft geändert wurde.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID der ambient-Eigenschaft geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen, wenn eine Ambiente-Eigenschaft den Wert geändert hat. Überschreiben Sie diese Funktion, um dieses Verhalten anzupassen.  
  
##  <a name="a-namecheckdlgbuttona--colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>COleControlContainer::CheckDlgButton  
 Ändert den aktuellen Status der Schaltfläche.  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDButton`  
 Die ID der Schaltfläche geändert werden.  
  
 `nCheck`  
 Gibt den Status der Schaltfläche. Einer der folgenden Werte ist möglich:  
  
- **BST_CHECKED** legt den Zustand der Schaltfläche auf aktiviert fest.  
  
- **BST_INDETERMINATE** wird der Zustand der Schaltfläche auf grau dargestellt, der angibt, in einem unbestimmten Zustand befindet. Verwenden Sie diesen Wert nur, wenn die Schaltfläche den **BS_3STATE** oder **BS_AUTO3STATE** Stil.  
  
- **BST_UNCHECKED** legt den Zustand der Schaltfläche auf deaktiviert fest.  
  
##  <a name="a-namecheckradiobuttona--colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>COleControlContainer::CheckRadioButton  
 Wählt eine angegebene Optionsfeld in einer Gruppe, und die übrigen Schaltflächen in der Gruppe gelöscht.  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDFirstButton`  
 Gibt den Bezeichner der das erste Optionsfeld in der Gruppe.  
  
 `nIDLastButton`  
 Gibt den Bezeichner des letzten Optionsfelds in der Gruppe.  
  
 `nIDCheckButton`  
 Gibt den Bezeichner des Optionsfelds überprüft werden soll.  
  
##  <a name="a-namecolecontrolcontainera--colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>COleControlContainer::COleControlContainer  
 Erstellt ein `COleControlContainer`-Objekt.  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Steuerelementcontainer.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem das Objekt erfolgreich erstellt wurde, fügen Sie eine benutzerdefiniertes Steuerelement-Website mit einem Aufruf von `AttachControlSite`.  
  
##  <a name="a-namecreatecontrola--colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>COleControlContainer::CreateControl  
 Erstellt ein ActiveX-Steuerelement, durch den angegebenen gehosteten `COleControlSite` Objekt.  
  
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
 `pWndCtrl`  
 Ein Zeiger auf das Steuerelement darstellt.  
  
 `clsid`  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 `lpszWindowName`  
 Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Beschriftung oder Text-Eigenschaft des Steuerelements fest, (sofern vorhanden). Wenn **NULL**, Beschriftung oder Text-Eigenschaft des Steuerelements wird nicht geändert.  
  
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
  
 *ppNewSite*  
 Ein Zeiger auf die vorhandene Website des Steuerelements, die als host des Steuerelements erstellt wird. Der Standardwert ist **NULL**, gibt an, dass eine neue Website des Steuerelements wird automatisch erstellt und an das neue Steuerelement angefügt.  
  
 `ppt`  
 Ein Zeiger auf eine **Punkt** Struktur, die die linke obere Ecke des Steuerelements enthält. Die Größe des Steuerelements wird bestimmt durch den Wert der *Psize*. Die `ppt` und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.  
  
 *psize*  
 Ein Zeiger auf eine **Größe** Struktur, die die Größe des Steuerelements enthält. Die linke obere Ecke wird bestimmt durch den Wert des `ppt`. Die `ppt` und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Nur eine Teilmenge der Windows `dwStyle` Flags werden von unterstützt `CreateControl`:  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort, wie gewöhnliche Fenster angezeigt werden soll.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktiviertes Fenster kann keine Eingabe vom Benutzer empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.  
  
- `WS_BORDER`Erstellt ein Fenster mit einem Rahmen thin-Zeile. Kann festgelegt werden, wenn Steuerelement eine BorderStyle-Eigenschaft besitzt.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen. Der Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern mithilfe der Richtung. Alle Steuerelemente, die mit definiert die **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Gruppe und startet die nächste Gruppe.  
  
- **WS_TABSTOP** gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Drücken die TAB-Taste den Tastaturfokus auf das nächste Steuerelement der ändert die **WS_TABSTOP** Stil.  
  
 Verwenden Sie die zweite Überladung zum Erstellen von Steuerelementen mit Standardgröße.  
  
##  <a name="a-namecreateolefonta--colecontrolcontainercreateolefont"></a><a name="createolefont"></a>COleControlContainer::CreateOleFont  
 Erstellt eine OLE-Schriftart.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 Ein Zeiger auf die Schriftart, die von der Steuerelement-Container verwendet werden.  
  
##  <a name="a-namefinditema--colecontrolcontainerfinditem"></a><a name="finditem"></a>COleControlContainer::FindItem  
 Sucht die benutzerdefinierte Website, die das angegebene Element enthält.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner des Elements gefunden werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die benutzerdefinierte Website des angegebenen Elements.  
  
##  <a name="a-namefreezealleventsa--colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents  
 Bestimmt, ob der Container wird Ereignisse von den Standorten des zugeordneten Steuerelements ignorieren oder akzeptieren.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parameter  
 `bFreeze`  
 Wert ungleich NULL, wenn Ereignisse verarbeitet werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um das Auslösen von Ereignissen nach dem Steuerelementcontainer beenden. Auslösen von Ereignissen fortgesetzt werden kann, jedoch alle nachfolgenden Ereignisse durch den Steuerelementcontainer ignoriert werden.  
  
##  <a name="a-namegetambientpropa--colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>COleControlContainer::GetAmbientProp  
 Ruft den Wert einer angegebenen ambient-Eigenschaft ab.  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>Parameter  
 `pSite`  
 Ein Zeiger auf eine Website des Steuerelements aus der Ambiente-Eigenschaft abgerufen wird.  
  
 `dispid`  
 Die Dispatch-ID der gewünschten ambient-Eigenschaft.  
  
 *pVarResult*  
 Ein Zeiger auf den Wert der ambient-Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namegetdlgitema--colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>COleControlContainer::GetDlgItem  
 Ruft einen Zeiger auf das angegebene Steuerelement oder ein untergeordnetes Fenster in einem Dialogfeld oder anderen Fenster an.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Bezeichner des abzurufenden Elements Dialogfeld.  
  
 `phWnd`  
 Ein Zeiger auf das Handle für das angegebene Dialogfeldelement Window-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dialogfeldelement Fenster.  
  
##  <a name="a-namegetdlgiteminta--colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt  
 Ruft den Wert der übersetzte Text des Steuerelements ab.  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner des Steuerelements.  
  
 `lpTrans`  
 Zeiger auf eine boolesche Variable, die einen Erfolg/Fehler-Funktionswert empfängt ( **TRUE** gibt Erfolg, **FALSE** gibt einen Fehler).  
  
 `bSigned`  
 Gibt an, ob die Funktion sollte den Text für ein Minuszeichen am Anfang untersuchen und eine Ganzzahl mit Vorzeichen zurück, wenn eine. Wenn die `bSigned` Parameter ist **TRUE**, angeben, dass der Wert abgerufen werden sollen eine Ganzzahl mit Vorzeichen, wandeln Sie den Rückgabewert in einer `int` Typ. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die Variable zeigt `lpTrans` Wert **TRUE**, und der Rückgabewert ist der übersetzte Wert der Steuerelementtext.  
  
 Wenn die Funktion fehlschlägt, die Variable auf den `lpTrans` Wert **FALSE**, und der Rückgabewert ist&0; (null). Beachten Sie, dass, da&0; (null) einer übersetzten Wert ist, ein Rückgabewert von&0; (null) nicht allein Fehler angegeben wird.  
  
 Wenn `lpTrans` ist **NULL**, keine Informationen über den Erfolg oder Fehler zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion übersetzt den abgerufenen Text durch zusätzlichen Leerzeichen am Anfang des Texts zu entfernen und dann die Dezimalstellen. Die Funktion beendet das Übersetzen von beim Erreichen des Endes des Texts oder einem nicht numerischen Zeichen findet.  
  
 Diese Funktion gibt&0; (null) zurück, wenn der übersetzte Wert übersteigt **INT_MAX** (für signierte Zahlen) oder **UINT_MAX** (für Zahlen ohne Vorzeichen).  
  
##  <a name="a-namegetdlgitemtexta--colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>COleControlContainer::GetDlgItemText  
 Ruft den Text des Steuerelements ab.  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner des Steuerelements.  
  
 `lpStr`  
 Zeiger auf den Text des Steuerelements.  
  
 `nMaxCount`  
 Gibt die maximale Länge in Zeichen der Zeichenfolge, die in den Puffer, die auf den zu kopierenden `lpStr`. Wenn die Länge der Zeichenfolge das Limit überschreitet, wird die Zeichenfolge abgeschnitten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, gibt der Rückgabewert die Anzahl der Zeichen, die in den Puffer, nicht einschließlich des abschließenden Zeichens Null kopiert.  
  
 Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
##  <a name="a-namehandlesetfocusa--colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>COleControlContainer::HandleSetFocus  
 Bestimmt, ob der Container verwaltet `WM_SETFOCUS` Nachrichten.  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Container verwaltet `WM_SETFOCUS` Nachrichten; andernfalls&0; (null).  
  
##  <a name="a-namehandlewindowlessmessagea--colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>COleControlContainer::HandleWindowlessMessage  
 Verarbeitet Windows-Meldungen für fensterlose Steuerelemente.  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Der Bezeichner für die Meldung, von Windows bereitgestellt wird.  
  
 `wParam`  
 Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche Message-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der `message` Parameter.  
  
 `lParam`  
 Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche Message-spezifische Informationen. Der Inhalt dieses Parameters hängt von den Wert der `message` Parameter.  
  
 *plResult*  
 Windows-Ergebniscode. Gibt das Ergebnis der Verarbeitung der Nachricht und hängt von der gesendeten Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Verarbeitung von Nachrichten fensterloses Steuerelement anpassen.  
  
##  <a name="a-nameisdlgbuttoncheckeda--colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked  
 Der Status der angegebenen Schaltfläche bestimmt.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDButton`  
 Der Bezeichner des Button-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert von einer Schaltfläche mit dem **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, oder **BS_3STATE** Stil. Einer der folgenden Werte ist möglich:  
  
- **BST_CHECKED** Schaltfläche aktiviert wird.  
  
- **BST_INDETERMINATE** Schaltfläche abgeblendet ist, einen unbestimmten Zustand angibt (gilt nur, wenn die Schaltfläche den **BS_3STATE** oder **BS_AUTO3STATE** Stil).  
  
- **BST_UNCHECKED** Schaltfläche deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche ein drei-Status-Steuerelement ist, die Memberfunktion bestimmt, ob es aktiviert, abgeblendet ist, oder keines von beiden.  
  
##  <a name="a-namemcrbacka--colecontrolcontainermcrback"></a><a name="m_crback"></a>COleControlContainer::m_crBack  
 Die Hintergrundfarbe des Containers.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="a-namemcrforea--colecontrolcontainermcrfore"></a><a name="m_crfore"></a>COleControlContainer::m_crFore  
 Die Vordergrundfarbe des Containers.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="a-namemlistsitesorwndsa--colecontrolcontainermlistsitesorwnds"></a><a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds  
 Eine Liste der Steuerelement-Websites, die vom Container gehostet werden soll.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="a-namemnwindowlesscontrolsa--colecontrolcontainermnwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>COleControlContainer::m_nWindowlessControls  
 Die Anzahl der fensterlose Steuerelemente, die von der Steuerelement-Container gehostet werden.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="a-namempolefonta--colecontrolcontainermpolefont"></a><a name="m_polefont"></a>COleControlContainer::m_pOleFont  
 Ein Zeiger auf die OLE-Schriftart der Site für das benutzerdefinierte Steuerelement.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="a-namempsitecapturea--colecontrolcontainermpsitecapture"></a><a name="m_psitecapture"></a>COleControlContainer::m_pSiteCapture  
 Ein Zeiger auf die Website des Steuerelements erfassen.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="a-namempsitefocusa--colecontrolcontainermpsitefocus"></a><a name="m_psitefocus"></a>COleControlContainer::m_pSiteFocus  
 Ein Zeiger auf die Website des Steuerelements, die aktuell den Eingabefokus besitzt.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="a-namempsiteuiactivea--colecontrolcontainermpsiteuiactive"></a><a name="m_psiteuiactive"></a>COleControlContainer::m_pSiteUIActive  
 Ein Zeiger auf die Website des Steuerelements, die in-Place-aktiviert ist.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="a-namempwnda--colecontrolcontainermpwnd"></a><a name="m_pwnd"></a>COleControlContainer::m_pWnd  
 Ein Zeiger auf das Window-Objekt, das dem Container zugeordnet.  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="a-namemsitemapa--colecontrolcontainermsitemap"></a><a name="m_sitemap"></a>COleControlContainer::m_siteMap  
 Der Siteübersicht.  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="a-nameonpainta--colecontrolcontaineronpaint"></a><a name="onpaint"></a>COleControlContainer::OnPaint  
 Aufgerufen, um behandeln `WM_PAINT` Anforderungen.  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, der vom Container verwendeten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Meldung verarbeitet wurde; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Zeichenprozess anpassen.  
  
##  <a name="a-nameonuiactivatea--colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>COleControlContainer::OnUIActivate  
 Vom Framework aufgerufen wenn die Website des Steuerelements, auf das `pSite`, werden direkte aktiviert.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parameter  
 `pSite`  
 Ein Zeiger auf die Website des Steuerelements direktes aktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Direkte Aktivierung bedeutet, dass der Container-Hauptmenü mit einem zusammengesetzten Menü ersetzt wird.  
  
##  <a name="a-nameonuideactivatea--colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate  
 Aufgerufen, wenn die Website des Steuerelements, auf das `pSite`, deaktiviert werden soll.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parameter  
 `pSite`  
 Ein Zeiger auf die Website des Steuerelements deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Benachrichtigung empfangen wird, sollte der Container die Benutzeroberfläche installieren und den Fokus.  
  
##  <a name="a-namescrollchildrena--colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>COleControlContainer::ScrollChildren  
 Führen Sie einen Bildlauf in einem untergeordneten Fenster Nachrichten vom Framework aufgerufen.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Parameter  
 `dx`  
 Das Ausmaß des Bildlaufs entlang der x-Achse in Pixel.  
  
 *dy*  
 Das Ausmaß des Bildlaufs entlang der y-Achse in Pixel.  
  
##  <a name="a-namesenddlgitemmessagea--colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>COleControlContainer::SendDlgItemMessage  
 Sendet eine Nachricht an das angegebene Steuerelement.  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt den Bezeichner des Steuerelements, das die Nachricht empfängt.  
  
 `message`  
 Gibt die Nachricht gesendet werden.  
  
 `wParam`  
 Gibt zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 Gibt zusätzliche Message-spezifische Informationen.  
  
##  <a name="a-namesetdlgiteminta--colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>COleControlContainer::SetDlgItemInt  
 Legt den Text eines Steuerelements in einem Dialogfeld auf die Zeichenfolgendarstellung für einen angegebenen ganzzahligen Wert fest.  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner des Steuerelements.  
  
 `nValue`  
 Der ganzzahlige Wert angezeigt werden.  
  
 `bSigned`  
 Gibt an, ob die `nValue` Parameter mit oder ohne Vorzeichen ist. Wenn dieser Parameter **TRUE**, `nValue` ist signiert. Wenn dieser Parameter **TRUE** und `nValue` ist kleiner als&0; (null), ein Minuszeichen anmelden werden vor der ersten Ziffer in der Zeichenfolge platziert. Wenn dieser Parameter **FALSE**, `nValue` ist nicht signiert.  
  
##  <a name="a-namesetdlgitemtexta--colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>COleControlContainer::SetDlgItemText  
 Legt den Text des angegebenen Steuerelements, mit dem Text, der in enthaltenen `lpszString`.  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Der Bezeichner des Steuerelements.  
  
 `lpszString`  
 Zeiger auf den Text des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager-Klasse](../../mfc/reference/coccmanager-class.md)

