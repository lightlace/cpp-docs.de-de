---
title: CContainedWindowT-Klasse
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 7fd9a941210407edc3424454b3375040717a05a2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261660"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT-Klasse

Diese Klasse implementiert ein Fenster in einem anderen Objekt enthalten sind.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Parameter

*TBase*<br/>
Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist `CWindow`.

*TWinTraits*<br/>
Eine "traits"-Klasse, die Formatvorlagen für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) ist eine Spezialisierung der `CContainedWindowT`. Wenn Sie die Basisklasse oder die "traits" ändern möchten, verwenden Sie `CContainedWindowT` direkt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Konstruktor. Initialisiert die Datenelemente aus, um anzugeben, welche meldungszuordnung das eigenständige Windows-Meldungen verarbeitet werden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::Create](#create)|Erstellt ein Fenster.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Registriert die Fensterklasse den im Fenster an.|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Änderungen der meldungszuordnung verwendet wird, um den im Fenster Nachrichten zu verarbeiten.|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|
|[CContainedWindowT::WindowProc](#windowproc)|(Statisch) Verarbeitet die Nachrichten gesendet, um den im Fenster.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Gibt an, welche meldungszuordnung das eigenständige Windows-Meldungen verarbeitet werden.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Gibt den Namen einer vorhandenen Fenster-Klasse, die auf dem eine neue Windows-Klasse basieren soll.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|
|[CContainedWindowT::m_pObject](#m_pobject)|Verweist auf das enthaltende Objekt.|

## <a name="remarks"></a>Hinweise

`CContainedWindowT` implementiert ein Fenster in einem anderen Objekt enthalten sind. `CContainedWindowT`ist die Fenster Beispielprozedur verwendet, die eine Nachricht in dem Objekt um direkte Nachrichten an die entsprechenden Handler zugeordnet. Beim Erstellen einer `CContainedWindowT` -Objekts können Sie angeben, welche meldungszuordnung verwendet werden soll.

`CContainedWindowT` ermöglicht Ihnen die Erstellung ein neues Fensters durch Erstellung einer übergeordneten Klasse eine vorhandene Fensterklasse. Die `Create` Methode zum ersten Mal eine Fensterklasse, die auf einer vorhandenen Klasse basiert, verwendet jedoch registriert `CContainedWindowT::WindowProc`. `Create` erstellt dann ein Fenster, die basierend auf dieses neue Windows-Klasse. Jede Instanz des `CContainedWindowT` können Sie die übergeordnete Klasse eine andere Fensterklasse.

`CContainedWindowT` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CContainedWindowT`-Objekt an und ändert die Fensterprozedur in `CContainedWindowT::WindowProc`. Jede Instanz von `CContainedWindowT` kann ein anderes Fenster unterordnen.

> [!NOTE]
>  Für jeden angegebenen `CContainedWindowT` Objekt, rufen Sie entweder `Create` oder `SubclassWindow`. Sie sollten nicht beide Methoden für das gleiche Objekt aufrufen.

Bei Verwendung der **Hinzufügen des Steuerelements basierend auf** option in der ATL-Projektassistent vom Assistenten werden automatisch hinzugefügt. eine `CContainedWindowT` Datenmember der Klasse, die Implementierung des Steuerelements. Das folgende Beispiel zeigt, wie der im Fenster deklariert wird:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Weitere Informationen finden Sie unter|Siehe|
|--------------------------------|---------|
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/desktop/winmsg/windows) und weiteren Themen im Windows SDK|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT

Der Konstruktor initialisiert die Datenmember.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>Parameter

*lpszClassName*<br/>
[in] Der Name einer vorhandenen Fenster-Klasse, die der im Fenster basiert.

*pObject*<br/>
[in] Ein Zeiger auf das enthaltende Objekt, das die meldungszuordnung deklariert. Klasse des Objekts abgeleitet muss [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] Identifiziert die meldungszuordnung, die den im Fenster Nachrichten verarbeitet werden. Der Standardwert 0 (null) gibt an, der Standard-meldungszuordnung, die mit deklariert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Mit Verwendung einer alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.

### <a name="remarks"></a>Hinweise

Wenn Sie ein neues Fenster über erstellen möchten [erstellen](#create), müssen Sie den Namen der für eine vorhandene Fensterklasse übergeben die *"lpszclassname"* Parameter. Ein Beispiel finden Sie unter den [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Übersicht.

Es gibt drei Konstruktoren:

- Der Konstruktor mit drei Argumenten wird in der Regel aufgerufen.

- Der Konstruktor mit zwei Argumenten verwendet den Klassennamen aus `TBase::GetWndClassName`.

- Der Konstruktor ohne Argumente wird verwendet, wenn Sie die Argumente später eingeben möchten. Sie müssen die Fensterklassenname Nachricht Map-Objekt und die ID der Nachricht-Zuordnung angeben, wenn Sie später Aufrufen `Create`.

Wenn Sie eine Unterklasse von einem vorhandenen Fenster über [SubclassWindow](#subclasswindow), *"lpszclassname"* Wert wird nicht verwendet; deshalb können Sie NULL für diesen Parameter übergeben.

##  <a name="create"></a>  CContainedWindow:: Create auf

Aufrufe [RegisterWndSuperclass](#registerwndsuperclass) eine Fensterklasse registrieren, die auf einer vorhandenen Klasse basiert, verwendet jedoch [CContainedWindowT::WindowProc](#windowproc).

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Parameter

*lpszClassName*<br/>
[in] Der Name einer vorhandenen Fenster-Klasse, die der im Fenster basiert.

*pObject*<br/>
[in] Ein Zeiger auf das enthaltende Objekt, das die meldungszuordnung deklariert. Klasse des Objekts abgeleitet muss [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] Identifiziert die meldungszuordnung, die den im Fenster Nachrichten verarbeitet werden. Der Standardwert 0 (null) gibt an, der Standard-meldungszuordnung, die mit deklariert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Mit Verwendung einer alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.

*hWndParent*<br/>
[in] Das Handle für das übergeordnete Element oder Besitzer-Fenster.

*rect*<br/>
[in] Ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position des Fensters angeben. Die `RECT` Zeiger oder Verweis übergeben werden kann.

*szWindowName*<br/>
[in] Gibt den Namen des Fensters. Der Standardwert ist NULL.

*dwStyle*<br/>
[in] Der Stil des Fensters. Der Standardwert ist WS_CHILD &#124; WS_VISIBLE. Eine Liste der möglichen Werte, finden Sie unter [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK.

*dwExStyle*<br/>
[in] Der erweiterte Fensterstil. Der Standardwert ist 0, d. h. keine erweiterten Stil. Eine Liste der möglichen Werte, finden Sie unter [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.

*MenuOrID*<br/>
[in] Für ein untergeordnetes Fenster den Fenster-Bezeichner. Für ein Fenster der obersten Ebene ein Menühandle für das Fenster. Der Standardwert ist **0 HE**.

*lpCreateParam*<br/>
[in] Ein Zeiger auf die fenstererstellung Daten. Eine vollständige Beschreibung finden Sie unter der Beschreibung für den letzten Parameter um [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle für das neu erstellte Fenster; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Der vorhandene Fensterklassenname wird gespeichert, [M_lpszClassName](#m_lpszclassname). `Create` erstellt dann ein Fenster, die basierend auf diese neue Klasse. Das neu erstellte Fenster wird automatisch angefügt, um die `CContainedWindowT` Objekt.

> [!NOTE]
>  Rufen Sie keine `Create` , wenn Sie bereits aufgerufen haben [SubclassWindow](#subclasswindow).

> [!NOTE]
>  Wenn 0, als Wert für verwendet wird die *MenuOrID* -Parameter muss als 0 HE angegeben werden (Standardwert), einen Compilerfehler zu vermeiden.

##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc

Wird aufgerufen, indem [WindowProc](#windowproc) zum Verarbeiten von Nachrichten von der nachrichtenzuordnung nicht verarbeitet.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*uMsg*<br/>
[in] Die Meldung, die an das Fenster gesendet wird.

*wParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `DefWindowProc` Aufrufe der [CallWindowProc](/windows/desktop/api/winuser/nf-winuser-callwindowproca) Win32-Funktion zum Senden von Informationen der Nachricht an die Fensterprozedur, die im angegebenen [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage

Gibt die aktuelle Nachricht (`m_pCurrentMsg`).

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Nachricht, die innerhalb der `MSG` Struktur.

##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID

Enthält den Bezeichner der Nachricht Zuordnung wird derzeit für den im Fenster verwendet.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Hinweise

Diese nachrichtenzuordnung muss in dem Objekt deklariert werden.

Die Standard-meldungszuordnung, die mit deklariert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), stets identifiziert, von 0 (null). Eine alternative meldungszuordnung, mit dem deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), wird durch identifiziert `msgMapID`.

`m_dwMsgMapID` wird zuerst vom Konstruktor initialisiert und kann geändert werden, durch den Aufruf [SwitchMessageMap](#switchmessagemap). Ein Beispiel finden Sie unter den [CContainedWindowT-Übersicht](../../atl/reference/ccontainedwindowt-class.md).

##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName

Gibt den Namen einer vorhandenen Fenster-Klasse.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Hinweise

Bei der Erstellung eines Fensters [erstellen](#create) registriert eine neue Windows-Klasse, die auf diesem vorhandenen Klasse basiert, verwendet jedoch [CContainedWindowT::WindowProc](#windowproc).

`m_lpszClassName` wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie unter den [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Übersicht.

##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc

Wenn Sie der im Fenster als Unterklasse definiert ist, `m_pfnSuperWindowProc` verweist auf die ursprüngliche Fensterprozedur der Fensterklasse.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Hinweise

Wenn das Fenster enthaltene Komponente ist, d. h. es basiert auf eine Fensterklasse, die eine vorhandene Klasse, ändert `m_pfnSuperWindowProc` verweist auf die vorhandene Fensterklasse Fensterprozedur.

Die [DefWindowProc](#defwindowproc) Methode sendet Informationen an die Fensterprozedur, die in gespeicherten `m_pfnSuperWindowProc`.

##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject

Verweist auf das Objekt mit der `CContainedWindowT` Objekt.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Hinweise

Dieser Container, dessen Klasse ableiten muss [CMessageMap](../../atl/reference/cmessagemap-class.md), deklariert die meldungszuordnung, die von den im Fenster verwendet.

`m_pObject` wird vom Konstruktor initialisiert werden. Ein Beispiel finden Sie unter den [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Übersicht.

##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass

Wird aufgerufen, indem [erstellen](#create) registriert die Fensterklasse des Fensters enthalten.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg wird ein Atom, die eindeutig identifiziert die Fensterklasse registriert wird; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Fensterklasse verwendet jedoch basiert auf einer vorhandenen Klasse [CContainedWindowT::WindowProc](#windowproc). Verfahren für die vorhandene Fensterklasse Namen und die Fenster werden gespeichert, [M_lpszClassName](#m_lpszclassname) und [M_pfnSuperWindowProc](#m_pfnsuperwindowproc)bzw.

##  <a name="subclasswindow"></a>  SubclassWindow

Unterklassen des Fensters identifizierte *hWnd* und fügt es der `CContainedWindowT` Objekt.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
[in] Das Handle des Fensters in Unterklassen unterteilt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn das Fenster erfolgreich als Unterklasse definiert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Fenster als Unterklasse verwendet jetzt [CContainedWindowT::WindowProc](#windowproc). Die ursprüngliche Fensterprozedur wird gespeichert, [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

> [!NOTE]
>  Rufen Sie keine `SubclassWindow` , wenn Sie bereits aufgerufen haben [erstellen](#create).

##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap

Ändert die meldungszuordnung zum Verarbeiten von Nachrichten von den im Fenster verwendet wird.

```
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Parameter

*dwMsgMapID*<br/>
[in] Der Nachrichtenbezeichner zuordnen. Verwenden Sie die Standard-meldungszuordnung, die mit deklariert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), übergeben Sie 0 (null). Mit Verwendung einer alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.

### <a name="remarks"></a>Hinweise

Die meldungszuordnung muss in dem Objekt definiert werden.

Legen Sie zu Beginn die Map-Nachrichten-ID im Konstruktor.

##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow

Trennt die untergeordnetes Fenster von der `CContainedWindowT` -Objekt und stellt die ursprüngliche Fensterprozedur, gespeichert [M_pfnSuperWindowProc](#m_pfnsuperwindowproc).

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Parameter

*bForce*<br/>
[in] Festlegen auf "true"-Force-die ursprüngliche Fensterprozedur wiederhergestellt werden, wenn die Fensterprozedur für diesen `CContainedWindowT` Objekt ist derzeit nicht aktiv. Wenn *bForce* die Fensterprozedur auf "false" festgelegt ist, die für diese `CContainedWindowT` Objekt ist derzeit nicht aktiv, wird die ursprüngliche Fensterprozedur nicht wiederhergestellt werden.

### <a name="return-value"></a>Rückgabewert

Das Handle des Fensters, das zuvor in Unterklassen unterteilt. Wenn *bForce* die Fensterprozedur auf "false" festgelegt ist, die für diese `CContainedWindowT` Objekt ist derzeit nicht aktiv ist, gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur, wenn Sie möchten, um die ursprüngliche Fensterprozedur wiederherzustellen, bevor das Fenster zerstört wird. Andernfalls [WindowProc](#windowproc) automatisch dieser Vorgang erfolgt, wenn das Fenster zerstört wird.

##  <a name="windowproc"></a>  CContainedWindowT::WindowProc

Diese statische Methode implementiert die Fensterprozedur.

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

*wParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

`WindowProc` leitet die Nachrichten in die nachrichtenzuordnung identifizierte [M_dwMsgMapID](#m_dwmsgmapid). Bei Bedarf `WindowProc` Aufrufe [DefWindowProc](#defwindowproc) für zusätzliche die Nachrichtenverarbeitung.

## <a name="see-also"></a>Siehe auch

[CWindow-Klasse](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap-Klasse](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
