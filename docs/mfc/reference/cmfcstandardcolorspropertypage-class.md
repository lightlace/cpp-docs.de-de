---
title: CMFCStandardColorsPropertyPage-Klasse
ms.date: 11/04/2016
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
ms.openlocfilehash: 91cfa609c31e83c02cce8b2a474a9b66ec3ba56f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388630"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage-Klasse

Stellt eine Eigenschaft dar, die Benutzer verwenden, um die standardmäßige Farben in einem Farbendialogfeld auswählen.

## <a name="syntax"></a>Syntax

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Standardkonstruktor|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|`CMFCStandardColorsPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCStandardColorsPropertyPage::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|

### <a name="remarks"></a>Hinweise

Die `CMFCColorDialog` -Klasse verwendet diese Klasse auf der Seite der Standardfarbe angezeigt. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxstandardcolorspropertypage.h

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCCustomColorsPropertyPage-Klasse](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
