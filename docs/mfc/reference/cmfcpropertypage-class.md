---
title: Cmfcpropertypage-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 4be584135ef789d7fbe3b1743ac0ad6ce66ac5b1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505044"
---
# <a name="cmfcpropertypage-class"></a>Cmfcpropertypage-Klasse

Die `CMFCPropertyPage` -Klasse unterstützt die Anzeige von Popup Menüs auf einer Eigenschaften Seite.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcpropertypage:: cmfcpropertypage](#cmfcpropertypage)|Erstellt ein `CMFCPropertyPage`-Objekt.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCPropertyPage::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|`CMFCPropertyPage::OnSetActive`|Diese Member-Funktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt und zur aktiven Seite wird. (Überschreibt [CPropertyPage:: OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. Weitere Informationen und Methoden Syntax finden Sie unter [CWnd::P retranslatemess Age](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Hinweise

Die `CMFCPropertyPage` -Klasse stellt einzelne Seiten eines Eigenschaften Blatts dar, die auch als Registerkarten Dialogfeld bezeichnet werden.

Verwenden Sie `CMFCPropertyPage` die-Klasse in Verbindung mit der [cmfcpropertysheet](../../mfc/reference/cmfcpropertysheet-class.md) -Klasse. Um Menüs auf einer Eigenschaften Seite zu verwenden, ersetzen Sie alle Vorkommen `CPropertyPage` der-Klasse `CMFCPropertyPage` durch die-Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertypage. h

##  <a name="cmfcpropertypage"></a>Cmfcpropertypage:: cmfcpropertypage

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
Die Ressourcen-ID der Vorlage für diese Seite.

*nIDCaption*<br/>
Die Ressourcen-ID der Bezeichnung, die auf der Registerkarte für diese Seite abgelegt werden soll. Wenn der Wert 0 ist, wird der Name aus der Dialogfeld Vorlage für diese Seite abgerufen. Der Standardwert ist 0.

*lpszTemplateName*<br/>
Zeigt auf den Namen der Vorlage für diese Seite. Lässt keine NULL-Werte zu.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den Konstruktorparametern finden Sie unter [CPropertyPage:: CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet-Klasse](../../mfc/reference/cmfcpropertysheet-class.md)
