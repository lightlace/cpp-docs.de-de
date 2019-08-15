---
title: CFontDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: b538acd564402459a05cc96303b63a35a99ba243
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506468"
---
# <a name="cfontdialog-class"></a>CFontDialog-Klasse

Ermöglicht es Ihnen, ein Dialogfeld für die Schriftart Auswahl in Ihre Anwendung einzubinden.

## <a name="syntax"></a>Syntax

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|Erstellt ein `CFontDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[CFontDialog::GetCharFormat](#getcharformat)|Ruft die Zeichen Formatierung der ausgewählten Schriftart ab.|
|[CFontDialog::GetColor](#getcolor)|Gibt die Farbe der ausgewählten Schriftart zurück.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Weist die Merkmale der aktuell ausgewählten Schriftart einer `LOGFONT` -Struktur zu.|
|[CFontDialog::GetFaceName](#getfacename)|Gibt den Namen der Vorderseite der ausgewählten Schriftart zurück.|
|[CFontDialog::GetSize](#getsize)|Gibt die Punktgröße der ausgewählten Schriftart zurück.|
|[CFontDialog::GetStyleName](#getstylename)|Gibt den Format Namen der ausgewählten Schriftart zurück.|
|[CFontDialog::GetWeight](#getweight)|Gibt die Gewichtung der ausgewählten Schriftart zurück.|
|[CFontDialog::IsBold](#isbold)|Bestimmt, ob die Schriftart fett formatiert ist.|
|[CFontDialog::IsItalic](#isitalic)|Bestimmt, ob die Schriftart kursiv formatiert ist.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|Bestimmt, ob die Schriftart mit Strichen angezeigt wird.|
|[CFontDialog::IsUnderline](#isunderline)|Bestimmt, ob die Schriftart unterstrichen ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Eine-Struktur, mit der `CFontDialog` ein-Objekt angepasst wird.|

## <a name="remarks"></a>Hinweise

Ein `CFontDialog` -Objekt ist ein Dialogfeld mit einer Liste von Schriftarten, die derzeit im System installiert sind. Der Benutzer kann eine bestimmte Schriftart aus der Liste auswählen, und diese Auswahl wird dann an die Anwendung zurückgemeldet.

Verwenden Sie zum `CFontDialog` Erstellen eines-Objekts den bereitgestellten Konstruktor, oder leiten Sie eine neue Unterklasse ab, und verwenden Sie Ihren eigenen benutzerdefinierten Konstruktor.

Sobald ein `CFontDialog` -Objekt erstellt wurde, können Sie die- `m_cf` Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die [m_cf](#m_cf) -Struktur ist vom Typ " [chooabfont](/windows/win32/api/commdlg/ns-commdlg-choosefontw)". Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

Nachdem Sie die Steuerelemente des Dialog Felds initialisiert haben `DoModal` , können Sie die Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer zu ermöglichen, eine Schriftart auszuwählen. `DoModal`Gibt zurück, ob der Benutzer die Schaltfläche OK (IDOK) oder Abbrechen (IDCANCEL) ausgewählt hat.

Wenn `DoModal` IDOK zurückgibt, können Sie eine der `CFontDialog`-Member-Funktionen verwenden, um die vom Benutzer eingegebenen Informationen abzurufen.

Mit der Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) können Sie feststellen, ob ein Fehler während der Initialisierung des Dialog Felds aufgetreten ist, und weitere Informationen zu diesem Fehler erhalten. Weitere Informationen zu dieser Funktion finden Sie in der Windows SDK.

`CFontDialog`basiert auf der kommdlg. DLL-Datei, die in der Windows-Version 3,1 und höher enthalten ist.

Zum Anpassen des Dialog Felds leiten Sie eine Klasse von `CFontDialog`ab, geben Sie eine benutzerdefinierte Dialogfeld Vorlage an, und fügen Sie eine Message-Map hinzu, um die Benachrichtigungs Meldungen von den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übermittelt werden.

Das Anpassen der Hook-Funktion ist nicht erforderlich.

Weitere Informationen zum Verwenden von `CFontDialog`finden Sie unter [Allgemeine Dialog Klassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="cfontdialog"></a>CFontDialog:: CFontDialog

Erstellt ein `CFontDialog`-Objekt.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*plfInitial*<br/>
Ein Zeiger auf eine [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Datenstruktur, mit der Sie einige der Schriftart Eigenschaften festlegen können.

*charFormat*<br/>
Ein Zeiger auf eine [Charformat](/windows/win32/api/richedit/ns-richedit-_charformat) -Datenstruktur, mit der Sie einige der Schriftart Merkmale in einem Rich-Edit-Steuerelement festlegen können.

*dwFlags*<br/>
Bestimmt eine oder mehrere Schriftart-wählen-Flags. Ein oder mehrere Vorgabewerte können mit dem bitweisen OR-Operator kombiniert werden. Wenn Sie den `m_cf.Flag`s-Strukturmember ändern, stellen Sie sicher, dass Sie einen bitweisen OR-Operator bei Ihren Änderungen verwenden, um das Standardverhalten unverändert zu lassen. Ausführliche Informationen zu den einzelnen Flags finden Sie in der Beschreibung der [Auswahl Schriftart](/windows/win32/api/commdlg/ns-commdlg-choosefontw) in der Windows SDK.

*pdcPrinter*<br/>
Ein Zeiger auf einen Druckgerätekontext. Sofern bereitgestellt, verweist dieser Parameter auf einen Druckgerätekontext für den Drucker, auf dem die Schriftarten ausgewählt werden sollen.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster oder das Besitzerfenster des Schriftartdialogfelds.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass der Konstruktor automatisch die Member der `CHOOSEFONT`-Struktur ausfüllt. Sie sollten diese nur ändern, wenn Sie ein anderes Schriftartdialogfeld als das standardmäßige verwenden möchten.

> [!NOTE]
>  Die erste Version dieser Funktion existiert nur, wenn es keine Unterstützung für das Rich-Edit-Steuerelement gibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

##  <a name="domodal"></a>CFontDialog::D omodal

Mit dieser Funktion können Sie das Windows-Dialogfeld "allgemeine Schriftart" anzeigen und dem Benutzer die Auswahl einer Schriftart gestatten.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) auf, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder Abbrechen ausgewählt hat.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Schriftart Dialogfeld-Steuerelemente durch Festlegen von Membern der [m_cf](#m_cf) -Struktur initialisieren möchten, sollten `DoModal`Sie dies vor dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie andere Element Funktionen aufrufen, um die Einstellungen oder Informationen einzugeben, die der Benutzer im Dialogfeld abruft.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie in den Beispielen für [CFontDialog:: CFontDialog](#cfontdialog) und [CFontDialog:: GetColor](#getcolor).

##  <a name="getcharformat"></a>CFontDialog:: getcharformat

Ruft die Zeichen Formatierung der ausgewählten Schriftart ab.

```
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Parameter

*cf*<br/>
Eine [Charformat](/windows/win32/api/richedit/ns-richedit-_charformat) -Struktur, die Informationen über die Zeichen Formatierung der ausgewählten Schriftart enthält.

##  <a name="getcolor"></a>CFontDialog:: GetColor

Rufen Sie diese Funktion auf, um die ausgewählte Schriftfarbe abzurufen.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe der ausgewählten Schriftart.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

##  <a name="getcurrentfont"></a>CFontDialog:: getcurrentfont

Mit dieser Funktion werden die Merkmale der aktuell ausgewählten Schriftart den Membern einer [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur zugewiesen.

```
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Parameter

*lplf*<br/>
Ein Zeiger auf eine `LOGFONT` -Struktur.

### <a name="remarks"></a>Hinweise

Für `CFontDialog` den Zugriff auf einzelne Merkmale der aktuellen Schriftart werden andere Element Funktionen bereitgestellt.

Wenn diese Funktion während eines Aufrufs von [DoModal](#domodal)aufgerufen wird, wird die aktuelle Auswahl zurückgegeben (was der Benutzer im Dialogfeld sieht oder geändert hat). Wenn diese Funktion nach einem Aufruf von `DoModal` aufgerufen wird (nur wenn `DoModal` IDOK zurückgibt), gibt Sie zurück, was der Benutzer tatsächlich ausgewählt hat.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

##  <a name="getfacename"></a>CFontDialog:: getfakename

Rufen Sie diese Funktion auf, um den Namen der Vorderseite der ausgewählten Schriftart abzurufen.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Gesichts Name der im `CFontDialog` Dialogfeld ausgewählten Schriftart.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

##  <a name="getsize"></a>CFontDialog:: GetSize

Rufen Sie diese Funktion auf, um die Größe der ausgewählten Schriftart abzurufen.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe der Schriftart in Zehntel eines Punkts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

##  <a name="getstylename"></a>CFontDialog:: getstylename

Mit dieser Funktion wird der Stilname der ausgewählten Schriftart abgerufen.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Stilname der Schriftart.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

##  <a name="getweight"></a>CFontDialog:: getweight

Rufen Sie diese Funktion auf, um die Gewichtung der ausgewählten Schriftart abzurufen.

```
int GetWeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die Gewichtung der ausgewählten Schriftart.

### <a name="remarks"></a>Hinweise

Weitere Informationen über die Gewichtung einer Schriftart finden Sie unter [CFont::](../../mfc/reference/cfont-class.md#createfont)up.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

##  <a name="isbold"></a>CFontDialog:: isbold

Mit dieser Funktion können Sie ermitteln, ob die ausgewählte Schriftart fett formatiert ist.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn für die ausgewählte Schriftart das Fett formatierte Merkmal aktiviert ist. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

##  <a name="isitalic"></a>CFontDialog:: IsItalic

Mit dieser Funktion können Sie ermitteln, ob die ausgewählte Schriftart kursiv formatiert ist.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn für die ausgewählte Schriftart das kursiv formatierte Merkmal aktiviert ist. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

##  <a name="isstrikeout"></a>CFontDialog:: isstrikeout

Mit dieser Funktion können Sie ermitteln, ob die ausgewählte Schriftart mit Strikeout angezeigt wird.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn für die ausgewählte Schriftart das Strikeout-Merkmal aktiviert ist. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

##  <a name="isunderline"></a>CFontDialog:: isunter Streichung

Mit dieser Funktion können Sie ermitteln, ob die ausgewählte Schriftart unterstrichen ist.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn für die ausgewählte Schriftart die Unterstreichung markiert ist. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

##  <a name="m_cf"></a>CFontDialog:: m_cf

Eine-Struktur, deren Elemente die Merkmale des Dialog Objekts speichern.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Hinweise

Nachdem Sie ein `CFontDialog` -Objekt erstellt haben, `m_cf` können Sie verwenden, um verschiedene Aspekte des Dialog Felds vor `DoModal` dem Aufrufen der Member-Funktion zu ändern. Weitere Informationen zu dieser Struktur finden Sie unter [ausgewählter Schriftart](/windows/win32/api/commdlg/ns-commdlg-choosefontw) in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
