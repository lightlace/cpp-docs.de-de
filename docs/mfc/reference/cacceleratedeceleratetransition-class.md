---
title: Caccelerateverlangsamatetransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 1e55e81b4d9b5c324f86bfd141b74d9faa362d94
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507740"
---
# <a name="cacceleratedeceleratetransition-class"></a>Caccelerateverlangsamatetransition-Klasse

Implementiert einen Übergang mit Beschleunigung/Verlangsamung.

## <a name="syntax"></a>Syntax

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Erstellt ein Übergangs Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com- (Überschreibt [cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Das Verhältnis der Zeit, die zum beschleunigen der Dauer aufgewendet wird.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Das Verhältnis der Zeit, die zur Verlangsamung der Dauer aufgewendet wurde.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Der Wert der Animations Variablen am Ende des Übergangs.|

## <a name="remarks"></a>Hinweise

Während der Umstellung auf schnellere Verlangsamung beschleunigt die Animations Variable und verlangsamt dann die Dauer des Übergangs und endet dabei mit einem angegebenen Wert. Sie können steuern, wie schnell die Variable beschleunigt und verlangsamt, indem Sie unterschiedliche Beschleunigung und Verlangsamungs Verhältnisse angeben. Wenn die anfängliche Geschwindigkeit 0 (null) ist, ist das Beschleunigungs Verhältnis der Bruchteil der Dauer, die die Variable beschleunigt. ebenso mit dem Verlangsamungs Verhältnis. Wenn die anfängliche Geschwindigkeit ungleich 0 (null) ist, ist dies der Bruchteil der Zeit zwischen der Geschwindigkeit, die 0 (null) und dem Ende des Übergangs erreicht. Das Beschleunigungs Verhältnis und das Verlangsamungs Verhältnis sollten auf einen maximalen Wert von 1,0 summiert werden. Da alle Übergänge automatisch gelöscht werden, empfiehlt es sich, diese mithilfe des new-Operators zuzuweisen. Das gekapselte iuianimationtransition com-Objekt wird von canimationcontroller:: animategroup erstellt, bis es NULL ist. Das Ändern von Element Variablen nach der Erstellung dieses COM-Objekts hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>Caccelerateverlangsamatetransition:: caccelerateverlangsamatetransition

Erstellt ein Übergangs Objekt.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parameter

*auf*<br/>
Die Dauer des Übergangs.

*finalValue*<br/>
Der Wert der Animations Variablen am Ende des Übergangs.

*accelerationRatio*<br/>
Das Verhältnis der Zeit, die zum beschleunigen der Dauer aufgewendet wird.

*decelerationRatio*<br/>
Das Verhältnis der Zeit, die zur Verlangsamung der Dauer aufgewendet wurde.

##  <a name="create"></a>Caccelerateverlangsamatetransition:: Create

Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com-

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf eine [iuianimationtransitionlibrary-Schnittstelle](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), die eine Bibliothek von Standard Übergängen definiert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Übergang erfolgreich erstellt wurde. andernfalls false.

##  <a name="m_accelerationratio"></a>Caccelerateverlangsamatetransition:: m_accelerationRatio

Das Verhältnis der Zeit, die zum beschleunigen der Dauer aufgewendet wird.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>Caccelerateverlangsamatetransition:: m_decelerationRatio

Das Verhältnis der Zeit, die zur Verlangsamung der Dauer aufgewendet wurde.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>Caccelerateverlangsamatetransition:: m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>Caccelerateverlangsamatetransition:: m_finalValue

Der Wert der Animations Variablen am Ende des Übergangs.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
