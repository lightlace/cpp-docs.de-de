---
title: CConstantTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: 9641af2f184d2edaa82922363dff75783e79f87e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182183"
---
# <a name="cconstanttransition-class"></a>CConstantTransition-Klasse

Kapselt einen konstanten Übergang.

## <a name="syntax"></a>Syntax

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Ein Übergangsobjekt erstellt und initialisiert seine Dauer.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CConstantTransition::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CConstantTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|

## <a name="remarks"></a>Hinweise

Bei der einen Konstanten Übergang bleibt der Wert einer Animationsvariablen an den ursprünglichen Wert über die Dauer des Übergangs. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cconstanttransition"></a>  CConstantTransition::CConstantTransition

Ein Übergangsobjekt erstellt und initialisiert seine Dauer.

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parameter

*duration*<br/>
Die Dauer des Übergangs.

##  <a name="create"></a>  CConstantTransition::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf ein [IUIAnimationTransitionLibrary Schnittstelle](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), das eine Bibliothek mit standard-Übergänge definiert.

### <a name="return-value"></a>Rückgabewert

True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".

##  <a name="m_duration"></a>  CConstantTransition::m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
