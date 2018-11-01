---
title: CFolderPickerDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ba189badaa9b1605e3467526e7b92a18a1bb5a73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561303"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog-Klasse

CFolderPickerDialog-Klasse implementiert CFileDialog im ordnerauswahlmodus.

## <a name="syntax"></a>Syntax

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Destruktor.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Konstruktor.|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

Konstruktor.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Parameter

*lpszFolder*<br/>
Anfängliche Ordner.

*dwFlags*<br/>
Eine Kombination von ein oder mehrere Flags, die Sie im Dialogfeld anpassen können.

*pParentWnd*<br/>
Ein Zeiger auf die Dialogfeldobjekt über- oder Besitzer-Fenster.

*dwSize*<br/>
Die Größe des der OPENFILENAME-Struktur.

### <a name="remarks"></a>Hinweise

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog:: ~ CFolderPickerDialog

Destruktor.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
