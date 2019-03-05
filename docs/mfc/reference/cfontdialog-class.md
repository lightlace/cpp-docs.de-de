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
ms.openlocfilehash: 3dea0f2ba358582b49de107c234a66a751e8f0b0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267185"
---
# <a name="cfontdialog-class"></a>CFontDialog-Klasse

Ermöglicht Ihnen ein Dialogfeld zum auswählen Schriftart in Ihre Anwendung integrieren.

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
|[CFontDialog::DoModal](#domodal)|Zeigt das Dialogfeld, und ermöglicht dem Benutzer eine Auswahl treffen.|
|[CFontDialog::GetCharFormat](#getcharformat)|Ruft ab, die zeichenformatierung des dem ausgewählten Schriftart.|
|[CFontDialog::GetColor](#getcolor)|Gibt die Farbe der ausgewählten Schriftart zurück.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Die Merkmale des derzeit ausgewählten Schriftart zum weist eine `LOGFONT` Struktur.|
|[CFontDialog::GetFaceName](#getfacename)|Gibt den Schriftartnamen der ausgewählten Schriftart zurück.|
|[CFontDialog::GetSize](#getsize)|Gibt die Größe der ausgewählten Schriftart zurück.|
|[CFontDialog::GetStyleName](#getstylename)|Gibt den Formatnamen der ausgewählten Schriftart zurück.|
|[CFontDialog::GetWeight](#getweight)|Gibt die Gewichtung der ausgewählten Schriftart zurück.|
|[CFontDialog::IsBold](#isbold)|Bestimmt, ob die Schriftart fett formatiert ist.|
|[CFontDialog::IsItalic](#isitalic)|Bestimmt, ob die Schriftart kursiv formatiert ist.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|Bestimmt, ob die Schriftart durchgestrichen angezeigt wird.|
|[CFontDialog::IsUnderline](#isunderline)|Bestimmt, ob die Schriftart unterstrichen formatiert ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Eine Struktur, die zum Anpassen einer `CFontDialog` Objekt.|

## <a name="remarks"></a>Hinweise

Ein `CFontDialog` Objekt ist ein Dialogfeld mit einer Liste von Schriftarten, die derzeit im System installiert sind. Der Benutzer kann eine bestimmte Schriftart auswählen, aus der Liste aus, und diese Auswahl wird dann wieder an die Anwendung gemeldet.

Zum Erstellen einer `CFontDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor oder leiten Sie eine neue Unterklasse und Ihre eigenen benutzerdefinierten Konstruktor verwenden.

Einmal eine `CFontDialog` -Objekts wird, können Sie mit der `m_cf` Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die [M_cf](#m_cf) Struktur ist vom Typ [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

Rufen Sie nach dem Initialisieren des Dialogfeldobjekts-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, wählen Sie eine Schriftart. `DoModal` Gibt zurück, ob der Benutzer die Schaltfläche "OK (IDOK) oder abzubrechen (IDCANCEL)" ausgewählt.

Wenn `DoModal` gibt IDOK, können Sie eine der `CFontDialog`Member-Funktionen zum Abrufen der Informationen, die vom Benutzer eingegebene.

Sie können die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) -Funktion zu bestimmen, ob ein während der Initialisierung des Dialogfelds Fehler und Weitere Informationen zum Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.

`CFontDialog` basiert auf der COMMDLG. DLL-Datei, die in Windows-Versionen 3.1 und höher enthalten ist.

Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFontDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten in der Basisklasse übergeben werden.

Anpassen der Hookfunktion ist nicht erforderlich.

Weitere Informationen zur Verwendung von `CFontDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog

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
Ein Zeiger auf eine ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) -Datenstruktur, die Sie einige der Schriftmerkmale festlegen kann.

*charFormat*<br/>
Ein Zeiger auf eine [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) -Datenstruktur, die Ihnen ermöglicht, legen Sie einige der Schriftmerkmale in einem Rich edit-Steuerelement.

*dwFlags*<br/>
Bestimmt eine oder mehrere Schriftart-wählen-Flags. Ein oder mehrere Vorgabewerte können mit dem bitweisen OR-Operator kombiniert werden. Wenn Sie den `m_cf.Flag`s-Strukturmember ändern, stellen Sie sicher, dass Sie einen bitweisen OR-Operator bei Ihren Änderungen verwenden, um das Standardverhalten unverändert zu lassen. Finden Sie ausführliche Informationen zu diesen Flags, die Beschreibung der [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) Struktur im Windows SDK.

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

##  <a name="domodal"></a>  CFontDialog::DoModal

Mit dieser Funktion können zeigt das Dialogfeld allgemeine Schriftart Windows und ermöglicht dem Benutzer für eine Schriftart entscheiden.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche "OK" oder "Abbrechen" aktiviert.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Schriftart Dialogfeld-Steuerelemente initialisieren, indem Sie Mitglieder festlegen möchten die [M_cf](#m_cf) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.

### <a name="example"></a>Beispiel

  Finden Sie unter den Beispielen für [CFontDialog::CFontDialog](#cfontdialog) und [CFontDialog::GetColor](#getcolor).

##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat

Ruft ab, die zeichenformatierung des dem ausgewählten Schriftart.

```
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Parameter

*cf*<br/>
Ein [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Struktur, die Informationen über die zeichenformatierung des dem ausgewählten Schriftart enthält.

##  <a name="getcolor"></a>  CFontDialog::GetColor

Rufen Sie diese Funktion, um die ausgewählte Schriftfarbe abzurufen.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe der ausgewählten Schriftart.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont

Mit dieser Funktion können Sie die Eigenschaften der derzeit ausgewählten Schriftart auf die Member des weisen eine ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur.

```
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Parameter

*lplf*<br/>
Ein Zeiger auf eine `LOGFONT` Struktur.

### <a name="remarks"></a>Hinweise

Andere `CFontDialog` Member-Funktionen werden bereitgestellt, um die einzelnen Eigenschaften der aktuellen Schriftart zugreifen.

Wenn während eines Aufrufs dieser Funktion aufgerufen wird [DoModal](#domodal), zum Zeitpunkt die aktuelle Auswahl wird (was der Benutzer sieht, oder wurde im Dialogfeld geändert). Wenn diese Funktion, nach einem Aufruf von aufgerufen wird `DoModal` (nur, wenn `DoModal` IDOK zurückgibt), was den Benutzer tatsächlich ausgewählt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

##  <a name="getfacename"></a>  CFontDialog::GetFaceName

Rufen Sie diese Funktion zum Abrufen der Name des Gesichts der ausgewählten Schriftart.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des Gesichts der ausgewählten Schriftart der `CFontDialog` Dialogfeld.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

##  <a name="getsize"></a>  CFontDialog::GetSize

Rufen Sie diese Funktion zum Abrufen der Größe der ausgewählten Schriftart.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Der Schriftgrad, Uhrzeitdaten eines Punkts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

##  <a name="getstylename"></a>  CFontDialog::GetStyleName

Rufen Sie diese Funktion zum Abrufen der Namen der Formatvorlage der ausgewählten Schriftart.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name der Stil der Schriftart.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

##  <a name="getweight"></a>  CFontDialog::GetWeight

Rufen Sie diese Funktion zum Abrufen der Breite der ausgewählten Schriftart.

```
int GetWeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die Gewichtung der ausgewählten Schriftart.

### <a name="remarks"></a>Hinweise

Weitere Informationen auf der Last einer Schriftart finden Sie unter [CFont::](../../mfc/reference/cfont-class.md#createfont).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

##  <a name="isbold"></a>  CFontDialog::IsBold

Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart fett formatiert ist.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die ausgewählte Schriftart das fett Merkmal aktiviert wurde; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

##  <a name="isitalic"></a>  CFontDialog::IsItalic

Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart kursiv formatiert ist.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die ausgewählte Schriftart das kursive Merkmal aktiviert ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut

Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart durchgestrichen angezeigt wird.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die ausgewählte Schriftart die durchgestrichen-Eigenschaft aktiviert ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

##  <a name="isunderline"></a>  CFontDialog::IsUnderline

Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart unterstrichen formatiert ist.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die ausgewählte Schriftart die Unterstreichung-Eigenschaft aktiviert ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

##  <a name="m_cf"></a>  CFontDialog::m_cf

Eine Struktur, deren Mitglieder die Merkmale des Dialog-Objekts zu speichern.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CFontDialog` -Objekts verwenden Sie `m_cf` so ändern Sie die verschiedenen Aspekte der im Dialogfeld vor dem Aufruf der `DoModal` Member-Funktion. Weitere Informationen zu dieser Struktur finden Sie unter [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
