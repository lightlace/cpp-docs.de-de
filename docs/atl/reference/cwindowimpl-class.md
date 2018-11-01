---
title: CWindowImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: 0a1d0c79e97cf9f9cb0c2b0c6b140654deb4c227
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454651"
---
# <a name="cwindowimpl-class"></a>CWindowImpl-Klasse

Stellt Methoden für das Erstellen eines Fensters oder von Unterklassen eines Fensters bereit

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die neue Klasse, die von `CWindowImpl` abgeleitet ist.

*TBase*<br/>
Die Basisklasse der Klasse. Standardmäßig ist die Basisklasse [CWindow](../../atl/reference/cwindow-class.md).

*TWinTraits*<br/>
Ein ["traits"-Klasse](../../atl/understanding-window-traits.md) , Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWindowImpl:: Create](#create)|Erstellt ein Fenster.|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT-Methoden

|||
|-|-|
|[DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|
|[GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|
|[GetWindowProc](#getwindowproc)|Gibt die aktuelle Fensterprozedur zurück.|
|[OnFinalMessage](#onfinalmessage)|Wird aufgerufen, nachdem die letzte Nachricht empfangen wird (in der Regel WM_NCDESTROY).|
|[SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|
|[UnsubclassWindow auf](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|

### <a name="static-methods"></a>Statische Methoden

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|Gibt eine statische Instanz der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), der die fensterklasseninformationen verwaltet.|
|[WindowProc](#windowproc)|Verarbeitet die Nachrichten, die an das Fenster gesendet werden.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|

## <a name="remarks"></a>Hinweise

Sie können `CWindowImpl` um ein vorhandenes Fenster ein Fenster oder eine Unterklasse zu erstellen. die `CWindowImpl` Fensterprozedur verwendet eine nachrichtenzuordnung, um Nachrichten an die entsprechenden Handler zu leiten.

`CWindowImpl::Create` erstellt ein Fenster, die basierend auf der fensterklasseninformationen, die von verwalteten [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` enthält die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) Makro, das bedeutet, dass `CWndClassInfo` registriert eine neue Windows-Klasse. Wenn Sie Informationen für eine vorhandene Fensterklasse erstellen möchten, leiten Sie eine Klasse von `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro. In diesem Fall wird mit `CWndClassInfo` eine Fensterklasse registriert, die auf einer vorhandenen Klasse basiert, aber `CWindowImpl::WindowProc` verwendet. Zum Beispiel:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  Da `CWndClassInfo` nur die Informationen für eine Fensterklasse verwaltet, basiert jedes Fenster, das durch eine Instanz von `CWindowImpl` erstellt wird, auf der gleichen Fensterklasse.

`CWindowImpl` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CWindowImpl`-Objekt an und ändert die Fensterprozedur in `CWindowImpl::WindowProc`. Jede Instanz von `CWindowImpl` kann ein anderes Fenster unterordnen.

> [!NOTE]
>  Für jeden angegebenen `CWindowImpl` Objekt, rufen Sie entweder `Create` oder `SubclassWindow`. Rufen Sie nicht beide Methoden für dasselbe Objekt auf.

Zusätzlich zu `CWindowImpl`, ATL stellt [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) in einem anderen Objekt erstellen, ein Fenster, das enthalten ist.

Dem Basisklassendestruktor (~ `CWindowImplRoot`) wird sichergestellt, dass das Fenster nicht mehr vorhanden ist, bevor das Objekt zerstört wird.

`CWindowImpl` leitet sich von `CWindowImplBaseT`, die sich daraus ableitet `CWindowImplRoot`, die sich daraus ableitet `TBase` und [CMessageMap](../../atl/reference/cmessagemap-class.md).

|Weitere Informationen finden Sie unter|Siehe|
|--------------------------------|---------|
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="create"></a>  CWindowImpl:: Create

Erstellt ein Fenster, die basierend auf einem neuen Fensterklasse.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
[in] Das Handle für das übergeordnete Element oder Besitzer-Fenster.

*Rect*<br/>
[in] Ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` Zeiger oder Verweis übergeben werden kann.

*szWindowName*<br/>
[in] Gibt den Namen des Fensters. Der Standardwert ist NULL.

*dwStyle*<br/>
[in] Der Stil des Fensters. Dieser Wert wird mit der Formatvorlage, die von der "traits"-Klasse bereitgestellt wird, für das Fenster kombiniert. Der Standardwert bietet die "traits"-Klasse vollständige Kontrolle über den Stil an. Eine Liste der möglichen Werte, finden Sie unter [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK.

*dwExStyle*<br/>
[in] Der erweiterte Fensterstil. Dieser Wert wird mit der Formatvorlage, die von der "traits"-Klasse bereitgestellt wird, für das Fenster kombiniert. Der Standardwert bietet die "traits"-Klasse vollständige Kontrolle über den Stil an. Eine Liste der möglichen Werte, finden Sie unter [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.

*MenuOrID*<br/>
[in] Für ein untergeordnetes Fenster den Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menühandle für das Fenster. Der Standardwert ist **0 HE**.

*lpCreateParam*<br/>
[in] Ein Zeiger auf die fenstererstellung Daten. Eine vollständige Beschreibung finden Sie unter der Beschreibung für den letzten Parameter um [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle für das neu erstellte Fenster. Andernfalls NULL.

### <a name="remarks"></a>Hinweise

`Create` zuerst registriert die Fensterklasse auf, wenn er noch nicht registriert wurde. Das neu erstellte Fenster wird automatisch angefügt, um die `CWindowImpl` Objekt.

> [!NOTE]
>  Rufen Sie keine `Create` , wenn Sie bereits aufgerufen haben [SubclassWindow](#subclasswindow).

Um eine Fensterklasse verwenden, die auf eine vorhandene Fensterklasse basieren, leiten Sie eine Klasse von `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro. Die vorhandene Fensterklasse Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc). Weitere Informationen finden Sie unter den [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Übersicht.

> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die *MenuOrID* -Parameter muss als 0 HE angegeben werden (Standardwert), einen Compilerfehler zu vermeiden.

##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc

Wird aufgerufen, indem [WindowProc](#windowproc) zum Verarbeiten von Nachrichten von der nachrichtenzuordnung nicht verarbeitet.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Parameter

*uMsg*<br/>
[in] Die Meldung, die an das Fenster gesendet wird.

*wParam-Parameter*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `DefWindowProc` Aufrufe der [CallWindowProc](https://msdn.microsoft.com/library/windows/desktop/ms633571) Win32-Funktion zum Senden von Informationen der Nachricht an die Fensterprozedur, die im angegebenen [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

Die Funktion ohne Parameter ruft automatisch die erforderlichen Parameter aus der aktuellen Nachricht ab.

##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage

Gibt die aktuelle Nachricht, die innerhalb der `MSG` Struktur.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Meldung.

##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc

Gibt `WindowProc`, die aktuelle Fensterprozedur.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Fensterprozedur.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Fensterprozedur durch Ihre eigenen zu ersetzen.

##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo

Wird aufgerufen, indem [erstellen](#create) auf die fensterklasseninformationen zugreifen.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Rückgabewert

Eine statische Instanz der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `CWindowImpl` ruft diese Methode über die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) Makro, das eine neue Windows-Klasse angibt.

Auf der übergeordneten Klasse eine vorhandene Fensterklasse, ableiten der Klasse aus `CWindowImpl` und enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro überschreiben `GetWndClassInfo`. Weitere Informationen finden Sie unter den [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Übersicht.

Sie können neben dem Verwenden der Makros DECLARE_WND_CLASS und DECLARE_WND_SUPERCLASS, überschreiben `GetWndClassInfo` durch Ihre eigene Implementierung.

##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc

Abhängig von dem Fenster verweist auf eines der folgenden Verfahren Fenster.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Hinweise

|Typ des Fensters|Die Fensterprozedur|
|--------------------|----------------------|
|Ein Fenster auf der Grundlage von einer neue Fensterklasse, die durch die angegebenen die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) Makro.|Die [DefWindowProc](/windows/desktop/api/winuser/nf-winuser-defwindowproca) Win32-Funktion.|
|Ein Fenster auf der Grundlage von einer Fensterklasse, die eine vorhandene Klasse, die durch die angegebenen ändert die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro.|Die Fensterprozedur der vorhandene Fensterklasse.|
|Ein untergeordnetes Fenster.|Der als Unterklasse ursprüngliche Fensterprozedur von Windows.|

[CWindowImpl::DefWindowProc](#defwindowproc) telemetrienachricht Informationen auf die Fensterprozedur, die in gespeicherten `m_pfnSuperWindowProc`.

##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage

Wird aufgerufen, nachdem die letzte Meldung erhalten (in der Regel WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Ein Handle für das Fenster zerstört wird.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung des `OnFinalMessage` hat keine Auswirkungen, aber Sie können diese Funktion, um die Bereinigung behandeln, vor dem Zerstören eines Fensters überschreiben. Wenn bei der fensterzerstörung Ihr Objekt automatisch gelöscht werden sollen, können Sie aufrufen **löschen;** in dieser Funktion.

##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow

Unterklassen des Fensters identifizierte *hWnd* und fügt es der `CWindowImpl` Objekt.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Das Handle des Fensters in Unterklassen unterteilt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn das Fenster erfolgreich als Unterklasse definiert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Fenster als Unterklasse verwendet jetzt [CWindowImpl:: WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

> [!NOTE]
>  Rufen Sie keine `SubclassWindow` , wenn Sie bereits aufgerufen haben [erstellen](#create).

##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow

Trennt die untergeordnetes Fenster von der `CWindowImpl` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Rückgabewert

Das Handle des Fensters, das zuvor in Unterklassen unterteilt.

##  <a name="windowproc"></a>  CWindowImpl:: WindowProc

Diese statischen Funktion implementiert die Fensterprozedur.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Das Handle des Fensters.

*uMsg*<br/>
[in] Die Meldung, die an das Fenster gesendet wird.

*wParam-Parameter*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

`WindowProc` verwendet die Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) um Nachrichten an die entsprechenden Handler zu leiten. Bei Bedarf `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für zusätzliche die Nachrichtenverarbeitung. Wenn die letzte Nachricht nicht behandelt wird, `WindowProc` bewirkt Folgendes:

- Führt unsubclassing, wenn das Fenster unsubclassed wurde.

- Löscht `m_hWnd`.

- Aufrufe [OnFinalMessage](#onfinalmessage) , bevor das Fenster zerstört wird.

Sie können außer Kraft setzen `WindowProc` , geben Sie einen anderen Mechanismus zum Verarbeiten von Nachrichten.

## <a name="see-also"></a>Siehe auch

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
