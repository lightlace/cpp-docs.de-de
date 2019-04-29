---
title: COleDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 353e2ed312fa7dbb9ef7bdfabc2b174abf8e1e1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375716"
---
# <a name="coledialog-class"></a>COleDialog-Klasse

Stellt die Funktionalität allgemeiner Dialogfelder für OLE bereit.

## <a name="syntax"></a>Syntax

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|Ruft den vom Dialogfeld zurückgegebenen Fehlercode ab.|

## <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class Library stellt mehrere Klassen, die von `COleDialog`:

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="getlasterror"></a>  COleDialog::GetLastError

Rufen Sie die `GetLastError` Memberfunktion versucht, zusätzlichen Fehlerinformationen abgerufen werden beim `DoModal` IDABORT zurückgibt.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Rückgabewert

Der vom zurückgegebenen Fehlercodes `GetLastError` richten sich nach der bestimmten Dialogfeld angezeigt.

### <a name="remarks"></a>Hinweise

Finden Sie unter den `DoModal` Member-Funktion in den abgeleiteten Klassen Informationen zu bestimmten Fehlermeldungen.

## <a name="see-also"></a>Siehe auch

[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
