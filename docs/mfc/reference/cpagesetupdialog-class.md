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
ms.openlocfilehash: 18b17d0f40aaab6ba2a018a568950549eda23016
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503014"
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
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext zum Drucken.|
|[CPageSetupDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Gibt den Gerätenamen des Druckers zurück.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Gibt den aktuellen DEVMODE-Wert des Druckers zurück.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|Gibt den vom Drucker verwendeten Treiber zurück.|
|[CPageSetupDialog::GetMargins](#getmargins)|Gibt die aktuellen Rand Einstellungen des Druckers zurück.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Gibt das Papierformat des Druckers zurück.|
|[CPageSetupDialog::GetPortName](#getportname)|Gibt den Namen des Ausgabeports zurück.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Wird von Framework aufgerufen, um ein Bildschirm Bild einer gedruckten Seite zu Rendering.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Wird von Framework aufgerufen, bevor ein Bildschirm Bild einer gedruckten Seite gerendert wird.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Eine-Struktur, mit der `CPageSetupDialog` ein-Objekt angepasst wird.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist darauf ausgelegt, den Platz des Dialog Felds Druck Setup zu verwenden.

Um ein `CPageSetupDialog` -Objekt zu verwenden, erstellen Sie zunächst das `CPageSetupDialog` -Objekt mit dem-Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie alle Werte im `m_psd` Datenmember festlegen oder ändern, um die Werte der Steuerelemente des Dialog Felds zu initialisieren. Die [m_psd](#m_psd) -Struktur ist vom Typ pagesetupdlg.

Nachdem Sie die Dialogfeld Steuerelemente initialisiert haben `DoModal` , können Sie die Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer die Auswahl von Druckoptionen zu ermöglichen. `DoModal`Gibt zurück, ob der Benutzer die Schaltfläche OK (IDOK) oder Abbrechen (IDCANCEL) ausgewählt hat.

Wenn `DoModal` IDOK zurückgibt, können Sie mehrere der `CPageSetupDialog`Element Funktionen verwenden oder auf den `m_psd` Datenmember zugreifen, um die vom Benutzer eingegebenen Informationen abzurufen.

> [!NOTE]
>  Nach dem verwerfen des Dialog Felds Common OLE Page Setup werden alle vom Benutzer vorgenommenen Änderungen nicht vom Framework gespeichert. Es liegt an der Anwendung selbst, alle Werte aus diesem Dialogfeld an einem permanenten Speicherort zu speichern, z. b. in dem Dokument oder in der Anwendungsklasse der Anwendung.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="cpagesetupdialog"></a>CPageSetupDialog:: CPageSetupDialog

Mit dieser Funktion können Sie ein `CPageSetupDialog` -Objekt erstellen.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen des Dialog Felds anzupassen. Die Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutungen:

- PSD_DEFAULTMINMARGINS legt die minimale zulässige Breite für die Seitenränder fest, sodass Sie mit den Minimums des Druckers identisch sind. Dieses Flag wird ignoriert, wenn die Flags PSD_MARGINS und PSD_MINMARGINS ebenfalls angegeben sind.

- PSD_INWININIINTLMEASURE nicht implementiert.

- PSD_MINMARGINS bewirkt, dass das System die im `rtMinMargin` -Member angegebenen Werte als minimale zulässige Breite für den linken, oberen, rechten und unteren Rand verwendet. Das System hindert den Benutzer an der Eingabe einer Breite, die kleiner ist als die angegebene Mindestanzahl. Wenn PSD_MINMARGINS nicht angegeben ist, legt das System die minimale zulässige Breite auf die vom Drucker zugelassenen Werte fest.

- PSD_MARGINS aktiviert den Rand Steuerungs Bereich.

- PSD_INTHOUSANDTHSOFINCHES bewirkt, dass die Einheiten des Dialog Felds in 1/1000 Zoll gemessen werden.

- PSD_INHUNDREDTHSOFMILLIMETERS bewirkt, dass die Einheiten des Dialog Felds in 1/100 Millimeter gemessen werden.

- PSD_DISABLEMARGINS deaktiviert die Dialogfeld-Steuerelemente für Rand.

- PSD_DISABLEPRINTER deaktiviert die Schaltfläche Drucker.

- PSD_NOWARNING verhindert, dass die Warnmeldung angezeigt wird, wenn kein Standarddrucker vorhanden ist.

- PSD_DISABLEORIENTATION deaktiviert das Dialogfeld Steuerelement Seitenausrichtung.

- PSD_RETURNDEFAULT bewirkt `CPageSetupDialog` , dass [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen zurückgegeben werden, die für den System Standarddrucker initialisiert werden, ohne dass ein Dialogfeld angezeigt wird. Es wird davon ausgegangen, `hDevNames` dass `hDevMode` sowohl als auch NULL sind; andernfalls gibt die Funktion einen Fehler zurück. Wenn der System Standarddrucker von einem alten Druckertreiber unterstützt wird (früher als Windows Version 3,0), `hDevNames` wird nur zurückgegeben. `hDevMode` ist NULL.

- PSD_DISABLEPAPER deaktiviert das Steuerelement für die Papier Auswahl.

- PSD_SHOWHELP bewirkt, dass im Dialogfeld die Schaltfläche Hilfe angezeigt wird. Der `hwndOwner` Member darf nicht NULL sein, wenn dieses Flag angegeben wird.

- PSD_ENABLEPAGESETUPHOOK aktiviert die Hook-Funktion, `lpfnSetupHook`die in angegeben ist.

- PSD_ENABLEPAGESETUPTEMPLATE bewirkt, dass das-Betriebssystem das Dialogfeld mit dem Dialogfeld Vorlagen Feld erstellt `hInstance` , `lpSetupTemplateName`das von und identifiziert wird.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE gibt an `hInstance` , dass einen Datenblock identifiziert, der eine vorab geladene Dialogfeld Vorlage enthält. Das System ignoriert `lpSetupTemplateName` , wenn dieses Flag angegeben wird.

- PSD_ENABLEPAGEPAINTHOOK aktiviert die Hook-Funktion, `lpfnPagePaintHook`die in angegeben ist.

- PSD_DISABLEPAGEPAINTING deaktiviert den Zeichnungs Bereich des Dialog Felds.

*pParentWnd*<br/>
Zeiger auf das übergeordnete Element oder den Besitzer des Dialog Felds.

### <a name="remarks"></a>Hinweise

Verwenden Sie die Funktion [DoModal](../../mfc/reference/cdialog-class.md#domodal) , um das Dialogfeld anzuzeigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>CPageSetupDialog:: "kreateprinterdc"

Erstellt einen Drucker Gerätekontext aus den [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker Gerätekontext (DC).

##  <a name="domodal"></a>CPageSetupDialog::D omodal

Mit dieser Funktion können Sie das Windows Common OLE Page Setup-Dialogfeld anzeigen und dem Benutzer die Auswahl verschiedener Druck Setup Optionen (z. b. Druckränder, Größe und Ausrichtung des Papiers und Ziel Druckers) ermöglichen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) auf, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder Abbrechen ausgewählt hat.

### <a name="remarks"></a>Hinweise

Außerdem kann der Benutzer auf die Installationsoptionen für den Drucker zugreifen, z. b. Netzwerk Speicherort und Eigenschaften, die für den ausgewählten Drucker spezifisch sind.

Wenn Sie die verschiedenen Seiten Setup Dialogfelder durch Festlegen der Elemente der `m_psd` Struktur initialisieren möchten, sollten Sie dies vor dem Aufrufen `DoModal`von und nach dem Erstellen des Dialog Objekts tun. Rufen Sie `DoModal`nach dem Aufrufen von andere Element Funktionen auf, um die Einstellungen oder die Eingabeinformationen vom Benutzer in das Dialogfeld abzurufen.

Wenn Sie die vom Benutzer eingegebenen aktuellen Einstellungen weitergeben möchten, müssen Sie [CWinApp:: selectprinter](../../mfc/reference/cwinapp-class.md#selectprinter)aufrufen. Diese Funktion übernimmt die Informationen aus dem `CPageSetupDialog` -Objekt und initialisiert und wählt einen neuen Drucker-DC mit den richtigen Attributen aus.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CPageSetupDialog:: CPageSetupDialog](#cpagesetupdialog).

##  <a name="getdevicename"></a>CPageSetupDialog:: GetDeviceName

Rufen Sie diese Funktion `DoModal` nach auf, um den Namen des aktuell ausgewählten Druckers abzurufen.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Gerätename, der vom `CPageSetupDialog` -Objekt verwendet wird.

##  <a name="getdevmode"></a>CPageSetupDialog:: getdevmode

Rufen `DoModal` Sie diese Funktion nach dem Aufruf `CPageSetupDialog` von auf, um Informationen zum Drucker Gerätekontext des-Objekts abzurufen.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -Datenstruktur, die Informationen über die Geräte Initialisierung und die Umgebung eines Druck Treibers enthält. Sie müssen den von dieser Struktur erstellten Arbeitsspeicher mit der Funktion Windows [globalunlock](/windows/win32/api/winbase/nf-winbase-globalunlock) entsperren, die im Windows SDK beschrieben wird.

##  <a name="getdrivername"></a>CPageSetupDialog:: getDriverName

Rufen Sie diese Funktion nach dem Aufrufen von [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) auf, um den Namen des System definierten Drucker-Gerätetreibers abzurufen.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , der den Namen des System definierten Treibers angibt.

### <a name="remarks"></a>Hinweise

Verwenden Sie einen Zeiger auf `CString` das Objekt, `GetDriverName` das von als Wert `lpszDriverName` von zurückgegeben wird, in einem Aufrufen von [CDC:: anatedc](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getmargins"></a>CPageSetupDialog:: getMargin

Rufen Sie diese Funktion nach einem aufrufen `DoModal` von auf, um die Ränder des Drucker Gerätetreibers abzurufen.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Parameter

*lpRectMargins*<br/>
Ein Zeiger auf eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Druckränder für den aktuell ausgewählten Drucker (in 1/1000 Zoll oder 1/100 mm) beschreibt. Übergeben Sie NULL für diesen Parameter, wenn Sie an diesem Rechteck nicht interessiert sind.

*lpRectMinMargins*<br/>
Ein Zeiger auf `RECT` eine Struktur `CRect` oder ein Objekt, das die minimalen Druckränder für den aktuell ausgewählten Drucker (in 1/1000 Zoll oder 1/100 mm) beschreibt. Übergeben Sie NULL für diesen Parameter, wenn Sie an diesem Rechteck nicht interessiert sind.

##  <a name="getpapersize"></a>CPageSetupDialog:: getpapersize

Rufen Sie diese Funktion auf, um die für das Drucken ausgewählte Papiergröße abzurufen.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die für das Drucken ausgewählte Papiergröße (in 1/1000 Zoll oder 1/100 mm) enthält.

##  <a name="getportname"></a>CPageSetupDialog:: getportname

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um den Namen des aktuell ausgewählten Drucker Ports abzurufen.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Drucker Anschlusses.

##  <a name="m_psd"></a>CPageSetupDialog:: m_psd

Eine Struktur vom Typ pagesetupdlg, deren Member die Merkmale des Dialog Objekts speichern.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Hinweise

Nachdem Sie ein `CPageSetupDialog` -Objekt erstellt haben, `m_psd` können Sie verwenden, um verschiedene Aspekte des Dialog Felds vor `DoModal` dem Aufruf der Member-Funktion festzulegen.

Wenn Sie den `m_psd` Datenmember direkt ändern, überschreiben Sie jedes Standardverhalten.

Weitere Informationen zur [pagesetupdlg](/windows/win32/api/commdlg/ns-commdlg-psdw) -Struktur finden Sie in der Windows SDK.

Weitere Informationen finden Sie im Beispiel für [CPageSetupDialog:: CPageSetupDialog](#cpagesetupdialog).

##  <a name="ondrawpage"></a>CPageSetupDialog:: ondrawpage

Wird von Framework aufgerufen, um ein Bildschirm Bild einer gedruckten Seite zu zeichnen.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeiger auf den Drucker Gerätekontext.

*nMessage*<br/>
Gibt eine Meldung an, die den Bereich der Seite angibt, die gerade gezeichnet wird. Kann einen der folgenden Werte annehmen:

- WM_PSD_FULLPAGERECT der gesamte Seitenbereich.

- WM_PSD_MINMARGINRECT aktuelle minimale Ränder.

- WM_PSD_MARGINRECT aktuelle Ränder.

- WM_PSD_GREEKTEXTRECT Inhalt der Seite.

- WM_PSD_ENVSTAMPRECT Bereich, der für eine Poststempel Darstellung reserviert ist.

- WM_PSD_YAFULLPAGERECT Bereich für eine Rückgabe Adress Darstellung. Dieser Bereich erstreckt sich auf die Ränder des Bereichs der Beispielseite.

*lpRect*<br/>
Zeiger auf ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -oder [Rect](/windows/win32/api/windef/ns-windef-rect) -Objekt, das die Koordinaten des Zeichnungs Bereichs enthält.

### <a name="return-value"></a>Rückgabewert

Wert ungleich 0 (null), wenn behandelt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dieses Bild wird dann im Rahmen des allgemeinen Setup-Dialog Felds der OLE-Seite angezeigt. Die Standard Implementierung zeichnet ein Bild einer Textseite.

Überschreiben Sie diese Funktion, um die Zeichnung eines bestimmten Bereichs des Bilds oder das gesamte Bild anzupassen. Hierfür können Sie eine **Switch** -Anweisung mit **Case** -Anweisungen verwenden, die den Wert von *nmessage*überprüfen. Wenn Sie z. b. das Rendering der Inhalte des Seiten Bilds anpassen möchten, können Sie den folgenden Beispielcode verwenden:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Beachten Sie, dass Sie nicht jeden Fall von *nmessage*behandeln müssen. Sie können auswählen, ob eine Komponente des Bilds, mehrere Komponenten des Bilds oder der gesamte Bereich verarbeitet werden sollen.

##  <a name="predrawpage"></a>CPageSetupDialog::P redrawpage

Wird von Framework aufgerufen, bevor das Bildschirm Bild einer gedruckten Seite gezeichnet wird.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Parameter

*wPaper*<br/>
Gibt einen Wert an, der das Papierformat angibt. Bei diesem Wert kann es sich um einen der **DMPAPER_** -Werte handeln, die in der Beschreibung der [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -Struktur aufgeführt sind.

*wFlags*<br/>
Gibt die Ausrichtung des Papiers oder des Umschlags an und gibt an, ob der Drucker ein Punktmatrix-oder HPPCL-Gerät (Hewlett Packard Printer Control Language) ist. Dieser Parameter kann einen der folgenden Werte aufweisen:

- 0x001-Papier im Querformat (Punktmatrix)

- 0x003 Paper im Querformat (HPPCL)

- 0x005 Papier im Hochformat (Punktmatrix)

- 0x007-Papier im Hochformat (HPPCL)

- Umschlag 0x00b im Querformat (HPPCL)

- Umschlag 0x00d im Hochformat (Punktmatrix)

- 0x019-Umschlag im Querformat (Punktmatrix)

- Umschlag 0x01f im Hochformat (Punktmatrix)

*pPSD*<br/>
Zeiger auf eine `PAGESETUPDLG`-Struktur. Weitere Informationen zu [pagesetupdlg](/windows/win32/api/commdlg/ns-commdlg-psdw)finden Sie in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Wert ungleich 0 (null), wenn behandelt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um das Zeichnen des Bilds anzupassen. Wenn Sie diese Funktion überschreiben und true zurückgeben, müssen Sie das gesamte Bild zeichnen. Wenn Sie diese Funktion überschreiben und false zurückgeben, wird das gesamte Standardbild vom Framework gezeichnet.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WordPad](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
