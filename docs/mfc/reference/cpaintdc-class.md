---
title: CPaintDC-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: d587f1cfa6ec38dd564da196da8130bffac11302
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503142"
---
# <a name="cpaintdc-class"></a>CPaintDC-Klasse

Eine von [CDC](../../mfc/reference/cdc-class.md)abgeleitete Gerätekontext Klasse.

## <a name="syntax"></a>Syntax

```
class CPaintDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Erstellt eine `CPaintDC` , die mit dem angegebenen [CWnd](../../mfc/reference/cwnd-class.md)verbunden ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|Enthält die zum Zeichnen des Client Bereichs verwendete [Pinsel Struktur](/windows/win32/api/winuser/ns-winuser-paintstruct) .|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|Das HWND, an das `CPaintDC` dieses-Objekt angefügt wird.|

## <a name="remarks"></a>Hinweise

Die [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) wird zur Konstruktionszeit und [CWnd:: endpaint](../../mfc/reference/cwnd-class.md#endpaint) zur Zerstörungs Zeit durchführt.

Ein `CPaintDC` -Objekt kann nur bei der Reaktion auf eine [WM_PAINT](/windows/win32/gdi/wm-paint) -Nachricht verwendet werden `OnPaint` , in der Regel in der Message-Handler-Member-Funktion.

Weitere Informationen zum Verwenden von `CPaintDC`finden Sie unter [Geräte Kontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cpaintdc"></a>CPaintDC:: CPaintDC

Erstellt ein `CPaintDC` -Objekt, bereitet das Anwendungsfenster für das Zeichnen vor und speichert die [paintstruct](/windows/win32/api/winuser/ns-winuser-paintstruct) -Struktur in der [m_ps](#m_ps) -Member-Variablen.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das `CWnd` Objekt, zu dem `CPaintDC` das Objekt gehört.

### <a name="remarks"></a>Hinweise

Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn der Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) -Befehl fehlschlägt. Ein Gerätekontext ist möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexte zugewiesen hat. Die Anwendung ist für die fünf allgemeinen Anzeige Kontexte, die zu jedem beliebigen Zeitpunkt unter Windows verfügbar sind, konkurrenzfähig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>CPaintDC:: m_hWnd

Das `HWND` , an das `CPaintDC` dieses-Objekt angefügt wird.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Hinweise

*m_hWnd* ist eine geschützte Variable vom Typ HWND.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>CPaintDC:: m_ps

`m_ps`ist eine öffentliche Member-Variable vom Typ " [paintstruct](/windows/win32/api/winuser/ns-winuser-paintstruct)".

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Hinweise

Es ist das `PAINTSTRUCT` , das an übergeben und von [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)ausgefüllt wird.

Enthält Informationen, die von der Anwendung verwendet werden, um den Client Bereich des Fensters zu zeichnen `CPaintDC` , das einem-Objekt zugeordnet ist. `PAINTSTRUCT`

Beachten Sie, dass Sie über die `PAINTSTRUCT`auf das Gerätekontext handle zugreifen können. Sie können jedoch direkt über die `m_hDC` Member-Variable, `CPaintDC` die von CDC erbt, auf das Handle zugreifen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPaintDC:: m_hWnd](#m_hwnd).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
