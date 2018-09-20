---
title: CSinusoidalTransitionFromVelocity-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d69e3ed213d9ad207dbf664088598a7232d40a32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401536"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity-Klasse

Kapselt einen Übergang mit sinusförmiger Geschwindigkeit und einer Amplitude, die von der ursprünglichen Geschwindigkeit der Animationsvariablen bestimmt wird.

## <a name="syntax"></a>Syntax

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|Erstellt einen Übergangsobjekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::m_duration](#m_duration)|Die Dauer des Übergangs.|
|[CSinusoidalTransitionFromVelocity::m_period](#m_period)|Der Zeitraum Oszillation der sinusförmiger Welle in Sekunden.|

## <a name="remarks"></a>Hinweise

Der Wert der Animationsvariablen oszilliert rund um den ursprünglichen Wert über die gesamte Dauer eines Übergangs sinusförmigem Bereich. Amplitude für das die Oszillation richtet sich nach Geschwindigkeit der Animationsvariable, wenn der Übergang beginnt. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="create"></a>  CSinusoidalTransitionFromVelocity::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf den Übergangsbibliothek, die für die Erstellung der standard-Übergänge zuständig ist.

### <a name="return-value"></a>Rückgabewert

True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".

##  <a name="csinusoidaltransitionfromvelocity"></a>  CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity

Erstellt einen Übergangsobjekt.

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

*Zeitraum*<br/>
Der Zeitraum Oszillation der sinusförmiger Welle in Sekunden.

##  <a name="m_duration"></a>  CSinusoidalTransitionFromVelocity::m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_period"></a>  CSinusoidalTransitionFromVelocity::m_period

Der Zeitraum Oszillation der sinusförmiger Welle in Sekunden.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
