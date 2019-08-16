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
ms.openlocfilehash: 45b4698cc70487a6c3fe1470fe27f7b5c4f95402
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504600"
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
|[CMiniFrameWnd::Create](#create)|Erstellt ein `CMiniFrameWnd` -Objekt nach der Erstellung.|
|[CMiniFrameWnd::CreateEx](#createex)|Erstellt nach `CMiniFrameWnd` der Erstellung ein-Objekt (mit zusätzlichen Optionen).|

## <a name="remarks"></a>Hinweise

Diese Mini Rahmen Fenster Verhalten sich wie normale Rahmen Fenster, mit dem Unterschied, dass Sie nicht über Schaltflächen zum minimieren/maximieren verfügen, und Sie müssen nur auf das Systemmenü klicken, um Sie zu schließen.

Um ein `CMiniFrameWnd` -Objekt zu verwenden, definieren Sie zuerst das-Objekt. Rufen Sie dann die [Create](#create) Member-Funktion auf, um das Mini Rahmen Fenster anzuzeigen.

Weitere Informationen zur Verwendung `CMiniFrameWnd` von Objekten finden Sie im Artikel [Andocken und](../../mfc/docking-and-floating-toolbars.md)Unverankerte Symbolleisten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cminiframewnd"></a>CMiniFrameWnd:: CMiniFrameWnd

Erstellt ein `CMiniFrameWnd` -Objekt, erstellt jedoch das Fenster nicht.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Hinweise

Rufen Sie zum Erstellen des Fensters [CMiniFrameWnd:: Create](#create)auf.

##  <a name="create"></a>CMiniFrameWnd:: Create

Erstellt das Windows-Mini Rahmen Fenster und fügt es an das `CMiniFrameWnd` -Objekt an.

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
Verweist auf eine mit NULL endenden Zeichenfolge, die die Windows-Klasse benennt. Der Klassenname kann ein beliebiger Name sein, der in der globalen [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion registriert ist. Wenn der Wert NULL ist, wird die Fenster Klasse vom Framework für Sie registriert. MFC gibt der Standardklasse die folgenden Stile und Attribute:

- Legt Style Bit CS_DBLCLKS fest, das Doppelklick-Meldungen an die Fenster Prozedur sendet, wenn der Benutzer auf die Maus doppelklickt.

- Legt die stilbits CS_HREDRAW und CS_VREDRAW fest, die den Inhalt des Client Bereichs so weiterleiten, dass er neu gezeichnet wird, wenn die Größe des Fensters geändert wird.

- Legt den Klassen Cursor auf den Windows-Standard IDC_ARROW fest.

- Legt den klassenhintergrund Pinsel auf NULL fest, damit das Fenster seinen Hintergrund nicht löscht.

- Legt das Klassen Symbol auf das Windows-Logo Symbol Standard, waving-Flag fest.

- Legt das Fenster auf die Standardgröße und die Standardposition fest, wie von Windows angegeben.

*lpWindowName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die den Fensternamen enthält.

*dwStyle*<br/>
Gibt die Fenster Stil Attribute an. Diese können Standardfenster Stile und einen oder mehrere der folgenden speziellen Stile enthalten:

- MFS_MOVEFRAME ermöglicht das Verschieben des Mini Rahmen Fensters durch Klicken auf einen beliebigen Rand des Fensters, nicht nur auf die Beschriftung.

- MFS_4THICKFRAME deaktiviert die Größe des Mini Rahmen Fensters.

- MFS_SYNCACTIVE synchronisiert die Aktivierung des Mini Rahmen Fensters mit der Aktivierung des übergeordneten Fensters.

- MFS_THICKFRAME ermöglicht, dass das Mini Rahmen Fenster so klein wie der Inhalt des Client Bereichs ist.

- MFS_BLOCKSYSMENU deaktiviert den Zugriff auf das Systemmenü und das Menü Steuerelement und konvertiert sie in einen Teil der Beschriftung (Titelleiste).

Unter [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) finden Sie eine Beschreibung möglicher Fenster Stil Werte. Die typische für Mini Rahmen Fenster verwendete Kombination ist WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU.

*Rect*<br/>
Eine `RECT` -Struktur, die die gewünschten Abmessungen des Fensters angibt.

*pParentWnd*<br/>
Zeigt auf das übergeordnete Fenster. Verwenden Sie NULL für Fenster der obersten Ebene.

*nID*<br/>
Wenn das Mini Rahmen Fenster als untergeordnetes Fenster erstellt wird, ist dies der Bezeichner des untergeordneten Steuer Elements. andernfalls 0.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Create`Initialisiert den Klassennamen und den Fensternamen des Fensters und registriert die Standardwerte für den Stil und das übergeordnete Element.

##  <a name="createex"></a>CMiniFrameWnd:: up-Ex

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
Gibt den erweiterten Stil der `CMiniFrameWnd` zu erstellenden an. Anwenden eines der [erweiterten Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) auf das Fenster.

*lpClassName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die die Windows-Klasse benennt (eine [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) -Struktur). Der Klassenname kann ein beliebiger Name sein, der mit der globalen [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion oder einem der vordefinierten Steuerelement Klassennamen registriert wird. Er darf nicht NULL sein.

*lpWindowName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die den Fensternamen enthält.

*dwStyle*<br/>
Gibt die Fenster Stil Attribute an. Eine Beschreibung der möglichen Werte finden Sie unter [Window Styles](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) .

*Rect*<br/>
Die Größe und Position des Fensters in den Client Koordinaten von *pparameentwnd*.

*pParentWnd*<br/>
Zeigt auf das übergeordnete Fenster Objekt.

*nID*<br/>
Der Bezeichner des untergeordneten Fensters.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die `CreateEx` Parameter geben die WNDCLASS, den Fenster Stil und die (optional) Anfangsposition und die Größe des Fensters an. `CreateEx`gibt auch das übergeordnete Element (sofern vorhanden) und die ID des Fensters an.

Wenn `CreateEx` ausgeführt wird, sendet Windows die [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)-, [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)-, [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)-und [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) -Meldungen an das-Fenster.

Um die standardmäßige Nachrichten Behandlung zu erweitern, leiten Sie `CMiniFrameWnd`eine Klasse von ab, fügen Sie der neuen Klasse eine Meldungs Zuordnung hinzu, und stellen Sie Element Funktionen für die obigen Meldungen bereit. Über `OnCreate`schreiben Sie z. b., um die erforderliche Initialisierung für eine neue Klasse auszuführen.

Überschreiben `On`Sie weitere Meldungs Handler für *Meldungen* , um ihrer abgeleiteten Klasse weitere Funktionen hinzuzufügen.

Wenn der WS_VISIBLE-Stil angegeben ist, sendet Windows alle zum Aktivieren und Anzeigen des Fensters erforderlichen Meldungen an das Fenster. Wenn im Fenster Stil eine Titelleiste angegeben ist, wird der Fenstertitel, auf den der *lpszWindowName* -Parameter zeigt, in der Titelleiste angezeigt.

Der Parameter " *dwstyle* " kann eine beliebige Kombination von [Fenster Stilen](../../mfc/reference/styles-used-by-mfc.md#window-styles)sein.

Die alten Fenster der Stil Palette der Toolbox werden nicht mehr unterstützt. Der alte Stil, der keine "X"-Schaltfläche "Schließen" enthielt, wurde beim Ausführen einer MFC-Anwendung unter früheren Versionen von Windows unterstützt, wird in Visual C++.NET jedoch nicht mehr unterstützt. Nur der neue WS_EX_TOOLWINDOW-Stil wird jetzt unterstützt. eine Beschreibung dieses Stils finden Sie unter [Erweiterte Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>Siehe auch

[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
