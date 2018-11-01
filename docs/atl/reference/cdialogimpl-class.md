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
ms.openlocfilehash: 3ac8037e032112e269332d2bbf9c2065ade84ded
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572095"
---
# <a name="cdialogimpl-class"></a>CDialogImpl-Klasse

Diese Klasse stellt Methoden zum Erstellen ein modales oder nicht modales Dialogfeld an.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `CDialogImpl`.

*TBase*<br/>
Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Erstellen](#create)|Erstellt ein nicht modales Dialogfeld an.|
|[DestroyWindow](#destroywindow)|Zerstört ein nicht modales Dialogfeld an.|
|[DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|
|[EndDialog](#enddialog)|Zerstört ein modales Dialogfeld an.|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT-Methoden

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Gibt die aktuelle Dialogfeldprozedur zurück.|
|[MapDialogRect](#mapdialogrect)|Ordnet die Dialogfeld-Einheiten des angegebenen Rechtecks Bildschirm Einheiten (in Pixel).|
|[OnFinalMessage](#onfinalmessage)|Wird aufgerufen, nachdem die letzte Meldung erhalten, in der Regel WM_NCDESTROY.|

### <a name="static-functions"></a>Statische Funktionen

|||
|-|-|
|[DialogProc-Funktion](#dialogproc)|Verarbeitet die Nachrichten gesendet, um das Dialogfeld.|
|[StartDialogProc](#startdialogproc)|Wird aufgerufen, wenn die erste Nachricht empfangen wird, zum Verarbeiten von Nachrichten gesendet, um das Dialogfeld.|

## <a name="remarks"></a>Hinweise

Mit `CDialogImpl` können Sie ein modales oder nicht modales Dialogfeld erstellen. `CDialogImpl` enthält die Dialogfeldprozedur, die die Standard-meldungszuordnung verwendet werden, um Nachrichten an die entsprechenden Handler zu leiten.

Der Destruktor der Basisklasse `~CWindowImplRoot` wird sichergestellt, dass das Fenster vor dem Zerstören des Objekts aufgetreten ist.

`CDialogImpl` wird von `CDialogImplBaseT` abgeleitet, was wiederum von `CWindowImplRoot` abgeleitet wird.

> [!NOTE]
>  Die Klasse muss definiert eine `IDD` Member, der angibt, die Dialogfeld Vorlage-Ressourcen-ID ATL-Projektassistenten fügt z. B. die folgende Zeile automatisch auf die Klasse hinzu:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

in denen `MyDlg` ist die **Kurznamen** in des Assistenten eingegebenen **Namen** Seite.

|Weitere Informationen finden Sie unter|Siehe|
|--------------------------------|---------|
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|
|Mithilfe der Dialogfelder in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|
|Dialogfelder|[Dialogfelder](https://msdn.microsoft.com/library/windows/desktop/ms632588) und weiteren Themen im Windows SDK|

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="create"></a>  CDialogImpl::Create

Erstellt ein nicht modales Dialogfeld an.

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
[in] Das Handle für das besitzende Fenster.

**RECT &** *Rect* [in] ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die Größe und Position des Dialogfelds angibt.

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

### <a name="return-value"></a>Rückgabewert

Das Handle für das neu erstellte Dialogfeld.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt. Rufen Sie zum Erstellen eines modalen Dialogfelds [DoModal](#domodal). Die oben genannten beim zweiten Überschreiben wird verwendet, nur mit [CComControl](../../atl/reference/ccomcontrol-class.md).

##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow

Zerstört ein nicht modales Dialogfeld an.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Dialogfeld erfolgreich gelöscht wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Gibt TRUE zurück, wenn das Dialogfeld erfolgreich gelöscht wurde. andernfalls "false".

##  <a name="dialogproc"></a>  CDialogImpl::DialogProc

Diese statischen Funktion implementiert die Dialogfeldprozedur.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Das Handle für das Dialogfeld.

*uMsg*<br/>
[in] Die Nachricht gesendet, um das Dialogfeld.

*wParam-Parameter*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

True, wenn die Nachricht verarbeitet wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

`DialogProc` verwendet die Standard-meldungszuordnung, um Nachrichten an die entsprechenden Handler zu leiten.

Sie können außer Kraft setzen `DialogProc` , geben Sie einen anderen Mechanismus zum Verarbeiten von Nachrichten.

##  <a name="domodal"></a>  CDialogImpl::DoModal

Erstellt ein modales Dialogfeld an.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
[in] Das Handle für das besitzende Fenster. Der Standardwert ist der Rückgabewert von der [GetActiveWindow](https://msdn.microsoft.com/library/windows/desktop/ms646292) Win32-Funktion.

*dwInitParam*<br/>
[in] Gibt den Wert zu übergeben, um das Dialogfeld in der *lParam* -Parameter der WM_INITDIALOG-Meldung.

### <a name="return-value"></a>Rückgabewert

Im Erfolgsfall den Wert des der *nRetCode* Parameter im Aufruf angegeben [EndDialog](#enddialog). Andernfalls -1.

### <a name="remarks"></a>Hinweise

Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt.

Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).

##  <a name="enddialog"></a>  CDialogImpl::EndDialog

Zerstört ein modales Dialogfeld an.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parameter

*nRetCode*<br/>
[in] Der Wert, der von zurückgegeben werden [CDialogImpl::DoModal](#domodal).

### <a name="return-value"></a>Rückgabewert

True, wenn das Dialogfeld zerstört wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

`EndDialog` muss über die Dialogfeldprozedur aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der *nRetCode* als Rückgabewert für `DoModal`, dem Sie das Dialogfeld erstellt.

> [!NOTE]
>  Rufen Sie keine `EndDialog` zum Zerstören eines nicht modalen Dialogfelds. Rufen Sie [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) stattdessen.

##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc

Gibt `DialogProc`, die aktuelle Dialogfeldprozedur.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Dialogfeldprozedur.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Dialogfeldprozedur mit Ihrer eigenen zu ersetzen.

##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect

Konvertiert (Maps) die Dialogfeld-Einheiten des angegebenen Rechtecks Bildschirm Einheiten (in Pixel).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `CRect` Objekt oder [RECT](../../mfc/reference/rect-structure.md) -Struktur, die die Clientkoordinaten des Updates zu erhalten, die dem Aktualisierungsbereich umschließt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Update erfolgreich ausgeführt wird; 0, wenn das Update fehlschlägt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.

### <a name="remarks"></a>Hinweise

Die Funktion ersetzt die Koordinaten in der angegebenen `RECT` Struktur mit den Koordinaten konvertierten, sodass die Struktur, die zum Erstellen eines Dialogfelds oder position eines Steuerelements in einem Dialogfeld verwendet werden.

##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage

Wird aufgerufen, nachdem die letzte Meldung erhalten (in der Regel `WM_NCDESTROY`).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Ein Handle für das Fenster zerstört wird.

### <a name="remarks"></a>Hinweise

Beachten Sie, wenn das Objekt bei der fensterzerstörung automatisch gelöscht werden sollen, können Sie aufrufen **löschen;** hier.

##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc

Wenn die erste Nachricht, zum Verarbeiten von Nachrichten gesendet, um das Dialogfeld empfangen wird, nur einmal aufgerufen.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Das Handle für das Dialogfeld.

*uMsg*<br/>
[in] Die Nachricht gesendet, um das Dialogfeld.

*wParam-Parameter*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Die Fensterprozedur.

### <a name="remarks"></a>Hinweise

Nach dem ersten Aufruf von `StartDialogProc`, `DialogProc` festgelegt ist, wie eine Dialogfeldprozedur und weitere Aufrufe dorthin navigieren.

## <a name="see-also"></a>Siehe auch

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)