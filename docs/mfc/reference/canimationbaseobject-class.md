---
title: CAnimationBaseObject-Klasse
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: e9c5ed98d654eb37be7ab8523d44c9da6eecd9c7
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565883"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject-Klasse

Die Basisklasse für alle Animationsobjekte.

## <a name="syntax"></a>Syntax

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Überladen. Erstellt eine Animationsobjekt.|
|[CAnimationBaseObject::~CAnimationBaseObject](#_dtorcanimationbaseobject)|Der Destruktor. Wird aufgerufen, wenn ein Animationsobjekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Fügt Übergänge mit gekapselte Animationsvariable Storyboard hinzu.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Entfernt alle zugehörigen Übergänge.|
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Bestimmt, ob ein Animationsobjekt eine bestimmte Animationen-Variable enthält.|
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Erstellt eine Animationsobjekt zugeordneten Übergänge.|
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Trennt ein Animationsobjekt von übergeordneten Animationscontroller an.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Legt fest, um Ereignishandler ganzzahligen Wert geändert.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Legt fest, um Ereignishandler Wert geändert.|
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Erfahren Sie, ob verwandter Übergang werden automatisch zerstört.|
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Gibt aktuelle Gruppen-ID.|
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Gibt aktuelle Objekt-ID zurück.|
|[CAnimationBaseObject::GetUserData](#getuserdata)|Gibt den benutzerdefinierten Daten.|
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Legt ein Flag Übergänge automatisch zerstört.|
|[CAnimationBaseObject::SetID](#setid)|Legt neue IDs.|
|[CAnimationBaseObject::SetUserData](#setuserdata)|Legt den benutzerdefinierten Daten.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Werden Verweise auf enthaltene Animationsvariablen erfasst.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Stellt die Beziehung zwischen Animationsvariablen, die innerhalb eines Animationsobjekts und ihrem Container her.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob die zugehörigen Übergänge automatisch zerstört werden soll.|
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Speichert den benutzerdefinierten Daten.|
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Gibt an, die Gruppen-ID des Animationsobjekts.|
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Gibt die Objekt-ID des Animationsobjekts an.|
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den übergeordneten Animationscontroller.|

## <a name="remarks"></a>Hinweise

Diese Klasse implementiert die grundlegende Methoden für alle Animationsobjekte. Ein Animationsobjekt kann ein Wert, der Punkt, der Größe, Rechteck oder darstellen Farbe in eine Anwendung als auch eine benutzerdefinierte Entität. Animationsobjekte werden in Animationsgruppen gespeichert (Siehe CAnimationGroup). Jede Gruppe getrennt animiert werden kann und analog des Storyboards behandelt werden kann. Ein Animationsobjekt kapselt einen oder mehrere Animationsvariablen (Siehe CAnimationVariable), abhängig von der logischen Darstellung. CAnimationRect enthält z. B. vier Animationsvariablen - eine Variable für jede Seite des Rechtecks. Jede Animation-Objektklasse stellt überladene AddTransition-Methode, die gekapselten Animationsvariablen Übergänge zuweisen verwendet werden soll. Ein Animationsobjekt kann durch die Objekt-ID (optional) identifiziert werden und nach Gruppen-ID. Eine Gruppen-ID ist erforderlich, um ein Animationsobjekt zur richtigen Gruppe zu platzieren, aber wenn eine Gruppen-ID nicht angegeben ist, wird ein Objekt in der Standardgruppe mit der ID 0 platziert. Wenn Sie SetID mit verschiedenen GroupID aufrufen, wird ein Animationsobjekt in eine andere Gruppe verschoben werden (eine neue Gruppe wird bei Bedarf erstellt).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject

Der Destruktor. Wird aufgerufen, wenn ein Animationsobjekt zerstört wird.

```
virtual ~CAnimationBaseObject();
```

##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions

Fügt Übergänge mit gekapselte Animationsvariable Storyboard hinzu.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard.

*bDependOnKeyframes*<br/>
Bei "FALSE" fügt diese Methode nur die Übergänge, die nicht für Keyframes abhängen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Übergänge erfolgreich hinzugefügt wurden.

### <a name="remarks"></a>Hinweise

Fügt die zugehörigen Übergänge, die, die mit AddTransition (überladene Methoden in abgeleiteten Klassen), um das storyboard hinzugefügt wurden.

##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject

Erstellt eine Animationsobjekt.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Benutzerdefinierte Daten, die "Animation"-Objekts zugeordnet und später zur Laufzeit abgerufen werden können.

### <a name="remarks"></a>Hinweise

Erstellt eine Animationsobjekte aus, und weist standardmäßig mit der Objekt-ID (0) und Gruppen-ID (0).

##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions

Entfernt alle zugehörigen Übergänge.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parameter

*bAutodestroy*<br/>
Gibt an, ob Übergangsobjekte automatisch zerstört, oder entfernen Sie diese einfach aus der verknüpften Liste.

### <a name="remarks"></a>Hinweise

Entfernt alle zugehörigen Übergänge und zerstört, wenn bAutodestroy oder M_bAutodestroyTransitions-Flag auf "true" ist. Übergänge sollte automatisch zerstört werden, nur dann, wenn sie nicht auf dem Stapel zugeordnet sind. Wenn die oben genannten Flags auf "false" sind, werden die Übergänge nur aus der internen Liste der zugehörigen Übergänge entfernt.

##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable

Bestimmt, ob ein Animationsobjekt eine bestimmte Animationen-Variable enthält.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parameter

*pVariable*<br/>
Ein Zeiger auf eine Animationsvariable.

### <a name="return-value"></a>Rückgabewert

True, wenn die Animationsvariable in der "Animation"-Objekts enthalten ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode kann verwendet werden, um zu bestimmen, ob eine Animationsvariable von pVariable angegebene eines Animationsobjekts enthalten ist. Ein Animationsobjekt, abhängig von der Art, kann es sich um mehrere Animationsvariablen enthalten. CAnimationColor enthält beispielsweise drei Variablen, eine für jede Farbkomponente (Rot, Grün und Blau). Wenn ein Wert der Animationsvariablen geändert hat, sendet Windows Animations-API ValueChanged-Ereignis oder IntegerValueChanged Ereignisse (sofern aktiviert), und der Parameter für dieses Ereignis ist ein Zeiger auf IUIAnimationVariable Animationsvariablen-Schnittstelle. Diese Methode kann einen Zeiger auf die Animation von einem Zeiger auf die darin enthaltenen COM-Objekte abrufen.

##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions

Erstellt eine Animationsobjekt zugeordneten Übergänge.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Rückgabewert

True, wenn Übergänge erfolgreich erstellt wurden. andernfalls "false".

### <a name="remarks"></a>Hinweise

Durchläuft eine Liste der Animationsvariablen, die in einem abgeleiteten Animationsobjekt gekapselt sind, und erstellt Übergänge, die jede Animationsvariablen zugeordnet.

##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController

Trennt ein Animationsobjekt von übergeordneten Animationscontroller an.

```
void DetachFromController();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird intern verwendet.

##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject

Legt fest, um Ereignishandler ganzzahligen Wert geändert.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*pController*<br/>
Ein Zeiger auf einen übergeordneten Controller.

*bEnable*<br/>
Gibt an, ob aktivieren oder Deaktivieren der ganzzahligen Wert ein Änderungsereignis.

### <a name="remarks"></a>Hinweise

Wenn der ganzzahligen Wert geändert-Ereignishandler aktiviert ist, können Sie dieses Ereignis in CAnimationController:: OnAnimationIntegerValueChanged-Methode, behandeln, die in einer CAnimationController-abgeleiteten Klasse überschrieben werden sollte. Diese Methode wird aufgerufen, jedes Mal, wenn die Animation Integer-Wert geändert wurde.

##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent

Legt fest, um Ereignishandler Wert geändert.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*pController*<br/>
Ein Zeiger auf einen übergeordneten Controller.

*bEnable*<br/>
Gibt an, ob aktivieren oder Deaktivieren der ValueChanged-Ereignis.

### <a name="remarks"></a>Hinweise

Wenn der Wert geändert Ereignishandler aktiviert ist, können Sie dieses Ereignis in CAnimationController:: OnAnimationValueChanged-Methode, behandeln, die in einer CAnimationController-abgeleiteten Klasse überschrieben werden sollte. Diese Methode wird aufgerufen, jedes Mal, wenn der Animationswert geändert wurde.

##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject:: GetAnimationVariableList

Werden Verweise auf enthaltene Animationsvariablen erfasst.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>Parameter

*list*<br/>
Eine Liste, die mit Animationsvariablen, die innerhalb eines Animationsobjekts ausgefüllt werden müssen.

### <a name="remarks"></a>Hinweise

Diese rein virtuelle Methode muss in einer abgeleiteten Klasse überschrieben werden. Ein Animationsobjekt, abhängig von der Art, enthält eine oder mehrere Animationsvariablen. CAnimationPoint enthält beispielsweise zwei Variablen für X- und Y-Koordinaten. Die Basisklasse CAnimationBaseObject implementiert einige generischen Methoden, die in der Liste der Animationsvariablen fungieren: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Diese Methoden rufen GetAnimationVariableList auf, die in einer abgeleiteten Klasse mit der tatsächlichen Animationsvariablen in ein bestimmtes Animationsobjekt gefüllt ist, und klicken Sie dann Schleife in der Liste und erforderlichen Aktionen durchführen. Wenn Sie ein benutzerdefiniertes Animationsobjekt erstellen, müssen Sie zum Hinzufügen *Liste* alle Animationsvariablen, die in diesem Objekt enthalten sind.

##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions

Erfahren Sie, ob verwandter Übergang werden automatisch zerstört.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Rückgabewert

Bei "true", werden die zugehörigen Übergänge automatisch zerstört; Wenn "FALSE" sollte Übergangsobjekte Zuordnung aufgehoben werden, von der aufrufenden Anwendung.

### <a name="remarks"></a>Hinweise

Standardmäßig ist dieses Flag "true". Legen Sie dieses Flag nur, wenn Sie die Umstellung auf dem Stapel zugeordnet bzw. Übergänge von der aufrufenden Anwendung aufgehoben werden soll.

##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID

Gibt aktuelle Gruppen-ID.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Gruppen-ID.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Abrufen der Gruppen-ID. Es ist 0, wenn die Gruppen-ID nicht explizit im Konstruktor oder mit SetID festgelegt wurde.

##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID

Gibt aktuelle Objekt-ID zurück.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Objekt-ID.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Abrufen der Objekt-ID. Es ist 0, wenn der Objekt-ID nicht explizit im Konstruktor oder mit SetID festgelegt wurde.

##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData

Gibt den benutzerdefinierten Daten.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert der benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Abrufen der benutzerdefinierten Daten zur Laufzeit auf. Der zurückgegebene Wert ist 0, wenn er im Konstruktor oder mit SetUserData explizit nicht initialisiert wurde.

##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions

Gibt an, ob die zugehörigen Übergänge automatisch zerstört werden soll.

```
BOOL m_bAutodestroyTransitions;
```

##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData

Speichert den benutzerdefinierten Daten.

```
DWORD m_dwUserData;
```

##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID

Gibt an, die Gruppen-ID des Animationsobjekts.

```
UINT32 m_nGroupID;
```

##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID

Gibt die Objekt-ID des Animationsobjekts an.

```
UINT32 m_nObjectID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController

Ein Zeiger auf den übergeordneten Animationscontroller.

```
CAnimationController* m_pParentController;
```

##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions

Legt ein Flag Übergänge automatisch zerstört.

```
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Parameter

*bValue*<br/>
Gibt an, die automatisch zerstört Flag.

### <a name="remarks"></a>Hinweise

Legen Sie dieses Flag nur, wenn Sie mit dem Operator new Übergangsobjekte zugeordnet. Wenn aus irgendeinem Grund Übergangsobjekte auf dem Stapel zugeordnet sind, automatisch zerstört. sollte das Flag "false". Standardmäßig ist dieses Flag "true".

##  <a name="setid"></a>  CAnimationBaseObject:: SetID

Legt neue IDs.

```
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Parameter

*nObjectID*<br/>
Gibt das neue Objekt-ID an

*nGroupID*<br/>
Gibt an, neue Gruppen-ID.

### <a name="remarks"></a>Hinweise

Ermöglicht es Ihnen so ändern Sie die Objekt-ID und die Gruppen-ID. Wenn sich die neuen Gruppen-ID aus der aktuellen-ID unterscheidet, wird ein Animationsobjekt in eine andere Gruppe verschoben (eine neue Gruppe wird, bei Bedarf erstellt werden).

##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects

Stellt die Beziehung zwischen Animationsvariablen, die innerhalb eines Animationsobjekts und ihrem Container her.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Hinweise

Dieses Hilfsprogramm kann verwendet werden, um eine Beziehung zwischen der Animationsvariablen innerhalb eines Animationsobjekts und ihrem Container herzustellen. Es durchläuft Animationsvariablen und einem Gegenzeiger auf ein übergeordnetes Objekt jedes Animationsvariablen Animation. Die tatsächliche Beziehung in CAnimationBaseObject::ApplyTransitions eingerichtet, daher Back Zeiger sind nicht festgelegt, bis Sie CAnimationGroup::Animate aufrufen, in der aktuellen Implementierung. Kennen die Beziehung kann hilfreich sein, wenn Sie die Verarbeitung von Ereignissen und Grund, die eine Animation übergeordneten aus CAnimationVariable-Objekt. Verwenden Sie CAnimationVariable::GetParentAnimationObject.

##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData

Legt den benutzerdefinierten Daten.

```
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Parameter

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein Animationsobjekt eine benutzerdefinierte Daten zuzuordnen. Diese Daten können später von GetUserData zur Laufzeit abgerufen werden.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
