---
title: CCustomTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: e0e5250b27ce6b902939ebcbfa03bf022a202788
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304014"
---
# <a name="ccustomtransition-class"></a>CCustomTransition-Klasse

Implementiert einen benutzerdefinierten Übergang.

## <a name="syntax"></a>Syntax

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Erstellt einen benutzerdefinierten Übergang-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCustomTransition::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Legt einen Anfangswert, die auf eine Animationsvariable zugeordneten dieses Übergangs angewendet werden.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Legt eine ursprüngliche Geschwindigkeit, die auf eine Animationsvariable zugeordneten dieses Übergangs angewendet werden.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Gibt an, ob der anfängliche Wert mit SetInitialValue angegeben wurde.|
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Gibt an, ob die ursprüngliche Geschwindigkeit mit SetInitialVelocity angegeben wurde.|
|[CCustomTransition::m_initialValue](#m_initialvalue)|Speichert den ersten Wert.|
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Speichert die ursprüngliche Geschwindigkeit an.|
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Speichert einen Zeiger auf einen benutzerdefinierten Interpolator.|

## <a name="remarks"></a>Hinweise

Die CCustomTransitions-Klasse kann Entwickler benutzerdefinierte Übergänge zu implementieren. Es erstellt und als Standardübergang verwendet hat, aber ihr Konstruktor nimmt als Parameter einen Zeiger auf ein benutzerdefinierter Interpolator. Führen Sie die folgenden Schritte aus, um benutzerdefinierte Übergänge zu verwenden: 1. CCustomInterpolator eine Klasse ableiten und implementieren Sie mindestens InterpolateValue-Methode. 2. Stellen Sie sicher, dass die Lebensdauer des Objekts mit benutzerdefinierter Interpolator muss länger als die Dauer der Animation, wo sie verwendet wird. 3. Ein CCustomTransition-Objekt instanziiert werden (mit dem Operator new) und einen Zeiger auf benutzerdefinierter Interpolator in den Konstruktor übergeben. 4. Rufen Sie CCustomTransition::SetInitialValue und CCustomTransition::SetInitialVelocity aus, wenn diese Parameter für die benutzerdefinierten Interpolation erforderlich sind. 5. Übergeben Sie den Zeiger für den benutzerdefinierten Übergang AddTransition-Methode eines Animationsobjekts, mit dem benutzerdefinierten Algorithmus, dessen Wert animiert werden soll. 6. Wenn der Wert eines Animationsobjekts ändern soll wird Windows Animations-API in CCustomInterpolator "InterpolateValue" (und andere relevanten Methoden) aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition

Erstellt einen benutzerdefinierten Übergang-Objekt.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parameter

*pInterpolator*<br/>
Ein Zeiger auf benutzerdefinierter Interpolator.

##  <a name="create"></a>  CCustomTransition::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Parameter

*pFactory*<br/>
Ein Zeiger auf den Übergangsfactory, die für die Erstellung von benutzerdefinierten Übergänge zuständig ist.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Diese Methode kann auch festgelegt werden, Anfangswert und die ursprüngliche Geschwindigkeit auf einer Animationsvariablen angewendet werden, dem dieser Übergang zugeordnet ist. Zu diesem Zweck müssen Sie SetInitialValue und SetInitialVelocity aufrufen, bevor das Framework das gekapselte Übergang COM-Objekt erstellt (es geschieht, wenn Sie mit CAnimationController:: AnimateGroup aufrufen).

##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified

Gibt an, ob der anfängliche Wert mit SetInitialValue angegeben wurde.

```
BOOL m_bInitialValueSpecified;
```

##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified

Gibt an, ob die ursprüngliche Geschwindigkeit mit SetInitialVelocity angegeben wurde.

```
BOOL m_bInitialVelocitySpecified;
```

##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue

Speichert den ersten Wert.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity

Speichert die ursprüngliche Geschwindigkeit an.

```
DOUBLE m_initialVelocity;
```

##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator

Speichert einen Zeiger auf einen benutzerdefinierten Interpolator.

```
CCustomInterpolator* m_pInterpolator;
```

##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue

Legt einen Anfangswert, die auf eine Animationsvariable zugeordneten dieses Übergangs angewendet werden.

```
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Parameter

*initialValue*

##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity

Legt eine ursprüngliche Geschwindigkeit, die auf eine Animationsvariable zugeordneten dieses Übergangs angewendet werden.

```
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parameter

*initialVelocity*

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
