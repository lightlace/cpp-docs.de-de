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
ms.openlocfilehash: bdae64ff4a7bcfef761eaf3dd70a85a54efc28b7
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916962"
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
|[COlePropertiesDialog:: COlePropertiesDialog](#colepropertiesdialog)|Erstellt ein `COlePropertiesDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, eine Auswahl vorzunehmen.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Wird von Framework aufgerufen, wenn sich die Skalierung des Dokument Elements geändert hat.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COlePropertiesDialog:: m_gp](#m_gp)|Eine-Struktur, die zum Initialisieren der allgemeinen Seite eines `COlePropertiesDialog` -Objekts verwendet wird.|
|[COlePropertiesDialog::m_lp](#m_lp)|Eine-Struktur, die verwendet wird, um die Linkseite eines `COlePropertiesDialog` -Objekts zu initialisieren.|
|[COlePropertiesDialog:: m_Op](#m_op)|Eine-Struktur, die zum Initialisieren des `COlePropertiesDialog` -Objekts verwendet wird.|
|[COlePropertiesDialog:: m_psh](#m_psh)|Eine-Struktur, mit der zusätzliche benutzerdefinierte Eigenschaften Seiten hinzugefügt werden.|
|[COlePropertiesDialog:: m_vp](#m_vp)|Eine-Struktur, die verwendet wird, um die Seite " `COlePropertiesDialog` Ansicht" eines-Objekts anzupassen.|

## <a name="remarks"></a>Hinweise

Allgemeine Eigenschaften von OLE-Objekteigenschaften stellen eine einfache Möglichkeit dar, die Eigenschaften eines OLE-Dokument Elements in Übereinstimmung mit Windows-Standards anzuzeigen und zu ändern. Zu diesen Eigenschaften gehören unter anderem Informationen zu der durch das Dokument Element dargestellten Datei, Optionen zum Anzeigen des Symbols und der Bildskalierung sowie Informationen zum Link des Elements (wenn das Element verknüpft ist).

Um ein `COlePropertiesDialog` -Objekt zu verwenden, erstellen Sie zunächst das `COlePropertiesDialog` -Objekt mit dem-Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie die `DoModal` Member-Funktion aufrufen, um das Dialogfeld anzuzeigen und dem Benutzer zu ermöglichen, alle Eigenschaften des Elements zu ändern. `DoModal`Gibt zurück, ob der Benutzer die Schaltfläche OK (IDOK) oder Abbrechen (IDCANCEL) ausgewählt hat. Zusätzlich zu den Schaltflächen OK und Abbrechen gibt es eine Schaltfläche anwenden. Wenn der Benutzer übernehmen auswählt, werden alle Änderungen an den Eigenschaften des Dokument Elements auf das Element angewendet, und das Bild wird automatisch aktualisiert, bleibt jedoch aktiv.

Der [m_psh](#m_psh) -Datenmember ist ein Zeiger auf `PROPSHEETHEADER` eine Struktur, und in den meisten Fällen müssen Sie nicht explizit darauf zugreifen. Eine Ausnahme ist, wenn Sie zusätzliche Eigenschaften Seiten benötigen, die über die allgemeinen Standard-, Ansichts-und Link Seiten hinausgehen. In diesem Fall können Sie den `m_psh` Datenmember so ändern, dass die benutzerdefinierten Seiten eingeschlossen werden, bevor Sie die `DoModal` Member-Funktion aufrufen.

Weitere Informationen zu OLE-Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="colepropertiesdialog"></a>COlePropertiesDialog:: COlePropertiesDialog

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
Zeiger auf das Dokument Element, auf dessen Eigenschaften zugegriffen wird.

*nScaleMin*<br/>
Minimaler Skalierungs Prozentsatz für das Dokument Element Image.

*nScaleMax*<br/>
Maximaler Skalierungs Prozentsatz für das Dokument Element Image.

*pParentWnd*<br/>
Zeiger auf das übergeordnete Element oder den Besitzer des Dialog Felds.

### <a name="remarks"></a>Hinweise

Leiten Sie die allgemeine Dialogfeld Klasse von OLE `COlePropertiesDialog` -Objekteigenschaften von ab, um die Skalierung für die Dokument Elemente zu implementieren. Alle Dialogfelder, die von einer Instanz dieser Klasse implementiert werden, unterstützen keine Skalierung des Dokument Elements.

Standardmäßig verfügt das Dialogfeld Eigenschaften des allgemeinen OLE-Objekts über drei Standardseiten:

- Allgemein

   Diese Seite enthält Systeminformationen für die Datei, die vom ausgewählten Dokument Element dargestellt wird. Auf dieser Seite kann der Benutzer das ausgewählte Element in einen anderen Typ konvertieren.

- Ansicht

   Diese Seite enthält Optionen zum Anzeigen des Elements, zum Ändern des Symbols und zum Ändern der Skalierung des Bilds.

- Link

   Diese Seite enthält Optionen, mit denen Sie den Speicherort des verknüpften Elements ändern und das verknüpfte Element aktualisieren. Auf dieser Seite kann der Benutzer die Verknüpfung des ausgewählten Elements unterbrechen.

Um Seiten hinzuzufügen, die über die standardmäßig bereitgestellten verfügen, ändern Sie die [m_psh](#m_psh) -Element Variable `COlePropertiesDialog`, bevor Sie den Konstruktor der von abgeleiteten Klasse beenden. Dies ist eine erweiterte Implementierung des `COlePropertiesDialog` -Konstruktors.

##  <a name="domodal"></a>COlePropertiesDialog::D omodal

Mit dieser Member-Funktion können Sie das Eigenschaften Dialogfeld für das allgemeine Windows-OLE-Objekt anzeigen und dem Benutzer die Möglichkeit geben, die verschiedenen Eigenschaften des Dokument Elements anzuzeigen und/oder zu ändern.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

IDOK oder IDCANCEL, wenn erfolgreich; andernfalls 0. IDOK und IDCANCEL sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder Abbrechen ausgewählt hat.

Wenn IDCANCEL zurückgegeben wird, können Sie die Windows-Funktion [commdlgextendederror](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) aufrufen, um zu bestimmen, ob ein Fehler aufgetreten ist.

##  <a name="m_gp"></a>COlePropertiesDialog:: m_gp

Eine Struktur vom Typ [oleuignrlproperties](/windows/desktop/api/oledlg/ns-oledlg-tagoleuignrlpropsa), die verwendet wird, um die Seite Allgemein des Dialog Felds OLE-Objekteigenschaften zu initialisieren.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Hinweise

Diese Seite zeigt den Typ und die Größe einer Einbettung an und ermöglicht dem Benutzer den Zugriff auf das Dialogfeld "konvertieren". Diese Seite zeigt auch das Linkziel an, wenn es sich bei dem Objekt um einen Link handelt.

Weitere Informationen zur- `OLEUIGNRLPROPS` Struktur finden Sie in der Windows SDK.

##  <a name="m_lp"></a>COlePropertiesDialog:: m_lp

Eine Struktur vom Typ [oleuilinkproperties](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa), die verwendet wird, um die Linkseite des Dialog Felds OLE-Objekteigenschaften zu initialisieren.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Hinweise

Diese Seite zeigt den Speicherort des verknüpften Elements an und ermöglicht dem Benutzer, den Link zum Element zu aktualisieren oder zu unterbrechen.

Weitere Informationen zur- `OLEUILINKPROPS` Struktur finden Sie in der Windows SDK.

##  <a name="m_op"></a>COlePropertiesDialog:: m_Op

Eine Struktur vom Typ [oleuiobjectproperties](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiobjectpropsa), die verwendet wird, um das Dialogfeld allgemeine OLE-Objekteigenschaften zu initialisieren.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Hinweise

Diese Struktur enthält Elemente, die zum Initialisieren der allgemeinen, Link-und Ansichts Seiten verwendet werden.

Weitere Informationen finden Sie in den oleuiobject-und [oleuilinkrequik-Strukturen](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa) in der Windows SDK.

##  <a name="m_psh"></a>COlePropertiesDialog:: m_psh

Eine Struktur vom Typ " [propsheederader](/windows/desktop/api/prsht/ns-prsht-propsheetheadera_v2)", deren Member die Merkmale des Dialog Objekts speichern.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Hinweise

Nachdem Sie ein `COlePropertiesDialog` -Objekt erstellt haben, `m_psh` können Sie verwenden, um verschiedene Aspekte des Dialog Felds vor `DoModal` dem Aufruf der Member-Funktion festzulegen.

Wenn Sie den `m_psh` Datenmember direkt ändern, überschreiben Sie jedes Standardverhalten.

Weitere Informationen zur- `PROPSHEETHEADER` Struktur finden Sie in der Windows SDK.

##  <a name="m_vp"></a>COlePropertiesDialog:: m_vp

Eine Struktur vom Typ [oleuiviewproperties](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiviewpropsa), die verwendet wird, um die Ansichts Seite des Dialog Felds OLE-Objekteigenschaften zu initialisieren.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Hinweise

Auf dieser Seite kann der Benutzer zwischen den Ansichten "Content" und "Iconic" des Objekts umschalten und die Skalierung im Container ändern. Außerdem ermöglicht Sie dem Benutzer den Zugriff auf das Dialogfeld "Symbol ändern", wenn das Objekt als Symbol angezeigt wird.

Weitere Informationen zur- `OLEUIVIEWPROPS` Struktur finden Sie in der Windows SDK.

##  <a name="onapplyscale"></a>COlePropertiesDialog:: onapplyscale

Wird von Framework aufgerufen, wenn der Skalierungs Wert geändert wurde und entweder OK oder Apply ausgewählt wurde.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Dokument Element, auf dessen Eigenschaften zugegriffen wird.

*nCurrentScale*<br/>
Numerischer Wert der Dialogfeld Skala.

*bRelativeToOrig*<br/>
Gibt an, ob die Skalierung für die ursprüngliche Größe des Dokument Elements gilt.

### <a name="return-value"></a>Rückgabewert

Nicht NULL, wenn behandelt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen diese Funktion überschreiben, um die Skalierungs Steuerelemente zu aktivieren.

> [!NOTE]
>  Bevor das Dialogfeld allgemeine OLE-Objekteigenschaften angezeigt wird, ruft das Framework diese Funktion mit einem NULL-Wert für *pitem* und einem-1 für *ncurrentscale*auf. Dies geschieht, um zu bestimmen, ob die Skalierungs Steuerelemente aktiviert werden sollen.

## <a name="see-also"></a>Siehe auch

[MFC-beispielcirc](../../overview/visual-cpp-samples.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage-Klasse](../../mfc/reference/cpropertypage-class.md)
