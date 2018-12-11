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
ms.openlocfilehash: fb88cc39ddaffe51b80484bbe8460507a1d0aecb
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178446"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx-Klasse

Kapselt die Dienste, die von der Windows-druckeigenschaftenblatt bereitgestellt.

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
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Erstellt einen druckergerätkontext ohne Anzeige des Dialogfelds drucken.|
|[CPrintDialogEx::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|
|[CPrintDialogEx::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Ruft die Standardeinstellungen des Geräts ohne das Anzeigen eines Dialogfelds ab.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Ruft den Namen des Geräts aktuell ausgewählten Drucker.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Ruft den Namen von den systemeigenen Druckertreiber.|
|[CPrintDialogEx::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Ports.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker-Gerätekontext ab.|
|[CPrintDialogEx::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments zu drucken.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Bestimmt, ob die sortierte Kopien angefordert werden.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Bestimmt, ob die aktuelle Seite des Dokuments gedruckt wird.|
|[CPrintDialogEx::PrintRange](#printrange)|Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.|
|[CPrintDialogEx::PrintSelection](#printselection)|Bestimmt, ob nur die ausgewählten Elemente zu drucken.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Eine Struktur, die zum Anpassen einer `CPrintDialogEx` Objekt.|

## <a name="remarks"></a>Hinweise

Sie können das Framework, behandeln zahlreiche Aspekte des Druckvorgangs für Ihre Anwendung verwenden. Weitere Informationen zur Verwendung von Framework Druckaufgaben behandelt, finden Sie im Artikel [Drucken](../../mfc/printing.md).

Wenn Sie Ihre Anwendung drucken, ohne die Framework Beteiligung verarbeiten möchten, können Sie die `CPrintDialogEx` -Klasse "wie besehen" mit dem Konstruktor angegeben oder Sie können Ihre eigenen Dialogfeldklasse von ableiten `CPrintDialogEx` und schreiben ein Konstruktors entsprechend Ihren Anforderungen. In beiden Fällen Aufrufen dieser Dialogfelder verhält sich wie die standard-MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.

Verwenden einer `CPrintDialogEx` Objekt, erstellen Sie zunächst das Objekt mit der `CPrintDialogEx` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pdex](#m_pdex) Struktur zum Initialisieren der Werte der Dialogfeld-Steuerelemente. Die `m_pdex` Struktur ist vom Typ [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

Wenn Sie keine eigene Handles im angeben `m_pdex` für die `hDevMode` und `hDevNames` Member, achten Sie darauf, dass Sie die Windows-Funktion aufrufen `GlobalFree` für diese Handles, wenn Sie das Dialogfeld abgeschlossen haben.

Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. Wenn `DoModal` zurückgegeben wird, können Sie bestimmen, ob der Benutzer die Schaltfläche "OK", "übernehmen, oder" Abbrechen "aktiviert.

Wenn der Benutzer auf OK geklickt, können Sie `CPrintDialogEx`Member-Funktionen zum Abrufen der Informationen, die vom Benutzer eingegebene.

Die `CPrintDialogEx::GetDefaults` Member-Funktion ist nützlich, um den aktuellen Druckerstandardeinstellungen abzurufen, ohne ein Dialogfeld angezeigt. Diese Methode erfordert kein Eingreifen des Benutzers.

Sie können die Windows `CommDlgExtendedError` -Funktion zu bestimmen, ob ein während der Initialisierung des Dialogfelds Fehler und Weitere Informationen zum Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.

Weitere Informationen zur Verwendung von `CPrintDialogEx`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).

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

**Header:** afxdlgs.h

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Erstellt eine Windows-druckeigenschaftenblatt an.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie, zum Anpassen der Einstellungen im Dialogfeld verwenden können, mit dem bitweisen OR-Operator kombiniert. Beispielsweise legt das Flag PD_ALLPAGES drucken Standardbereich für alle Seiten des Dokuments. Finden Sie unter den [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Struktur im Windows SDK für Weitere Informationen zu diesen Flags.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element oder Besitzer des Dialogfelds-Fenster.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird nur das Objekt erstellt. Verwenden der `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Rückgabewert

Handle für den neu erstellten Drucker-Gerätekontext.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Domänencontroller befindet sich auch in der `hDC` Mitglied [M_pdex](#m_pdex).

Dieser DC wird als den aktuellen Drucker-Gerätekontext aus, und alle anderen zuvor abgerufen haben, Drucker, den Domänencontrollern müssen gelöscht werden. Diese Funktion kann aufgerufen werden, und der daraus resultierende DC verwendet, ohne jemals Anzeige des Dialogfelds drucken.

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Mit dieser Funktion können Sie die Windows-druckeigenschaftenblatt angezeigt und ermöglicht dem Benutzer, wählen Sie die verschiedenen Druckoptionen wie z. B. die Anzahl der Kopien, Seitenbereich, und gibt an, ob Kopien sortiert werden sollen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Die INT_PTR zurück, dass der Wert tatsächlich ein HRESULT ist. Finden Sie im Abschnitt Return Values [PrintDlgEx](https://msdn.microsoft.com/library/windows/desktop/ms646942) im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Optionen für Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pdex` Struktur, Sie sollten dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.

Wenn das PD_RETURNDC-Flag verwendet wird, beim Aufrufen von `DoModal`, um ein druckerdomänencontroller werden im zurückgegeben der `hDC` Mitglied [M_pdex](#m_pdex). Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) durch den Aufrufer der `CPrintDialogEx`.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen der Anzahl der Kopien, die angefordert.

```
int GetCopies() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Kopien, die angefordert werden soll.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

Rufen Sie diese Funktion, um die Gerätestandards von den Standarddrucker abgerufen werden, ohne ein Dialogfeld angezeigt.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls "false".

### <a name="remarks"></a>Hinweise

Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen.

`GetDefaults` die druckeigenschaftenblatt wird nicht angezeigt werden. Stattdessen wird die `hDevNames` und `hDevMode` Mitglieder der [M_pdex](#m_pdex) , Handles für die [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) und [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Strukturen, die initialisiert werden, für die Standarddrucker des Systems. Beide `hDevNames` und `hDevMode` muss NULL sein, oder `GetDefaults` ein Fehler auftritt.

Die PD_RETURNDC-Flag festgelegt ist, diese Funktion wird nur zurückgegeben, wenn `hDevNames` und `hDevMode` (befindet sich in `m_pdex.hDevNames` und `m_pdex.hDevMode`) an den Aufrufer gibt jedoch auch zurück, um einen druckerdomänencontroller in `m_pdex.hDC`. Es liegt in der Verantwortung des Aufrufers, löschen den Drucker-Gerätekontext aus, und rufen die Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) Funktion auf die Ziehpunkte, die Sie abschließend mit der `CPrintDialogEx` Objekt.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers, oder klicken Sie nach dem Aufruf [GetDefaults](#getdefaults) um den Namen des Standarddruckers abzurufen.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Drucker.

### <a name="remarks"></a>Hinweise

Verwenden eines Zeigers auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) Abrufen von Informationen über das Druckgerät.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Rückgabewert

Die [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckertreibers enthält. Sie müssen den Arbeitsspeicher, die von dieser Struktur mit der Windows Entsperren [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) -Funktion, die im Windows SDK beschrieben wird.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens, der den systemeigenen Druckertreiber.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` den systemdefinierte Treibernamen angeben.

### <a name="remarks"></a>Hinweise

Verwenden eines Zeigers auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des *LpszDriverName* in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) um den Namen des aktuell ausgewählten Ports abzurufen.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des aktuell ausgewählten Ports.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

Gibt ein Handle für den Drucker-Gerätekontext zurück.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den Drucker-Gerätekontext.

### <a name="remarks"></a>Hinweise

Rufen Sie die Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) Funktion, um den Gerätekontext zu löschen, wenn Sie fertig sind verwenden.

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

Eine PRINTDLGEX-Struktur, deren Mitglieder die Merkmale des Dialog-Objekts zu speichern.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CPrintDialogEx` -Objekts verwenden Sie `m_pdex` festzulegende verschiedene Aspekte im Dialogfeld vor dem Aufruf der [DoModal](#domodal) Member-Funktion. Weitere Informationen zu den `m_pdex` Struktur, siehe [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) im Windows SDK.

Wenn Sie ändern die `m_pdex` Datenmember direkt, überschreiben Sie Standardverhalten.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob alle Seiten im Dokument zu drucken.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn alle Seiten im Dokument gedruckt werden sollen; andernfalls "false".

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren sollte.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Benutzer das Kontrollkästchen "Collate" im Dialogfeld auswählt. andernfalls "false".

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob die aktuelle Seite im Dokument zu drucken.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn **aktuelle Seite drucken** in das Dialogfeld "Drucken" ausgewählte ist; andernfalls "false".

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob nur einen Bereich von Seiten im Dokument zu drucken.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn nur ein Bereich von Seiten im Dokument gedruckt werden sollen. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der angegebene Seitenbereiche bestimmt werden können, aus [M_pdex](#m_pdex) (finden Sie unter `nPageRanges`, `nMaxPageRanges`, und `lpPageRanges` in die [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Struktur im Windows SDK).

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob nur die ausgewählten Elemente zu drucken.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn nur die ausgewählten Elemente werden gedruckt werden sollen. andernfalls "false".

## <a name="see-also"></a>Siehe auch

[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
