---
title: CEditView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: e0095f2c490ebde10d20ec0705b1297b976b76b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528660"
---
# <a name="ceditview-class"></a>CEditView-Klasse

Ein Ansichtsklassentyp, die die Funktionalität eines Windows-Bearbeitungssteuerelements bereitstellt und verwendet werden kann, um einfache Textbearbeitungsfunktionalität zu implementieren.

## <a name="syntax"></a>Syntax

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CEditView::CEditView](#ceditview)|Konstruiert ein Objekt vom Typ `CEditView`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CEditView::FindText](#findtext)|Sucht nach einer Zeichenfolge innerhalb des Texts.|
|[CEditView::GetBufferLength](#getbufferlength)|Ruft die Länge des Zeichenpuffers ab.|
|[CEditView::GetEditCtrl](#geteditctrl)|Ermöglicht den Zugriff auf die `CEdit` Teil einer `CEditView` Objekt (das Windows-Steuerelement bearbeiten).|
|[CEditView::GetPrinterFont](#getprinterfont)|Ruft die aktuelle Druckerschriftart ab.|
|[CEditView::GetSelectedText](#getselectedtext)|Ruft die aktuelle Textauswahl ab.|
|[CEditView::LockBuffer](#lockbuffer)|Sperren des Puffers.|
|[CEditView::PrintInsideRect](#printinsiderect)|Rendert Text in einem bestimmten Rechteck.|
|[SerializeRaw](#serializeraw)|Serialisiert ein `CEditView` Objekt auf den Datenträger als unformatierter Text.|
|[CEditView::SetPrinterFont](#setprinterfont)|Legt eine neuen Druckerschriftart fest.|
|[CEditView::SetTabStops](#settabstops)|Legt Tabstopps für Bildschirm anzeigen und drucken.|
|[CEditView::UnlockBuffer](#unlockbuffer)|Hebt die Sperre des Puffers.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|Sucht nächste Vorkommen einer Textzeichenfolge.|
|[CEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer bestimmten Zeichenfolge durch eine neue Zeichenfolge.|
|[CEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Auswahl.|
|[CEditView::OnTextNotFound](#ontextnotfound)|Aufgerufen, wenn ein Suchvorgang findet keine Übereinstimmung von weiteren Text.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|Standardstil für Objekte vom Typ `CEditView`.|

## <a name="remarks"></a>Hinweise

Die `CEditView` Klasse bietet die folgenden zusätzlichen Funktionen:

- Drucken.

- Suchen und ersetzen.

Da Klasse `CEditView` ist eine Ableitung von der Klasse `CView`, Objekte der Klasse `CEditView` mit Dokumenten und Dokumentvorlagen verwendet werden können.

Jede `CEditView` den Text des Steuerelements in sein eigenes Objekt globaler Speicher aufbewahrt. Ihre Anwendung kann eine beliebige Anzahl von verfügen `CEditView` Objekte.

Erstellen von Objekten des Typs `CEditView` Wunsch eine Editor-Fenster mit den oben aufgeführten zusätzlicher Funktionalität, oder sollen einfachen Text-Editor-Funktionen. Ein `CEditView` Objekt belegt werden kann den gesamte Clientbereich eines Fensters. Leiten Sie Ihre eigenen Klassen von `CEditView` hinzufügen oder ändern die grundlegende Funktionen oder Klassen deklarieren, die eine Dokumentvorlage hinzugefügt werden kann.

Die Standardimplementierung der Klasse `CEditView` behandelt die folgenden Befehle: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT und ID_FILE_PRINT.

Das Standardlimit für die Zeichen für `CEditView` ist (1024 \* 1024-1 = 1048575). Dies kann durch Aufrufen der Funktion EM_LIMITTEXT des zugrunde liegenden Edit-Steuerelements geändert werden. Allerdings die Grenzwerte unterscheiden sich je nach Betriebssystem und der Typ des Bearbeitungssteuerelements (einzelne oder mehrzeiligen). Weitere Informationen zu diesen Einschränkungen finden Sie unter [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext).

Zum Ändern dieses Limits in Ihrem Steuerelement außer Kraft setzen der `OnCreate()` für funktionsfähig sein, Ihre `CEditView` Klasse und fügen Sie die folgende Codezeile:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Objekte des Typs `CEditView` (oder von abgeleiteten Typen `CEditView`) weisen die folgenden Einschränkungen:

- `CEditView` implementiert nicht "true" Was ist das Ergebnis (WYSIWYG) bearbeiten. Eine Wahl zwischen Lesbarkeit auf dem Bildschirm und entsprechende gedruckte Ausgabe `CEditView` "OPTS" für den Bildschirm zu lesen.

- `CEditView` Anzeigen von Text in nur einer einzelnen Schriftart an. Keine Sonderzeichen Formatierung wird unterstützt. Finden Sie unter Klasse [CRichEditView](../../mfc/reference/cricheditview-class.md) für mehr Funktionen.

- Die Größe des Texts einer `CEditView` darf ist beschränkt. Die Grenzwerte sind als für die `CEdit` Steuerelement.

Weitere Informationen zu `CEditView`, finden Sie unter [abgeleitete Sicht Klassen in MFC verfügbare](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="ceditview"></a>  CEditView::CEditView

Konstruiert ein Objekt vom Typ `CEditView`.

```
CEditView();
```

### <a name="remarks"></a>Hinweise

Sie müssen nach dem Erstellen des Objekts Aufrufen der [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) funktionieren, bevor das Steuerelement zum Bearbeiten verwendet wird. Wenn Sie beim Ableiten einer Klasse von `CEditView` und Hinzufügen der Vorlage mithilfe `CWinApp::AddDocTemplate`, das Framework ruft beide dieser Konstruktor und die `Create` Funktion.

##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault

Enthält den Standardstil der der `CEditView` Objekt.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Hinweise

Übergeben dieses statische Element als die *DwStyle* Parameter der `Create` Funktion zum Abrufen des Standardstil für den `CEditView` Objekt.

##  <a name="findtext"></a>  CEditView::FindText

Rufen Sie die `FindText` Funktion zum Suchen der `CEditView` des Objekts den Textpuffer.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text gefunden werden.

*bWeiter*<br/>
Gibt die Richtung für die Suche. Wenn TRUE, ist die suchrichtung zum Ende des Puffers. False gibt an, wird die Suche Richtung am Anfang des Puffers.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn "true", bei der Suche die Groß-/Kleinschreibung beachtet wird. False gibt an, wird die Suche keine Groß-/Kleinschreibung beachtet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Suchtext gefunden wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion durchsucht den Text im Puffer für den angegebenen Text *LpszFind*, beginnend ab der aktuellen Auswahl, in der vom angegebenen Richtung *bWeiter*, und mit Groß-und Kleinschreibung durch angegeben*bCase*. Wenn der Text gefunden wird, legt die Auswahl auf der gefundene Text fest und gibt einen Wert ungleich NULL zurück. Wenn der Text nicht gefunden wird, gibt die Funktion 0 zurück.

Sie normalerweise nicht müssen zum Aufrufen der `FindText` funktionieren, wenn Sie außer Kraft setzen `OnFindNext`, welche Aufrufe `FindText`.

##  <a name="getbufferlength"></a>  CEditView::GetBufferLength

Rufen Sie diese Memberfunktion, um die Anzahl der Zeichen, die derzeit in der das Steuerelement zum Bearbeiten der Puffer nicht einschließlich null-Terminator zu erhalten.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge im Puffer.

##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl

Rufen Sie `GetEditCtrl` zum Abrufen eines Verweises auf das Steuerelement zum Bearbeiten, die von der Bearbeitungsansicht verwendet.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein `CEdit`-Objekt.

### <a name="remarks"></a>Hinweise

Dieses Steuerelement ist vom Typ [CEdit](../../mfc/reference/cedit-class.md), sodass Sie direkt mit Windows-Edit-Steuerelements ändern, können die `CEdit` Memberfunktionen.

> [!CAUTION]
>  Mithilfe der `CEdit` Objekt kann ändern den Status der zugrunde liegenden Windows-edit-Steuerelement. Beispielsweise sollten Sie nicht mithilfe von Einstellungen auf der Registerkarte Ändern der [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) funktionieren, da `CEditView` speichert diese Einstellungen für die Verwendung in das Bearbeitungssteuerelement sowohl beim Drucken. Verwenden Sie stattdessen [CEditView::SetTabStops](#settabstops).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont

Rufen Sie `GetPrinterFont` um einen Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Objekt, das die aktuelle Druckerschriftart beschreibt.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CFont` Objekt, das den aktuellen Druckerschriftart angibt. NULL, wenn die Druckerschriftart nicht festgelegt wurde. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.

### <a name="remarks"></a>Hinweise

Wenn die Druckerschriftart nicht, Drucken Verhalten standardmäßig festgelegt wurde die `CEditView` Klasse ist mit dem gleichen Schriftgrad, die für die Anzeige verwendet.

Verwenden Sie diese Funktion, um die aktuelle Druckerschriftart zu bestimmen. Wenn sie nicht die gewünschten Drucker-Schriftart ist, verwenden [CEditView::SetPrinterFont](#setprinterfont) , ihn zu ändern.

##  <a name="getselectedtext"></a>  CEditView::GetSelectedText

Rufen Sie `GetSelectedText` kopiert den markierten Text in einem `CString` Objekt bis zum Ende der Auswahl oder das Zeichen vor dem ersten Zeichen für Wagenrücklauf in der Auswahl.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Parameter

*"strResult"*<br/>
Ein Verweis auf die `CString` -Objekt, das den ausgewählten Text zu empfangen.

##  <a name="lockbuffer"></a>  CEditView::LockBuffer

Rufen Sie diese Memberfunktion, um einen Zeiger auf den Puffer zu erhalten. Der Puffer sollte nicht geändert werden.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Steuerelement zum Bearbeiten des Puffers.

##  <a name="onfindnext"></a>  CEditView::OnFindNext

Durchsucht den Text im Puffer für den angegebenen Text *LpszFind*, in der vom angegebenen Richtung *bWeiter*, mit Groß-und Kleinschreibung gemäß *bCase*.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text gefunden werden.

*bWeiter*<br/>
Gibt die Richtung für die Suche. Wenn TRUE, ist die suchrichtung zum Ende des Puffers. False gibt an, wird die Suche Richtung am Anfang des Puffers.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn "true", bei der Suche die Groß-/Kleinschreibung beachtet wird. False gibt an, wird die Suche keine Groß-/Kleinschreibung beachtet.

### <a name="remarks"></a>Hinweise

Die Suche beginnt am Anfang der aktuellen Auswahl und erfolgt über einen Aufruf von [FindText](#findtext). In der Standardimplementierung `OnFindNext` Aufrufe [OnTextNotFound](#ontextnotfound) , wenn der Text nicht gefunden wird.

Außer Kraft setzen `OnFindNext` so ändern Sie die Möglichkeit einer `CEditView`-abgeleitetes Objekt sucht im Text. `CEditView` Aufrufe `OnFindNext` Wenn der Benutzer die Schaltfläche "Weitersuchen" auswählt, in das standardmäßige Dialogfeld Suchen.

##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll

`CEditView` Aufrufe `OnReplaceAll` Wenn der Benutzer die Schaltfläche "Alle ersetzen" auswählt, in das Standarddialogfeld ersetzen.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text gefunden werden.

*lpszReplace*<br/>
Der Text, der der Suchtext ersetzt werden soll.

*bCase*<br/>
Gibt an, ob die Suche die Groß-/Kleinschreibung beachtet wird. Wenn "true", bei der Suche die Groß-/Kleinschreibung beachtet wird. False gibt an, wird die Suche keine Groß-/Kleinschreibung beachtet.

### <a name="remarks"></a>Hinweise

`OnReplaceAll` durchsucht den Text im Puffer für den angegebenen Text *LpszFind*, mit Groß-und Kleinschreibung gemäß *bCase*. Die Suche beginnt am Anfang der aktuellen Auswahl. Jedes Mal der Suchtext gefunden wird, wird diese Funktion ersetzt, Vorkommen des Texts mit dem Text, der anhand des *LpszReplace*. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). In der Standardimplementierung [OnTextNotFound](#ontextnotfound) wird aufgerufen, wenn der Text nicht gefunden wird.

Stimmt nicht mit die aktuelle Auswahl überein *LpszFind*, die Auswahl aktualisiert wird, auf das erste Vorkommen des Texts gemäß *LpszFind* und eine Ersetzung wird nicht ausgeführt. Dadurch kann der Benutzer zu bestätigen, dass dies Was möchten sie tun, wenn die Auswahl der zu ersetzende Text nicht übereinstimmt.

Außer Kraft setzen `OnReplaceAll` so ändern Sie die Möglichkeit einer `CEditView`-abgeleitetes Objekt ersetzt Text.

##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel

`CEditView` Aufrufe `OnReplaceSel` Wenn der Benutzer die Schaltfläche "ersetzen" auswählt, in das Standarddialogfeld ersetzen.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text gefunden werden.

*bWeiter*<br/>
Gibt die Richtung für die Suche. Wenn TRUE, ist die suchrichtung zum Ende des Puffers. False gibt an, wird die Suche Richtung am Anfang des Puffers.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn "true", bei der Suche die Groß-/Kleinschreibung beachtet wird. False gibt an, wird die Suche keine Groß-/Kleinschreibung beachtet.

*lpszReplace*<br/>
Der Text den gefundenen Text ersetzt werden soll.

### <a name="remarks"></a>Hinweise

Ersetzen Sie die Auswahl, und diese Funktion durchsucht den Text im Puffer für das nächste Vorkommen des Texts innerhalb *LpszFind*, in der vom angegebenen Richtung *bWeiter*, mit der Groß-/Kleinschreibung gemäß *bCase*. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). Wenn der Text nicht gefunden wird, [OnTextNotFound](#ontextnotfound) aufgerufen wird.

Außer Kraft setzen `OnReplaceSel` so ändern Sie die Möglichkeit einer `CEditView`-abgeleitetes Objekt ersetzt den markierten Text.

##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound

Überschreiben Sie diese Funktion, um die standardmäßige Implementierung, zu ändern, die die Windows-Funktion aufruft `MessageBeep`.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text gefunden werden.

##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect

Rufen Sie `PrintInsideRect` So drucken Sie Text in das Rechteck, das vom angegebenen *RectLayout*.

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeiger auf den Druckergerätekontext.

*rectLayout*<br/>
Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) angeben des Rechtecks, das in der der Text ist, gerendert werden soll.

*nIndexStart*<br/>
Der Index innerhalb des Puffers des ersten Zeichens gerendert werden soll.

*nIndexStop*<br/>
Der Index innerhalb des Puffers, der das Zeichen, die nach dem letzten Zeichen gerendert werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des nächsten Zeichens gedruckt werden sollen (d. h. das Zeichen nach dem letzten Zeichen dargestellt).

### <a name="remarks"></a>Hinweise

Wenn die `CEditView` -Steuerelement verfügt nicht über den Stil ES_AUTOHSCROLL, Text innerhalb des Rechtecks Rendering umbrochen wird. Wenn das Steuerelement den Stil ES_AUTOHSCROLL besitzt, wird der Text am rechten Rand des Rechtecks abgeschnitten.

Die `rect.bottom` Element der *RectLayout* Objekt hat sich geändert, sodass den Abmessungen des Rechtecks den Teil der das ursprüngliche Rechteck definieren, die durch den Text belegt wird.

##  <a name="serializeraw"></a>  SerializeRaw

Rufen Sie `SerializeRaw` haben eine `CArchive` Objekt lesen und Schreiben von Text in die `CEditView` Objekt in eine Textdatei.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
Ein Verweis auf die `CArchive` -Objekt, das den serialisierten Text gespeichert.

### <a name="remarks"></a>Hinweise

`SerializeRaw` unterscheidet sich von `CEditView`die interne Implementierung der `Serialize` liest und schreibt nur den Text, ohne die objektbeschreibung Daten vor.

##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont

Rufen Sie `SetPrinterFont` für die Druckerschriftart festzulegen, der vom angegebenen Schriftart *pFont*.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf ein Objekt des Typs `CFont`. Wenn NULL, ist der Bildschirm-Schriftart die Schriftart für den Druck abhängig.

### <a name="remarks"></a>Hinweise

Wenn Sie die Ansicht, um immer eine bestimmte Schriftart für das Drucken verwenden möchten, fügen Sie einen Aufruf `SetPrinterFont` in der Ihre Klasse `OnPreparePrinting` Funktion. Diese virtuelle Funktion wird aufgerufen, bevor es sich bei gedruckt wird, damit die Änderung der Schriftart stattfindet, bevor Sie den Inhalt der Ansicht gedruckt werden.

##  <a name="settabstops"></a>  CEditView::SetTabStops

Rufen Sie diese Funktion zum Festlegen von Tabstopps zum Anzeigen und drucken.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Parameter

*nTabStops*<br/>
Breite des Tabstopp entsprechen, in Dialogeinheiten.

### <a name="remarks"></a>Hinweise

Nur eine einzelne Tabstopp Breite wird unterstützt. ( `CEdit` Objekte unterstützen mehrere Tabulatorposition.) Breite werden in Dialogeinheiten, die ein Viertel der durchschnittliche Zeichenbreite (basierend auf Groß- und Kleinschreibung nur alphabetische Zeichen) zum Zeitpunkt der drucken oder Anzeigen der Schriftart gleich. Verwenden Sie nicht `CEdit::SetTabStops` da `CEditView` muss den Wert der Tabstopp Zwischenspeichern.

Diese Funktion ändert nur die Registerkarten des Objekts für das es aufgerufen wird. So ändern Sie die Registerkarte "wird beendet, für die einzelnen `CEditView` -Objekts in der Anwendung, des Objekts aufrufen `SetTabStops` Funktion.

### <a name="example"></a>Beispiel

Dieses Codefragment werden die Tabstopps in das Steuerelement, das jedem vierten Zeichen festgelegt, durch das Messen sorgfältig der Schriftart, die das Steuerelement verwendet.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer

Rufen Sie diese Memberfunktion um den Puffer zu entsperren.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Hinweise

Rufen Sie `UnlockBuffer` Sie nach der Verwendung des vom Zeigers [LockBuffer](#lockbuffer).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CDocument-Klasse](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
