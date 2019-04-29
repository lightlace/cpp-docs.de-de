---
title: CPageSetupDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 01a320fbcd9760bab484f3c75553613852ca9aed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373166"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog-Klasse

Kapselt die Dienste, die durch das allgemeine Windows-OLE-Dialogfeld "Seiteneinrichtung" bereitgestellt werden, zusammen mit zusätzlicher Unterstützung für das Festlegen und Ändern von Druckrändern.

## <a name="syntax"></a>Syntax

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Erstellt ein `CPageSetupDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext für das Drucken.|
|[CPageSetupDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer stellen eine Auswahl.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Gibt zurück, der Gerätename des Druckers.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Gibt den aktuelle DEVMODE des Druckers an.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|Gibt zurück, den Treiber, die vom Drucker verwendet.|
|[CPageSetupDialog::GetMargins](#getmargins)|Gibt die aktuellen Randeinstellungen des Druckers an.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Gibt zurück, das Papierformat des Druckers.|
|[CPageSetupDialog::GetPortName](#getportname)|Gibt den Namen der Ausgabe-Port.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Wird aufgerufen, durch das Framework eine Bildschirmgrafik einer gedruckten Seite gerendert wird.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Wird vom Framework aufgerufen, bevor eine Bildschirmgrafik einer gedruckten Seite gerendert wird.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Eine Struktur, die zum Anpassen einer `CPageSetupDialog` Objekt.|

## <a name="remarks"></a>Hinweise

Diese Klasse soll die Stelle im Dialogfeld einrichten.

Verwenden einer `CPageSetupDialog` Objekt, erstellen Sie zunächst das Objekt mit der `CPageSetupDialog` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der `m_psd` Datenmembers, der die Werte der Dialogfeld-Steuerelemente initialisieren. Die [M_psd](#m_psd) Struktur des Typs PAGESETUPDLG ist.

Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. `DoModal` Gibt zurück, ob der Benutzer die Schaltfläche "OK (IDOK) oder abzubrechen (IDCANCEL)" ausgewählt.

Wenn `DoModal` gibt IDOK, können Sie mehrere `CPageSetupDialog`Memberfunktionen oder Zugriff die `m_psd` Datenmember, zum Abrufen von Informationen vom Benutzer eingegebene.

> [!NOTE]
>  Nachdem das Standarddialogfeld für OLE-Seiteneinrichtung geschlossen wird, werden alle Änderungen, die vom Benutzer nicht durch das Framework gespeichert werden. Es ist Aufgabe der Anwendung selbst, alle Werte in diesem Dialogfeld an einem permanenten Speicherort, z. B. Mitglied der Anwendung Dokument oder eine Application-Klasse gespeichert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog

Mit dieser Funktion wird zum Erstellen einer `CPageSetupDialog` Objekt.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie, zum Anpassen der Einstellungen des Dialogfelds verwenden können. Die Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:

- PSD_DEFAULTMINMARGINS legt die minimale zulässige Breite für die Seitenränder des Druckers Mindestwerte identisch sein. Dieses Flag wird ignoriert, wenn die Flags PSD_MARGINS und PSD_MINMARGINS auch angegeben werden.

- PSD_INWININIINTLMEASURE nicht implementiert.

- PSD_MINMARGINS bewirkt, dass das System die im angegebenen Werte die `rtMinMargin` Member als die zulässige Mindestbreite für die Links, oben, rechten und unteren Rands. Das System verhindert, dass den Benutzer, der kleiner als die angegebene minimale Breite eingeben. Wenn PSD_MINMARGINS nicht angegeben ist, setzt das System die minimale zulässige Breite, mit denen vom Drucker zulässig.

- PSD_MARGINS aktiviert den Randbereich des Steuerelements.

- PSD_INTHOUSANDTHSOFINCHES bewirkt, dass die Einheiten im Dialogfeld in 1/1000 Zoll gemessen wird.

- PSD_INHUNDREDTHSOFMILLIMETERS bewirkt, dass die Einheiten im Dialogfeld in 1/100 Millimeter gemessen werden.

- PSD_DISABLEMARGINS deaktiviert den Rand Dialogfeld-Steuerelemente.

- PSD_DISABLEPRINTER deaktiviert die Schaltfläche "Drucker".

- PSD_NOWARNING wird verhindert, dass die Warnmeldung angezeigt wird, wenn es wurde kein Standarddrucker.

- PSD_DISABLEORIENTATION deaktiviert das Steuerelement Seite Ausrichtung des Dialogfelds.

- Bewirkt, dass PSD_RETURNDEFAULT `CPageSetupDialog` zurückzugebenden [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen, die für den Standarddrucker System initialisiert werden, ohne dass ein Dialogfeld angezeigt. Es wird davon ausgegangen, dass beide `hDevNames` und `hDevMode` NULL sind; andernfalls gibt die Funktion einen Fehler zurück. Wenn Sie der Standarddrucker System von einer alten Druckertreiber (älter als Windows-Version 3.0) unterstützt wird nur `hDevNames` zurückgegeben. `hDevMode` ist NULL.

- PSD_DISABLEPAPER deaktiviert das Steuerelement zur Auswahl von Papier.

- PSD_SHOWHELP bewirkt, dass das Dialogfeld die Hilfeschaltfläche angezeigt wird. Die `hwndOwner` Element darf nicht NULL sein, wenn dieses Flag angegeben ist.

- PSD_ENABLEPAGESETUPHOOK ermöglicht die Hookfunktion in angegebenen `lpfnSetupHook`.

- PSD_ENABLEPAGESETUPTEMPLATE bewirkt, dass das Betriebssystem, um das Dialogfeld zu erstellen, indem Sie die Vorlage im Dialogfeld identifizierte `hInstance` und `lpSetupTemplateName`.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE gibt an, dass `hInstance` identifiziert einen Datenblock, der eine vorab geladene Dialogfeldvorlage enthält. Das System ignoriert `lpSetupTemplateName` Wenn dieses Flag angegeben ist.

- PSD_ENABLEPAGEPAINTHOOK ermöglicht die Hookfunktion in angegebenen `lpfnPagePaintHook`.

- PSD_DISABLEPAGEPAINTING deaktiviert den Draw-Bereich des Dialogfelds.

*pParentWnd*<br/>
Zeiger auf das übergeordnete Element oder den Besitzer des Dialogfelds.

### <a name="remarks"></a>Hinweise

Verwenden der [DoModal](../../mfc/reference/cdialog-class.md#domodal) Funktion, um das Dialogfeld anzuzeigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC

Erstellt einen Drucker-Gerätekontext aus der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker-Gerätekontext (DC).

##  <a name="domodal"></a>  CPageSetupDialog::DoModal

Rufen Sie diese Funktion, um das Windows OLE-Seiteneinrichtung Standarddialogfeld anzuzeigen und der Benutzer die Auswahl verschiedener print Setup-Optionen wie z. B. die Druckränder, Größe und Ausrichtung der Artikel und Zieldrucker zu ermöglichen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche "OK" oder "Abbrechen" aktiviert.

### <a name="remarks"></a>Hinweise

Darüber hinaus kann der Benutzer die Drucker-Setup-Optionen wie z. B. die Netzwerkadresse und Eigenschaften, die spezifisch für den ausgewählten Drucker zugreifen.

Wenn Sie die verschiedenen Optionen der Seite Setup-Dialogfeld zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_psd` Struktur, gehen Sie daher vor dem Aufruf `DoModal`, und nachdem das Dialogfeldobjekt erstellt wird. Nach dem Aufruf `DoModal`, rufen Sie andere Memberfunktionen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.

Wenn Sie die aktuellen Einstellungen, die vom Benutzer eingegebene weitergeben möchten, stellen Sie einen Aufruf von [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Diese Funktion verwendet die Informationen aus der `CPageSetupDialog` -Objekt und initialisiert und wählt einen neuen Drucker-Gerätekontext mit den richtigen Attributen.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName

Rufen Sie diese Funktion nach `DoModal` zum Abrufen des Namens, der den aktuell ausgewählten Drucker.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des Geräts ein, die die `CPageSetupDialog` Objekt.

##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode

Mit dieser Funktion wird nach dem Aufruf `DoModal` Abrufen von Informationen zu den Drucker-Gerätekontext, der die `CPageSetupDialog` Objekt.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckertreibers enthält. Sie müssen den Arbeitsspeicher, die von dieser Struktur mit der Windows Entsperren [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) -Funktion, die im Windows SDK beschrieben wird.

##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName

Mit dieser Funktion wird nach dem Aufruf [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) zum Abrufen des Namens, der den systemeigenen Druckertreiber.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` den systemdefinierte Treibernamen angeben.

### <a name="remarks"></a>Hinweise

Verwenden eines Zeigers auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins

Mit dieser Funktion wird nach einem Aufruf von `DoModal` die Ränder des Druckertreibers Gerät abgerufen.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Parameter

*lpRectMargins*<br/>
Zeiger auf eine [RECT](/windows/desktop/api/windef/ns-windef-tagrect) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das (in 1/1000 Zoll oder 1/100 mm) die Druckränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie NULL für diesen Parameter fest, wenn Sie nicht dieses Rechteck interessiert sind.

*lpRectMinMargins*<br/>
Zeiger auf eine `RECT` Struktur oder `CRect` Objekt, das (in 1/1000 Zoll oder 1/100 mm) die minimalen Druckränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie NULL für diesen Parameter fest, wenn Sie nicht dieses Rechteck interessiert sind.

##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize

Rufen Sie diese Funktion, um die Größe des Papiers, der zum Drucken ausgewählte abzurufen.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Größe des Papiers (in 1/1000 Zoll oder 1/100 mm), die zum Drucken ausgewählte enthält.

##  <a name="getportname"></a>  CPageSetupDialog::GetPortName

Mit dieser Funktion wird nach dem Aufruf `DoModal` um den Namen des aktuell ausgewählten Ports abzurufen.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Ports.

##  <a name="m_psd"></a>  CPageSetupDialog::m_psd

Eine Struktur vom Typ PAGESETUPDLG, deren Mitglieder die Merkmale des Dialog-Objekts zu speichern.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CPageSetupDialog` -Objekts verwenden Sie `m_psd` festzulegende verschiedene Aspekte im Dialogfeld vor dem Aufruf der `DoModal` Member-Funktion.

Wenn Sie ändern die `m_psd` Datenmember direkt, überschreiben Sie Standardverhalten.

Weitere Informationen zu den [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda) Struktur, finden Sie im Windows SDK.

Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage

Wird aufgerufen, durch das Framework, um eine Bildschirmgrafik einer gedruckten Seite zu zeichnen.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeiger auf den Druckergerätekontext.

*nMessage*<br/>
Gibt eine Meldung an, den Bereich der Seite derzeit gerade gezeichnet wird. Einer der folgenden Werte ist möglich:

- WM_PSD_FULLPAGERECT den Bereich für die gesamte Seite.

- Aktuelle WM_PSD_MINMARGINRECT minimale Ränder.

- Aktuelle WM_PSD_MARGINRECT Ränder.

- WM_PSD_GREEKTEXTRECT den Inhalt der Seite.

- WM_PSD_ENVSTAMPRECT-Bereich für eine Darstellung der Verpackung Stempel reserviert.

- Eine Darstellung der Rückgabeadresse WM_PSD_YAFULLPAGERECT-Bereich. Dieser Bereich wird auf dem Rand des Seitenbereichs Beispiel erweitert.

*lpRect*<br/>
Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) oder [RECT](/windows/desktop/api/windef/ns-windef-tagrect) -Objekt, das die Koordinaten des Zeichenbereichs enthält.

### <a name="return-value"></a>Rückgabewert

Wert ungleich NULL, wenn behandelt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dieses Image wird als Teil der OLE-Seiteneinrichtung Standarddialogfeld angezeigt. Die Standardimplementierung zeichnet ein Bild einer Seite des Texts.

Überschreiben Sie diese Funktion, um das Zeichnen von einem bestimmten Bereich des Bilds, oder das gesamte Bild angepasst. Sie erreichen dies, indem eine **wechseln** -Anweisung mit **Fall** Anweisungen, die Überprüfung des Werts der *%nMeldung*. Um das Rendern des Inhalts der Seite, Bild anzupassen, könnten Sie z. B. den folgende Beispielcode verwenden:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Beachten Sie, dass Sie nicht alle vom behandeln müssen *%nMeldung*. Sie können auswählen, um eine Komponente des Bilds, mehrere Komponenten von dem Abbild oder den gesamten Bereich zu behandeln.

##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage

Vom Framework aufgerufen, bevor die Bildschirmgrafik einer gedruckten Seite zu zeichnen.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Parameter

*wPaper*<br/>
Gibt einen Wert, der das Papierformat angibt. Dieser Wert kann eine der der **DMPAPER_** Werte aufgeführt, in der Beschreibung der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Struktur.

*wFlags*<br/>
Gibt die Ausrichtung des Papiers oder Umschlag, und gibt an, ob der Drucker einen Matrix- oder ein HPPCL (Hewlett Packard Drucker Control Language)-Gerät ist. Dieser Parameter kann einen der folgenden Werte aufweisen:

- 0 x 001 Artikel werden die im Querformat (Punktmatrix)

- 0 x 003 Artikel werden die im Querformat (HPPCL)

- 0x005 Artikel werden die im Hochformat (Punktmatrix)

- 0x007 Artikel werden die im Hochformat (HPPCL)

- 0x00b Umschlag im Querformat (HPPCL)

- 0x00d Umschlag im Hochformat (Punktmatrix)

- 0x019 Umschlag im Querformat (Punktmatrix)

- 0x01f Umschlag im Hochformat (Punktmatrix)

*pPSD*<br/>
Zeiger auf eine `PAGESETUPDLG`-Struktur. Weitere Informationen zu [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda), finden Sie im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Wert ungleich NULL, wenn behandelt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um das Zeichnen des Bilds angepasst. Wenn Sie außer Kraft dieser Funktion setzen und "True gibt", müssen Sie das gesamte Bild zeichnen. Wenn Sie außer Kraft dieser Funktion setzen und "False gibt", wird das gesamte Standardbild durch das Framework gezeichnet.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
