---
title: CClientDC-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aa255552156fe0bbcb671f39afdcb966e7157ea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422180"
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

|name|Beschreibung|
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

*Aufnehmen*<br/>
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

[MDI MFC-Beispiel](../../visual-cpp-samples.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)
