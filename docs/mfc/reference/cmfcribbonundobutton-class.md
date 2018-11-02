---
title: CMFCRibbonUndoButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 78d6b3423f19fe0cf3caf3aa0184fbe779a6c029
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512892"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton-Klasse

Die `CMFCRibbonUndoButton` -Klasse implementiert eine Dropdown-Listenfeld-Schaltfläche, die neuesten Benutzerbefehle enthält. Benutzer können eine oder mehrere der neuesten Befehle auswählen, aus der Dropdown-Liste entweder wiederholen oder rückgängig machen.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Erstellt ein neues `CMFCRibbonUndoButton` Objekt mithilfe des Befehls-ID, die Sie angeben, Beschriftung und Bilder aus der Liste der Bilder des übergeordneten Objekts.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Die Liste der Aktionen wird eine neue Aktion hinzugefügt.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Löscht die Aktionsliste, die die Dropdown-Liste ist.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Bestimmt die Anzahl von Elementen, die ein Benutzer aus der Dropdownliste ausgewählt.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Gibt an, ob das Objekt ein Menü enthält.|

## <a name="remarks"></a>Hinweise

Die `CMFCRibbonUndoButton` Klasse verwendet einen Stapel, um die Dropdown-Liste darstellen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonUndoButton` Klasse, und eine neue Aktion hinzufügen, um die Liste der Aktionen. Dieser Codeausschnitt ist Teil der [Menüband Gadgets Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonundobutton.h

##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction

Die Liste der Aktionen wird eine neue Aktion hinzugefügt.

```
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Die aktionsbezeichnung, die in der Dropdown-Liste angezeigt werden.

##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList

Löscht die Aktionsliste, die die Dropdown-Liste ist.

```
void CleanUpUndoList();
```

##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton

Erstellt ein neues `CMFCRibbonUndoButton` Objekt mithilfe des Befehls-ID, die Sie angeben, Beschriftung und Bilder aus der Liste der Bilder des übergeordneten Objekts.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Gibt die Befehls-ID an.

*lpszText*<br/>
[in] Gibt die Beschriftung der Schaltfläche an.

*nSmallImageIndex*<br/>
[in] Nullbasierte Index in der Bildliste an, der das übergeordnete Objekt für kleines Bild der Schaltfläche.

*nLargeImageIndex*<br/>
[in] Nullbasierte Index in der Bildliste an, der das übergeordnete Objekt für die von der Schaltfläche großes Bild.

*hIcon*<br/>
[in] Ein Handle für ein Symbol, das Sie als Image mit einer Schaltfläche verwenden können.

##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber

Bestimmt die Anzahl von Elementen, die ein Benutzer aus der Dropdownliste ausgewählt.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente, die ein Benutzer ausgewählt.

##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu

Gibt an, ob das Objekt ein Menü enthält.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt immer "true" zurück.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
