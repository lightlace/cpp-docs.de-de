---
title: CPrintDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: 2a856c8067394e33976ba8ccdaa34be81ee11091
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58771044"
---
# <a name="cprintdialog-class"></a>CPrintDialog-Klasse

Kapselt die Dienste, die vom allgemeinen Windows-Dialogfeld für das Drucken bereitgestellt werden.

## <a name="syntax"></a>Syntax

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Erstellt ein `CPrintDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen druckergerätkontext ohne Anzeige des Dialogfelds drucken.|
|[CPrintDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|
|[CPrintDialog::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|
|[CPrintDialog::GetDefaults](#getdefaults)|Ruft die Standardeinstellungen des Geräts ohne das Anzeigen eines Dialogfelds ab.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Ruft den Namen des Geräts aktuell ausgewählten Drucker.|
|[CPrintDialog::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|
|[CPrintDialog::GetDriverName](#getdrivername)|Ruft den Namen des aktuell ausgewählten Drucker-Treibers ab.|
|[CPrintDialog::GetFromPage](#getfrompage)|Ruft die Startseite des drucken Bereichs ab.|
|[CPrintDialog::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Ports.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker-Gerätekontext ab.|
|[CPrintDialog::GetToPage](#gettopage)|Ruft die Endseite des drucken Bereichs ab.|
|[CPrintDialog::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments zu drucken.|
|[CPrintDialog::PrintCollate](#printcollate)|Bestimmt, ob die sortierte Kopien angefordert werden.|
|[CPrintDialog::PrintRange](#printrange)|Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.|
|[CPrintDialog::PrintSelection](#printselection)|Bestimmt, ob nur die ausgewählten Elemente zu drucken.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Eine Struktur, die zum Anpassen einer `CPrintDialog` Objekt.|

## <a name="remarks"></a>Hinweise

Drucken Standarddialogfelder bieten eine einfache Möglichkeit zum Drucken und Drucken von Setup-Dialogfelder in Übereinstimmung mit den Windows-Standards zu implementieren.

> [!NOTE]
>  Die `CPrintDialogEx` Klasse kapselt die Dienste, die von der Windows-druckeigenschaftenblatt bereitgestellt. Weitere Informationen finden Sie unter den [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Übersicht.

`CPrintDialog`die Funktionalität wird von der abgelöst [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), die Sie für beide das Setup und Seite drucken ein Standarddialogfeld bereitstellen soll.

Sie können das Framework, behandeln zahlreiche Aspekte des Druckvorgangs für Ihre Anwendung verwenden. In diesem Fall zeigt das Framework automatisch die Windows-Standarddialogfeld zum Drucken. Sie können auch das Framework-Handle, das für Ihre Anwendung drucken haben jedoch außer Kraft setzen das Standarddialogfeld Drucken mit aktiviertem Kontrollkästchen für Ihre eigenen Dialogfeld "Drucken". Weitere Informationen zur Verwendung von Framework Druckaufgaben behandelt, finden Sie im Artikel [Drucken](../../mfc/printing.md).

Wenn Sie Ihre Anwendung drucken, ohne die Framework Beteiligung verarbeiten möchten, können Sie die `CPrintDialog` -Klasse "wie besehen" mit dem Konstruktor angegeben oder Sie können Ihre eigenen Dialogfeldklasse von ableiten `CPrintDialog` und schreiben ein Konstruktors entsprechend Ihren Anforderungen. In beiden Fällen Aufrufen dieser Dialogfelder verhält sich wie die standard-MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.

Verwenden einer `CPrintDialog` Objekt, erstellen Sie zunächst das Objekt mit der `CPrintDialog` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pd](#m_pd) Struktur zum Initialisieren der Werte der Dialogfeld-Steuerelemente. Die `m_pd` Struktur ist vom Typ [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

Wenn Sie keine eigene Handles im angeben `m_pd` für die `hDevMode` und `hDevNames` Member, achten Sie darauf, dass Sie die Windows-Funktion aufrufen `GlobalFree` für diese Handles, wenn Sie das Dialogfeld abgeschlossen haben. Bei Verwendung des Frameworks einrichten-Implementierung von `CWinApp::OnFilePrintSetup`, Sie müssen keine diese Handles frei. Die Handles werden vom verwaltet `CWinApp` und freigegeben werden, `CWinApp`den Destruktor. Es ist nur erforderlich, diese Handles freizugeben, wenn mit `CPrintDialog` eigenständigen.

Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. `DoModal` Gibt zurück, ob der Benutzer die Schaltfläche "OK (IDOK) oder abzubrechen (IDCANCEL)" ausgewählt.

Wenn `DoModal` gibt IDOK, können Sie eine der `CPrintDialog`Member-Funktionen zum Abrufen der Informationen, die vom Benutzer eingegebene.

Die `CPrintDialog::GetDefaults` Member-Funktion ist nützlich, um den aktuellen Druckerstandardeinstellungen abzurufen, ohne ein Dialogfeld angezeigt. Diese Memberfunktion ist kein Benutzereingriff erforderlich.

Sie können die Windows `CommDlgExtendedError` -Funktion zu bestimmen, ob ein während der Initialisierung des Dialogfelds Fehler und Weitere Informationen zum Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.

`CPrintDialog` basiert auf der COMMDLG. DLL-Datei, die in Windows-Versionen 3.1 und höher enthalten ist.

Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CPrintDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollte auf die Basisklasse übergeben werden. Anpassen der Hookfunktion ist nicht erforderlich.

Um die gleiche Nachricht unterschiedlich je nachdem, ob das Dialogfeld Drucken oder einrichten zu verarbeiten, müssen Sie eine Klasse für jedes Dialogfeld ableiten. Sie müssen auch überschreiben, die Windows `AttachOnSetup` -Funktion, die die Erstellung eines neuen Dialogfelds behandelt, wenn die Schaltfläche "Drucken Setup" in einem Druckdialogfeld ausgewählt ist.

Weitere Informationen zur Verwendung von `CPrintDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog

Erstellt eine Windows-Druckserver oder Print Setup-Dialogfeld-Objekt.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*bPrintSetupOnly*<br/>
Gibt an, ob das Drucken von Windows-Standarddialogfeld oder Drucken einrichten (Dialogfeld) angezeigt wird. Legen Sie diesen Parameter auf True, um anzuzeigen, das Standarddialogfeld für Windows einrichten. Legen Sie sie auf "false", um das Dialogfeld Drucken von Windows anzuzeigen. Wenn *bPrintSetupOnly* ist "false", ein Optionsfeld noch immer, in das Dialogfeld Drucken angezeigt wird einrichten.

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie, zum Anpassen der Einstellungen im Dialogfeld verwenden können, mit dem bitweisen OR-Operator kombiniert. Beispielsweise legt das Flag PD_ALLPAGES drucken Standardbereich für alle Seiten des Dokuments. Finden Sie unter den [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Struktur im Windows SDK für Weitere Informationen zu diesen Flags.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element oder Besitzer des Dialogfelds-Fenster.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird nur das Objekt erstellt. Verwenden der `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen.

Beachten Sie, dass beim Aufrufen des Konstruktors mit *bPrintSetupOnly* auf "false" festgelegt, wird automatisch das PD_RETURNDC-Flag verwendet. Nach dem Aufruf `DoModal`, `GetDefaults`, oder `GetPrinterDC`, um ein druckerdomänencontroller werden im zurückgegeben `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) durch den Aufrufer der `CPrintDialog`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC

Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker-Gerätekontext.

### <a name="remarks"></a>Hinweise

Dieser DC wird als den aktuellen Drucker-Gerätekontext aus, und alle anderen zuvor abgerufen haben, Drucker, den Domänencontroller, die vom Benutzer gelöscht werden müssen. Diese Funktion kann aufgerufen werden, und der daraus resultierende DC verwendet, ohne jemals Anzeige des Dialogfelds drucken.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>  CPrintDialog::DoModal

Zeigt das Dialogfeld "Drucken" der Windows-Standarddialogfeld an und ermöglicht dem Benutzer, wählen Sie die verschiedenen Druckoptionen wie z. B. die Anzahl der Kopien, Seitenbereich, und gibt an, ob Kopien sortiert werden sollen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche "OK" oder "Abbrechen" aktiviert.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Optionen für Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pd` Struktur, Sie sollten dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.

Beachten Sie, dass beim Aufrufen des Konstruktors mit *bPrintSetupOnly* auf "false" festgelegt, wird automatisch das PD_RETURNDC-Flag verwendet. Nach dem Aufruf `DoModal`, `GetDefaults`, oder `GetPrinterDC`, um ein druckerdomänencontroller werden im zurückgegeben `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) durch den Aufrufer der `CPrintDialog`.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::CreatePrinterDC](#createprinterdc).

##  <a name="getcopies"></a>  CPrintDialog::GetCopies

Ruft die Anzahl der Kopien, die angefordert.

```
int GetCopies() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Kopien, die angefordert werden soll.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen der Anzahl der Kopien, die angefordert.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults

Ruft ab die Gerätestandards von den Standarddrucker ohne ein Dialogfeld angezeigt.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die abgerufenen Werte befinden sich der `m_pd` Struktur.

In einigen Fällen ein Aufruf dieser Funktion rufen die [Konstruktor](#cprintdialog) für `CPrintDialog` mit *bPrintSetupOnly* auf "false" festgelegt. In diesen Fällen um einen druckerdomänencontroller und `hDevNames` und `hDevMode` (zwei Handles befindet sich in der `m_pd` Datenmember) werden automatisch zugewiesen.

If der Konstruktor für `CPrintDialog` aufgerufen wurde, wobei *bPrintSetupOnly* auf "false" festgelegt, diese Funktion wird nicht nur zurückgeben `hDevNames` und `hDevMode` befindet sich in `m_pd.hDevNames` und `m_pd.hDevMode`) an den Aufrufer aber gibt auch einen druckerdomänencontroller in `m_pd.hDC`. Es liegt in der Verantwortung des Aufrufers, löschen den Drucker-Gerätekontext aus, und rufen die Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) Funktion auf die Ziehpunkte, die Sie abschließend mit der `CPrintDialog` Objekt.

### <a name="example"></a>Beispiel

Dieses Codefragment wird von den Standarddrucker Gerätekontext und meldet dem Benutzer die Auflösung des Druckers in Punkten pro Zoll. (Dieses Attribut der Funktionen des Druckers ist häufig als DPI-Werte bezeichnet.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName

Ruft den Namen des Geräts aktuell ausgewählten Drucker.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Drucker.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers, oder klicken Sie nach dem Aufruf [GetDefaults](#getdefaults) um die aktuellen Gerät Standardeinstellungen des Standarddruckers abzurufen. Verwenden eines Zeigers auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Beispiel

Dieses Codefragment zeigt den standardmäßigen Drucker des Benutzers und den Port an, die, den Sie zusammen mit dem Namen der Spooler verbunden ist, die der Drucker verwendet. Der Code möglicherweise ein Dialogfeld mit der Meldung, zeigt "der Standarddrucker ist HP LaserJet IIIP \\\server\share mit WINSPOOL verwendet.", z. B.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode

Ruft die `DEVMODE` Struktur.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckertreibers enthält. Sie müssen den Arbeitsspeicher, die von dieser Struktur mit der Windows Entsperren [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) -Funktion, die im Windows SDK beschrieben wird.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) Abrufen von Informationen über das Druckgerät.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName

Ruft den Namen des aktuell ausgewählten Drucker-Treibers ab.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` den systemdefinierte Treibernamen angeben.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens, der den systemeigenen Druckertreiber. Verwenden eines Zeigers auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage

Ruft die Startseite des drucken Bereichs ab.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Seitenzahl im Bereich der zu druckenden Seiten.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` die Seitenzahl der ersten im Bereich der zu druckenden Seiten abrufen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).

##  <a name="getportname"></a>  CPrintDialog::GetPortName

Ruft den Namen des aktuell ausgewählten Ports.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Ports.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) um den Namen des aktuell ausgewählten Ports abzurufen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC

Ruft ein Handle für den Drucker-Gerätekontext ab.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den Drucker-Gerätekontext bei erfolgreicher Ausführung; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn die *bPrintSetupOnly* Parameter, der die `CPrintDialog` Konstruktor wurde "false" (gibt an, dass das Drucken-Dialogfeld angezeigt wird), klicken Sie dann `GetPrinterDC` gibt ein Handle für den Drucker-Gerätekontext. Rufen Sie die Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) Funktion, um den Gerätekontext zu löschen, wenn Sie fertig sind verwenden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>  CPrintDialog::GetToPage

Ruft die Endseite des drucken Bereichs ab.

```
int GetToPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die abschließende Seitenzahl im Bereich der zu druckenden Seiten.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` die Endseitennummer im Bereich der zu druckenden Seiten abrufen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).

##  <a name="m_pd"></a>  CPrintDialog::m_pd

Eine Struktur, deren Mitglieder die Merkmale des Dialog-Objekts zu speichern.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CPrintDialog` -Objekts verwenden Sie `m_pd` festzulegende verschiedene Aspekte im Dialogfeld vor dem Aufruf der [DoModal](#domodal) Member-Funktion. Weitere Informationen zu den `m_pd` Struktur, siehe [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) im Windows SDK.

Wenn Sie ändern die `m_pd` Datenmember direkt, überschreiben Sie Standardverhalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>  CPrintDialog::PrintAll

Bestimmt, ob alle Seiten des Dokuments zu drucken.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn alle Seiten im Dokument sind gedruckt werden sollen. andernfalls 0.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob alle Seiten im Dokument zu drucken.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).

##  <a name="printcollate"></a>  CPrintDialog::PrintCollate

Bestimmt, ob die sortierte Kopien angefordert werden.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Benutzer das Kontrollkästchen "Collate" im Dialogfeld auswählt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren sollte.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>  CPrintDialog::PrintRange

Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL sind nur ein Bereich von Seiten im Dokument gedruckt werden sollen; andernfalls 0.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob nur einen Bereich von Seiten im Dokument zu drucken.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).

##  <a name="printselection"></a>  CPrintDialog::PrintSelection

Bestimmt, ob nur die ausgewählten Elemente zu drucken.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn nur die ausgewählten Elemente werden gedruckt werden sollen; andernfalls 0.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob nur die ausgewählten Elemente zu drucken.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
