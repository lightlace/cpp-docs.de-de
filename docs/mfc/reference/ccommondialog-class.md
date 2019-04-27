---
title: CCommonDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 4fa7aa51d1ce482e00f68365045cd35c3fb7939b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182266"
---
# <a name="ccommondialog-class"></a>CCommonDialog-Klasse

Die Basisklasse für Klassen, die Funktionalität der allgemeinen Windows-Dialogfelder kapseln.

## <a name="syntax"></a>Syntax

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|Erstellt ein `CCommonDialog`-Objekt.|

## <a name="remarks"></a>Hinweise

Die folgenden Klassen kapseln die Funktionalität der Windows-Standarddialogfelder:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog

Erstellt ein `CCommonDialog`-Objekt.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Finden Sie unter [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) vollständige Informationen.

## <a name="see-also"></a>Siehe auch

[CDialog-Klasse](../../mfc/reference/cdialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)<br/>
[CFontDialog-Klasse](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog-Klasse](../../mfc/reference/ccolordialog-class.md)<br/>
[CPageSetupDialog-Klasse](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog-Klasse](../../mfc/reference/cprintdialog-class.md)<br/>
[CFindReplaceDialog-Klasse](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
