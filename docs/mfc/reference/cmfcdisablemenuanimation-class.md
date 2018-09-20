---
title: CMFCDisableMenuAnimation-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 431b7caf3efcf9e569d6eee3c309b409d8479730
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443318"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation-Klasse

Deaktiviert die Popup-Menü-Animation.

## <a name="syntax"></a>Syntax

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Erstellt ein `CMFCDisableMenuAnimation`-Objekt.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCDisableMenuAnimation::Restore](#restore)|Wird von der vorherigen Animation, die das Framework verwendet wird, um ein Popupmenü anzuzeigen.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|name|Beschreibung|
|`CMFCDisableMenuAnimation::m_animType`|Speichert den vorherigen Popupmenü-Animation-Typ.|

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Hilfsklasse vorübergehend deaktivieren, Popup-Menüanimationen (z. B., wenn Sie die Maus oder Tastatur Befehle verarbeiten).

Ein `CMFCDisableMenuAnimation` Objekt deaktiviert die Popup-Menüanimation während ihrer Lebensdauer. Der Konstruktor speichert den aktuellen Typ der Popup-Menü Animationen in der `m_animType` -Feld und setzt die aktuelle Animation Typ `CMFCPopupMenu::NO_ANIMATION`. Der Destruktor wird der vorherige Animationstyp.

Sie erstellen eine `CMFCDisableMenuAnimation` Objekt im Stapel, um Popup-Menüanimationen in einer einzelnen Funktion zu deaktivieren. Wenn Sie Popup-Menü-Animation zwischen Funktionen deaktivieren möchten, erstellen Sie eine `CMFCDisableMenuAnimation` Objekt auf dem Heap, und löschen Sie sie bei der Popup-Menüanimationen wiederherstellen möchten.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie den Stapel zu verwenden, um die Menüanimation vorübergehend zu deaktivieren.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpopupmenu.h

##  <a name="restore"></a>  CMFCDisableMenuAnimation::Restore

Wird von der vorherigen Animation, die das Framework verwendet wird, um ein Popupmenü anzuzeigen.

```
void Restore ();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, indem die `CMFCDisableMenuAnimation` Destruktor die vorherige Animation wiederherstellen, die das Framework verwendet wird, um ein Popupmenü anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)
