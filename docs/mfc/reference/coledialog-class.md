---
title: COleDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs:
- C++
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ecfe5ba4ac2144ff626d6d37d8639f1798acda8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079297"
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

