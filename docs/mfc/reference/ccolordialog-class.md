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
ms.openlocfilehash: 39868ed27a0dfb8756b4829ea7c378c798bd2ff3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304209"
---
# <a name="ccolordialog-class"></a>CColorDialog-Klasse

Können Sie ein Farbauswahl-Dialogfeld in Ihre Anwendung integrieren.

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
|[CColorDialog::DoModal](#domodal)|Zeigt ein Farbendialogfeld an, und ermöglicht dem Benutzer eine Auswahl treffen.|
|[CColorDialog::GetColor](#getcolor)|Gibt eine `COLORREF` Struktur, die mit den Werten der ausgewählten Farbe.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Ruft benutzerdefinierte Farben, die vom Benutzer erstellten ab.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Erzwingt, dass die aktuelle Farbauswahl auf die angegebene Farbe.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|Außer Kraft setzen Sie, um zu überprüfen, ob die Farbe, die in das Dialogfeld eingegeben haben.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|Eine Struktur, die zum Anpassen der Einstellungen des Dialogfelds verwendet wird.|

## <a name="remarks"></a>Hinweise

Ein `CColorDialog` Objekt ist ein Dialogfeld mit einer Liste von Farben, die für die Anzeigesystem definiert sind. Der Benutzer kann auswählen oder erstellen Sie eine bestimmte Farbe aus der Liste der wieder dann an die Anwendung gemeldet wird, wenn das Dialogfeld beendet wird.

Zum Erstellen einer `CColorDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor oder eine neue Klasse ableiten und Ihre eigenen benutzerdefinierten Konstruktor verwenden.

Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_cc](#m_cc) Struktur zum Initialisieren der Werte der Dialogfeld-Steuerelemente. Die *M_cc* Struktur ist vom Typ [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora).

Rufen Sie nach dem initialisieren das Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglicht dem Benutzer, eine Farbe auszuwählen. `DoModal` Gibt die Auswahl des Benutzers, der entweder das Dialogfeld die Schaltfläche "OK (IDOK) oder abzubrechen (IDCANCEL)" zurück.

Wenn `DoModal` gibt IDOK, können Sie eine der `CColorDialog`Member-Funktionen zum Abrufen der Informationen, die vom Benutzer eingegebene.

Sie können die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) -Funktion zu bestimmen, ob ein während der Initialisierung des Dialogfelds Fehler und Weitere Informationen zum Fehler.

`CColorDialog` basiert auf der COMMDLG. DLL-Datei, die in Windows-Versionen 3.1 und höher enthalten ist.

Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CColorDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten in der Basisklasse übergeben werden.

Anpassen der Hookfunktion ist nicht erforderlich.

> [!NOTE]
>  Bei einigen Installationen der `CColorDialog` Objekt wird nicht mit grauem Hintergrund angezeigt, wenn Sie das Framework, zum Ausführen weiterer verwendet haben `CDialog` Objekte grau dargestellt.

Weitere Informationen zur Verwendung von `CColorDialog`, finden Sie unter [Standarddialogfeld-Klassen](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog

Erstellt ein `CColorDialog`-Objekt.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*clrInit*<br/>
Die Standardauswahl für die Farbe. Wenn kein Wert angegeben wird, ist die Standardeinstellung RGB(0,0,0) (Schwarz).

*dwFlags*<br/>
Ein Satz von Flags, die die Funktion und die Darstellung des Dialogfelds anpassen. Weitere Informationen finden Sie unter den [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora) Struktur im Windows SDK.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element oder Besitzer des Dialogfelds-Fenster.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>  CColorDialog::DoModal

Mit dieser Funktion können zeigt das Dialogfeld allgemeine Farbe Windows und ermöglicht dem Benutzer, eine Farbe auszuwählen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL. Wenn IDCANCEL zurückgegeben wird, rufen Sie die Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.

IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche "OK" oder "Abbrechen" aktiviert.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Farbe im Dialogfeld Optionen zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cc](#m_cc) Struktur, Sie sollten dies tun, vor dem Aufruf `DoModal` allerdings erst, nachdem das Dialogfeld-Objekt erstellt wird.

Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CColorDialog::CColorDialog](#ccolordialog).

##  <a name="getcolor"></a>  CColorDialog::GetColor

Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen von Informationen zu den vom Benutzer ausgewählten Farbe.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) -Wert, der den RGB-Informationen für das Dialogfeld "Farbe" ausgewählte Farbe an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors

`CColorDialog` Objekte ermöglichen es dem Benutzer, zusätzlich zur Auswahl von Farben, um bis zu 16 Farben zu definieren.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Array von 16 RGB-Werte, die Farben, die vom Benutzer erstellten speichert.

### <a name="remarks"></a>Hinweise

Die `GetSavedCustomColors` Member-Funktion ermöglicht den Zugriff auf diese Farben. Diese Farben abgerufen werden können, nach dem [DoModal](#domodal) IDOK zurückgibt.

Alle 16 RGB-Werte im zurückgegebenen Array wird mit RGB(255,255,255) (weiß) initialisiert. Die benutzerdefinierten Farben, die vom Benutzer ausgewählten werden nur zwischen Dialogfeld-Box-Aufrufe innerhalb der Anwendung gespeichert. Wenn Sie diese Farben zwischen den Aufrufen der Anwendung speichern möchten, müssen speichern Sie diese in eine andere Weise, wie z. B. in einer Initialisierung (. INI)-Datei.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>  CColorDialog::m_cc

Eine Struktur des Typs [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora), die Merkmale und die Werte im Dialogfeld, deren Mitglieder zu speichern.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `CColorDialog` -Objekts verwenden Sie *M_cc* festzulegende verschiedene Aspekte im Dialogfeld vor dem Aufruf der [DoModal](#domodal) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>  CColorDialog::OnColorOK

Außer Kraft setzen Sie, um zu überprüfen, ob die Farbe, die in das Dialogfeld eingegeben haben.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Dialogfeld nicht geschlossen werden soll; Andernfalls wird 0, akzeptieren die Farbe, die eingegeben wurde.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion nur, wenn Sie benutzerdefinierte Validierung der Farbe, die der Benutzer das Dialogfeld "Farbe" auswählt, bereitstellen möchten.

Der Benutzer kann eine Farbe von einem der beiden folgenden Methoden auswählen:

- Klicken Sie auf eine Farbe auf der Farbpalette. Die ausgewählte Farbe der RGB-Werte werden dann in die entsprechenden Eingabefelder für die RGB-wiedergegeben.

- Eingabe von Werten in den RGB-Bearbeitungsfelder

Überschreiben von `OnColorOK` können Sie eine Farbe Ablehnen der Benutzer in einem Standarddialogfeld für Farbe, anwendungsspezifischen Gründen gibt.

In der Regel müssen Sie nicht diese Funktion zu verwenden, da das Framework bietet die standardüberprüfung von Farben und zeigt ein Meldungsfeld an, wenn eine ungültige Farbe eingegeben wird.

Rufen Sie [SetCurrentColor](#setcurrentcolor) aus `OnColorOK` eine Farbauswahl zu erzwingen. Einmal `OnColorOK` wurde ausgelöst wurde (d. h. der Benutzer klickt auf **OK** , ändert sich die Farbe zu akzeptieren), rufen Sie [GetColor](#getcolor) zum Abrufen der RGB-Wert, der neuen Farbe.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor

Mit dieser Funktion wird nach dem Aufruf `DoModal` zu erzwingen, dass die aktuelle Auswahl im angegebenen Wert für die Farbe *Clr*.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

Diese Funktion wird innerhalb eines meldungshandlers aufgerufen oder `OnColorOK`. Das Dialogfeld aktualisiert automatisch die Auswahl des Benutzers anhand des Werts von der *Clr* Parameter.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CColorDialog::OnColorOK](#oncolorok).

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)<br/>
[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
