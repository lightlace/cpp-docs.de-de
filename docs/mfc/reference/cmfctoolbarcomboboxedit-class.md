---
title: Cmfctoolbarcomboboxedit-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: 2a0ab1766f42d34c86339cffb86f876358c97a4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504868"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>Cmfctoolbarcomboboxedit-Klasse

Das Framework verwendet die `CMFCToolBarComboBoxEdit` -Klasse zum Erstellen einer Symbolleisten-Schaltfläche, die sich wie ein bearbeitbares Kombinations Feld-Steuerelement verhält

## <a name="syntax"></a>Syntax

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfctoolbarcomboboxedit:: cmfctoolbarcomboboxedit](#cmfctoolbarcomboboxedit)|Erstellt ein `CMFCToolBarComboBoxEdit`-Objekt.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|

### <a name="remarks"></a>Hinweise

Leiten Sie eine Klasse von `CMFCToolBarComboBoxEdit` der-Klasse ab, um die Bearbeitungsvorgänge anzupassen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarcomboboxbutton. h

##  <a name="cmfctoolbarcomboboxedit"></a>Cmfctoolbarcomboboxedit:: cmfctoolbarcomboboxedit

Erstellt ein `CMFCToolBarComboBoxEdit`-Objekt.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Parameter

*combo*<br/>
in Ein Verweis auf ein [cmfctoolbarcomboboxbutton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) -Objekt, das eine Symbolleisten-Schaltfläche ist, die ein Kombinations Feld-Steuerelement enthält.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCToolBarComboBoxEdit` -Klasse erstellt wird. Dieser Code Ausschnitt ist Teil des IE- [Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
