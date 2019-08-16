---
title: CDialogImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: bc39a5deeb270b0426a4b199fc9ba01917c292bc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496817"
---
# <a name="cdialogimpl-class"></a>CDialogImpl-Klasse

Diese Klasse stellt Methoden zum Erstellen eines modalen oder nicht modalen Dialog Felds bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `CDialogImpl`abgeleitete Klasse.

*Tbase*<br/>
Die Basisklasse der neuen Klasse. Die Standardbasis Klasse ist [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Erstellen](#create)|Erstellt ein Dialogfeld ohne Modus.|
|[DestroyWindow](#destroywindow)|Zerstört ein nicht modalem Dialogfeld.|
|[DoModal](#domodal)|Erstellt ein modales Dialogfeld.|
|[EndDialog](#enddialog)|Zerstört ein modales Dialogfeld.|

### <a name="cdialogimplbaset-methods"></a>Cdialogimplbaset-Methoden

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Gibt die aktuelle Dialogfeld Prozedur zurück.|
|[MapDialogRect](#mapdialogrect)|Ordnet die Dialogfeld Einheiten des angegebenen Rechtecks den Bildschirm Einheiten (Pixel) zu.|
|[OnFinalMessage](#onfinalmessage)|Wird aufgerufen, nachdem die letzte Meldung empfangen wurde, in der Regel WM_NCDESTROY.|

### <a name="static-functions"></a>Statische Funktionen

|||
|-|-|
|[DialogProc](#dialogproc)|Verarbeitet Nachrichten, die an das Dialogfeld gesendet werden.|
|[StartDialogProc](#startdialogproc)|Wird aufgerufen, wenn die erste Meldung empfangen wird, um die an das Dialogfeld gesendeten Nachrichten zu verarbeiten.|

## <a name="remarks"></a>Hinweise

Mit `CDialogImpl` können Sie ein modales oder nicht modales Dialogfeld erstellen. `CDialogImpl`stellt die Dialogfeld Prozedur bereit, in der die standardmäßige Meldungs Zuordnung zum Weiterleiten von Nachrichten an die entsprechenden Handler verwendet wird.

Der basisklassendebugtor `~CWindowImplRoot` stellt sicher, dass das Fenster vor dem Zerstören des Objekts Weg ist.

`CDialogImpl` wird von `CDialogImplBaseT` abgeleitet, was wiederum von `CWindowImplRoot` abgeleitet wird.

> [!NOTE]
>  Die Klasse muss einen `IDD` Member definieren, der die Ressourcen-ID der Dialogfeld Vorlage angibt. Beispielsweise fügt der ATL-Projekt-Assistent der Klasse automatisch die folgende Zeile hinzu:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

Dabei ist der **Kurzname** , der auf der Seite mit den Namen des Assistenten eingegeben wurde. `MyDlg`

|Weitere Informationen finden Sie unter|Siehe|
|--------------------------------|---------|
|Erstellen von Steuerelementen|[ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md)|
|Verwenden von Dialogfeldern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|
|Dialogfelder|[Dialog Felder](/windows/win32/dlgbox/dialog-boxes) und nachfolgende Themen in der Windows SDK|

## <a name="requirements"></a>Anforderungen

**Header:** atlwin. h

##  <a name="create"></a>CDialogImpl:: Create

Erstellt ein Dialogfeld ohne Modus.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
in Das Handle für das Besitzer Fenster.

**Rect-&** *Rect* in Eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des Dialog Felds angibt.

*dwInitParam*<br/>
in Gibt den Wert an, der dem Dialogfeld im *LPARAM* -Parameter der WM_INITDIALOG-Nachricht übergeben werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle für das neu erstellte Dialogfeld.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch an das `CDialogImpl` -Objekt angefügt. Um ein modales Dialogfeld zu erstellen, rufen Sie [DoModal](#domodal)auf. Die zweite außer Kraft Setzung oben wird nur mit [CComControl](../../atl/reference/ccomcontrol-class.md)verwendet.

##  <a name="destroywindow"></a>CDialogImpl::D estroywindow

Zerstört ein nicht modalem Dialogfeld.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Dialogfeld erfolgreich gelöscht wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Gibt true zurück, wenn das Dialogfeld erfolgreich gelöscht wurde. andernfalls false.

##  <a name="dialogproc"></a>CDialogImpl::D ialogproc

Diese statische Funktion implementiert die Dialogfeld Prozedur.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
in Das Handle für das Dialogfeld.

*uMsg*<br/>
in Die an das Dialogfeld gesendete Meldung.

*wParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

*lParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Meldung verarbeitet wird. andernfalls false.

### <a name="remarks"></a>Hinweise

`DialogProc`verwendet die standardmäßige Meldungs Zuordnung zum Weiterleiten von Nachrichten an die entsprechenden Handler.

Sie können über `DialogProc` schreiben, um einen anderen Mechanismus für die Verarbeitung von Nachrichten bereitzustellen.

##  <a name="domodal"></a>CDialogImpl::D omodal

Erstellt ein modales Dialogfeld.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
in Das Handle für das Besitzer Fenster. Der Standardwert ist der Rückgabewert der Win32-Funktion [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) .

*dwInitParam*<br/>
in Gibt den Wert an, der dem Dialogfeld im *LPARAM* -Parameter der WM_INITDIALOG-Nachricht übergeben werden soll.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg der Wert des *nretcode* -Parameters, der im Aufrufen von [EndDialog](#enddialog)angegeben wurde. Andernfalls-1.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch an das `CDialogImpl` -Objekt angefügt.

Um ein nicht modalem Dialogfeld zu erstellen, rufen Sie [Create](#create)auf.

##  <a name="enddialog"></a>CDialogImpl:: EndDialog

Zerstört ein modales Dialogfeld.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parameter

*nRetCode*<br/>
in Der Wert, der von [CDialogImpl::D omodal](#domodal)zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Dialogfeld zerstört wird. andernfalls false.

### <a name="remarks"></a>Hinweise

`EndDialog`muss durch die Dialogfeld Prozedur aufgerufen werden. Nachdem das Dialogfeld zerstört wurde, verwendet Windows den Wert von *nretcode* als Rückgabewert für `DoModal`, der das Dialogfeld erstellt hat.

> [!NOTE]
>  Nicht aufgerufen `EndDialog` , um ein nicht modalem Dialogfeld zu zerstören. Aufrufen von [CWindow::D estroywindow](../../atl/reference/cwindow-class.md#destroywindow) .

##  <a name="getdialogproc"></a>CDialogImpl:: getdialogproc

Gibt `DialogProc`die aktuelle Dialogfeld Prozedur zurück.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Dialogfeld Prozedur.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Dialogfeld Prozedur durch ihre eigenen zu ersetzen.

##  <a name="mapdialogrect"></a>CDialogImpl:: mapdialogrect

Konvertiert (ordnet) die Dialogfeld Einheiten des angegebenen Rechtecks in Bildschirm Einheiten (Pixel).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf ein `CRect` -Objekt oder eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur, die die Client Koordinaten des Updates empfangen soll, das den Update Bereich einschließt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Update erfolgreich ist. 0, wenn das Update fehlschlägt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.

### <a name="remarks"></a>Hinweise

Die-Funktion ersetzt die Koordinaten in der `RECT` angegebenen-Struktur durch die konvertierten Koordinaten, wodurch die-Struktur verwendet werden kann, um ein Dialogfeld zu erstellen oder ein Steuerelement in einem Dialogfeld zu positionieren.

##  <a name="onfinalmessage"></a>CDialogImpl:: onfinalmessage

Wird aufgerufen, nachdem die letzte Meldung empfangen `WM_NCDESTROY`wurde (in der Regel).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
in Ein Handle für das Fenster, das zerstört wird.

### <a name="remarks"></a>Hinweise

Beachten Sie Folgendes: Wenn Sie das Objekt bei der Löschung des Fensters automatisch löschen möchten, können Sie **delete this** (hier) aufzurufen.

##  <a name="startdialogproc"></a>CDialogImpl:: startdialogproc

Wird nur einmal aufgerufen, wenn die erste Meldung empfangen wird, um Nachrichten zu verarbeiten, die an das Dialogfeld gesendet werden.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
in Das Handle für das Dialogfeld.

*uMsg*<br/>
in Die an das Dialogfeld gesendete Meldung.

*wParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

*lParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Die Fenster Prozedur.

### <a name="remarks"></a>Hinweise

Nach dem ersten Aufruf von `StartDialogProc` `DialogProc` wird als Dialogfeld Prozedur festgelegt, und weitere Aufrufe können dort durchlaufen werden.

## <a name="see-also"></a>Siehe auch

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
