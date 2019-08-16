---
title: COleUpdateDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: 150e78b7880a61343db21c3c787ffdd1f0b734a5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503171"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog-Klasse

Wird für einen Sonderfall des OLE-Dialogfelds "Verknüpfungen bearbeiten" verwendet, das eingesetzt werden sollte, wenn in einem Dokument nur vorhandene Links oder eingebettete Objekte aktualisiert werden müssen.

## <a name="syntax"></a>Syntax

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Erstellt ein `COleUpdateDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleUpdateDialog::DoModal](#domodal)|Zeigt das Dialogfeld **Verknüpfungen bearbeiten** in einem Aktualisierungs Modus an.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="coleupdatedialog"></a>COleUpdateDialog:: COleUpdateDialog

Erstellt ein `COleUpdateDialog`-Objekt.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pDoc*<br/>
Verweist auf das Dokument, das die Links enthält, die möglicherweise aktualisiert werden müssen.

*bUpdateLinks*<br/>
Flag, das bestimmt, ob verknüpfte Objekte aktualisiert werden sollen.

*bUpdateEmbeddings*<br/>
Flag, das bestimmt, ob eingebettete Objekte aktualisiert werden sollen.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Felds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Diese Funktion erstellt nur ein `COleUpdateDialog` -Objekt. Um das Dialogfeld anzuzeigen, nennen Sie [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Diese Klasse sollte anstelle von `COleLinksDialog` verwendet werden, wenn Sie nur vorhandene verknüpfte oder eingebettete Elemente aktualisieren möchten.

##  <a name="domodal"></a>COleUpdateDialog::D omodal

Zeigt das Dialogfeld Verknüpfungen bearbeiten im Aktualisierungs Modus an.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich zurückgegeben wurde.

- IDCANCEL, wenn keines der verknüpften oder eingebetteten Elemente im aktuellen Dokument aktualisiert werden muss.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können Sie die Member-Funktion [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) aufrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der Funktion [oleuieditlinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) im Windows SDK.

### <a name="remarks"></a>Hinweise

Alle Verknüpfungen und/oder Einbettungen werden aktualisiert, es sei denn, der Benutzer wählt die Schaltfläche Abbrechen aus.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)
