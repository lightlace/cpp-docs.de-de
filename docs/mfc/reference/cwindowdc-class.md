---
title: Cwindowdc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 0ef9b4917dc834eb8335690f9b0d171245f5c170
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502152"
---
# <a name="cwindowdc-class"></a>Cwindowdc-Klasse

Abgeleitet von `CDC`.

## <a name="syntax"></a>Syntax

```
class CWindowDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|Erstellt ein `CWindowDC`-Objekt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|Das HWND, an das `CWindowDC` dieser angefügt ist.|

## <a name="remarks"></a>Hinweise

Ruft die Windows-Funktion [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)bei der Erstellung und [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) zur Zerstörungs Zeit auf. Dies bedeutet, dass `CWindowDC` ein-Objekt auf den gesamten Bildschirmbereich eines [CWnd](../../mfc/reference/cwnd-class.md) (sowohl Client-als auch nicht-Client-Bereiche) zugreift.

Weitere Informationen zum Verwenden von `CWindowDC`finden Sie unter [Geräte Kontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Anforderungen

Header: afxwin.h

##  <a name="cwindowdc"></a>Cwindowdc:: cwindowdc

Erstellt ein `CWindowDC` -Objekt, das auf den gesamten Bildschirmbereich (sowohl Client als auch nicht- `CWnd` Client) des Objekts zugreift, auf das *pwnd*zeigt.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Das Fenster, auf dessen Client Bereich das Gerätekontext Objekt zugreift.

### <a name="remarks"></a>Hinweise

Der Konstruktor ruft die Windows-Funktion [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)auf.

Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn der `GetWindowDC` Windows-Befehl fehlschlägt. Ein Gerätekontext ist möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexte zugewiesen hat. Die Anwendung ist für die fünf allgemeinen Anzeige Kontexte, die zu jedem beliebigen Zeitpunkt unter Windows verfügbar sind, konkurrenzfähig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>Cwindowdc:: m_hWnd

Das HWND des `CWnd` Zeigers wird zum Erstellen des `CWindowDC` -Objekts verwendet.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Hinweise

`m_hWnd`ist eine geschützte Variable vom Typ HWND.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [cwindowdc:: cwindowdc](#cwindowdc).

## <a name="see-also"></a>Siehe auch

[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)
