---
title: CAccelerateDecelerateTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: f37670d6e965cb034b81a6fb9ec8cc252bd5ee31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614694"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition-Klasse

Implementiert einen Übergang mit Beschleunigung/Verlangsamung.

## <a name="syntax"></a>Syntax

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Erstellt einen Übergangsobjekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Das Verhältnis der Zeit, für die Dauer zu beschleunigen.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Das Verhältnis der Zeit damit verbracht, verlangsamen, die für die Dauer verwendet wird.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|

## <a name="remarks"></a>Hinweise

Bei einer Beschleunigung-Übergang zu verlangsamen, Animationsvariablen beschleunigt, und klicken Sie dann die Dauer des Übergangs, endet mit einem angegebenen Wert verlangsamt. Sie können steuern, wie schnell die Variable beschleunigt und unabhängig voneinander und durch Angabe von verschiedenen Beschleunigung und Verlangsamung Verhältnisse verlangsamt. Wenn die ursprüngliche Geschwindigkeit 0 (null) ist, ist das Beschleunigungsverhältnis der Anteil für die Dauer, die die Variable investieren wird beschleunigt. Ebenso mit der Verlangsamungsrate. Wenn die ursprüngliche Geschwindigkeit ungleich NULL ist, ist es der Bruchteil der Zeit zwischen der Geschwindigkeit, 0 (null) und das Ende des Übergangs zu erreichen. Die Acceleration-Verhältnis und der Verlangsamungsrate sollte auf ein Maximum von 1,0 summieren. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

Erstellt einen Übergangsobjekt.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

*finalValue*<br/>
Der Wert der Animationsvariablen am Ende des Übergangs.

*accelerationRatio*<br/>
Das Verhältnis der Zeit, für die Dauer zu beschleunigen.

*decelerationRatio*<br/>
Das Verhältnis der Zeit damit verbracht, verlangsamen, die für die Dauer verwendet wird.

##  <a name="create"></a>  CAccelerateDecelerateTransition::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf ein [IUIAnimationTransitionLibrary Schnittstelle](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), das eine Bibliothek mit standard-Übergänge definiert.

### <a name="return-value"></a>Rückgabewert

True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".

##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio

Das Verhältnis der Zeit, für die Dauer zu beschleunigen.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio

Das Verhältnis der Zeit damit verbracht, verlangsamen, die für die Dauer verwendet wird.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue

Der Wert der Animationsvariablen am Ende des Übergangs.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
