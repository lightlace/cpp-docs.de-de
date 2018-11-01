---
title: CMFCRibbonButtonsGroup-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0babda16ee29671a584599699b459062c22406e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592737"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup-Klasse

Die `CMFCRibbonButtonsGroup` -Klasse ermöglicht es Ihnen, einen Satz von Schaltflächen auf dem Menüband in einer Gruppe zu organisieren. Alle Schaltflächen der Gruppe liegen innerhalb eines Rahmens direkt horizontal nebeneinander.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Fügt eine Schaltfläche zu einer Gruppe hinzu.|
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Fügt eine Liste der Schaltflächen zu einer Gruppe hinzu.|
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Gibt einen Zeiger auf die Schaltfläche, die sich am angegebenen Index befindet.|
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Gibt die Anzahl der Schaltflächen in der Gruppe zurück.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Gibt die Bildgröße der normalen-Images in der Menübandgruppe (überschreibt [cmfcribbonbaseelement:: Getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück (überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Berichte, ob die `CMFCRibbonButtonsGroup` Objekt enthält Symbolleistenbilder.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Zeichnet das entsprechende Image für eine angegebene Schaltfläche aus, je nachdem, ob die Schaltfläche mit der normalen, hervorgehobene oder deaktiviert.|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Entfernt alle Schaltflächen aus der `CMFCRibbonButtonsGroup` Objekt.|
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Bilder und der Gruppe zugewiesen.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Legt die übergeordnete `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle darin enthaltenen Schaltflächen (überschreibt [cmfcribbonbaseelement:: Setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|

## <a name="remarks"></a>Hinweise

Die Gruppe ergibt sich aus [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) und kann als eine Einheit bearbeitet werden. Sie können die Gruppe alle Panel oder Popup-Menü positionieren.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonButtonsGroup` -Klasse. Das Beispiel zeigt, wie zum Erstellen einer `CMFCRibbonButtonsGroup` Objekt, weisen Sie Images für die Gruppe von Schaltflächen auf dem Menüband und die Gruppe von Schaltflächen auf dem Menüband eine Schaltfläche hinzufügen. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonbuttonsgroup.h

##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton

Fügt eine Schaltfläche zu einer Gruppe hinzu.

```
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parameter

*pButton*<br/>
[in] Ein Zeiger auf eine Schaltfläche zum Hinzufügen.

##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons

Fügt eine Liste der Schaltflächen zu einer Gruppe hinzu.

```
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Parameter

*lstButtons*<br/>
[in] Eine Liste von Zeigern auf die Schaltflächen, die Sie hinzufügen möchten.

##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parameter

*pButton*<br/>
[in] Gibt an, eine Schaltfläche zum Hinzufügen auf das neu erstellte `CMFCRibbonButtonsGroup` Objekt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton

Gibt einen Zeiger auf die Schaltfläche, die sich am angegebenen Index befindet.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Parameter

*i*<br/>
[in] Ein nullbasierter Index, eine Schaltfläche zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Schaltfläche, die sich am angegebenen Index befindet. NULL, wenn der angegebene Index außerhalb des gültigen Bereichs befindet.

### <a name="remarks"></a>Hinweise

##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount

Gibt die Anzahl der Schaltflächen in der Gruppe zurück.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Schaltflächen in der Gruppe.

##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize

Ruft die Größe der geschützten Image `CMFCToolBarImages` Member `m_Images`.

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Größe der Symbolleiste Images, Image zurück, wenn vorhanden, oder ein `CSize` 0 (null), ist dies nicht.

### <a name="remarks"></a>Hinweise

##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize

Ruft die maximale Größe des Menübandelements Gruppe ab.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf den Gerätekontext der Menübandgruppe.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages

Berichte, ob die `CMFCRibbonButtonsGroup` Objekt enthält Symbolleistenbilder.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die geschützte `CMFCToolBarImages` Member `m_Images` enthält alle Bilder oder FALSE, wenn nicht.

### <a name="remarks"></a>Hinweise

##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage

Zeichnet das entsprechende Image für eine angegebene Schaltfläche aus, je nachdem, ob die Schaltfläche mit der normalen, hervorgehobene oder deaktiviert.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf den Gerätekontext, der die `CMFCRibbonButtonsGroup` Objekt.

*rectImage*<br/>
[in] Das Rechteck, in dem das Bild gezeichnet werden soll.

*pButton*<br/>
[in] Die Schaltfläche für die zum Zeichnen des Bilds.

*nImageIndex*<br/>
[in] Der Index des Bildes, das auf die Schaltfläche "(in einem der drei Images Arrays für normale, hervorgehobene oder deaktivierte Schaltflächen) zu zeichnen.

### <a name="remarks"></a>Hinweise

##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll

Entfernt alle Schaltflächen aus der `CMFCRibbonButtonsGroup` Objekt.

```
void RemoveAll();
```

### <a name="remarks"></a>Hinweise

##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages

Weist Abbilder für die Gruppe von Schaltflächen auf dem Menüband.

```
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Parameter

*pImages*<br/>
[in] Regulären Abbildern.

*pHotImages*<br/>
[in] Hot-Images.

*pDisabledImages*<br/>
[in] Deaktivierte Bilder.

### <a name="remarks"></a>Hinweise

Rufen Sie `SetImages` vor dem Hinzufügen von Schaltflächen zu einer Gruppe. Die Anzahl der Abbilder muss größer oder gleich der Anzahl der Schaltflächen, um der Gruppe hinzugefügt werden.

> [!NOTE]
>  Hot-Images sind die Images, die angezeigt werden, wenn der Benutzer über die Schaltfläche bewegt wird. Deaktiviert-Images sind die Images, die angezeigt werden, wenn die Schaltfläche deaktiviert ist.

##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory

Legt die übergeordnete `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle darin enthaltenen Schaltflächen.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Parameter

*pCategory*<br/>
[in] Zeiger auf die übergeordnete Kategorie festlegen (der Gruppen im Registerkartenformat im Menübandsteuerelemente werden Kategorien genannt).

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
