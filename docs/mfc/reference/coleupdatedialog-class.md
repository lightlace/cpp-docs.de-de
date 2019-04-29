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
ms.openlocfilehash: b8e580130b025f07b8f85a624b7f5a224a00e49e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373595"
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
|[COleUpdateDialog::DoModal](#domodal)|Zeigt die **Verknüpfungen bearbeiten** Dialogfeld in einem Aktualisierungsmodus.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

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

**Header:** afxodlgs.h

##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog

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
Verweist auf das Dokument mit den Links, die möglicherweise aktualisieren.

*bUpdateLinks*<br/>
Flag, die bestimmt, ob verknüpfte Objekte aktualisiert werden.

*bUpdateEmbeddings*<br/>
Flag, die bestimmt, ob eingebettete Objekte aktualisiert werden.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt werden.

### <a name="remarks"></a>Hinweise

Diese Funktion erstellt nur eine `COleUpdateDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Diese Klasse sollte verwendet werden, anstelle von `COleLinksDialog` verknüpfte oder eingebettete Elemente sollen nur vorhandene zu aktualisieren.

##  <a name="domodal"></a>  COleUpdateDialog::DoModal

Zeigt das Dialogfeld "Verknüpfungen bearbeiten" im Feld Updatemodus.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld wurde erfolgreich zurückgegeben.

- IDCANCEL, wenn die verknüpfte oder eingebettete Elemente im aktuellen Dokument eine Aktualisierung erforderlich.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIEditLinks](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa) -Funktion in das Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn der Benutzer auf "Abbrechen"-Schaltfläche auswählt, werden alle Verknüpfungen und/oder einbettungen aktualisiert.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)
