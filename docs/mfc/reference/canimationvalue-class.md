---
title: CAnimationValue-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: 86a2caa8946bcafeabf85687a24b2430ecefe790
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338687"
---
# <a name="canimationvalue-class"></a>CAnimationValue-Klasse

Implementiert die Funktion eines Animationsobjekts, das über einen Wert verfügt.

## <a name="syntax"></a>Syntax

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Überladen. Erstellt ein CAnimationValue-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationValue::AddTransition](#addtransition)|Fügt einen Übergang zu einem Wert angewendet werden.|
|[CAnimationValue::GetValue](#getvalue)|Überladen. Ruft den aktuellen Wert.|
|[CAnimationValue::GetVariable](#getvariable)|Bietet Zugriff auf gekapselte Animationsvariable.|
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselte Animationsvariable in einer Liste an. (Overrides [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationValue::operator DOUBLE](#operator_double)|Stellt die Konvertierung zwischen CAnimationValue und Double-Wert.|
|[CAnimationValue::operator INT32](#operator_int32)|Stellt die Konvertierung zwischen CAnimationValue und INT32.|
|[CAnimationValue::operator=](#operator_eq)|Überladen. CAnimationValue wird einen INT32-Wert zugewiesen.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationValue::m_value](#m_value)|Die gekapselte Animationsvariable, die Animationswert darstellt.|

## <a name="remarks"></a>Hinweise

CAnimationValue-Klasse kapselt ein einzelnes CAnimationVariable-Objekt und kann in Anwendungen einen einzelnen animierten Wert darstellen. Beispielsweise können Sie diese Klasse verwenden, für Winkel des animierten Transparenz (Ausblendeffekt), (zum Drehen von Objekten) oder bei allen anderen Fällen, wenn Sie eine Animation, je nach einem einzelnen animierten Wert erstellen müssen. Um diese Klasse in der Anwendung verwenden zu können, einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie für jeden Übergang AddTransition, auf den Wert angewendet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationValue::AddTransition

Fügt einen Übergang zu einem Wert angewendet werden.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parameter

*pTransition*<br/>
Ein Zeiger auf den Übergangsobjekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Hinzufügen eines Übergangs internen Liste von Übergängen, die auf eine Animationsvariable angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert werden soll. Übergänge werden angewendet (hinzugefügt zu einem Storyboard für einen bestimmten Wert) beim Aufruf CAnimationController:: AnimateGroup.

##  <a name="canimationvalue"></a>  CAnimationValue::CAnimationValue

Erstellt ein CAnimationValue-Objekt.

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*dblDefaultValue*<br/>
Gibt den Standardwert an.

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

CAnimationValue-Objekt mit Eigenschaften erstellt: Standardwert, die Gruppen-ID und Objekt-ID werden auf 0 festgelegt.

##  <a name="getanimationvariablelist"></a>  CAnimationValue::GetAnimationVariableList

Legt die gekapselte Animationsvariable in einer Liste an.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
Wenn die Funktion zurückgibt, enthält es sich um einen Zeiger auf CAnimationVariable, die den animierten Wert darstellt.

##  <a name="getvalue"></a>  CAnimationValue::GetValue

Ruft den aktuellen Wert.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parameter

*dblValue*<br/>
Die Ausgabe. Bei Rückgabe der Funktion enthält es einen aktuellen Wert der Animationsvariablen an.

*nValue*<br/>
Die Ausgabe. Bei Rückgabe der Funktion enthält es einen aktuellen Wert der Animationsvariablen an.

### <a name="return-value"></a>Rückgabewert

True, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen des aktuellen Werts. Diese Implementierung ruft die gekapselte COM-Objekt, und wenn der Aufruf fehlschlägt, gibt diese Methode den Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.

##  <a name="getvariable"></a>  CAnimationValue::GetVariable

Bietet Zugriff auf gekapselte Animationsvariable.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte Animationsvariable.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die gekapselte Animationsvariable zuzugreifen. Von CAnimationVariable erhalten Sie Zugriff auf zugrunde liegende IUIAnimationVariable-Objekt, dessen Zeiger NULL sein kann, wenn der Animationsvariablen nicht erstellt wurde.

##  <a name="m_value"></a>  CAnimationValue::m_value

Die gekapselte Animationsvariable, die Animationswert darstellt.

```
CAnimationVariable m_value;
```

##  <a name="operator_double"></a>  CAnimationValue::operator DOUBLE

Stellt die Konvertierung zwischen CAnimationValue und Double-Wert.

```
operator DOUBLE();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der Animation-Wert.

### <a name="remarks"></a>Hinweise

Stellt die Konvertierung zwischen CAnimationValue und Double-Wert. Diese Methode wird intern "GetValue" aufruft, und nicht auf Fehler überprüfen. Wenn "GetValue" ein Fehler auftritt, wird der zurückgegebene Wert einen Standardwert, der zuvor festgelegten im Konstruktor oder mit SetDefaultValue enthalten.

##  <a name="operator_int32"></a>  CAnimationValue::operator INT32

Stellt die Konvertierung zwischen CAnimationValue und INT32.

```
operator INT32();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der Animation-Wert als ganze Zahl.

### <a name="remarks"></a>Hinweise

Stellt die Konvertierung zwischen CAnimationValue und INT32. Diese Methode wird intern "GetValue" aufruft, und nicht auf Fehler überprüfen. Wenn "GetValue" ein Fehler auftritt, wird der zurückgegebene Wert einen Standardwert, der zuvor festgelegten im Konstruktor oder mit SetDefaultValue enthalten.

##  <a name="operator_eq"></a>  CAnimationValue::operator =

Weist einen doppelten Wert CAnimationValue zu.

```
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Parameter

*dblVal*<br/>
Gibt den Wert, der Wert der Animation zugewiesen werden soll.

*nVal*<br/>
Gibt den Wert, der Wert der Animation zugewiesen werden soll.

### <a name="remarks"></a>Hinweise

Weist einen doppelten Wert CAnimationValue zu. Dieser Wert wird als Standardwert für gekapselte Animationsvariable festgelegt. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

##  <a name="setdefaultvalue"></a>  CAnimationValue::SetDefaultValue

Legt den Standardwert fest.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parameter

*dblDefaultValue*<br/>
Gibt den Standardwert an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um einen Standardwert festzulegen. Ein Standardwert ist auf die Anwendung zurückgegeben, wenn Animation nicht gestartet wurde, bzw. zugrunde liegenden COM-Objekt wurde nicht erstellt. Wenn das zugrunde liegende COM-Objekt, das in den CAnimationVarible gekapselt ist bereits erstellt wurde, wird diese Methode erstellt, aus diesem Grund müssen möglicherweise EnableValueChanged/EnableIntegerValueChanged Methoden erneut aufrufen.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
