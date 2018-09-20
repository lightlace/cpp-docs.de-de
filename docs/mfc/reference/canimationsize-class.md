---
title: CAnimationSize-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 974bf49b4315095a2103c50bfb81cc5e164273d6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433170"
---
# <a name="canimationsize-class"></a>CAnimationSize-Klasse

Implementiert die Funktion eines Größenobjekts, dessen Dimensionen animiert werden können.

## <a name="syntax"></a>Syntax

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|Überladen. Erstellt eine Animation Größe-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationSize::AddTransition](#addtransition)|Fügt die Übergänge für Breite und Höhe hinzu.|
|[CAnimationSize::GetCX](#getcx)|Bietet Zugriff auf CAnimationVariable, die Breite darstellt.|
|[CAnimationSize::GetCY](#getcy)|Bietet Zugriff auf CAnimationVariable, Höhe darstellt.|
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für Breite und Höhe zurück.|
|[CAnimationSize::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationSize::operator CSize](#operator_csize)|Konvertiert einen CAnimationSize in einen CSize an.|
|[CAnimationSize::operator =](#operator_eq)|CAnimationSize SzSrc zugewiesen haben.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|Die gekapselte Animationsvariable, die Breite der Animationsgröße darstellt.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|Die gekapselte Animationsvariable, die Höhe der Animationsgröße darstellt.|

## <a name="remarks"></a>Hinweise

CAnimationSize-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Anwendungen eine Größe dar. Beispielsweise können diese Klasse zum Animieren einer Größe von zwei dimensionale Objekt auf dem Bildschirm (Rechteck, Steuerelement usw.). Um diese Klasse in der Anwendung verwenden zu können, einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf die Breite bzw. Höhe angewendet werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationSize::AddTransition

Fügt die Übergänge für Breite und Höhe hinzu.

```
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Parameter

*pCXTransition*<br/>
Ein Zeiger auf den Übergang für die Breite.

*pCYTransition*<br/>
Ein Zeiger auf den Übergang für Höhe.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Hinzufügen der angegebenen Übergänge der internen Liste von Übergängen, die für Breite und Höhe auf Animationsvariablen angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert werden soll. Übergänge werden angewendet (hinzugefügt zu einem Storyboard für einen bestimmten Wert) beim Aufruf CAnimationController:: AnimateGroup. Wenn Sie keine Übergang auf eine der Dimensionen anwenden möchten, können Sie NULL übergeben.

##  <a name="canimationsize"></a>  CAnimationSize::CAnimationSize

Erstellt eine Animation Größe-Objekt.

```
CAnimationSize();


CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*szDefault*<br/>
Gibt die standardmäßige Größe an.

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

Das Objekt erstellt wird, mit Standardwerten für Breite, Höhe, Objekt-ID und die Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mithilfe SetDefaultValue und SetID später geändert werden.

##  <a name="getanimationvariablelist"></a>  CAnimationSize::GetAnimationVariableList

Legt die gekapselten Animationsvariablen in einer Liste an.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
Wenn die Funktion zurückgibt, enthält Zeiger auf zwei CAnimationVariable-Objekte, die die Breite und Höhe darstellt.

##  <a name="getcx"></a>  CAnimationSize::GetCX

Bietet Zugriff auf CAnimationVariable, die Breite darstellt.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die Breite darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, die Breite darstellt erhalten aufrufen.

##  <a name="getcy"></a>  CAnimationSize::GetCY

Bietet Zugriff auf CAnimationVariable, Höhe darstellt.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, Höhe darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, Höhe darstellt erhalten aufrufen.

##  <a name="getdefaultvalue"></a>  CAnimationSize::GetDefaultValue

Gibt die Standardwerte für Breite und Höhe zurück.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Rückgabewert

Ein CSize-Objekt, das Standardwerte enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von Standardwert, der zuvor vom Konstruktor oder SetDefaultValue festgelegt wurde.

##  <a name="getvalue"></a>  CAnimationSize::GetValue

Gibt den aktuellen Wert zurück.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Parameter

*szValue einen*<br/>
Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den aktuellen Wert der Animationsgröße abzurufen. Wenn diese Methode schlägt fehl, oder vom zugrunde liegenden COM-Objekte für Breite und die Größe nicht initialisiert wurden, enthält szValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.

##  <a name="m_cxvalue"></a>  CAnimationSize::m_cxValue

Die gekapselte Animationsvariable, die Breite der Animationsgröße darstellt.

```
CAnimationVariable m_cxValue;
```

##  <a name="m_cyvalue"></a>  CAnimationSize::m_cyValue

Die gekapselte Animationsvariable, die Höhe der Animationsgröße darstellt.

```
CAnimationVariable m_cyValue;
```

##  <a name="operator_csize"></a>  CAnimationSize::operator CSize

Konvertiert einen CAnimationSize in einen CSize an.

```
operator CSize();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der Animationsgröße als CSize.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft intern "GetValue". Wenn "GetValue" aus irgendeinem Grund ein Fehler auftritt, enthält die zurückgegebene Größe Standardwerte für Breite und Höhe.

##  <a name="operator_eq"></a>  CAnimationSize::operator =

CAnimationSize SzSrc zugewiesen haben.

```
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Parameter

*szSrc*<br/>
Bezieht sich auf CSize oder Größe.

### <a name="remarks"></a>Hinweise

CAnimationSize SzSrc zugewiesen haben. Es wird dies vor dem Animationsstart, empfohlen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Breite und Höhe neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

##  <a name="setdefaultvalue"></a>  CAnimationSize::SetDefaultValue

Legt den Standardwert fest.

```
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Parameter

*szDefault*<br/>
Gibt die standardmäßige Größe des neuen.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um einen Standardwert auf "Animation"-Objekts festzulegen. Diese Methoden weisen Standardwerte auf Breite und Höhe der Animationsgröße. Es erstellt auch zugrunde liegende COM-Objekte neu, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
