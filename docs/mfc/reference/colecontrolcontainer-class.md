---
title: COleControlContainer-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: e89096b553814285f61093af81e31b294e3ad2bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603008"
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
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Erstellt eine Steuerelement-Website, die vom Container gehostet.|
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Dass alle gehostete Steuerelementen, die Ambiente-Eigenschaft geändert wurde.|
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Ändert den angegebenen Schaltflächen-Steuerelement.|
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Wählt das angegebene Optionsfeld einer Gruppe an.|
|[COleControlContainer::CreateControl](#createcontrol)|Erstellt ein gehostetes ActiveX-Steuerelement.|
|[COleControlContainer::CreateOleFont](#createolefont)|Erstellt eine OLE-Schriftart.|
|[COleControlContainer::FindItem](#finditem)|Gibt die benutzerdefinierte Website des angegebenen Steuerelements zurück.|
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Bestimmt, ob die Website des Steuerelements Ereignisse akzeptiert.|
|[COleControlContainer::GetAmbientProp](#getambientprop)|Ruft die angegebene ambient-Eigenschaft ab.|
|[COleControlContainer::GetDlgItem](#getdlgitem)|Ruft das angegebene Dialogfeld-Steuerelement ab.|
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Ruft den Wert der angegebenen Dialogfeld-Steuerelement ab.|
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Ruft die Beschriftung des Steuerelements angegebenen Dialogfeld ab.|
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Bestimmt, ob der Container WM_SETFOCUS-Nachrichten verarbeitet.|
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Verarbeitet Nachrichten, die an einem fensterlosen Steuerelement gesendet.|
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Bestimmt den Zustand der angegebenen Schaltfläche.|
|[COleControlContainer::OnPaint](#onpaint)|Wird aufgerufen, um einen Teil der Container neu zu zeichnen.|
|[COleControlContainer::OnUIActivate](#onuiactivate)|Wird aufgerufen, wenn ein Steuerelement, direkt aktiviert werden soll.|
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Wird aufgerufen, wenn ein Steuerelement deaktiviert wird.|
|[COleControlContainer::ScrollChildren](#scrollchildren)|Vom Framework aufgerufen, wenn in einem untergeordneten Fenster Scrollen Nachrichten empfangen werden.|
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Sendet eine Nachricht an das angegebene Steuerelement.|
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Legt den Wert des angegebenen Steuerelements.|
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Legt den Text des angegebenen Steuerelements.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleControlContainer::m_crBack](#m_crback)|Die Hintergrundfarbe des Containers.|
|[COleControlContainer::m_crFore](#m_crfore)|Die Vordergrundfarbe des Containers.|
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Eine Liste der unterstützten Steuerelement-Websites.|
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Die Anzahl der gehosteten Fensterlose Steuerelemente.|
|[COleControlContainer::m_pOleFont](#m_polefont)|Ein Zeiger auf die OLE-Schriftart für die Website des benutzerdefinierten Steuerelements.|
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Zeiger auf die Website des Capture-Steuerelements.|
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Zeiger auf das Steuerelement, das aktuell den Eingabefokus besitzt.|
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Zeiger auf das Steuerelement, das derzeit direkt aktiviert ist.|
|[COleControlContainer::m_pWnd](#m_pwnd)|Zeiger auf das Fenster, den Steuerelementcontainer implementieren.|
|[COleControlContainer::m_siteMap](#m_sitemap)|Die sitezuordnung.|

## <a name="remarks"></a>Hinweise

Dies erfolgt durch die Unterstützung für einen oder mehrere ActiveX-Steuerelement-Standorte (durch implementiert `COleControlSite`). `COleControlContainer` vollständig implementiert die [IOleInPlaceFrame](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceframe) und [IOleContainer](/windows/desktop/api/oleidl/nn-oleidl-iolecontainer) Schnittstellen, sodass die enthaltenen ActiveX-Steuerelemente, um die Qualifizierung jetzt als direktes Elemente zu erfüllen.

Diese Klasse wird normalerweise verwendet, in Verbindung mit `COccManager` und `COleControlSite` zum Implementieren eines benutzerdefinierten ActiveX-Steuerelementcontainers mit benutzerdefinierten Websites für eine oder mehrere ActiveX-Steuerelemente.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Anforderungen

**Header:** afxocc.h

##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite

Wird aufgerufen, durch das Framework zum Erstellen und Anfügen einer Website des Steuerelements.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
Ein Zeiger auf ein `CWnd` -Objekt.

*nIDC*<br/>
Die ID des Steuerelements angefügt werden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie diesen Prozess anpassen möchten.

> [!NOTE]
>  Verwenden Sie die erste Form dieser Funktion, wenn Sie die MFC-Bibliothek statisch verknüpfen möchten. Verwenden Sie das zweite Formular aus, wenn Sie dynamisch die MFC-Bibliothek verknüpfen möchten.

##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange

Dass alle gehostete Steuerelementen, die Ambiente-Eigenschaft geändert wurde.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die Dispatch-ID der ambient-Eigenschaft geändert wird.

### <a name="remarks"></a>Hinweise

Diese Funktion wird vom Framework aufgerufen, wenn eine Ambiente-Eigenschaft den Wert geändert wurde. Überschreiben Sie diese Funktion, um dieses Verhalten anpassen.

##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton

Ändert den aktuellen Zustand der Schaltfläche.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Parameter

*nIDButton*<br/>
Die ID der Schaltfläche geändert werden.

*nPrüfen*<br/>
Gibt den Zustand der Schaltfläche. Einer der folgenden Werte ist möglich:

- BST_CHECKED legt überprüft den Zustand der Schaltfläche auf.

- BST_INDETERMINATE legt fest, um den Zustand der Schaltfläche abgeblendet, der angibt, in einem unbestimmten Zustand befindet. Verwenden Sie diesen Wert nur, wenn die Schaltfläche den BS_3STATE oder BS_AUTO3STATE-Stil.

- BST_UNCHECKED legt fest, die Schaltfläche mit der Zustand deaktiviert.

##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton

Wählt ein Optionsfeld für die angegebene in einer Gruppe aus, und löscht die übrigen Schaltflächen in der Gruppe.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Parameter

*nIDFirstButton*<br/>
Gibt den Bezeichner der das erste Optionsfeld in der Gruppe an.

*nIDLastButton*<br/>
Gibt den Bezeichner des letzten Optionsfelds in der Gruppe an.

*nIDCheckButton*<br/>
Gibt den Bezeichner des Optionsfelds überprüft werden soll.

##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer

Erstellt ein `COleControlContainer`-Objekt.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
Ein Zeiger auf das übergeordnete Fenster des Steuerelementcontainers.

### <a name="remarks"></a>Hinweise

Sobald das Objekt wurde erfolgreich erstellt wurde, fügen Sie eine benutzerdefiniertes Steuerelement-Website mit einem Aufruf von `AttachControlSite`.

##  <a name="createcontrol"></a>  COleControlContainer::CreateControl

Erstellt ein ActiveX-Steuerelement, mit dem angegebenen gehosteten `COleControlSite` Objekt.

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

*pWndCtrl*<br/>
Ein Zeiger auf das Window-Objekt, das das Steuerelement darstellt.

*clsid*<br/>
Die eindeutige Klasse-ID des Steuerelements.

*lpszWindowName*<br/>
Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Beschriftung oder den Text-Eigenschaft des Steuerelements fest, (sofern vorhanden). Wenn der Wert NULL ist, wird die Beschriftung oder den Text-Eigenschaft des Steuerelements nicht geändert.

*dwStyle*<br/>
Windows-Formate. Die verfügbaren Formate finden Sie unter den **"Hinweise"** Abschnitt.

*Rect*<br/>
Gibt an, die Größe und Position des Steuerelements. Es kann sein, entweder eine `CRect` Objekt oder ein `RECT` Struktur.

*nID*<br/>
Gibt an, der ID des Steuerelements untergeordnete Fenster

*pPersist*<br/>
Ein Zeiger auf eine `CFile` , die den dauerhaften Status für das Steuerelement enthält. Der Standardwert ist NULL, gibt an, dass das Steuerelement selbst ohne Wiederherstellung von seinen Zustand aus dem alle permanenten Speicher initialisiert. Wenn nicht NULL ist, wird ein Zeiger auf eine `CFile`-abgeleitetes Objekt, das persistente Daten des Steuerelements im Formular einen Stream oder ein Speicherkonto enthält. Diese Daten können in eine vorherige Aktivierung des Clients gespeichert wurden. Die `CFile` können weitere Daten enthalten, jedoch müssen der Lese-/ Schreibzugriff Zeiger auf das erste Byte von persistenten Daten festgelegt werden, zum Zeitpunkt des Aufrufs von `CreateControl`.

*bStorage*<br/>
Gibt an, ob die Daten in *pPersist* interpretiert werden soll, als `IStorage` oder `IStream` Daten. Wenn die Daten in *pPersist* ist ein Speicher, *bStorage* sollte "true" sein. Wenn die Daten in *pPersist* ist ein Datenstrom, *bStorage* sollte "false" sein. Der Standardwert ist "false".

*bstrLicKey*<br/>
Lizenz-Schlüsseldaten ist optional. Diese Daten ist nur für das Erstellen von Steuerelementen, die erfordern einen Laufzeit-Lizenzschlüssel erforderlich. Wenn das Steuerelement unterstützt die Lizenzierung, müssen Sie einen Lizenzschlüssel für die Erstellung des Steuerelements erfolgreich bereitstellen. Der Standardwert ist NULL.

*ppNewSite*<br/>
Ein Zeiger auf die vorhandene Website des Steuerelements, die als host das Steuerelement erstellt wird. Der Standardwert ist NULL, gibt an, dass eine neue Website des Steuerelements automatisch erstellt und auf das neue Steuerelement angefügt werden.

*PPT*<br/>
Ein Zeiger auf eine `POINT` Struktur, die die linke obere Ecke des Steuerelements enthält. Die Größe des Steuerelements richtet sich nach dem Wert der *Psize*. Die *ppt* und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.

*psize*<br/>
Ein Zeiger auf eine `SIZE` Struktur, die die Größe des Steuerelements enthält. Die linke obere Ecke richtet sich nach dem Wert der *ppt*. Die *ppt* und *Psize* Werte sind eine optionale Methode dar, die die Größe und Position des Steuerelements angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Nur ein Teil der Windows *DwStyle* Flags werden von unterstützt `CreateControl`:

- WS_VISIBLE erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort wie gewöhnliche Fenster angezeigt werden soll.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktiviertes Fensters kann keine Eingabe vom Benutzer empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.

- WS_BORDER erstellt ein Fenster mit einem thin-Line-Rahmen. Kann festgelegt werden, wenn Steuerelement eine BorderStyle-Eigenschaft verfügt.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen an. Der Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern mithilfe der Richtung. Alle Steuerelemente, die mit dem WS_GROUP-Stil definiert wird, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit dem Stil WS_GROUP beendet die Gruppe und beginnt die nächste Gruppe.

- WS_TABSTOP gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Durch Drücken der TAB-Taste ändert den Tastaturfokus auf das nächste Steuerelement für den WS_TABSTOP-Stil.

Verwenden Sie die zweite Überladung, um die Standardgröße Steuerelemente zu erstellen.

##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont

Erstellt eine OLE-Schriftart.

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf die Schriftart, die von der Control-Container verwendet werden.

##  <a name="finditem"></a>  COleControlContainer::FindItem

Ermittelt die benutzerdefinierte Website, die das angegebene Element hostet.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der Bezeichner des Elements gefunden werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die benutzerdefinierte Website des angegebenen Elements.

##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents

Bestimmt, ob der Container wird der angefügte Steuerelement Standorte von Ereignissen ignorieren, oder akzeptieren Sie diese.

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parameter

*bFreeze*<br/>
Ungleich NULL, wenn Ereignisse verarbeitet werden; andernfalls 0.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um das Auslösen von Ereignissen nach Aufforderung von der Control-Container zu beenden. Sie können das Ereignis weiterhin ausgelöst, aber alle nachfolgenden Ereignisse durch den Steuerelementcontainer ignoriert werden.

##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp

Ruft den Wert einer angegebenen ambient-Eigenschaft.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Parameter

*pSite*<br/>
Ein Zeiger auf eine Website des Steuerelements aus der die Ambiente-Eigenschaft abgerufen werden wird.

*DISPID*<br/>
Die Dispatch-ID der gewünschte ambient-Eigenschaft.

*pVarResult*<br/>
Ein Zeiger auf den Wert der ambient-Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem

Ruft einen Zeiger auf das angegebene Steuerelement oder ein untergeordnetes Fenster in einem Dialogfeld oder anderen Fenster ab.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Bezeichner des abzurufenden Elements Dialogfeld.

*phWnd*<br/>
Ein Zeiger auf das Handle des Window-Objekt für das angegebene Dialogfeld-Element.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Dialogfeldelement Fenster.

##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt

Ruft den Wert des übersetzten Texts in der das angegebene Steuerelement.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der Bezeichner des Steuerelements.

*lpTrans*<br/>
Zeiger auf eine boolesche Variable, die Wert einer Funktion Erfolg/Fehler empfängt ("true" gibt an, Erfolg, "false" gibt an, Fehler).

*bSigned*<br/>
Gibt an, ob die Funktion prüfen Sie den Text für ein Minuszeichen (-) am Anfang und eine Ganzzahl mit Vorzeichen zurück, wenn eine Datei gefunden werden soll. Wenn die *bSigned* Parameter ist "true", die angeben, dass der Wert abgerufen werden sollen eine Ganzzahl mit Vorzeichen, umgewandelt den Rückgabewert in einer **Int** Typ. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, die Variable, zeigt *LpTrans* auf "true" festgelegt ist und der Rückgabewert ist der übersetzte Wert, der den Text des Steuerelements.

Wenn die Funktion fehlschlägt, die Variable verweist *LpTrans* auf "FALSE" festgelegt ist und der Rückgabewert ist 0 (null). Beachten Sie, dass 0 (null) ein möglicher Wert für die übersetzten daher ein Rückgabewert von 0 (null) nicht selbst Fehler angibt.

Wenn *LpTrans* NULL ist, die Funktion gibt keine Informationen über den Erfolg oder Fehler zurück.

### <a name="remarks"></a>Hinweise

Die Funktion übersetzt den abgerufenen Text entfernt zusätzlichen Leerzeichen am Anfang des Texts, und konvertieren Sie dann die Dezimalstellen. Die Funktion beendet wird, übersetzen beim Erreichen des Endes des Texts oder ein nicht numerischer Zeichen erkennt.

Diese Funktion gibt 0 (null) zurück, wenn der übersetzte Wert größer als INT_MAX (für Zahlen mit Vorzeichen) oder UINT_MAX (für unsignierte Zahlen) ist.

##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText

Ruft den Text des angegebenen Steuerelements ab.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der Bezeichner des Steuerelements.

*lpStr*<br/>
Zeiger auf den Text des Steuerelements.

*nMaxCount*<br/>
Gibt die maximale Länge in Zeichen der Zeichenfolge, die in den Puffer, die auf zu kopierenden *LpStr*. Wenn die Länge der Zeichenfolge das Limit überschreitet, wird die Zeichenfolge abgeschnitten.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, gibt der Rückgabewert die Anzahl der Zeichen kopiert werden, in den Puffer, der das abschließende Nullzeichen nicht eingeschlossen.

Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus

Bestimmt, ob der Container WM_SETFOCUS-Nachrichten verarbeitet.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Container WM_SETFOCUS-Nachrichten verarbeitet werden; andernfalls 0 (null).

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

*message*<br/>
Der Bezeichner für die fenstermeldung, die von Windows bereitgestellt.

*wParam-Parameter*<br/>
Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche meldungsspezifische Informationen. Der Inhalt dieses Parameters ist hängt von den Wert des der *Nachricht* Parameter.

*lParam*<br/>
Die Parameter der Nachricht. von Windows bereitgestellt. Gibt zusätzliche meldungsspezifische Informationen. Der Inhalt dieses Parameters ist hängt von den Wert des der *Nachricht* Parameter.

*plResult*<br/>
Windows-Ergebniscode. Gibt das Ergebnis der Nachrichtenverarbeitung und hängt von der gesendeten Nachricht.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Behandlung von fensterloses Steuerelement Nachrichten anzupassen.

##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked

Bestimmt den Zustand der angegebenen Schaltfläche.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Parameter

*nIDButton*<br/>
Der Bezeichner des Button-Steuerelements.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert von der Schaltfläche mit den BS_AUTOCHECKBOX BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON oder BS_3STATE-Stil erstellt. Einer der folgenden Werte ist möglich:

- Schaltfläche "BST_CHECKED" aktiviert ist.

- BST_INDETERMINATE Schaltfläche ist grau unterlegt, der angibt, in einem unbestimmten Zustand befindet (gilt nur, wenn die Schaltfläche den BS_3STATE oder BS_AUTO3STATE-Stil).

- Schaltfläche "BST_UNCHECKED" wird gelöscht.

### <a name="remarks"></a>Hinweise

Wenn die Schaltfläche "eines drei-Status-Steuerelements ist, die Memberfunktion bestimmt, ob sie die Option aktiviert ist, abgeblendet ist, oder keines von beiden.

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

Eine Liste der Steuerelement-Standorte, die vom Container gehostet werden soll.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls

Die Anzahl der fensterlose Steuerelemente, die von der Control-Container gehostet wird.

```
int m_nWindowlessControls;
```

##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont

Ein Zeiger auf die OLE-Schriftart für die Website des benutzerdefinierten Steuerelements.

```
LPFONTDISP m_pOleFont;
```

##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture

Zeiger auf die Website des Capture-Steuerelements.

```
COleControlSite* m_pSiteCapture;
```

##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus

Ein Zeiger auf die Website des Steuerelements, die aktuell den Eingabefokus besitzt.

```
COleControlSite* m_pSiteFocus;
```

##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive

Ein Zeiger auf die Website des Steuerelements, die direkt aktiviert ist.

```
COleControlSite* m_pSiteUIActive;
```

##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd

Ein Zeiger auf das Window-Objekt, das dem Container zugeordnet.

```
CWnd* m_pWnd;
```

##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap

Die sitezuordnung.

```
CMapPtrToPtr m_siteMap;
```

##  <a name="onpaint"></a>  COleControlContainer::OnPaint

Wird aufgerufen, durch das Framework um WM_PAINT-Anforderungen zu verarbeiten.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf den Gerätekontext, die vom Container verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Meldung behandelt wurde; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um den Prozess für die Darstellung anzupassen.

##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate

Vom Framework aufgerufen, wenn die Website des Steuerelements, verweist *pSite*, wird direkt aktiviert.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parameter

*pSite*<br/>
Ein Zeiger auf die Website des Steuerelements, direkt aktiviert werden soll.

### <a name="remarks"></a>Hinweise

Direkte Aktivierung bedeutet, dass es sich bei Hauptmenü des Containers durch ein zusammengesetztes Menü ersetzt wird.

##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate

Vom Framework aufgerufen, wenn die Website des Steuerelements, verweist *pSite*, deaktiviert werden soll.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parameter

*pSite*<br/>
Ein Zeiger auf die Site für das Steuerelement deaktiviert wird.

### <a name="remarks"></a>Hinweise

Beim Empfang dieser Benachrichtigung ist, sollte der Container die Benutzeroberfläche installieren und den Fokus erhalten.

##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren

Vom Framework aufgerufen, wenn in einem untergeordneten Fenster Scrollen Nachrichten empfangen werden.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Parameter

*DX*<br/>
Das Ausmaß des Bildlaufs auf der x-Achse in Pixel.

*dy*<br/>
Das Ausmaß des Bildlaufs auf der y-Achse in Pixel.

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

*nID*<br/>
Gibt den Bezeichner des Steuerelements, das die Nachricht empfängt.

*message*<br/>
Gibt die Meldung gesendet werden.

*wParam-Parameter*<br/>
Gibt zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
Gibt zusätzliche meldungsspezifische Informationen.

##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt

Legt den Text eines Steuerelements in einem Dialogfeld, um die angegebene Zeichenfolgendarstellung einer angegebenen ganzzahligen Wert fest.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der Bezeichner des Steuerelements.

*nWert*<br/>
Der ganzzahlige Wert, der angezeigt werden.

*bSigned*<br/>
Gibt an, ob die *nWert* Parameter mit oder ohne Vorzeichen ist. Wenn dieser Parameter auf "true" ist *nWert* signiert ist. Wenn dieser Parameter auf "true" ist und *nWert* ist kleiner als 0 (null), ein Minuszeichen anmelden werden vor der ersten Ziffer in der Zeichenfolge platziert. Wenn dieser Parameter auf "FALSE" ist *nWert* nicht signiert ist.

##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText

Legt den Text des angegebenen Steuerelements, mit dem Text, der in enthaltenen *LpszString*.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der Bezeichner des Steuerelements.

*lpszString*<br/>
Zeiger auf den Text des Steuerelements.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager-Klasse](../../mfc/reference/coccmanager-class.md)
