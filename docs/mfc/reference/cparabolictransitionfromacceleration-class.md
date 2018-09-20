---
title: CParabolicTransitionFromAcceleration-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
dev_langs:
- C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e4db0932b2a2171e47c1b8e6c42a84fa100c9e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389355"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration-Klasse

Kapselt einen Übergang mit parabelförmiger Beschleunigung.

## <a name="syntax"></a>Syntax

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Erstellt einen Übergang mit parabelförmiger Beschleunigung und initialisiert sie mit der angegebenen Parameter.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Die Beschleunigung der Animationsvariablen während des Übergangs.|
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.|

## <a name="remarks"></a>Hinweise

Während eines Übergangs mit parabelförmiger Beschleunigung ändert sich der Wert der Animationsvariablen von den ursprünglichen Wert auf den endgültigen Wert endet mit einer angegebenen Geschwindigkeit. Sie können steuern, wie schnell die Variable den endgültigen Wert erreicht, indem Sie die Rate der Beschleunigung angeben. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cparabolictransitionfromacceleration"></a>  CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration

Erstellt einen Übergang mit parabelförmiger Beschleunigung und initialisiert sie mit der angegebenen Parameter.

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>Parameter

*dblFinalValue*<br/>
Der Wert der Animationsvariablen am Ende des Übergangs.

*dblFinalVelocity*<br/>
Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.

*dblAcceleration*<br/>
Die Beschleunigung der Animationsvariablen während des Übergangs.

##  <a name="create"></a>  CParabolicTransitionFromAcceleration::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf den Übergangsbibliothek, die für die Erstellung der standard-Übergänge zuständig ist.

### <a name="return-value"></a>Rückgabewert

True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".

##  <a name="m_dblacceleration"></a>  CParabolicTransitionFromAcceleration::m_dblAcceleration

Die Beschleunigung der Animationsvariablen während des Übergangs.

```
DOUBLE m_dblAcceleration;
```

##  <a name="m_dblfinalvalue"></a>  CParabolicTransitionFromAcceleration::m_dblFinalValue

Der Wert der Animationsvariablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CParabolicTransitionFromAcceleration::m_dblFinalVelocity

Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
