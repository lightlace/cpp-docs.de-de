---
title: CMFCToolBarComboBoxEdit-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: fcf89623fcde2067f2def83f1e491db015375e02
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280536"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit-Klasse

Das Framework verwendet die `CMFCToolBarComboBoxEdit` Klasse, um eine Symbolleisten-Schaltfläche zu erstellen, die sich wie eine bearbeitbare Kombinationsfeld-Steuerelement verhält.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|Erstellt ein `CMFCToolBarComboBoxEdit`-Objekt.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|

### <a name="remarks"></a>Hinweise

Leiten Sie eine Klasse aus der `CMFCToolBarComboBoxEdit` Klasse, um die Bearbeitungsvorgänge anzupassen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarcomboboxbutton.h

##  <a name="cmfctoolbarcomboboxedit"></a>  CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit

Erstellt ein `CMFCToolBarComboBoxEdit`-Objekt.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Parameter

*combo*<br/>
[in] Ein Verweis auf eine [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt, das eine Symbolleisten-Schaltfläche darstellt, das ein Kombinationsfeld-Steuerelement enthält.

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCToolBarComboBoxEdit` Klasse. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
