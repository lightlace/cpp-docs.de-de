---
title: CLinearTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
helpviewer_keywords:
- CLinearTransition [MFC], CLinearTransition
- CLinearTransition [MFC], Create
- CLinearTransition [MFC], m_dblFinalValue
- CLinearTransition [MFC], m_duration
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
ms.openlocfilehash: 1a6348d1afd0117683bd31af61324b14e16f710c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505743"
---
# <a name="clineartransition-class"></a>CLinearTransition-Klasse

Kapselt einen linearen Übergang.

## <a name="syntax"></a>Syntax

```
class CLinearTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransition::CLinearTransition](#clineartransition)|Erstellt ein lineares Übergangs Objekt und initialisiert es mit Duration und Endwert.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransition::Create](#create)|Ruft die Übergangs Bibliothek auf, um ein gekapseltes Übergangs-com- (Überschreibt [cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animations Variablen am Ende des Übergangs.|
|[CLinearTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|

## <a name="remarks"></a>Hinweise

Während eines linearen Übergangs wechselt der Wert der Animations Variablen linear von seinem Anfangswert in einen angegebenen Endwert. Da alle Übergänge automatisch gelöscht werden, empfiehlt es sich, diese mithilfe des new-Operators zuzuweisen. Das gekapselte iuianimationtransition com-Objekt wird von canimationcontroller:: animategroup erstellt, bis es NULL ist. Das Ändern von Element Variablen nach der Erstellung dieses COM-Objekts hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CLinearTransition](../../mfc/reference/clineartransition-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="clineartransition"></a>Clineartransition:: clineartransition

Erstellt ein lineares Übergangs Objekt und initialisiert es mit Duration und Endwert.

```
CLinearTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parameter

*auf*<br/>
Die Dauer des Übergangs.

*dblFinalValue*<br/>
Der Wert der Animations Variablen am Ende des Übergangs.

##  <a name="create"></a>Clineartransition:: Create

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

##  <a name="m_dblfinalvalue"></a>Clineartransition:: m_dblFinalValue

Der Wert der Animations Variablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_duration"></a>Clineartransition:: m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
