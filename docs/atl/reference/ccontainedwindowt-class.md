---
title: Ccontainedwindowt-Klasse
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
ms.openlocfilehash: 2eae6e149cf6f7422d0653c1c15f46985d8d55c8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496847"
---
# <a name="ccontainedwindowt-class"></a>Ccontainedwindowt-Klasse

Diese Klasse implementiert ein Fenster, das in einem anderen-Objekt enthalten ist.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Parameter

*Tbase*<br/>
Die Basisklasse der neuen Klasse. Die Standardbasis Klasse ist `CWindow`.

*TWinTraits*<br/>
Eine Eigenschaften Klasse, die Stile für das Fenster definiert. Die Standardeinstellung ist `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) ist eine Spezialisierung von `CContainedWindowT`. Wenn Sie die Basisklasse oder die Merkmale ändern möchten, verwenden `CContainedWindowT` Sie direkt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Konstruktor. Initialisiert Datenmember, um anzugeben, welche Meldungs Zuordnung die Nachrichten des enthaltenen Fensters verarbeitet.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::Create](#create)|Erstellt ein Fenster.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Stellt die Standardverarbeitung von Nachrichten bereit.|
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Die gibt die aktuelle Nachricht zurück.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Registriert die Fenster Klasse des enthaltenen Fensters.|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Erstellt Unterklassen eines Fensters.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Ändert, welche Meldungs Zuordnung zum Verarbeiten der Nachrichten des enthaltenen Fensters verwendet wird.|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Stellt ein zuvor untergeordnetes Fenster wieder her.|
|[CContainedWindowT::WindowProc](#windowproc)|Kum Verarbeitet Nachrichten, die an das enthaltene Fenster gesendet werden.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Gibt an, welche Meldungs Zuordnung die Nachrichten des enthaltenen Fensters verarbeitet.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Gibt den Namen einer vorhandenen Fenster Klasse an, auf der eine neue Fenster Klasse basieren soll.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|
|[CContainedWindowT::m_pObject](#m_pobject)|Verweist auf das enthaltende Objekt.|

## <a name="remarks"></a>Hinweise

`CContainedWindowT`implementiert ein Fenster, das in einem anderen Objekt enthalten ist. `CContainedWindowT`die Fenster Prozedur verwendet eine Meldungs Zuordnung im enthaltenden Objekt, um Nachrichten an die entsprechenden Handler weiterzuleiten. Beim Erstellen eines `CContainedWindowT` -Objekts geben Sie an, welche Meldungs Zuordnung verwendet werden soll.

`CContainedWindowT`ermöglicht es Ihnen, ein neues Fenster zu erstellen, indem Sie eine vorhandene Fenster Klasse überlagern. Die `Create` -Methode registriert zuerst eine Fenster Klasse, die auf einer vorhandenen Klasse basiert, `CContainedWindowT::WindowProc`aber verwendet. `Create`Anschließend wird ein Fenster erstellt, das auf dieser neuen Fenster Klasse basiert. Jede Instanz von `CContainedWindowT` kann eine andere Fenster Klasse überlagern.

`CContainedWindowT` unterstützt auch die Erstellung von Unterklassen von Fenstern. Die `SubclassWindow`-Methode fügt ein vorhandenes Fenster an das `CContainedWindowT`-Objekt an und ändert die Fensterprozedur in `CContainedWindowT::WindowProc`. Jede Instanz von `CContainedWindowT` kann ein anderes Fenster unterordnen.

> [!NOTE]
>  Für ein bestimmtes `CContainedWindowT` Objekt wird entweder `Create` oder `SubclassWindow`aufgerufen. Sie sollten nicht beide Methoden für dasselbe Objekt aufrufen.

Wenn Sie die Option **Steuerelement auf Grundlage von hinzufügen** im ATL-Projekt-Assistenten verwenden, fügt der `CContainedWindowT` Assistent der-Klasse, die das Steuerelement implementiert, automatisch einen Datenmember hinzu. Im folgenden Beispiel wird gezeigt, wie das enthaltene Fenster deklariert wird:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Weitere Informationen finden Sie unter|Siehe|
|--------------------------------|---------|
|Erstellen von Steuerelementen|[ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md)|
|Verwenden von Fenstern in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/win32/winmsg/windows) und nachfolgende Themen in der Windows SDK|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Anforderungen

**Header:** atlwin. h

##  <a name="ccontainedwindowt"></a>Ccontainedwindowt:: ccontainedwindowt

Der-Konstruktor initialisiert Datenmember.

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
in Der Name einer vorhandenen Fenster Klasse, auf der das enthaltene Fenster basieren soll.

*pObject*<br/>
in Ein Zeiger auf das enthaltende Objekt, das die Meldungs Zuordnung deklariert. Die Klasse dieses Objekts muss von [cmessagemap](../../atl/reference/cmessagemap-class.md)abgeleitet werden.

*dwMsgMapID*<br/>
in Gibt die Meldungs Zuordnung an, mit der die Nachrichten des enthaltenen Fensters verarbeitet werden. Der Standardwert 0 gibt die mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)deklarierte Standard Meldungs Zuordnung an. Wenn Sie eine Alternative Nachrichten Zuordnung verwenden möchten, die mit [ALT_MSG_MAP (msgmapid)](message-map-macros-atl.md#alt_msg_map)deklariert wurde, übergeben `msgMapID`Sie.

### <a name="remarks"></a>Hinweise

Wenn Sie ein neues Fenster mithilfe von [Create](#create)erstellen möchten, müssen Sie den Namen einer vorhandenen Fenster Klasse für den *lpszClassName* -Parameter übergeben. Ein Beispiel finden Sie in der Übersicht über [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) .

Es gibt drei Konstruktoren:

- Der Konstruktor mit drei Argumenten wird in der Regel als bezeichnet.

- Der-Konstruktor mit zwei Argumenten verwendet den Klassennamen `TBase::GetWndClassName`aus.

- Der Konstruktor ohne Argumente wird verwendet, wenn Sie die Argumente später bereitstellen möchten. Sie müssen den Fenster Klassennamen, das Nachrichten Zuordnungs Objekt und die Meldungs Zuordnungs-ID `Create`angeben, wenn Sie einen späteren Zeitpunkt abrufen.

Wenn Sie ein vorhandenes Fenster über ein [Unterklassen Fenster](#subclasswindow)unterteilen, wird der Wert *lpszClassName* nicht verwendet. Daher können Sie NULL für diesen Parameter übergeben.

##  <a name="create"></a>Ccontainedwindowt:: Create

Ruft [registerwndsuperclass](#registerwndsuperclass) auf, um eine Fenster Klasse zu registrieren, die auf einer vorhandenen Klasse basiert, aber [ccontainedwindowt:: WindowProc](#windowproc)verwendet.

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
in Der Name einer vorhandenen Fenster Klasse, auf der das enthaltene Fenster basieren soll.

*pObject*<br/>
in Ein Zeiger auf das enthaltende Objekt, das die Meldungs Zuordnung deklariert. Die Klasse dieses Objekts muss von [cmessagemap](../../atl/reference/cmessagemap-class.md)abgeleitet werden.

*dwMsgMapID*<br/>
in Gibt die Meldungs Zuordnung an, mit der die Nachrichten des enthaltenen Fensters verarbeitet werden. Der Standardwert 0 gibt die mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)deklarierte Standard Meldungs Zuordnung an. Wenn Sie eine Alternative Nachrichten Zuordnung verwenden möchten, die mit [ALT_MSG_MAP (msgmapid)](message-map-macros-atl.md#alt_msg_map)deklariert wurde, übergeben `msgMapID`Sie.

*hWndParent*<br/>
in Das Handle für das übergeordnete Fenster oder Besitzer Fenster.

*Rect*<br/>
in Eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position des Fensters angibt. Der `RECT` kann als Zeiger oder als Verweis übermittelt werden.

*szWindowName*<br/>
in Gibt den Namen des Fensters an. Der Standardwert ist NULL.

*dwStyle*<br/>
in Der Stil des Fensters. Der Standardwert ist WS_CHILD &#124; WS_VISIBLE. Eine Liste möglicher Werte finden Sie unter " [kreatewindow](/windows/win32/api/winuser/nf-winuser-createwindoww) " in der Windows SDK.

*dwExStyle*<br/>
in Der erweiterte Fenster Stil. Der Standardwert ist 0, d. h. kein erweiterter Stil. Eine Liste möglicher Werte finden Sie unter " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) " in der Windows SDK.

*Menuorid*<br/>
in Für ein untergeordnetes Fenster der Fenster Bezeichner. Für ein Fenster der obersten Ebene ein Menü Handle für das Fenster. Der Standardwert ist **0U**.

*lpCreateParam*<br/>
in Ein Zeiger auf Fenster Erstellungs Daten. Eine vollständige Beschreibung finden Sie in der Beschreibung des letzten Parameters für " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw)".

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle für das neu erstellte Fenster andernfalls NULL.

### <a name="remarks"></a>Hinweise

Der vorhandene Fenster Klassenname wird in [m_lpszClassName](#m_lpszclassname)gespeichert. `Create`Anschließend wird ein Fenster erstellt, das auf dieser neuen Klasse basiert. Das neu erstellte Fenster wird automatisch an das `CContainedWindowT` -Objekt angefügt.

> [!NOTE]
>  Nicht aufrufen `Create` , wenn Sie bereits [SubclassWindow](#subclasswindow)aufgerufen haben.

> [!NOTE]
>  Wenn 0 als Wert für den *menuorid-* Parameter verwendet wird, muss es als 0U (Standardwert) angegeben werden, um einen Compilerfehler zu vermeiden.

##  <a name="defwindowproc"></a>Ccontainedwindowt::D efwindowproc

Wird von [WindowProc](#windowproc) aufgerufen, um Meldungen zu verarbeiten, die nicht von der Meldungs Zuordnung behandelt werden.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*uMsg*<br/>
in Die an das Fenster gesendete Nachricht.

*wParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

*lParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

In der Standard `DefWindowProc` Einstellung Ruft die Win32-Funktion [callwindowproc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) auf, um die Nachrichten Informationen an die in [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)angegebene Fenster Prozedur zu senden.

##  <a name="getcurrentmessage"></a>Ccontainedwindowt:: GetCurrentMessage

Gibt die aktuelle Meldung zurück`m_pCurrentMsg`().

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Meldung, gepackt in der `MSG` -Struktur.

##  <a name="m_dwmsgmapid"></a>Ccontainedwindowt:: m_dwMsgMapID

Enthält den Bezeichner der Meldungs Zuordnung, die derzeit für das enthaltene Fenster verwendet wird.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Hinweise

Diese Nachrichten Zuordnung muss im enthaltenden Objekt deklariert werden.

Die Standard Meldungs Zuordnung, die mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)deklariert wird, wird immer durch 0 (null) identifiziert. Eine Alternative Meldungs Zuordnung, die mit [ALT_MSG_MAP (msgmapid)](message-map-macros-atl.md#alt_msg_map)deklariert wurde, `msgMapID`wird von identifiziert.

`m_dwMsgMapID`wird zuerst vom-Konstruktor initialisiert und kann durch Aufrufen von [switchmessagemap](#switchmessagemap)geändert werden. Ein Beispiel finden Sie in der [Übersicht über ccontainedwindowt](../../atl/reference/ccontainedwindowt-class.md).

##  <a name="m_lpszclassname"></a>Ccontainedwindowt:: m_lpszClassName

Gibt den Namen einer vorhandenen Fenster Klasse an.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Hinweise

Wenn Sie ein Fenster erstellen, registriert [Create](#create) eine neue Fenster Klasse, die auf dieser vorhandenen Klasse basiert, aber [ccontainedwindowt:: WindowProc](#windowproc)verwendet.

`m_lpszClassName`wird vom-Konstruktor initialisiert. Ein Beispiel finden Sie in der Übersicht über [ccontainedwindowt](../../atl/reference/ccontainedwindowt-class.md) .

##  <a name="m_pfnsuperwindowproc"></a>Ccontainedwindowt:: m_pfnSuperWindowProc

Wenn das enthaltene Fenster untergeordnet ist, `m_pfnSuperWindowProc` verweist auf die ursprüngliche Fenster Prozedur der Fenster Klasse.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Hinweise

Wenn das enthaltene Fenster eine übergeordnete Klasse ist, was bedeutet, dass es auf einer Fenster Klasse basiert, die eine `m_pfnSuperWindowProc` vorhandene Klasse ändert, verweist auf die Fenster Prozedur der vorhandenen Fenster Klasse.

Die [defwindowproc](#defwindowproc) -Methode sendet Nachrichten Informationen an die in `m_pfnSuperWindowProc`gespeicherte Fenster Prozedur.

##  <a name="m_pobject"></a>Ccontainedwindowt:: m_pObject

Verweist auf das Objekt, das `CContainedWindowT` das Objekt enthält.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Hinweise

Dieser Container, dessen Klasse von [cmessagemap](../../atl/reference/cmessagemap-class.md)abgeleitet werden muss, deklariert die Nachrichten Zuordnung, die vom enthaltenen Fenster verwendet wird.

`m_pObject`wird vom-Konstruktor initialisiert. Ein Beispiel finden Sie in der Übersicht über [ccontainedwindowt](../../atl/reference/ccontainedwindowt-class.md) .

##  <a name="registerwndsuperclass"></a>Ccontainedwindowt:: registerwndsuperclass

Wird von [Create](#create) aufgerufen, um die Fenster Klasse des enthaltenen Fensters zu registrieren.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Atom, das die Fenster Klasse eindeutig identifiziert, die registriert wird. andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Fenster Klasse basiert auf einer vorhandenen Klasse, verwendet jedoch [ccontainedwindowt:: WindowProc](#windowproc). Der Name und die Fenster Prozedur der vorhandenen Fenster Klasse werden in [m_lpszClassName](#m_lpszclassname) bzw. [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)gespeichert.

##  <a name="subclasswindow"></a>Ccontainedwindowt:: SubclassWindow

Unterklassen das von *HWND* identifizierte Fenster und fügt es an das `CContainedWindowT` -Objekt an.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
in Das Handle für das Fenster, das untergeordnet wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Fenster erfolgreich untergeordnet ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Das untergeordnete Fenster verwendet nun [ccontainedwindowt:: WindowProc](#windowproc). Die ursprüngliche Fenster Prozedur wird in [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)gespeichert.

> [!NOTE]
>  Rufen `SubclassWindow` Sie nicht auf, wenn Sie " [Create](#create)" bereits aufgerufen haben.

##  <a name="switchmessagemap"></a>Ccontainedwindowt:: switchmessagemap

Ändert, welche Meldungs Zuordnung zum Verarbeiten der Nachrichten des enthaltenen Fensters verwendet wird.

```
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Parameter

*dwMsgMapID*<br/>
in Der Bezeichner der Meldungs Zuordnung. Wenn Sie die mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)deklarierte Standard Meldungs Zuordnung verwenden möchten, übergeben Sie NULL. Wenn Sie eine Alternative Nachrichten Zuordnung verwenden möchten, die mit [ALT_MSG_MAP (msgmapid)](message-map-macros-atl.md#alt_msg_map)deklariert wurde, übergeben `msgMapID`Sie.

### <a name="remarks"></a>Hinweise

Die Meldungs Zuordnung muss im enthaltenden Objekt definiert werden.

Zunächst geben Sie den Bezeichner der Meldungs Zuordnung im Konstruktor an.

##  <a name="unsubclasswindow"></a>Ccontainedwindowt:: unsubclasswindow

Trennt das untergeordnete Fenster vom `CContainedWindowT` -Objekt und stellt die ursprüngliche Fenster Prozedur wieder her, die in [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)gespeichert ist.

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Parameter

*bForce*<br/>
in Legen Sie diese Einstellung auf "true" fest, um die Wiederherstellung der ursprünglichen Fenster Prozedur zu `CContainedWindowT` erzwingen, auch wenn die Fenster Prozedur für dieses Objekt derzeit nicht aktiv ist. Wenn *bForce* auf false festgelegt ist und die Fenster Prozedur für `CContainedWindowT` dieses Objekt zurzeit nicht aktiv ist, wird die ursprüngliche Fenster Prozedur nicht wieder hergestellt.

### <a name="return-value"></a>Rückgabewert

Das Handle für das Fenster, das zuvor untergeordnet ist. Wenn *bForce* auf false festgelegt ist und die Fenster Prozedur für `CContainedWindowT` dieses Objekt derzeit nicht aktiv ist, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur, wenn Sie die ursprüngliche Fenster Prozedur wiederherstellen möchten, bevor das Fenster zerstört wird. Andernfalls wird dies von [WindowProc](#windowproc) automatisch durchführt, wenn das Fenster zerstört wird.

##  <a name="windowproc"></a>Ccontainedwindowt:: WindowProc

Diese statische Methode implementiert die Fenster Prozedur.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
in Das Handle für das Fenster.

*uMsg*<br/>
in Die an das Fenster gesendete Nachricht.

*wParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

*lParam*<br/>
in Zusätzliche Nachrichten spezifische Informationen.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung.

### <a name="remarks"></a>Hinweise

`WindowProc`leitet Nachrichten an die von [m_dwMsgMapID](#m_dwmsgmapid)identifizierte Nachrichten Zuordnung. Bei Bedarf wird `WindowProc` [defwindowproc](#defwindowproc) für die weitere Nachrichtenverarbeitung aufgerufen.

## <a name="see-also"></a>Siehe auch

[CWindow-Klasse](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap-Klasse](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgmapid)](message-map-macros-atl.md#alt_msg_map)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
