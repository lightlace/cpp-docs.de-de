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
ms.openlocfilehash: a67af5d7d82b8bd7d0490d4ae6f9535bf3283ea2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206623"
---
# <a name="cclientdc-class"></a>CClientDC-Klasse

Übernimmt die Windows-Funktionen aufrufen [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) zur Erstellungszeit und [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) zur zerstörungszeit.

## <a name="syntax"></a>Syntax

```
class CClientDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|Erstellt eine `CClientDC` Objekt verbunden, um die `CWnd`.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|Das HWND des Fensters für den dieser `CClientDC` gültig ist.|

## <a name="remarks"></a>Hinweise

Dies bedeutet, dass den Gerätekontext zugeordneten eine `CClientDC` Objekt ist, das den Clientbereich eines Fensters.

Weitere Informationen zu `CClientDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cclientdc"></a>  CClientDC::CClientDC

Erstellt eine `CClientDC` -Objekt, das den Clientbereich des greift auf die [CWnd](../../mfc/reference/cwnd-class.md) verweist *aufnehmen*.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Das Fenster, dessen Client-Bereich, der das Device Context-Objekt zugegriffen wird.

### <a name="remarks"></a>Hinweise

Der Konstruktor ruft die Windows-Funktion [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc).

Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn die Windows `GetDC` -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn es sich bei allen Kontexten verfügbare Gerät Windows bereits zugewiesen wurde. Ihre Anwendung Computerressourcen für die fünf allgemeinen Anzeige Kontexte zu jedem Zeitpunkt unter Windows verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CClientDC::m_hWnd

Die `HWND` von der `CWnd` Zeiger, die zum Erstellen der `CClientDC` Objekt.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Hinweise

*M_hWnd* ist eine geschützte Variable.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CClientDC::CClientDC](#cclientdc).

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)
