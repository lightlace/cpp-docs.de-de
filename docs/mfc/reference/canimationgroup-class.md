---
title: CAnimationGroup-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 9be0a5b76f91ddf4dc3d1c4ff2816b7ffd5a1986
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304378"
---
# <a name="canimationgroup-class"></a>CAnimationGroup-Klasse

Implementiert eine Animationsgruppe, die ein Animationsstoryboard, Animationsobjekte und Übergänge zum Definieren einer Animation kombiniert.

## <a name="syntax"></a>Syntax

```
class CAnimationGroup;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Erstellt eine Animation aus.|
|[CAnimationGroup::~CAnimationGroup](#canimationgroup__~canimationgroup)|Der Destruktor. Wird aufgerufen, wenn eine Animation aus zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationGroup::Animate](#animate)|Führt eine Animation eine Gruppe.|
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Übergänge und Animationsobjekte gilt.|
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Sucht nach einer Animationsobjekt, das die angegebene Animation-Variable enthält.|
|[CAnimationGroup::GetGroupID](#getgroupid)|Gibt die Gruppen-ID zurück.|
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Entfernt und löscht optional alle Keyframes, die eine Animationsgruppe angehören.|
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.|
|[CAnimationGroup::Schedule](#schedule)|Plant eine Animation zum angegebenen Zeitpunkt.|
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Weist, dass alle Animationsobjekte, die zum Gruppieren automatisch gehören Übergänge zu zerstören.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Ein Hilfsprogramm, das ein Storyboard Keyframes hinzufügt.|
|[CAnimationGroup::AddTransitions](#addtransitions)|Ein Hilfsprogramm, das ein Storyboard Übergänge hinzufügt.|
|[CAnimationGroup::CreateTransitions](#createtransitions)|Ein Hilfsprogramm, die COM-Übergang-Objekte erstellt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieses Element auf "true" ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie zum manuellen Entfernen der Übergänge.|
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Gibt an, wie Animationsobjekte zerstört werden sollen. Wenn dieser Parameter TRUE ist, werden Animationsobjekte automatisch zerstört werden, wenn die Gruppe gelöscht wird. Andernfalls müssen manuell die Animationsobjekte zerstört werden. Der Standardwert ist "false". Legen Sie diesen Wert auf "true", nur dann, wenn alle Animationsobjekte, die Gruppe angehören, mit dem neuen Operator dynamisch zugewiesen werden.|
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert TRUE ist, werden alle Keyframes entfernt und zerstört; Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist "true".|
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Enthält eine Liste von Animationsobjekten.|
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Enthält eine Liste von Keyframes.|
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Verweist auf Animationsstoryboard. This-Zeiger ist erst nach Aufruf Animate gültig.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Ein eindeutiger Bezeichner der Gruppe "Animation".|
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den Animationscontroller, zu der dieser Gruppe gehört.|

## <a name="remarks"></a>Hinweise

Animationsgruppen werden automatisch von Animationscontroller (CAnimationController) erstellt, beim Hinzufügen von Animationsobjekten, die AddAnimationObject. Eine Animationsgruppe wird von GroupID, identifiziert, die in der Regel als Parameter verwendet wird, um Animationsgruppen zu manipulieren. Die Gruppen-ID stammt aus dem ersten Animationsobjekt, das eine neue Animationsgruppe hinzugefügt wird. Ein gekapselten Animationsstoryboard wird erstellt, nachdem Sie CAnimationController:: AnimateGroup aufrufen und über die öffentlichen Member M_pStoryboard zugegriffen werden können.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CAnimationGroup`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="_dtorcanimationgroup"></a>  CAnimationGroup:: ~ CAnimationGroup

Der Destruktor. Wird aufgerufen, wenn eine Animation aus zerstört wird.

```
~CAnimationGroup();
```

##  <a name="addkeyframes"></a>  CAnimationGroup::AddKeyframes

Ein Hilfsprogramm, das ein Storyboard Keyframes hinzufügt.

```
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard COM-Objekt.

*bAddDeep*<br/>
Gibt an, ob diese Methode die Storyboardkeyframes hinzufügen sollten, die für andere Keyframes abhängig sind.

##  <a name="addtransitions"></a>  CAnimationGroup::AddTransitions

Ein Hilfsprogramm, das ein Storyboard Übergänge hinzufügt.

```
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard COM-Objekt.

*bDependOnKeyframes*

##  <a name="animate"></a>  CAnimationGroup::Animate

Führt eine Animation eine Gruppe.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Parameter

*pManager*<br/>
*pTimer*
*bScheduleNow*

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode erstellt ein internes Storyboard, erstellt und gilt Übergänge und plant eine Animation, wenn bScheduleNow "true" ist. Wenn bScheduleNow "false" ist, müssen Sie Zeitplan zum Starten der Animation zum angegebenen Zeitpunkt aufzurufen.

##  <a name="applytransitions"></a>  CAnimationGroup::ApplyTransitions

Übergänge und Animationsobjekte gilt.

```
void ApplyTransitions();
```

### <a name="remarks"></a>Hinweise

Diese Methode bestätigt im Debugmodus, wenn das Storyboard nicht erstellt wurde. Alle Übergänge zuerst erstellt und dann fügt "static" Keyframes (Keyframes, die Offsets abhängig), fügt Übergänge, die nicht für Keyframes abhängen, fügt Keyframes je nach Übergänge und andere Keyframes und zu guter Letzt fügt Übergänge, die abhängig von keyframes .

##  <a name="canimationgroup"></a>  CAnimationGroup::CAnimationGroup

Erstellt eine Animation aus.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Parameter

*pParentController*<br/>
Ein Zeiger auf den Animationscontroller, der eine Gruppe erstellt.

*nGroupID*<br/>
Gibt die Gruppen-ID an.

##  <a name="createtransitions"></a>  CAnimationGroup::CreateTransitions

Ein Hilfsprogramm, die COM-Übergang-Objekte erstellt.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Rückgabewert

"True" ist die Methode erfolgreich ist, andernfalls "false".

##  <a name="findanimationobject"></a>  CAnimationGroup::FindAnimationObject

Sucht nach einer Animationsobjekt, das die angegebene Animation-Variable enthält.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parameter

*pVariable*<br/>
Ein Zeiger auf eine Animationsvariable.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf "Animation"-Objekts oder NULL, wenn die Animationsobjekt nicht gefunden wird.

##  <a name="getgroupid"></a>  CAnimationGroup::GetGroupID

Gibt die Gruppen-ID zurück.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Gruppen-ID ein.

##  <a name="m_bautocleartransitions"></a>  CAnimationGroup::m_bAutoclearTransitions

Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieses Element auf "true" ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie zum manuellen Entfernen der Übergänge.

```
BOOL m_bAutoclearTransitions;
```

##  <a name="m_bautodestroyanimationobjects"></a>  CAnimationGroup:: M_bautodestroyanimationobjects

Gibt an, wie Animationsobjekte zerstört werden sollen. Wenn dieser Parameter TRUE ist, werden Animationsobjekte automatisch zerstört werden, wenn die Gruppe gelöscht wird. Andernfalls müssen manuell die Animationsobjekte zerstört werden. Der Standardwert ist "false". Legen Sie diesen Wert auf "true", nur dann, wenn alle Animationsobjekte, die Gruppe angehören, mit dem neuen Operator dynamisch zugewiesen werden.

```
BOOL m_bAutodestroyAnimationObjects;
```

##  <a name="m_bautodestroykeyframes"></a>  CAnimationGroup::m_bAutodestroyKeyframes

Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert TRUE ist, werden alle Keyframes entfernt und zerstört; Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist "true".

```
BOOL m_bAutodestroyKeyframes;
```

##  <a name="m_lstanimationobjects"></a>  CAnimationGroup::m_lstAnimationObjects

Enthält eine Liste von Animationsobjekten.

```
CObList m_lstAnimationObjects;
```

##  <a name="m_lstkeyframes"></a>  CAnimationGroup::m_lstKeyFrames

Enthält eine Liste von Keyframes.

```
CObList m_lstKeyFrames;
```

##  <a name="m_ngroupid"></a>  CAnimationGroup::m_nGroupID

Ein eindeutiger Bezeichner der Gruppe "Animation".

```
UINT32 m_nGroupID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationGroup::m_pParentController

Ein Zeiger auf den Animationscontroller, zu der dieser Gruppe gehört.

```
CAnimationController* m_pParentController;
```

##  <a name="m_pstoryboard"></a>  CAnimationGroup::m_pStoryboard

Verweist auf Animationsstoryboard. This-Zeiger ist erst nach Aufruf Animate gültig.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

##  <a name="removekeyframes"></a>  CAnimationGroup::RemoveKeyframes

Entfernt und löscht optional alle Keyframes, die eine Animationsgruppe angehören.

```
void RemoveKeyframes();
```

### <a name="remarks"></a>Hinweise

Wenn der M_bAutodestroyKeyframes-Member "true" ist, und klicken Sie dann die Keyframes werden entfernt und zerstört, andernfalls Keyframes aus der internen Liste von Keyframes nur entfernt werden.

##  <a name="removetransitions"></a>  CAnimationGroup::RemoveTransitions

Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.

```
void RemoveTransitions();
```

### <a name="remarks"></a>Hinweise

Wenn das M_bAutoclearTransitions-Flag auf "true" festgelegt ist, wird diese Methode durchläuft alle Animationsobjekte, die der Gruppe angehören, und ruft CAnimationObject::ClearTransitions(false) auf.

##  <a name="schedule"></a>  CAnimationGroup::Schedule

Plant eine Animation zum angegebenen Zeitpunkt.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Parameter

*pTimer*<br/>
Ein Zeiger auf die Animation Timer.

*time*<br/>
Gibt die Zeit, um die Animation zu planen.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. "False" hat, wenn die Methode fehlschlägt oder wenn animieren nicht mit bScheduleNow auf "false" festgelegt aufgerufen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um eine Animation zum angegebenen Zeitpunkt zu planen. Sie müssen animieren mit auf "false" Festlegen der ersten bScheduleNow aufrufen.

##  <a name="setautodestroytransitions"></a>  CAnimationGroup::SetAutodestroyTransitions

Weist, dass alle Animationsobjekte, die zum Gruppieren automatisch gehören Übergänge zu zerstören.

```
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*bAutoDestroy*<br/>
Gibt an, wie Übergänge zu zerstören.

### <a name="remarks"></a>Hinweise

Legen Sie diesen Wert auf "false" nur dann, wenn Sie geht auf dem Stapel zuordnen. Der Standardwert ist "true", es wird daher dringend empfohlen, Übergangsobjekte, die mit dem Operator new zuzuweisen.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
