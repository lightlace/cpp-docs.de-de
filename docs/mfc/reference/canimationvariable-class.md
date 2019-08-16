---
title: CAnimationVariable-Klasse
ms.date: 03/27/2019
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: b6767ed42d66aff467ef36bd2a7b5234ad181ced
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507545"
---
# <a name="canimationvariable-class"></a>CAnimationVariable-Klasse

Stellt eine Animationsvariable dar.

## <a name="syntax"></a>Syntax

```
class CAnimationVariable;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Erstellt ein Animations Variablen Objekt.|
|[Canimationvariable:: ~ canimationvariable](#_dtorcanimationvariable)|Der Destruktor. Wird aufgerufen, wenn ein canimationvariable-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariable::AddTransition](#addtransition)|Fügt einen Übergang hinzu.|
|[Canimationvariable:: applytransitions](#applytransitions)|Fügt Übergänge von der internen Liste in Storyboard hinzu.|
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Löscht Übergänge.|
|[CAnimationVariable::Create](#create)|Erstellt das zugrunde liegende COM-Objekt der Animations Variablen.|
|[CAnimationVariable::CreateTransitions](#createtransitions)|Erstellt alle Übergänge, die auf diese Animations Variable angewendet werden sollen.|
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Aktiviert oder deaktiviert das integervaluechanged-Ereignis.|
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Aktiviert oder deaktiviert das ValueChanged-Ereignis.|
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Gibt den Standardwert zurück.|
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Gibt das übergeordnete Animations Objekt zurück.|
|[CAnimationVariable::GetValue](#getvalue)|Überladen. Gibt den aktuellen Wert der Animations Variablen zurück.|
|[CAnimationVariable::GetVariable](#getvariable)|Gibt einen Zeiger auf das iuianimationvariable com-Objekt zurück.|
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest und gibt das iuianimationvariable com-Objekt frei.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Legt die Beziehung zwischen einer Animations Variablen und einem Animations Objekt fest.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob Verwandte Übergangs Objekte gelöscht werden sollen.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Gibt den Standardwert an, der an iuianimationvariable weitergegeben wird.|
|[Canimationvariable:: m_lstTransitions](#m_lsttransitions)|Enthält eine Liste von Übergängen, die diese Animations Variable animieren.|
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Ein Zeiger auf ein Animations Objekt, das diese Animations Variable kapselt.|
|[CAnimationVariable::m_variable](#m_variable)|Speichert einen Zeiger auf das iuianimationvariable com-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde, oder, wenn die Erstellung fehlgeschlagen ist.|

## <a name="remarks"></a>Hinweise

Die canimationvariable-Klasse kapselt das iuianimationvariable com-Objekt. Sie enthält auch eine Liste der Übergänge, die auf die Animations Variable in einem Storyboard angewendet werden sollen. Canimationvariable-Objekte werden in Animations Objekte eingebettet, die in einer Anwendung einen animierten Wert, Punkt, Größe, Farbe und Rechteck darstellen können.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CAnimationVariable`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="_dtorcanimationvariable"></a>Canimationvariable:: ~ canimationvariable

Der Destruktor. Wird aufgerufen, wenn ein canimationvariable-Objekt zerstört wird.

```
virtual ~CAnimationVariable();
```

##  <a name="addtransition"></a>Canimationvariable:: addtransition

Fügt einen Übergang hinzu.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parameter

*pTransition*<br/>
Ein Zeiger auf einen Übergang, der hinzugefügt werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, um der internen Liste der Übergänge, die auf die Animations Variable angewendet werden sollen, einen Übergang hinzuzufügen. Diese Liste sollte gelöscht werden, wenn eine Animation geplant wurde.

##  <a name="applytransitions"></a>Canimationvariable:: applytransitions

Fügt Übergänge von der internen Liste in Storyboard hinzu.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parameter

*pController*<br/>
Ein Zeiger auf den übergeordneten Animations Controller.

*pstoryboard*<br/>
Ein Zeiger auf das Storyboard.

*bDependOnKeyframes*<br/>
TRUE, wenn diese Methode Übergänge hinzufügen soll, die von Keyframes abhängen.

### <a name="remarks"></a>Hinweise

Diese Methode fügt Übergänge von der internen Liste in Storyboard hinzu. Sie wird aus dem Code der obersten Ebene mehrmals aufgerufen, um Übergänge hinzuzufügen, die nicht von Keyframes abhängen, und Übergänge hinzuzufügen, die von Keyframes abhängen. Wenn das zugrunde liegende COM-Objekt der Animations Variablen nicht erstellt wurde, erstellt diese Methode dieses in dieser Phase.

##  <a name="canimationvariable"></a>Canimationvariable:: canimationvariable

Erstellt ein Animations Variablen Objekt.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Parameter

*dblDefaultValue*<br/>
Gibt den Standardwert an.

### <a name="remarks"></a>Hinweise

Erstellt ein Animations Variablen Objekt und legt seinen Standardwert fest. Ein Standardwert wird verwendet, wenn eine Variable nicht animiert wird oder nicht animiert werden kann.

##  <a name="cleartransitions"></a>Canimationvariable:: cleartransitions

Löscht Übergänge.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parameter

*bAutodestroy*<br/>
Gibt an, ob diese Methode Übergangs Objekte löschen soll.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt alle Übergänge aus der internen Liste der Übergänge. Wenn "Bauto Destroy" den Wert "true" hat oder m_bAutodestroyTransitions true ist, werden Übergänge gelöscht. Andernfalls sollte der Aufrufer die Zuordnungen der Übergangs Objekte aufgehoben.

##  <a name="create"></a>Canimationvariable:: Create

Erstellt das zugrunde liegende COM-Objekt der Animations Variablen.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Parameter

*pManager*<br/>
Ein Zeiger auf den Animations-Manager.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Animations Variable erfolgreich erstellt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt das zugrunde liegende COM-Objekt der Animations Variablen und legt seinen Standardwert fest.

##  <a name="createtransitions"></a>Canimationvariable:: "foratetransitions"

Erstellt alle Übergänge, die auf diese Animations Variable angewendet werden sollen.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf eine [iuianimationtransitionlibrary-Schnittstelle](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), die eine Bibliothek von Standard Übergängen definiert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Übergänge erfolgreich erstellt wurden. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn Sie Übergänge erstellen muss, die der internen Liste von Übergängen der Variablen hinzugefügt wurden.

##  <a name="enableintegervaluechangedevent"></a>Canimationvariable:: enableintegervaluechangedebug

Aktiviert oder deaktiviert das integervaluechanged-Ereignis.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*pController*<br/>
Ein Zeiger auf den übergeordneten Controller.

*bEnable*<br/>
TRUE: Ereignis aktivieren, false-Ereignis deaktivieren.

### <a name="remarks"></a>Hinweise

Wenn das ValueChanged-Ereignis aktiviert ist, ruft das Framework die virtuelle Methode canimationcontroller:: onanimationintegervaluechanged auf. Sie müssen ihn in einer Klasse überschreiben, die von canimationcontroller abgeleitet ist, um dieses Ereignis zu verarbeiten. Diese Methode wird jedes Mal aufgerufen, wenn der ganzzahlige Wert der Animations Variablen geändert wird.

##  <a name="enablevaluechangedevent"></a>Canimationvariable:: enablevaluechangedebug

Aktiviert oder deaktiviert das ValueChanged-Ereignis.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*pController*<br/>
Ein Zeiger auf den übergeordneten Controller.

*bEnable*<br/>
TRUE: Ereignis aktivieren, false-Ereignis deaktivieren.

### <a name="remarks"></a>Hinweise

Wenn das ValueChanged-Ereignis aktiviert ist, ruft das Framework die virtuelle Methode canimationcontroller:: onanimationvaluechanged auf. Sie müssen ihn in einer Klasse überschreiben, die von canimationcontroller abgeleitet ist, um dieses Ereignis zu verarbeiten. Diese Methode wird jedes Mal aufgerufen, wenn der Wert der Animations Variablen geändert wird.

##  <a name="getdefaultvalue"></a>Canimationvariable:: getDefaultValue

Gibt den Standardwert zurück.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Rückgabewert

Der Standardwert.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um den Standardwert der Animations Variablen abzurufen. Der Standardwert kann im Konstruktor oder mit der setDefaultValue-Methode festgelegt werden.

##  <a name="getparentanimationobject"></a>Canimationvariable:: getanentanimationobject

Gibt das übergeordnete Animations Objekt zurück.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das übergeordnete Animations Objekt, wenn die Beziehung hergestellt wurde, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Methode kann aufgerufen werden, um einen Zeiger auf ein übergeordnetes Animations Objekt (einen Container) abzurufen.

##  <a name="getvalue"></a>Canimationvariable:: GetValue

Gibt den aktuellen Wert der Animations Variablen zurück.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parameter

*dblValue*<br/>
Der aktuelle Wert der Animations Variablen.

*nWert*<br/>
Der aktuelle Wert der Animations Variablen.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der Wert erfolgreich abgerufen wurde oder die zugrunde liegende Animations Variable nicht erstellt wurde. Andernfalls HRESULT-Fehlercode.

### <a name="remarks"></a>Hinweise

Diese Methode kann aufgerufen werden, um den aktuellen Wert der Animations Variablen abzurufen. Wenn das zugrunde liegende COM-Objekt nicht erstellt wurde, enthält dblvalue einen Standardwert, wenn die Funktion zurückgibt.

##  <a name="getvariable"></a>Canimationvariable:: GetVariable

Gibt einen Zeiger auf das iuianimationvariable com-Objekt zurück.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf das iuianimationvariable com-Objekt oder NULL, wenn keine Animations Variable erstellt wurde oder nicht erstellt werden kann.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um auf das zugrunde liegende iuianimationvariable com-Objekt zuzugreifen und seine Methoden bei Bedarf direkt aufzurufen.

##  <a name="m_bautodestroytransitions"></a>Canimationvariable:: m_bAutodestroyTransitions

Gibt an, ob Verwandte Übergangs Objekte gelöscht werden sollen.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Hinweise

Legen Sie diesen Wert auf "true" fest, um das Löschen von Übergangs Objekten zu erzwingen, wenn diese aus der internen Liste der Übergänge entfernt werden. Wenn dieser Wert false ist, sollten die Übergänge durch Aufrufen der Anwendung gelöscht werden. Die Liste der Übergänge wird immer gelöscht, nachdem eine Animation geplant wurde. Der Standardwert ist false.

##  <a name="m_dbldefaultvalue"></a>Canimationvariable:: m_dblDefaultValue

Gibt den Standardwert an, der an iuianimationvariable weitergegeben wird.

```
DOUBLE m_dblDefaultValue;
```

##  <a name="m_lsttransitions"></a>Canimationvariable:: m_lstTransitions

Enthält eine Liste von Übergängen, die diese Animations Variable animieren.

```
CObList m_lstTransitions;
```

##  <a name="m_pparentobject"></a>Canimationvariable:: m_pParentObject

Ein Zeiger auf ein Animations Objekt, das diese Animations Variable kapselt.

```
CAnimationBaseObject* m_pParentObject;
```

##  <a name="m_variable"></a>Canimationvariable:: m_variable

Speichert einen Zeiger auf das iuianimationvariable com-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde, oder, wenn die Erstellung fehlgeschlagen ist.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

##  <a name="setdefaultvalue"></a>Canimationvariable:: setDefaultValue

Legt den Standardwert fest und gibt das iuianimationvariable com-Objekt frei.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parameter

*dblDefaultValue*<br/>
Gibt den neuen Standardwert an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um den Standardwert zurückzusetzen. Diese Methode gibt das interne iuianimationvariable com-Objekt frei, sodass das zugrunde liegende COM-Objekt den neuen Standardwert erhält, wenn die Animations Variable neu erstellt wird. Der Standardwert wird von GetValue zurückgegeben, wenn das COM-Objekt, das die Animations Variable darstellt, nicht erstellt wurde oder wenn die Variable nicht animiert wurde.

##  <a name="setparentanimationobject"></a>Canimationvariable:: setParser-animationobject

Legt die Beziehung zwischen einer Animations Variablen und einem Animations Objekt fest.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Parameter

*pParentObject*<br/>
Ein Zeiger auf ein Animations Objekt, das diese Variable enthält.

### <a name="remarks"></a>Hinweise

Diese Methode wird intern aufgerufen, um eine 1:1-Beziehung zwischen einer Animations Variablen und einem Animations Objekt herzustellen, das Sie kapselt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
