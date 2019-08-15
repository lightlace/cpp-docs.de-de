---
title: CCubicTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: b6bb626f944ce87748809a5eb03a6f06f92c3de5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507138"
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
|[CCubicTransition::CCubicTransition](#ccubictransition)|Erstellt ein Übergangs Objekt und initialisiert seine Parameter.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCubicTransition::Create](#create)|Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com- (Überschreibt [cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animations Variablen am Ende des Übergangs.|
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Die Geschwindigkeit der Variablen am Ende des Übergangs.|
|[CCubicTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|

## <a name="remarks"></a>Hinweise

Während eines kubischen Übergangs ändert sich der Wert der Animations Variablen von seinem Anfangswert in einen angegebenen Endwert während der Übergangs Dauer und endet mit einer angegebenen Geschwindigkeit. Da alle Übergänge automatisch gelöscht werden, empfiehlt es sich, diese mithilfe des new-Operators zuzuweisen. Das gekapselte iuianimationtransition com-Objekt wird von canimationcontroller:: animategroup erstellt, bis es NULL ist. Das Ändern von Element Variablen nach der Erstellung dieses COM-Objekts hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="ccubictransition"></a>Ccubictransition:: ccubictransition

Erstellt ein Übergangs Objekt und initialisiert seine Parameter.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>Parameter

*auf*<br/>
Die Dauer des Übergangs.

*finalValue*<br/>
Der Wert der Animations Variablen am Ende des Übergangs.

*finalVelocity*<br/>
Die Geschwindigkeit der Variablen am Ende des Übergangs.

##  <a name="create"></a>Ccubictransition:: Create

Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com-

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf eine [iuianimationtransitionlibrary-Schnittstelle](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), die eine Bibliothek von Standard Übergängen definiert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Übergang erfolgreich erstellt wurde. andernfalls false.

##  <a name="m_dblfinalvalue"></a>Ccubictransition:: m_dblFinalValue

Der Wert der Animations Variablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>Ccubictransition:: m_dblFinalVelocity

Die Geschwindigkeit der Variablen am Ende des Übergangs.

```
DOUBLE m_dblFinalVelocity;
```

##  <a name="m_duration"></a>Ccubictransition:: m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
