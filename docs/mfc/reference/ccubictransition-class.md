---
title: CCubicTransition-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bd07d8f57396da78ce19cb5ac568d651f71459b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398067"
---
# <a name="ccubictransition-class"></a>CCubicTransition-Klasse

Kapselt einen kubischen Übergang.

## <a name="syntax"></a>Syntax

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCubicTransition::CCubicTransition](#ccubictransition)|Ein Übergangsobjekt erstellt und initialisiert seine Parameter.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCubicTransition::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Die Geschwindigkeit der Variablen an das Ende des Übergangs.|
|[CCubicTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|

## <a name="remarks"></a>Hinweise

Während eines Übergangs kubische ändert den Wert der Animationsvariablen vom Anfangswert auf einen angegebenen Wert für die endgültige über die Dauer des Übergangs, endet mit einer angegebenen Geschwindigkeit. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="ccubictransition"></a>  CCubicTransition::CCubicTransition

Ein Übergangsobjekt erstellt und initialisiert seine Parameter.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

*finalValue*<br/>
Der Wert der Animationsvariablen am Ende des Übergangs.

*finalVelocity*<br/>
Die Geschwindigkeit der Variablen an das Ende des Übergangs.

##  <a name="create"></a>  CCubicTransition::Create

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

##  <a name="m_dblfinalvalue"></a>  CCubicTransition::m_dblFinalValue

Der Wert der Animationsvariablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CCubicTransition::m_dblFinalVelocity

Die Geschwindigkeit der Variablen an das Ende des Übergangs.

```
DOUBLE m_dblFinalVelocity;
```

##  <a name="m_duration"></a>  CCubicTransition::m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
