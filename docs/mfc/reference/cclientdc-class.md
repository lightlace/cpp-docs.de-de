---
title: CClientDC-Klasse
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: 46428740d052c70218d4443395777428cdf3c3b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507339"
---
# <a name="cclientdc-class"></a>CClientDC-Klasse

Übernimmt das Aufrufen der Windows-Funktionen [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) zur Erstellungszeit und [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) zur Zerstörungs Zeit.

## <a name="syntax"></a>Syntax

```
class CClientDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|Erstellt ein `CClientDC` -Objekt, das `CWnd`mit verbunden ist.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|Das HWND des Fensters, für das dieser `CClientDC` gültig ist.|

## <a name="remarks"></a>Hinweise

Dies bedeutet, dass der einem `CClientDC` -Objekt zugeordnete Gerätekontext der Client Bereich eines Fensters ist.

Weitere Informationen zu `CClientDC`finden Sie unter [Geräte Kontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cclientdc"></a>CClientDC:: CClientDC

Erstellt ein `CClientDC` -Objekt, das auf den Client Bereich des [CWnd](../../mfc/reference/cwnd-class.md) zugreift, auf das von *pwnd*verwiesen wird.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Das Fenster, auf dessen Client Bereich das Gerätekontext Objekt zugreift.

### <a name="remarks"></a>Hinweise

Der Konstruktor ruft die Windows-Funktion [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)auf.

Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn der `GetDC` Windows-Befehl fehlschlägt. Ein Gerätekontext ist möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexte zugewiesen hat. Die Anwendung ist für die fünf allgemeinen Anzeige Kontexte, die zu jedem beliebigen Zeitpunkt unter Windows verfügbar sind, konkurrenzfähig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>CClientDC:: m_hWnd

Der `HWND` `CClientDC` des Zeigers, der zum Erstellen des-Objekts verwendet wird. `CWnd`

```
HWND m_hWnd;
```

### <a name="remarks"></a>Hinweise

*m_hWnd* ist eine geschützte Variable.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CClientDC:: CClientDC](#cclientdc).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)
