---
title: CPrintDialogEx-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 2334fb0a420e14aa4fa8b8b570671fb9a611de32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502885"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx-Klasse

Kapselt die Dienste, die vom Windows-Druckeigenschaften Blatt bereitgestellt werden.

## <a name="syntax"></a>Syntax

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Erstellt ein `CPrintDialogEx`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Erstellt einen Drucker Gerätekontext, ohne das Dialogfeld Drucken anzuzeigen.|
|[CPrintDialogEx::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[CPrintDialogEx::GetCopies](#getcopies)|Ruft die Anzahl der angeforderten Kopien ab.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Ruft Geräte Standardwerte ab, ohne ein Dialogfeld anzuzeigen.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Ruft den Namen des aktuell ausgewählten Drucker Geräts ab.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Ruft die `DEVMODE` -Struktur ab.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Ruft den Namen des System definierten Druckergerätetreibers ab.|
|[CPrintDialogEx::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Drucker Ports ab.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker Gerätekontext ab.|
|[CPrintDialogEx::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt werden.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Bestimmt, ob die aktuelle Seite des Dokuments gedruckt wird.|
|[CPrintDialogEx::PrintRange](#printrange)|Bestimmt, ob nur ein angegebener Seitenbereich gedruckt werden soll.|
|[CPrintDialogEx::PrintSelection](#printselection)|Bestimmt, ob nur die aktuell ausgewählten Elemente gedruckt werden.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Eine-Struktur, mit der `CPrintDialogEx` ein-Objekt angepasst wird.|

## <a name="remarks"></a>Hinweise

Sie können sich auf das Framework verlassen, um viele Aspekte des Druckprozesses für Ihre Anwendung zu bewältigen. Weitere Informationen zum Verwenden des Frameworks zum Verarbeiten von Druckaufgaben finden Sie im Artikel [Drucken](../../mfc/printing.md).

Wenn Sie möchten, dass Ihre Anwendung den Druck ohne die Einbindung des Frameworks behandelt, können `CPrintDialogEx` Sie die-Klasse mit dem bereitgestellten Konstruktor "unverändert" verwenden, oder Sie können eine eigene `CPrintDialogEx` Dialogfeld Klasse von ableiten und einen Konstruktor für Ihre Bedürfnisse schreiben. In beiden Fällen verhalten sich diese Dialogfelder wie Standard-MFC-Dialogfelder, da Sie von der `CCommonDialog`-Klasse abgeleitet sind.

Um ein `CPrintDialogEx` -Objekt zu verwenden, erstellen Sie zunächst das `CPrintDialogEx` -Objekt mit dem-Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie alle Werte in der [m_pdex](#m_pdex) -Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialog Felds zu initialisieren. Die `m_pdex` Struktur ist vom Typ " [printdlgex](/windows/win32/api/commdlg/ns-commdlg-pdexw)". Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

`m_pdex` Wenn Sie für die `hDevMode` Member und keine eigenen Handles in bereitstellen `hDevNames` , müssen Sie die Windows-Funktion `GlobalFree` für diese Handles aufzurufen, wenn Sie das Dialogfeld verwenden.

Nachdem Sie die Dialogfeld Steuerelemente initialisiert haben `DoModal` , können Sie die Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer die Auswahl von Druckoptionen zu ermöglichen. Wenn `DoModal` zurückgibt, können Sie bestimmen, ob der Benutzer die Schaltfläche OK, anwenden oder Abbrechen ausgewählt hat.

Wenn der Benutzer auf OK geklickt hat, können `CPrintDialogEx`Sie die Element Funktionen von verwenden, um die vom Benutzer eingegebenen Informationen abzurufen.

Die `CPrintDialogEx::GetDefaults` Member-Funktion ist nützlich, um die aktuellen Drucker Standardwerte abzurufen, ohne ein Dialogfeld anzuzeigen. Für diese Methode ist keine Benutzerinteraktion erforderlich.

Mit der Windows `CommDlgExtendedError` -Funktion können Sie feststellen, ob während der Initialisierung des Dialog Felds ein Fehler aufgetreten ist, und weitere Informationen zum Fehler erhalten. Weitere Informationen zu dieser Funktion finden Sie in der Windows SDK.

Weitere Informationen zum Verwenden von `CPrintDialogEx`finden Sie unter [Allgemeine Dialog Klassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="cprintdialogex"></a>CPrintDialogEx:: CPrintDialogEx

Erstellt ein Eigenschaften Blatt für den Windows-Druck.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen des Dialog Felds mithilfe des bitweisen OR-Operators zu ändern. Beispielsweise legt das Flag PD_ALLPAGES den Standarddruck Bereich auf alle Seiten des Dokuments fest. Weitere Informationen zu diesen Flags finden Sie in der [printdlgex](/windows/win32/api/commdlg/ns-commdlg-pdexw) -Struktur im Windows SDK.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete oder Besitzer Fenster des Dialog Felds.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion erstellt nur das-Objekt. Verwenden Sie `DoModal` die Member-Funktion, um das Dialogfeld anzuzeigen.

##  <a name="createprinterdc"></a>CPrintDialogEx:: up-interdc

Erstellt einen Drucker Gerätekontext (DC) aus den [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker Gerätekontext.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Domänen Controller wird auch `hDC` im Member von [m_pdex](#m_pdex)gespeichert.

Es wird davon ausgegangen, dass es sich bei diesem DC um den aktuellen Drucker-DC handelt, und alle anderen zuvor erhaltenen Drucker-DCS müssen gelöscht werden Diese Funktion kann aufgerufen werden, und der resultierende DC wird verwendet, ohne dass das Dialogfeld "Drucken" angezeigt wird.

##  <a name="domodal"></a>CPrintDialogEx::D omodal

Mit dieser Funktion können Sie das Eigenschaften Blatt Windows-Druck anzeigen und dem Benutzer die Auswahl verschiedener Druckoptionen, wie z. b. die Anzahl von Kopien, den Seitenbereich und ob Kopien sortiert werden sollen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der INT_PTR-Rückgabewert ist tatsächlich ein HRESULT. Weitere Informationen finden Sie im Abschnitt "Rückgabewerte" in " [printdlgex](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) " im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Druck Dialogfeld Optionen durch Festlegen der Elemente der `m_pdex` Struktur initialisieren möchten, sollten Sie dies vor dem Aufrufen `DoModal`von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Nach dem `DoModal`Aufrufen von können Sie andere Element Funktionen aufrufen, um die Einstellungen oder die Eingabeinformationen vom Benutzer in das Dialogfeld abzurufen.

Wenn das PD_RETURNDC-Flag verwendet wird, `DoModal`wenn aufgerufen wird, wird ein Drucker-DC `hDC` im Member von [m_pdex](#m_pdex)zurückgegeben. Dieser Domänen Controller muss durch einen Aufruf von [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) vom Aufrufer `CPrintDialogEx`von freigegeben werden.

##  <a name="getcopies"></a>CPrintDialogEx:: getkopien

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um die Anzahl der angeforderten Kopien abzurufen.

```
int GetCopies() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der angeforderten Kopien.

##  <a name="getdefaults"></a>CPrintDialogEx:: getdefaults

Rufen Sie diese Funktion auf, um die Geräte Standardwerte des Standard Druckers abzurufen, ohne ein Dialogfeld anzuzeigen.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls false.

### <a name="remarks"></a>Hinweise

Erstellt einen Drucker Gerätekontext (DC) aus den [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen.

`GetDefaults`Das Druckeigenschaften Blatt wird nicht angezeigt. Stattdessen `hDevNames` werden die-und- `hDevMode` Member von [m_pdex](#m_pdex) auf Handles für die [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -und [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) -Strukturen festgelegt, die für den System Standarddrucker initialisiert werden. Sowohl `hDevNames` als `hDevMode` auch müssen NULL sein, `GetDefaults` oder es tritt ein Fehler auf.

Wenn das PD_RETURNDC-Flag festgelegt ist, gibt diese Funktion nicht `hDevNames` nur `hDevMode` und (in `m_pdex.hDevNames` und `m_pdex.hDevMode`) an den Aufrufer zurück, sondern gibt auch einen Drucker `m_pdex.hDC`-DC in zurück. Es liegt in der Verantwortung des Aufrufers, den Drucker-DC zu löschen und die Windows [Global Free](/windows/win32/api/winbase/nf-winbase-globalfree) -Funktion für die Handles aufzurufen `CPrintDialogEx` , wenn Sie mit dem-Objekt fertig sind.

##  <a name="getdevicename"></a>CPrintDialogEx:: GetDeviceName

Rufen Sie diese Funktion nach dem Aufrufen von [DoModal](#domodal) auf, um den Namen des aktuell ausgewählten Druckers abzurufen, oder nachdem Sie [getdefaults](#getdefaults) aufgerufen haben, um den Namen des Standard Druckers abzurufen.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Druckers.

### <a name="remarks"></a>Hinweise

Verwenden Sie einen Zeiger auf `CString` das Objekt, `GetDeviceName` das von als Wert `lpszDeviceName` von zurückgegeben wird, in einem Aufrufen von [CDC:: anatedc](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>CPrintDialogEx:: getdevmode

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um Informationen zum Druck Gerät abzurufen.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -Datenstruktur, die Informationen über die Geräte Initialisierung und die Umgebung eines Druck Treibers enthält. Sie müssen den von dieser Struktur erstellten Arbeitsspeicher mit der Funktion Windows [globalunlock](/windows/win32/api/winbase/nf-winbase-globalunlock) entsperren, die im Windows SDK beschrieben wird.

##  <a name="getdrivername"></a>CPrintDialogEx:: getDriverName

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um den Namen des System definierten Drucker-Gerätetreibers abzurufen.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , der den Namen des System definierten Treibers angibt.

### <a name="remarks"></a>Hinweise

Verwenden Sie einen Zeiger auf `CString` das Objekt, `GetDriverName` das von als Wert von *lpszdrivername* in einem Aufrufen von [CDC:: | atedc](../../mfc/reference/cdc-class.md#createdc)zurückgegeben wird.

##  <a name="getportname"></a>CPrintDialogEx:: getportname

Rufen Sie diese Funktion nach dem Aufrufen von " [DoModal](#domodal) " oder " [getdefaults](#getdefaults) " auf, um den Namen des aktuell ausgewählten Drucker Ports abzurufen.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Drucker Anschlusses.

##  <a name="getprinterdc"></a>CPrintDialogEx:: getPrinterDC

Gibt ein Handle für den Drucker Gerätekontext zurück.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den Drucker Gerätekontext.

### <a name="remarks"></a>Hinweise

Sie müssen die Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) -Funktion aufrufen, um den Gerätekontext zu löschen, wenn Sie ihn nicht mehr benötigen.

##  <a name="m_pdex"></a>CPrintDialogEx:: m_pdex

Eine printdlgex-Struktur, deren Elemente die Merkmale des Dialog Objekts speichern.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Hinweise

Nachdem Sie ein `CPrintDialogEx` -Objekt erstellt haben, `m_pdex` können Sie verwenden, um verschiedene Aspekte des Dialog Felds festzulegen, bevor Sie die [DoModal](#domodal) -Member-Funktion aufrufen. Weitere Informationen zur `m_pdex` -Struktur finden Sie unter [printdlgex](/windows/win32/api/commdlg/ns-commdlg-pdexw) in der Windows SDK.

Wenn Sie den `m_pdex` Datenmember direkt ändern, überschreiben Sie jedes Standardverhalten.

##  <a name="printall"></a>CPrintDialogEx::P rintall

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob alle Seiten im Dokument gedruckt werden sollen.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn alle Seiten im Dokument gedruckt werden sollen. andernfalls false.

##  <a name="printcollate"></a>CPrintDialogEx::P rintcollate

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob der Drucker alle gedruckten Kopien des Dokuments anordnen soll.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Benutzer das Kontrollkästchen COLLATE im Dialogfeld aktiviert. andernfalls false.

##  <a name="printcurrentpage"></a>CPrintDialogEx::P rintcurrentpage

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob die aktuelle Seite im Dokument gedruckt werden soll.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die **aktuelle Seite drucken** im Dialogfeld Drucken ausgewählt ist. andernfalls false.

##  <a name="printrange"></a>CPrintDialogEx::P rintrange

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob nur ein Bereich von Seiten im Dokument gedruckt werden soll.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn nur ein Seitenbereich im Dokument gedruckt werden soll. andernfalls false.

### <a name="remarks"></a>Hinweise

Die angegebenen Seitenbereiche können von [m_pdex](#m_pdex) bestimmt werden (siehe `nPageRanges`, `nMaxPageRanges`und in `lpPageRanges` der [printdlgex](/windows/win32/api/commdlg/ns-commdlg-pdexw) -Struktur in der Windows SDK).

##  <a name="printselection"></a>CPrintDialogEx::P rintselection

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um zu bestimmen, ob nur die aktuell ausgewählten Elemente gedruckt werden sollen

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn nur die ausgewählten Elemente gedruckt werden sollen. andernfalls false.

## <a name="see-also"></a>Siehe auch

[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
