---
title: COleLinksDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: 911108f9a231b752790abfdf86d1b4042d30b149
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504118"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog-Klasse

Wird für das OLE-Dialogfeld "Verknüpfungen bearbeiten" verwendet.

## <a name="syntax"></a>Syntax

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Erstellt ein `COleLinksDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::DoModal](#domodal)|Zeigt das OLE-Dialogfeld Links bearbeiten an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|Eine Struktur vom Typ oleuieditlinks, die das Verhalten des Dialog Felds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der `COleLinksDialog` -Klasse, wenn Sie dieses Dialogfeld aufzurufen. Nachdem ein `COleLinksDialog` -Objekt erstellt wurde, können Sie die [m_el](#m_el) -Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_el` Struktur ist vom Typ oleuieditlinks. Weitere Informationen zum Verwenden dieser Dialogfeld Klasse finden Sie unter der [DoModal](#domodal) -Member-Funktion.

> [!NOTE]
>  Vom Anwendungs-Assistenten generierter Container Code verwendet diese Klasse.

Weitere Informationen finden Sie in der Struktur von [oleuieditlinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) im Windows SDK.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="domodal"></a>COleLinksDialog::D omodal

Zeigt das OLE-Dialogfeld Links bearbeiten an.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können `COleDialog::GetLastError` Sie die Member-Funktion abrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der Funktion [oleuieditlinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_el](#m_el) -Struktur initialisieren möchten, sollten Sie diese vor `DoModal`dem Aufrufen von verwenden, nachdem das Dialogfeld Objekt erstellt wurde.

##  <a name="colelinksdialog"></a>COleLinksDialog:: COleLinksDialog

Erstellt ein `COleLinksDialog`-Objekt.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pDoc*<br/>
Verweist auf das OLE-Dokument, das die zu bearbeitenden Links enthält.

*pView*<br/>
Verweist auf die aktuelle Ansicht in *Pdoc*.

*dwFlags*<br/>
Erstellungsflag, das entweder 0 oder ELF_SHOWHELP enthält, um anzugeben, ob die Hilfe Schaltfläche angezeigt wird, wenn das Dialogfeld angezeigt wird.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Felds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Diese Funktion erstellt nur ein `COleLinksDialog` -Objekt. Um das Dialogfeld anzuzeigen, müssen Sie die Funktion [DoModal](#domodal) aufrufen.

##  <a name="m_el"></a>COleLinksDialog:: m_el

Struktur vom Typ "oleuieditlinks", die zum Steuern des Verhaltens des Dialog Felds "Links bearbeiten" verwendet wird.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Hinweise

Member dieser Struktur können entweder direkt oder über Element Funktionen geändert werden.

Weitere Informationen finden Sie in der Struktur von [oleuieditlinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
