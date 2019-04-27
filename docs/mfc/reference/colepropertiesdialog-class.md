---
title: COlePropertiesDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: e574f535609ec9401bd76badf11fa7e05cc0c619
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224393"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog-Klasse

Kapselt das allgemeine Windows-OLE-Dialogfeld "Objekteigenschaften".

## <a name="syntax"></a>Syntax

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Erstellt ein `COlePropertiesDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Vom Framework aufgerufen, wenn sich die Skalierung der das Dokumentelement geändert hat.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|Eine Struktur, die zum Initialisieren der Seite "Allgemein" des verwendet eine `COlePropertiesDialog` Objekt.|
|[COlePropertiesDialog::m_lp](#m_lp)|Eine Struktur, die zum Initialisieren der Seite "Link" verwendet eine `COlePropertiesDialog` Objekt.|
|[COlePropertiesDialog::m_op](#m_op)|Eine Struktur, die zum Initialisieren der `COlePropertiesDialog` Objekt.|
|[COlePropertiesDialog::m_psh](#m_psh)|Eine Struktur, die zusätzliche benutzerdefinierte Eigenschaftenseiten hinzugefügt.|
|[COlePropertiesDialog::m_vp](#m_vp)|Eine Struktur, die zum Anpassen der Seite "View" verwendet eine `COlePropertiesDialog` Objekt.|

## <a name="remarks"></a>Hinweise

Eigenschaften für das OLE-Objekts Standarddialogfelder bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements des OLE-Dokument in Übereinstimmung mit den Windows-Standards. Zu diesen Eigenschaften zählen unter anderem Informationen zu der Datei, die durch das Dokumentelement, Optionen für die Anzeige von Symbol und Bildskalierung und Informationen auf der Link des Elements (sofern das Element verknüpft ist) dargestellt wird.

Verwenden einer `COlePropertiesDialog` Objekt, erstellen Sie zunächst das Objekt mit der `COlePropertiesDialog` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, rufen die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglicht dem Benutzer, alle Eigenschaften des Elements zu ändern. `DoModal` Gibt zurück, ob der Benutzer das OK (IDOK) oder auf die Schaltfläche Abbrechen (IDCANCEL) ausgewählt. Es gibt eine Schaltfläche "anwenden", zusätzlich zu die Schaltflächen OK und Abbrechen. Wenn der Benutzer übernehmen auswählt, wird alle Änderungen an den Eigenschaften des Dokumentelements gelten für das Element, und das Bild wird automatisch aktualisiert, aber es bleibt aktiv.

Die [M_psh](#m_psh) -Datenmember ist ein Zeiger auf eine `PROPSHEETHEADER` Struktur, die in den meisten Fällen, die Sie nicht benötigen für den Zugriff explizit. Eine Ausnahme ist, wenn Sie zusätzliche Eigenschaftenseiten über den Standardwert Allgemein, Ansicht und Link-Seiten benötigen. In diesem Fall können Sie ändern die `m_psh` Datenmember, enthalten Ihre benutzerdefinierten Seiten vor dem Aufruf der `DoModal` Member-Funktion.

Weitere Informationen zu OLE-Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="colepropertiesdialog"></a>  COlePropertiesDialog::COlePropertiesDialog

Erstellt ein `COlePropertiesDialog`-Objekt.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Dokumentelement, dessen Eigenschaften zugegriffen wird.

*nScaleMin*<br/>
Minimum-Prozentsatz für das Dokument Elementbild skalieren.

*nScaleMax*<br/>
Der maximale Prozentsatz für das Dokument Elementbild Skalierung.

*pParentWnd*<br/>
Zeiger auf das übergeordnete Element oder den Besitzer des Dialogfelds.

### <a name="remarks"></a>Hinweise

Leiten Sie die allgemeinen Eigenschaften für das OLE-Objekts Dialogfeld-Klasse aus `COlePropertiesDialog` um Skalierung für Ihre Dokumentelemente zu implementieren. Alle Dialogfelder, die von einer Instanz dieser Klasse implementiert unterstützt das Dokumentelement Skalierung nicht.

Das Dialogfeld für allgemeine Eigenschaften für das OLE-Objekts verfügt standardmäßig über drei Standardseiten:

- Allgemein

   Diese Seite enthält die Systeminformationen für die Datei, die durch das ausgewählte Dokument-Element dargestellt wird. Auf dieser Seite kann Benutzer das ausgewählte Element in einen anderen Typ konvertieren.

- Ansicht

   Diese Seite enthält Optionen für das Element anzuzeigen, ändern das Symbol und Ändern der Skalierung des Bilds.

- Link

   Diese Seite enthält Optionen zum Ändern des Speicherorts für das verknüpfte Element, und aktualisieren das verknüpfte Element. Auf dieser Seite kann Benutzer die Verknüpfung des ausgewählten Elements unterbrechen.

Um Seiten standardmäßig mehr hinzufügen, Ändern der [M_psh](#m_psh) Membervariable vor dem Beenden des Konstruktors der Ihre `COlePropertiesDialog`-abgeleitete Klasse. Dies ist eine erweiterte Implementierung von der `COlePropertiesDialog` Konstruktor.

##  <a name="domodal"></a>  COlePropertiesDialog::DoModal

Rufen Sie diese Memberfunktion zum Anzeigen des Dialogfelds von Windows für allgemeine Eigenschaften für das OLE-Objekts und ermöglicht dem Benutzer, anzuzeigen oder zu die verschiedenen Eigenschaften der das Dokumentelement ändern.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL, wenn erfolgreich; andernfalls 0. IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche "OK" oder "Abbrechen" aktiviert.

Wenn IDCANCEL zurückgegeben wird, können Sie die Windows aufrufen [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.

##  <a name="m_gp"></a>  COlePropertiesDialog::m_gp

Eine Struktur des Typs [OLEUIGNRLPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuignrlpropsa), mit der Registerkarte Allgemein im Dialogfeld Eigenschaften für das OLE-Objekts initialisieren.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Hinweise

Diese Seite zeigt den Typ und die Größe einer Einbettung und ermöglicht den Benutzerzugriff auf das Dialogfeld "konvertieren". Diese Seite enthält auch Ziel des Links, wenn das Objekt ein Link ist.

Weitere Informationen zu den `OLEUIGNRLPROPS` Struktur, finden Sie im Windows SDK.

##  <a name="m_lp"></a>  COlePropertiesDialog::m_lp

Eine Struktur des Typs [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa)verwendet, um die Link-Seite des Dialogfelds Eigenschaften für das OLE-Objekts zu initialisieren.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Hinweise

Diese Seite zeigt den Speicherort des verknüpften Elements und ermöglicht dem Benutzer zu aktualisieren oder zu unterbrechen, den Link, um das Element.

Weitere Informationen zu den `OLEUILINKPROPS` Struktur, finden Sie im Windows SDK.

##  <a name="m_op"></a>  COlePropertiesDialog::m_op

Eine Struktur des Typs [OLEUIOBJECTPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiobjectpropsa)verwendet, um das Dialogfeld für allgemeine Eigenschaften für das OLE-Objekts initialisieren.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Hinweise

Diese Struktur enthält Elemente für die Allgemein, links und Ansicht-Seiten zu initialisieren.

Weitere Informationen finden Sie unter den OLEUIOBJECTPROPS und [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa) Strukturen im Windows SDK.

##  <a name="m_psh"></a>  COlePropertiesDialog::m_psh

Eine Struktur des Typs [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2), zu speichern, deren Mitglieder die Merkmale des Dialog-Objekts.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen einer `COlePropertiesDialog` -Objekts verwenden Sie `m_psh` festzulegende verschiedene Aspekte im Dialogfeld vor dem Aufruf der `DoModal` Member-Funktion.

Wenn Sie ändern die `m_psh` Datenmember direkt, überschreiben Sie Standardverhalten.

Weitere Informationen zu den `PROPSHEETHEADER` Struktur, finden Sie im Windows SDK.

##  <a name="m_vp"></a>  COlePropertiesDialog::m_vp

Eine Struktur des Typs [OLEUIVIEWPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiviewpropsa)verwendet, um die Ansichtsseite im Dialogfeld Eigenschaften für das OLE-Objekts initialisieren.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Hinweise

Auf dieser Seite können den Benutzer zum Umschalten zwischen "Content" und "Symbol" Ansichten des Objekts, und ändern Sie ihre Skalierung innerhalb des Containers. Außerdem können den Benutzerzugriff auf das Dialogfeld "Symbol ändern", wenn das Objekt als Symbol angezeigt wird.

Weitere Informationen zu den `OLEUIVIEWPROPS` Struktur, finden Sie im Windows SDK.

##  <a name="onapplyscale"></a>  COlePropertiesDialog::OnApplyScale

Wird vom Framework aufgerufen, wenn es sich bei der Skalierung Wert wurde geändert, und entweder auf OK oder anwenden ausgewählt wurde.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Dokumentelement, dessen Eigenschaften zugegriffen wird.

*nCurrentScale*<br/>
Numerischer Wert der Skala Dialogfeld.

*bRelativeToOrig*<br/>
Gibt an, ob Skalierung auf die ursprüngliche Größe des Dokumentelements gilt.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null behandelt wird. andernfalls 0.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen diese Funktion, um die Skalierung Steuerelemente ermöglichen überschreiben.

> [!NOTE]
>  Bevor das allgemeine Eigenschaften für das OLE-Objekts-Dialogfeld angezeigt wird, wird das Framework ruft diese Funktion mit dem ein NULL- *pItem* und a - 1 für *nCurrentScale*. Dies erfolgt, um festzustellen, ob die Skalierung Steuerelemente aktiviert werden soll.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CIRC](../../overview/visual-cpp-samples.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage-Klasse](../../mfc/reference/cpropertypage-class.md)
