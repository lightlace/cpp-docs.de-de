---
title: CMFCPropertyPage-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bbfce70e33441c1713a2297ca925e83e6cbba9f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427146"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage-Klasse

Die `CMFCPropertyPage` Klasse unterstützt die Anzeige von Popupmenüs auf einer Eigenschaftenseite.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Erstellt ein `CMFCPropertyPage`-Objekt.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCPropertyPage::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|`CMFCPropertyPage::OnSetActive`|Diese Memberfunktion wird von Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und wird zur aktiven Seite. (Überschreibt [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Hinweise

Die `CMFCPropertyPage` Klasse stellt einzelne Seiten eines Eigenschaftenblatts, auch bekannt als ein Dialogfeld im Registerformat dar.

Verwenden der `CMFCPropertyPage` -Klasse zusammen mit den [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Klasse. Um Menüs auf einer Eigenschaftenseite zu verwenden, ersetzen Sie alle Vorkommen von der `CPropertyPage` -Klasse mit der `CMFCPropertyPage` Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertypage.h

##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage

Erstellt ein `CMFCPropertyPage`-Objekt.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);


CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Parameter

*nIDTemplate*<br/>
Ressourcen-ID der Vorlage für diese Seite.

*nIDCaption*<br/>
Ressourcen-ID der Bezeichnung auf der Registerkarte für diese Seite zu platzieren. Wenn der Wert 0, wird der Name aus der Dialogfeldvorlage für diese Seite abgerufen. Der Standardwert ist 0.

*lpszTemplateName*<br/>
Zeigt auf den Namen der Vorlage für diese Seite. Darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den Konstruktorparametern, finden Sie unter [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet-Klasse](../../mfc/reference/cmfcpropertysheet-class.md)
