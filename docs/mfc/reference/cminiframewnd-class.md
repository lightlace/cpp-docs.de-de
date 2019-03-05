---
title: CMiniFrameWnd-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: 70f090e2d9830ccfdd98640b54ff07440064d542
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293263"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd-Klasse

Stellt ein Rahmenfenster mit halber Höhe dar, das in der Regel um unverankerte Symbolleisten sichtbar ist.

## <a name="syntax"></a>Syntax

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Erstellt ein `CMiniFrameWnd`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMiniFrameWnd::Create](#create)|Erstellt eine `CMiniFrameWnd` Objekt nach der Erstellung.|
|[CMiniFrameWnd::CreateEx](#createex)|Erstellt eine `CMiniFrameWnd` Objekt (mit zusätzlichen Optionen) nach der Erstellung.|

## <a name="remarks"></a>Hinweise

Diese Minirahmenfenster Verhalten sich wie normale Rahmenfenstern werden, außer dass sie verfügen nicht über die Schaltflächen Minimieren/Maximieren oder Menüs und Sie nur im System auf sie verzichten auf Klick müssen.

Verwenden einer `CMiniFrameWnd` Objekt, das Objekt zuerst definieren. Rufen Sie dann die [erstellen](#create) Memberfunktion das Minirahmenfenster angezeigt.

Weitere Informationen zur Verwendung von `CMiniFrameWnd` Objekte finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../../mfc/docking-and-floating-toolbars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd

Erstellt eine `CMiniFrameWnd` Objekt, aber nicht das Fenster erstellt.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Hinweise

Rufen Sie zum Erstellen des Fensters [CMiniFrameWnd::Create](#create).

##  <a name="create"></a>  CMiniFrameWnd::Create

Erstellt die Windows-Minirahmenfenster und fügt es der `CMiniFrameWnd` Objekt.

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Parameter

*lpClassName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die Namen die Windows-Klasse. Der Klassenname kann einen beliebigen Namen, die mit der globalen registriert sein [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) Funktion. Bei NULL wird für Sie durch das Framework die Fensterklasse registriert werden. MFC bietet der Standardklasse, die folgenden Formate und Attribute:

- Legt fehlerstilbit CS_DBLCLKS, sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maustaste doppelklickt.

- Legt fest, Stilbits CS_HREDRAW und CS_VREDRAW, leiten den Inhalt des Clientbereichs neu gezeichnet wird, wenn die Größe des Fensters geändert wird.

- Legt den Cursor für die Klasse auf die Windows-standard-IDC_ARROW fest.

- Legt den Hintergrundpinsel für die Klasse für NULL-Werte fest, damit das Fenster den Hintergrund nicht gelöscht werden.

- Legt das Symbol "Klasse" standard ","-Flags winken Windows Logo-Symbol.

- Das Fenster festgelegt auf die standardmäßige Größe und Position, wie Windows durch.

*lpWindowName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen enthält.

*dwStyle*<br/>
Gibt an, der die Stilattribute für Fenster. Diese können standard Window-Stile und mindestens eine der folgenden speziellen Stile enthalten:

- MFS_MOVEFRAME ermöglicht das Minirahmenfenster durch Klicken auf keinem Rand des Fensters, nicht nur die Beschriftung verschoben werden soll.

- Deaktiviert die MFS_4THICKFRAME Ändern der Größe der Minirahmenfenster.

- MFS_SYNCACTIVE synchronisiert die Aktivierung von das Minirahmenfenster an die Aktivierung des übergeordneten Fensters.

- Das Minirahmenfenster waren so klein wie der Inhalt des Clientbereichs MFS_THICKFRAME kann ermöglicht werden.

- MFS_BLOCKSYSMENU deaktiviert den Zugriff auf das Systemmenü und klicken Sie im Steuerelementmenü, und wandelt sie in Teil der Beschriftung (Titelleiste).

Finden Sie unter [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Werte für Fensterstil. Die typische Kombination, die zum Minirahmenfenster ist WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU.

*rect*<br/>
Ein `RECT` -Struktur, die die gewünschten Dimensionen des Fensters angibt.

*pParentWnd*<br/>
Verweist auf das übergeordnete Fenster. Verwenden Sie NULL für Fenster auf oberster Ebene.

*nID*<br/>
Wenn das Minirahmenfenster als untergeordnetes Fenster erstellt wird, ist dies die ID des untergeordneten Steuerelements. andernfalls 0.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Create` Initialisiert, Klassen- und Namen des Fensters und registriert Standardwerte für die Stil und das übergeordnete Element.

##  <a name="createex"></a>  CMiniFrameWnd::CreateEx

Erstellt ein `CMiniFrameWnd`-Objekt.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Gibt an, den erweiterten Stil, der die `CMiniFrameWnd` erstellt wird. Wendet keine der der [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) an das Fenster.

*lpClassName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die Namen die Windows-Klasse (ein [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) Struktur). Der Klassenname kann einen beliebigen Namen, die mit der globalen registriert sein [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) Funktion oder einem der vordefinierten Steuerelementklasse-Namen. Es darf nicht NULL sein.

*lpWindowName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen enthält.

*dwStyle*<br/>
Gibt an, der die Stilattribute für Fenster. Finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Werte.

*rect*<br/>
Die Größe und Position des Fensters, in Clientkoordinaten des *pParentWnd*.

*pParentWnd*<br/>
Verweist auf das übergeordnete Fenster-Objekt.

*nID*<br/>
Der Bezeichner des untergeordneten Fensters.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die `CreateEx` Parameter geben die WNDCLASS, Fensterstil und (optional) ursprüngliche Position und Größe des Fensters. `CreateEx` übergeordnete (sofern vorhanden) und die ID des Fensters angibt

Wenn `CreateEx` ausgeführt wird, handelt es sich bei Windows sendet die [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) die Nachrichten an das Fenster.

Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CMiniFrameWnd`, hinzufügen eine meldungszuordnung an die neue Klasse und Member-Funktionen für die oben genannten Nachrichten bereitstellen. Außer Kraft setzen `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.

Weitere überschreiben `On` *Nachricht* message-Handler zum Hinzufügen weiterer Funktionen in der abgeleiteten Klasse.

Wenn das WS_VISIBLE-Format angegeben ist, sendet Windows im Fenster alle Nachrichten, die für die Aktivierung und das Fenster anzuzeigen. Wenn der Stil für Fenster eine Titelleiste angibt, der Titel des Fensters verweist die *LpszWindowName* Parameter wird in der Titelleiste angezeigt.

Die *DwStyle* Parameter kann eine beliebige Kombination von sein [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

Die alten Stil Palette Toolbox-Fenster werden nicht mehr unterstützt. Der alte Stil, die keine Schaltfläche "X" geschlossen, wurde bei der Ausführung einer MFC-Anwendung in früheren Versionen von Windows, unterstützt jedoch nicht mehr in Visual c++.NET unterstützt wird. Nur das neue Format WS_EX_TOOLWINDOW wird jetzt unterstützt. eine Beschreibung dieses Stils, finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>Siehe auch

[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
