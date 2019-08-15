---
title: CWndClassInfo-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: c416155ed103f1345c42e6680c2329ab98d35926
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496126"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo-Klasse

Diese Klasse stellt Methoden zum Registrieren von Informationen für eine Fenster Klasse bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CWndClassInfo
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|[Registrieren](#register)|Registriert die Fenster Klasse.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_atom](#m_atom)|Identifiziert die registrierte Fenster Klasse eindeutig.|
|[m_bSystemCursor](#m_bsystemcursor)|Gibt an, ob die Cursor Ressource auf einen System Cursor oder einen Cursor verweist, der in einer Modul Ressource enthalten ist.|
|[m_lpszCursorID](#m_lpszcursorid)|Gibt den Namen der Cursor Ressource an.|
|[m_lpszOrigName](#m_lpszorigname)|Enthält den Namen einer vorhandenen Fenster Klasse.|
|[m_szAutoName](#m_szautoname)|Enthält einen ATL-generierten Namen der Fenster Klasse.|
|[m_wc](#m_wc)|Verwaltet Fenster Klassen Informationen in einer `WNDCLASSEX` -Struktur.|
|[pWndProc](#pwndproc)|Verweist auf die Fenster Prozedur einer vorhandenen Fenster Klasse.|

## <a name="remarks"></a>Hinweise

`CWndClassInfo`verwaltet die Informationen einer Fenster Klasse. In der Regel `CWndClassInfo` verwenden Sie eine der drei Makros DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX oder DECLARE_WND_SUPERCLASS, wie in der folgenden Tabelle beschrieben:

|Makro|Beschreibung|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`registriert Informationen für eine neue Fenster Klasse.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`registriert Informationen für eine neue Fenster Klasse, einschließlich der Klassen Parameter.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`registriert Informationen für eine Fenster Klasse, die auf einer vorhandenen Klasse basiert, aber eine andere Fenster Prozedur verwendet. Dieses Verfahren wird als superclassingmethode bezeichnet.|

Standardmäßig enthält [CWindowImpl](../../atl/reference/cwindowimpl-class.md) das- `DECLARE_WND_CLASS` Makro, um auf der Grundlage einer neuen Fenster Klasse ein Fenster zu erstellen. DECLARE_WND_CLASS stellt Standard Stile und die Hintergrundfarbe für das-Steuerelement bereit. Wenn Sie den Stil und die Hintergrundfarbe selbst angeben möchten, leiten Sie die Klasse `CWindowImpl` von ab, und fügen Sie das DECLARE_WND_CLASS_EX-Makro in die Klassendefinition ein.

Wenn Sie ein Fenster erstellen möchten, das auf einer vorhandenen Fenster Klasse basiert, leiten Sie die `CWindowImpl` Klasse von ab, und fügen Sie das DECLARE_WND_SUPERCLASS-Makro in die Klassendefinition ein. Beispiel:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Weitere Informationen zu Fenster Klassen finden Sie unter [Fenster Klassen](/windows/win32/winmsg/window-classes) in der Windows SDK.

Weitere Informationen zur Verwendung von Windows in ATL finden Sie im Artikel [ATL-Fenster Klassen](../../atl/atl-window-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlwin. h

##  <a name="m_atom"></a>CWndClassInfo:: m_atom

Enthält den eindeutigen Bezeichner für die registrierte Fenster Klasse.

```
ATOM m_atom;
```

##  <a name="m_bsystemcursor"></a>CWndClassInfo:: m_bSystemCursor

TRUE gibt an, dass die System Cursor Ressource geladen wird, wenn die Fenster Klasse registriert wird.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Hinweise

Andernfalls wird die Cursor Ressource geladen, die in Ihrem Modul enthalten ist.

`CWndClassInfo`wird `m_bSystemCursor` nur verwendet, wenn [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder das [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro angegeben wird. In diesem Fall `m_bSystemCursor` wird mit true initialisiert. Weitere Informationen finden Sie in der Übersicht über [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) .

##  <a name="m_lpszcursorid"></a>CWndClassInfo:: m_lpszCursorID

Gibt entweder den Namen der Cursor Ressource oder den Ressourcen Bezeichner im nieder wertigen Wort und NULL im höherwertigen Wort an.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Hinweise

Wenn die Fenster Klasse registriert ist, wird das Handle für den Cursor, `m_lpszCursorID` der durch identifiziert wird, von [m_wc](#m_wc)abgerufen und gespeichert.

`CWndClassInfo`wird `m_lpszCursorID` nur verwendet, wenn [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder das [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro angegeben wird. In diesem Fall `m_lpszCursorID` wird mit IDC_ARROW initialisiert. Weitere Informationen finden Sie in der Übersicht über [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) .

##  <a name="m_lpszorigname"></a>CWndClassInfo:: m_lpszOrigName

Enthält den Namen einer vorhandenen Fenster Klasse.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Hinweise

`CWndClassInfo`wird `m_lpszOrigName` nur verwendet, wenn Sie das [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) -Makro in die Klassendefinition einschließen. In diesem Fall wird `CWndClassInfo` eine Fenster Klasse auf Grundlage der Klasse registriert, die `m_lpszOrigName`durch benannt wird. Weitere Informationen finden Sie in der Übersicht über [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) .

##  <a name="m_szautoname"></a>CWndClassInfo:: m_szAutoName

Enthält den Namen der Fenster Klasse.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Hinweise

`CWndClassInfo`verwendet `m_szAutoName` nur, wenn NULL für den `WndClassName` Parameter an [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) oder [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)übergeben wird. ATL erstellt einen Namen, wenn die Fenster Klasse registriert wird.

##  <a name="m_wc"></a>CWndClassInfo:: m_wc

Verwaltet die Fenster Klassen Informationen in einer [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) -Struktur.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Hinweise

Wenn Sie [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder das [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro angegeben haben `m_wc` , enthält Informationen zu einer neuen Fenster Klasse.

Wenn Sie das [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) -Makro angegeben haben `m_wc` , enthält Informationen über eine übergeordneten Klasse – eine Fenster Klasse, die auf einer vorhandenen Klasse basiert, aber eine andere Fenster Prozedur verwendet. [m_lpszOrigName](#m_lpszorigname) und [pwndproc](#pwndproc) speichern Sie den Namen bzw. die Fenster Prozedur der vorhandenen Fenster Klasse.

##  <a name="pwndproc"></a>CWndClassInfo::p WndProc

Verweist auf die Fenster Prozedur einer vorhandenen Fenster Klasse.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Hinweise

`CWndClassInfo`wird `pWndProc` nur verwendet, wenn Sie das [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) -Makro in die Klassendefinition einschließen. In diesem Fall wird `CWndClassInfo` eine Fenster Klasse registriert, die auf einer vorhandenen Klasse basiert, aber eine andere Fenster Prozedur verwendet. Die Fenster Prozedur der vorhandenen Fenster Klasse wird in `pWndProc`gespeichert. Weitere Informationen finden Sie in der Übersicht über [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) .

##  <a name="register"></a>CWndClassInfo:: Register

Wird von [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) aufgerufen, um die Fenster Klasse zu registrieren, wenn Sie noch nicht registriert wurde.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Parameter

*pProc*<br/>
vorgenommen Gibt die ursprüngliche Fenster Prozedur einer vorhandenen Fenster Klasse an.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Atom, das die Fenster Klasse eindeutig identifiziert, die registriert wird. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn Sie [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder das [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro angegeben haben `Register` , registriert eine neue Fenster Klasse. In diesem Fall wird der *pproc* -Parameter nicht verwendet.

Wenn Sie das [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) -Makro angegeben haben `Register` , registriert eine übergeordneten Klasse – eine Fenster Klasse, die auf einer vorhandenen Klasse basiert, aber eine andere Fenster Prozedur verwendet. Die Fenster Prozedur der vorhandenen Fenster Klasse wird in *pproc*zurückgegeben.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
