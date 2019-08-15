---
title: CLinearTransitionFromSpeed-Klasse
ms.date: 11/04/2016
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
helpviewer_keywords:
- CLinearTransitionFromSpeed [MFC], CLinearTransitionFromSpeed
- CLinearTransitionFromSpeed [MFC], Create
- CLinearTransitionFromSpeed [MFC], m_dblFinalValue
- CLinearTransitionFromSpeed [MFC], m_dblSpeed
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
ms.openlocfilehash: 50c958a092478f4b9ec4e94f9e5e973a74c334c2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505712"
---
# <a name="clineartransitionfromspeed-class"></a>CLinearTransitionFromSpeed-Klasse

Kapselt einen Übergang mit linearer Geschwindigkeit.

## <a name="syntax"></a>Syntax

```
class CLinearTransitionFromSpeed : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](#clineartransitionfromspeed)|Erstellt ein lineares Geschwindigkeits Übergangs Objekt und initialisiert es mit der Geschwindigkeit und dem endgültigen Wert.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransitionFromSpeed::Create](#create)|Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com- (Überschreibt [cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransitionFromSpeed::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animations Variablen am Ende des Übergangs.|
|[CLinearTransitionFromSpeed::m_dblSpeed](#m_dblspeed)|Der absolute Wert der Geschwindigkeit der Variablen.|

## <a name="remarks"></a>Hinweise

Während eines Übergangs der linearen Geschwindigkeit ändert sich der Wert der Animations Variablen zu einer bestimmten Rate. Die Dauer des Übergangs wird durch den Unterschied zwischen dem Anfangswert und dem angegebenen Endwert bestimmt. Da alle Übergänge automatisch gelöscht werden, empfiehlt es sich, diese mithilfe des new-Operators zuzuweisen. Das gekapselte iuianimationtransition com-Objekt wird von canimationcontroller:: animategroup erstellt, bis es NULL ist. Das Ändern von Element Variablen nach der Erstellung dieses COM-Objekts hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="clineartransitionfromspeed"></a>Clineartransitionfromspeed:: clineartransitionfromspeed

Erstellt ein lineares Geschwindigkeits Übergangs Objekt und initialisiert es mit der Geschwindigkeit und dem endgültigen Wert.

```
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parameter

*dblSpeed*<br/>
Der absolute Wert der Geschwindigkeit der Variablen.

*dblFinalValue*<br/>
Der Wert der Animations Variablen am Ende des Übergangs.

##  <a name="create"></a>Clineartransitionfromspeed:: Create

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

##  <a name="m_dblfinalvalue"></a>Clineartransitionfromspeed:: m_dblFinalValue

Der Wert der Animations Variablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblspeed"></a>Clineartransitionfromspeed:: m_dblSpeed

Der absolute Wert der Geschwindigkeit der Variablen.

```
DOUBLE m_dblSpeed;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
