---
title: CColorDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: f5c235008b72996424e01ee912ca78ecffab450a
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741575"
---
# <a name="ccolordialog-class"></a>CColorDialog-Klasse

Ermöglicht es Ihnen, ein Farbauswahl-Dialogfeld in Ihre Anwendung einzubinden.

## <a name="syntax"></a>Syntax

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|Erstellt ein `CColorDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|Zeigt das Dialogfeld Farbe an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[CColorDialog::GetColor](#getcolor)|Gibt eine `COLORREF` -Struktur zurück, die die Werte der ausgewählten Farbe enthält.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Ruft vom Benutzer erstellte benutzerdefinierte Farben ab.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Erzwingt die aktuelle Farbauswahl zur angegebenen Farbe.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|Überschreiben, um die in das Dialogfeld eingegebene Farbe zu überprüfen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|Eine-Struktur, die zum Anpassen der Einstellungen des Dialog Felds verwendet wird.|

## <a name="remarks"></a>Hinweise

Ein `CColorDialog` -Objekt ist ein Dialogfeld mit einer Liste von Farben, die für das Anzeigesystem definiert sind. Der Benutzer kann eine bestimmte Farbe aus der Liste auswählen oder erstellen, die dann an die Anwendung zurückgemeldet wird, wenn das Dialogfeld beendet wird.

Verwenden Sie zum `CColorDialog` Erstellen eines-Objekts den bereitgestellten Konstruktor, oder leiten Sie eine neue Klasse ab, und verwenden Sie Ihren eigenen benutzerdefinierten Konstruktor.

Nachdem das Dialogfeld erstellt wurde, können Sie alle Werte in der [m_cc](#m_cc) -Struktur festlegen oder ändern, um die Werte der Steuerelemente des Dialog Felds zu initialisieren. Die *m_cc* -Struktur ist vom Typ " [chooabcolor](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)".

Nachdem Sie die Steuerelemente des Dialog Felds initialisiert haben `DoModal` , können Sie die Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer die Auswahl einer Farbe zu ermöglichen. `DoModal`Gibt die Auswahl des Dialog Felds in der Schaltfläche OK (IDOK) oder Abbrechen (IDCANCEL) des Benutzers zurück.

Wenn `DoModal` IDOK zurückgibt, können Sie eine der `CColorDialog`-Member-Funktionen verwenden, um die vom Benutzer eingegebenen Informationen abzurufen.

Mit der Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) können Sie feststellen, ob ein Fehler während der Initialisierung des Dialog Felds aufgetreten ist, und weitere Informationen zu diesem Fehler erhalten.

`CColorDialog`basiert auf der kommdlg. DLL-Datei, die in der Windows-Version 3,1 und höher enthalten ist.

Zum Anpassen des Dialog Felds leiten Sie eine Klasse von `CColorDialog`ab, geben eine benutzerdefinierte Dialogfeld Vorlage an und fügen eine Meldungs Zuordnung hinzu, um die Benachrichtigungs Meldungen von den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übermittelt werden.

Das Anpassen der Hook-Funktion ist nicht erforderlich.

> [!NOTE]
>  Bei manchen Installationen wird `CColorDialog` das Objekt nicht mit einem grauen Hintergrund angezeigt, wenn Sie das Framework verwendet haben, um `CDialog` andere Objekte grau zu machen.

Weitere Informationen zum Verwenden von `CColorDialog`finden Sie unter [Allgemeine Dialog Klassen](../../mfc/common-dialog-classes.md) .

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs. h

##  <a name="ccolordialog"></a>CColorDialog:: CColorDialog

Erstellt ein `CColorDialog`-Objekt.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*clrInit*<br/>
Die Standard Farbauswahl. Wenn kein Wert angegeben wird, ist der Standardwert RGB (0, 0, 0) (schwarz).

*dwFlags*<br/>
Ein Satz von Flags, die die Funktion und Darstellung des Dialog Felds anpassen. Weitere Informationen finden Sie [in der-](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1) Windows SDK.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete oder Besitzer Fenster des Dialog Felds.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>CColorDialog::D omodal

Aufrufen Sie diese Funktion, um das Dialogfeld Allgemeine Windows-Farbe anzuzeigen und dem Benutzer die Auswahl einer Farbe zu ermöglichen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows-Funktion [commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) auf, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder Abbrechen ausgewählt hat.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Farb Dialogfeld Optionen durch Festlegen der Elemente der [m_cc](#m_cc) -Struktur initialisieren möchten, sollten Sie dies vor dem Aufrufen `DoModal` von, jedoch nach dem Konstruieren des Dialogfeld Objekts tun.

Nach dem `DoModal`Aufrufen von können Sie andere Element Funktionen aufrufen, um die Einstellungen oder die Eingabeinformationen vom Benutzer in das Dialogfeld abzurufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CColorDialog:: CColorDialog](#ccolordialog).

##  <a name="getcolor"></a>CColorDialog:: GetColor

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um die Informationen zu der vom Benutzer ausgewählten Farbe abzurufen.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/win32/gdi/colorref) -Wert, der die RGB-Informationen für die im Dialogfeld Farbe ausgewählte Farbe enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>CColorDialog:: getsavedcustomcolors

`CColorDialog`-Objekte ermöglichen es dem Benutzer, zusätzlich zu den Farben auszuwählen, bis zu 16 benutzerdefinierte Farben zu definieren.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Array von 16 RGB-Farbwerten, das vom Benutzer erstellte benutzerdefinierte Farben speichert.

### <a name="remarks"></a>Hinweise

Die `GetSavedCustomColors` Member-Funktion ermöglicht den Zugriff auf diese Farben. Diese Farben können abgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Jeder der 16 RGB-Werte im zurückgegebenen Array wird mit RGB (255255255) initialisiert (weiß). Die benutzerdefinierten Farben, die vom Benutzer ausgewählt werden, werden nur zwischen Dialogfeld aufrufen in der Anwendung gespeichert. Wenn Sie diese Farben zwischen den Aufrufen der Anwendung speichern möchten, müssen Sie Sie auf andere Weise speichern, z. b. in einer Initialisierung (. INI-Datei.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>CColorDialog:: m_cc

Eine Struktur vom Typ " [choogcolor](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)", deren Member die Merkmale und Werte des Dialog Felds speichern.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen `CColorDialog` eines-Objekts können Sie *m_cc* verwenden, um verschiedene Aspekte des Dialog Felds festzulegen, bevor Sie die [DoModal](#domodal) -Member-Funktion aufrufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>CColorDialog:: oncolorok

Überschreiben, um die in das Dialogfeld eingegebene Farbe zu überprüfen.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Dialogfeld nicht verworfen werden soll. andernfalls 0, um die eingegebene Farbe zu akzeptieren.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion nur, wenn Sie eine benutzerdefinierte Validierung der vom Benutzer im Dialogfeld Farbe ausgewählten Farbe bereitstellen möchten.

Der Benutzer kann eine Farbe mit einer der folgenden beiden Methoden auswählen:

- Klicken auf eine Farbe auf der Farbpalette. Die RGB-Werte der ausgewählten Farbe werden dann in den entsprechenden RGB-Bearbeitungs Feldern angezeigt.

- Eingeben von Werten in den RGB-Bearbeitungs Feldern

Wenn Sie überschreiben, könnenSieeineFarbeablehnen,diederBenutzerfürjedenanwendungsspezifischenGrundineingängigesFarbDialogfeldeingibt.`OnColorOK`

Normalerweise müssen Sie diese Funktion nicht verwenden, da das Framework Standard Validierung von Farben bereitstellt und ein Meldungs Feld anzeigt, wenn eine ungültige Farbe eingegeben wird.

Sie können [setcurrentcolor](#setcurrentcolor) innerhalb `OnColorOK` von aufrufen, um eine Farbauswahl zu erzwingen. Nachdem `OnColorOK` Sie ausgelöst wurde (d. h., der Benutzer klickt auf " **OK** ", um die Farbänderung zu akzeptieren), können Sie [GetColor](#getcolor) aufrufen, um den RGB-Wert der neuen Farbe zu erhalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>CColorDialog:: setcurrentcolor

Rufen `DoModal` Sie diese Funktion nach dem Aufruf von auf, um die aktuelle Farbauswahl auf den in *CLR*angegebenen Farbwert zu erzwingen.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

Diese Funktion wird in einem Nachrichten Handler oder `OnColorOK`aufgerufen. Im Dialogfeld wird die Auswahl des Benutzers basierend auf dem Wert des *CLR* -Parameters automatisch aktualisiert.

### <a name="example"></a>Beispiel

  Sehen Sie sich das Beispiel für [CColorDialog:: oncolorok](#oncolorok)an.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
