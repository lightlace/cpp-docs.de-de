---
title: CDiscreteTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: 7087dfa13972737f0a1244d2cc9a7088b23dc184
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506854"
---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition-Klasse

Kapselt einen einzelnen Übergang.

## <a name="syntax"></a>Syntax

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Erstellt ein diskretes Übergangs Objekt und initialisiert seine Parameter.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDiscreteTransition::Create](#create)|Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com- (Überschreibt [cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animations Variablen am Ende des Übergangs.|
|[CDiscreteTransition::m_delay](#m_delay)|Die Zeitspanne, um die der sofortige Wechsel zum endgültigen Wert verzögert werden soll.|
|[CDiscreteTransition::m_hold](#m_hold)|Die Zeitspanne, um die die Variable am Endwert gespeichert werden soll.|

## <a name="remarks"></a>Hinweise

Während eines diskreten Übergangs verbleibt die Animations Variable beim Anfangswert für eine angegebene Verzögerungszeit, schaltet dann sofort zu einem angegebenen Endwert um und verbleibt bei diesem Wert für eine bestimmte haltenzeit. Da alle Übergänge automatisch gelöscht werden, empfiehlt es sich, diese mithilfe des new-Operators zuzuweisen. Das gekapselte iuianimationtransition com-Objekt wird von canimationcontroller:: animategroup erstellt, bis es NULL ist. Das Ändern von Element Variablen nach der Erstellung dieses COM-Objekts hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cdiscretetransition"></a>Cdiskretetransition:: cdiskretetransition

Erstellt ein diskretes Übergangs Objekt und initialisiert seine Parameter.

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>Parameter

*delay*<br/>
Die Zeitspanne, um die der sofortige Wechsel zum endgültigen Wert verzögert werden soll.

*dblFinalValue*<br/>
Der Wert der Animations Variablen am Ende des Übergangs.

*verfügen*<br/>
Die Zeitspanne, um die die Variable am Endwert gespeichert werden soll.

##  <a name="create"></a>Cdiskretetransition:: Create

Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com-

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*pLibrary*<br/>
Ein Zeiger auf eine [iuianimationtransitionlibrary-Schnittstelle](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), die eine Bibliothek von Standard Übergängen definiert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Übergang erfolgreich erstellt wurde. andernfalls false.

##  <a name="m_dblfinalvalue"></a>Cdiskretetransition:: m_dblFinalValue

Der Wert der Animations Variablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_delay"></a>Cdiskretetransition:: m_delay

Die Zeitspanne, um die der sofortige Wechsel zum endgültigen Wert verzögert werden soll.

```
UI_ANIMATION_SECONDS m_delay;
```

##  <a name="m_hold"></a>Cdiskretetransition:: m_hold

Die Zeitspanne, um die die Variable am Endwert gespeichert werden soll.

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
