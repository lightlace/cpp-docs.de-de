---
title: CMFCTasksPaneTaskGroup-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb9446dde0c8a3ef7089fd50e722f96ead237c6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424884"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup-Klasse

Die `CMFCTasksPaneTaskGroup` -Klasse ist eine Hilfsklasse, die von der [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) Steuerelement. Objekte des Typs `CMFCTasksPaneTaskGroup` stellen eine *Aufgabengruppe*dar. Die Aufgabengruppe ist eine Liste von Elementen, die vom Framework in einem separaten Feld angezeigt wird, das eine Schaltfläche zum Reduzieren enthält. Das Feld kann über eine optionale Beschriftung (Gruppennamen) verfügen. Wenn eine Gruppe reduziert ist, ist die Liste der Aufgaben nicht sichtbar.

## <a name="syntax"></a>Syntax

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Erstellt ein `CMFCTasksPaneTaskGroup`-Objekt.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Bestimmt die barrierefreiheitsdaten für die aktuelle Aufgabengruppe.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Bestimmt, ob die Aufgabengruppe am unteren Rand der Aufgabenbereich-Steuerelement ausgerichtet wird.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Bestimmt, ob die Aufgabengruppe reduziert ist.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Bestimmt, ob die Aufgabengruppe ist *spezielle.* Das Framework werden spezielle Beschriftungen in einer anderen Farbe angezeigt.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Enthält die interne Liste von Aufgaben.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Gibt das umschließende Rechteck der gruppenbeschriftung an.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Gibt das umschließende Rechteck der Gruppe an.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Gibt den Namen der Gruppe an.|

## <a name="remarks"></a>Hinweise

Die folgende Abbildung zeigt eine erweiterte Aufgabengruppe:

![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "Nexttaskgrpexpand")

Die folgende Abbildung zeigt eine reduzierte Aufgabengruppe:

![Reduzierte Aufgabengruppe](../../mfc/reference/media/nexttaskgrpcollapse.png "Nexttaskgrpcollapse")

Die folgende Abbildung zeigt eine Aufgabengruppe ohne Beschriftung:

![Aufgabengruppe ohne Beschriftung](../../mfc/reference/media/nexttaskgrpnocapt.png "Nexttaskgrpnocapt")

Die folgende Abbildung zeigt zwei Aufgabengruppen. Die erste Aufgabengruppe wird als Sonderzeichen markiert, indem die `m_bIsSpecial` flag auf "true", die zweite Aufgabengruppe ist zwar keine speziellen. Beachten Sie, wie die Beschriftung für die erste Aufgabengruppe dunkler als der zweite Aufgabengruppe ist:

![Spezielle Aufgabengruppe](../../mfc/reference/media/nexttaskgrpspecial.png "Nexttaskgrpspecial")

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxTasksPane.h

##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

Erstellt ein `CMFCTasksPaneTaskGroup`-Objekt.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Gibt den Namen der Gruppe in der gruppenbeschriftung an.

*bIsBottom*<br/>
Gibt an, ob die Gruppe am unteren Rand der Aufgabenbereich-Steuerelement ausgerichtet ist.

*bIsSpecial*<br/>
Gibt an, ob die Gruppe, als festgelegt ist *spezielle* und daher, ob die gruppenbeschriftung mit einer anderen Farbe ausgefüllt wird.

*bIsCollapsed*<br/>
Gibt an, ob die Gruppe reduziert ist.

*P_seite*<br/>
Gibt an, die Eigenschaftenseite, der diese Aufgabengruppe gehört.

*hIcon*<br/>
Gibt das Symbol, das in der gruppenbeschriftung anzeigt.

### <a name="remarks"></a>Hinweise

##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom

Bestimmt, ob die Aufgabengruppe am unteren Rand der Aufgabenbereich-Steuerelement ausgerichtet wird.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Hinweise

Am unteren Rand der Aufgabenbereich-Steuerelement kann nur eine Gruppe ausgerichtet werden. Diese Aufgabengruppe muss zuletzt hinzugefügt werden. Weitere Informationen finden Sie unter [cmfctaskspane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed

Bestimmt, ob die Aufgabengruppe reduziert ist.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Hinweise

Sie können aktivieren oder deaktivieren Sie die Möglichkeit, die Gruppen des Aufgabenbereichs durch den Aufruf zu reduzieren [cmfctaskspane:: Enablegroupcollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).

##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial

Bestimmt, ob die Aufgabengruppe ist *spezielle* und gibt an, ob die Beschriftung für eine spezielle Aufgabengruppe durch eine andere Farbe identifiziert werden sollen.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung die Windows XP visual Studio-Designs verwendet wird und `m_bIsSpecial` ist "false", das Framework ruft `DrawThemeBackground` mit dem Flag EBP_NORMALGROUPBACKGROUND. Wenn `m_bIsSpecial` ist "true", das Framework ruft `DrawThemeBackground` mit dem Flag EBP_SPECIALGROUPBACKGROUND.

##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks

Enthält die interne Liste von Aufgaben.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Hinweise

Aufrufen, um diese Liste zu füllen, [cmfctaskspane:: Addtask](../../mfc/reference/cmfctaskspane-class.md#addtask).

##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect

Gibt das umschließende Rechteck der gruppenbeschriftung an.

```
CRect m_rect;
```

### <a name="remarks"></a>Hinweise

Dieser Wert wird vom Framework automatisch berechnet.

##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup

Gibt das umschließende Rechteck der Gruppe an.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Hinweise

Dieser Wert wird vom Framework automatisch berechnet.

##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName

Gibt den Namen der Gruppe an.

```
CString m_strName;
```

### <a name="remarks"></a>Hinweise

Wenn dieser Wert leer ist, wird die gruppenbeschriftung wird nicht angezeigt, und die Gruppe nicht reduziert werden kann.

##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData

Bestimmt die barrierefreiheitsdaten für die aktuelle Aufgabengruppe.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
[in] Stellt das übergeordnete Fenster des die aktuelle Aufgabengruppe dar.

*data*<br/>
[out] Ein Objekt des Typs `CAccessibilityData` , die mit den Zugriff auf Daten der aktuellen Aufgabengruppe aufgefüllt ist.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die *Daten* Parameter wurde erfolgreich mit den Zugriff auf Daten der aktuellen Aufgabengruppe aufgefüllt ist, andernfalls "false".

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane-Klasse](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)
