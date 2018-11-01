---
title: CBaseTransition-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: b4c15be574700730e847bce06aaa4a6f82aed4b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539125"
---
# <a name="cbasetransition-class"></a>CBaseTransition-Klasse

Stellt einen einfachen Übergang dar.

## <a name="syntax"></a>Syntax

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Member

### <a name="public-enumerations"></a>Öffentliche Enumerationen

|Name|Beschreibung|
|----------|-----------------|
|[CBaseTransition::TRANSITION_TYPE-Enumeration](#transition_type_enumeration)|Definiert die Übergangstypen, die derzeit von der MFC-Implementierung der Windows Animations-API unterstützt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBaseTransition::CBaseTransition](#cbasetransition)|Erstellt ein Basis-Übergang-Objekt.|
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Der Destruktor. Wird aufgerufen, wenn ein Übergangsobjekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Fügt einen Übergang zu einem Storyboard an.|
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Fügt einen Übergang zu einem Storyboard an.|
|[CBaseTransition::Clear](#clear)|Releases gekapselt IUIAnimationTransition COM-Objekt.|
|[CBaseTransition:: Create](#create)|Erstellt einen Übergang von COM.|
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Gibt starten Keyframe.|
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Gibt einen Zeiger auf Verwandte Variable.|
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Gibt starten Keyframe.|
|[CBaseTransition::GetTransition](#gettransition)|Überladen. Gibt einen Zeiger auf die zugrunde liegende COM-Übergang-Objekt.|
|[CBaseTransition::GetType](#gettype)|Gibt die Übergangstyp an.|
|[CBaseTransition::IsAdded](#isadded)|Erfahren Sie, ob ein Übergang zu einem Storyboard hinzugefügt wurde.|
|[CBaseTransition:: SetKeyframes](#setkeyframes)|Legt fest, für einen Übergang Keyframes.|
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Legt eine Beziehung zwischen der Animationsvariablen und Übergang.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CBaseTransition::m_bAdded](#m_badded)|Gibt an, ob es sich bei ein Übergang zu einem Storyboard hinzugefügt wurde.|
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Speichert einen Zeiger auf den Keyframe, der das Ende des Übergangs angibt.|
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Ein Zeiger auf eine Animationsvariable, die mit dem Übergang in M_transition gespeicherten animiert wird.|
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Speichert einen Zeiger auf den Keyframe, der den Anfang des Übergangs angibt.|
|[CBaseTransition::m_transition](#m_transition)|Ein Zeiger auf IUIAnimationTransition gespeichert. NULL, wenn ein COM-Übergang-Objekt nicht erstellt wurde.|
|[CBaseTransition::m_type](#m_type)|Speichert, den Übergangstyp.|

## <a name="remarks"></a>Hinweise

Diese Klasse kapselt IUIAnimationTransitions-Schnittstelle und dient als Basisklasse für alle Übergänge.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="_dtorcbasetransition"></a>  CBaseTransition:: ~ CBaseTransition

Der Destruktor. Wird aufgerufen, wenn ein Übergangsobjekt zerstört wird.

```
virtual ~CBaseTransition();
```

##  <a name="addtostoryboard"></a>  CBaseTransition::AddToStoryboard

Fügt einen Übergang zu einem Storyboard an.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf storyboard, der der entsprechenden Variablen animiert werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Übergang zu einem Storyboard erfolgreich hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Wendet den Übergang der entsprechenden Variablen im Storyboard an. Wenn dies auf den ersten Übergang, der auf diese Variable in diesem Storyboard angewendet ist, beginnt sich der Übergang zu Beginn des Storyboards. Andernfalls wird der Übergang des Übergangs auf die Variable zuletzt hinzugefügt wurde angefügt.

##  <a name="addtostoryboardatkeyframes"></a>  CBaseTransition::AddToStoryboardAtKeyframes

Fügt einen Übergang zu einem Storyboard an.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf storyboard, der der entsprechenden Variablen animiert werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Übergang zu einem Storyboard erfolgreich hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Wendet den Übergang der entsprechenden Variablen im Storyboard an. Wenn der Startkeyframe angegeben wurde, beginnt der Übergang, bei diesem Keyframe. Wenn der End-Keyframe angegeben wurde, wird der Übergang beginnt am Anfang Keyframe und hält bei der End-Keyframe. Wenn der Übergang mit einem angegebenen Duration-Parameter erstellt wurde, wird diese Dauer mit der Dauer der Zeit zwischen den Start- und Endzeit Keyframes überschrieben. Wenn kein Keyframe angegeben wurde, wird der Übergang des Übergangs auf die Variable zuletzt hinzugefügt wurde angefügt.

##  <a name="cbasetransition"></a>  CBaseTransition::CBaseTransition

Erstellt ein Basis-Übergang-Objekt.

```
CBaseTransition();
```

##  <a name="clear"></a>  CBaseTransition::Clear

Releases gekapselt IUIAnimationTransition COM-Objekt.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Diese Methode sollte von einer abgeleiteten Klasse-Create-Methode aufgerufen werden, um Speicherverluste der IUITransitions Schnittstelle zu vermeiden.

##  <a name="create"></a>  CBaseTransition:: Create

Erstellt einen Übergang von COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf den Übergangsbibliothek, die standard-Übergänge erstellt. Für benutzerdefinierte Übergänge kann NULL sein.

*pFactory*<br/>
Ein Zeiger auf den Übergangsfactory, die benutzerdefinierte Übergänge erstellt. Für standard-Übergänge kann NULL sein.

### <a name="return-value"></a>Rückgabewert

True, wenn ein von COM-Übergangsobjekt wurde erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Dies ist eine rein virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben werden muss. Sie wird durch das Framework instanziiert das zugrunde liegende COM-Übergang-Objekt aufgerufen.

##  <a name="getendkeyframe"></a>  CBaseTransition::GetEndKeyframe

Gibt starten Keyframe.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf ein Keyframe oder NULL, wenn Sie ein Übergang zwischen Keyframes nicht eingefügt werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode kann verwendet werden, auf einem Keyframe-Objekt zuzugreifen, die zuvor von SetKeyframes festgelegt wurde. Durch den Top-Level-Code wird aufgerufen, wenn Übergänge Storyboard hinzugefügt werden.

##  <a name="getrelatedvariable"></a>  CBaseTransition::GetRelatedVariable

Gibt einen Zeiger auf Verwandte Variable.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf Animationsvariablen oder NULL, wenn eine Animationsvariable von SetRelatedVariable nicht festgelegt wurde.

### <a name="remarks"></a>Hinweise

Dies ist ein Accessor für die zugehörige Animationsvariable.

##  <a name="getstartkeyframe"></a>  CBaseTransition::GetStartKeyframe

Gibt starten Keyframe.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf einen Keyframe oder NULL, wenn ein Übergang nicht nach einem Keyframe gestartet werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode kann verwendet werden, auf einem Keyframe-Objekt zuzugreifen, die zuvor von SetKeyframes festgelegt wurde. Durch den Top-Level-Code wird aufgerufen, wenn Übergänge Storyboard hinzugefügt werden.

##  <a name="gettransition"></a>  CBaseTransition::GetTransition

Gibt einen Zeiger auf die zugrunde liegende COM-Übergang-Objekt.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf den Übergangsbibliothek, die standard-Übergänge erstellt. Für benutzerdefinierte Übergänge kann NULL sein.

*pFactory*<br/>
Ein Zeiger auf den Übergangsfactory, die benutzerdefinierte Übergänge erstellt. Für standard-Übergänge kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf IUIAnimationTransition oder NULL, wenn die zugrunde liegende Übergang kann nicht erstellt werden.

### <a name="remarks"></a>Hinweise

Diese Methode gibt einen Zeiger auf die zugrunde liegende COM-Übergang-Objekt, und erstellt diese bei Bedarf.

##  <a name="gettype"></a>  CBaseTransition::GetType

Gibt die Übergangstyp an.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Rückgabewert

Einer der TRANSITION_TYPE-Enumerationswerte.

### <a name="remarks"></a>Hinweise

Diese Methode kann zum Identifizieren eines Übergangs-Objekts verwendet werden, um anhand des Typs. Der Typ wird in einem Konstruktor in einer abgeleiteten Klasse festgelegt.

##  <a name="isadded"></a>  CBaseTransition::IsAdded

Erfahren Sie, ob ein Übergang zu einem Storyboard hinzugefügt wurde.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn ein Übergang zu einem Storyboard ist, andernfalls "false" hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Dieses Flag wird intern festgelegt, wenn der Code auf oberster Ebene storyboard Übergänge hinzufügt.

##  <a name="m_badded"></a>  CBaseTransition::m_bAdded

Gibt an, ob es sich bei ein Übergang zu einem Storyboard hinzugefügt wurde.

```
BOOL m_bAdded;
```

##  <a name="m_pendkeyframe"></a>  CBaseTransition::m_pEndKeyframe

Speichert einen Zeiger auf den Keyframe, der das Ende des Übergangs angibt.

```
CBaseKeyFrame* m_pEndKeyframe;
```

##  <a name="m_prelatedvariable"></a>  CBaseTransition::m_pRelatedVariable

Ein Zeiger auf eine Animationsvariable, die mit dem Übergang in M_transition gespeicherten animiert wird.

```
CAnimationVariable* m_pRelatedVariable;
```

##  <a name="m_pstartkeyframe"></a>  CBaseTransition::m_pStartKeyframe

Speichert einen Zeiger auf den Keyframe, der den Anfang des Übergangs angibt.

```
CBaseKeyFrame* m_pStartKeyframe;
```

##  <a name="m_transition"></a>  CBaseTransition::m_transition

Ein Zeiger auf IUIAnimationTransition gespeichert. NULL, wenn ein COM-Übergang-Objekt nicht erstellt wurde.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

##  <a name="m_type"></a>  CBaseTransition::m_type

Speichert, den Übergangstyp.

```
TRANSITION_TYPE m_type;
```

##  <a name="setkeyframes"></a>  CBaseTransition:: SetKeyframes

Legt fest, für einen Übergang Keyframes.

```
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Parameter

*pStart*<br/>
Ein Keyframe, der den Anfang des Übergangs angibt.

*Ausgesetzt*<br/>
Ein Keyframe, der das Ende des Übergangs angibt.

### <a name="remarks"></a>Hinweise

Diese Methode teilt die Umstellung auf nach der angegebenen Keyframe starten und, optional, wenn ausgesetzt nicht NULL ist, am Ende vor der angegebenen Keyframe. Wenn der Übergang mit einem angegebenen Duration-Parameter erstellt wurde, wird diese Dauer mit der Dauer der Zeit zwischen den Start- und Endzeit Keyframes überschrieben.

##  <a name="setrelatedvariable"></a>  CBaseTransition::SetRelatedVariable

Legt eine Beziehung zwischen der Animationsvariablen und Übergang.

```
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parameter

*pVariable*<br/>
Ein Zeiger auf die zugehörige Animationsvariable.

### <a name="remarks"></a>Hinweise

Legt eine Beziehung zwischen der Animationsvariablen und Übergang. Ein Übergang kann nur auf eine Variable angewendet werden.

##  <a name="transition_type_enumeration"></a>  CBaseTransition::TRANSITION_TYPE-Enumeration

Definiert die Übergangstypen, die derzeit von der MFC-Implementierung der Windows Animations-API unterstützt.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Hinweise

Ein Übergangstyp ist im Konstruktor der spezifischen Übergang festgelegt. CSinusoidalTransitionFromRange legt beispielsweise den Typ auf SINUSOIDAL_FROM_RANGE fest.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
