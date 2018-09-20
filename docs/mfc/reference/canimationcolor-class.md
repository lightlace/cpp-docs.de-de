---
title: CAnimationColor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 565881fdbc085e7046574d3d468073f49b24f565
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421016"
---
# <a name="canimationcolor-class"></a>CAnimationColor-Klasse

Implementiert die Funktion einer Farbe, deren Rot-, Grün- und Blauanteil animiert werden kann.

## <a name="syntax"></a>Syntax

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Überladen. Erstellt eine Animation Color-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationColor::AddTransition](#addtransition)|Fügt die Übergänge für Rot, Grün und Blau-Komponenten hinzu.|
|[CAnimationColor::GetB](#getb)|Bietet Zugriff auf CAnimationVariable, die blaue Komponente darstellt.|
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für Farbkomponenten zurück.|
|[CAnimationColor::GetG](#getg)|Bietet Zugriff auf CAnimationVariable Grünanteils darstellt.|
|[CAnimationColor::GetR](#getr)|Bietet Zugriff auf CAnimationVariable Rotanteils darstellt.|
|[CAnimationColor::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationColor::operator COLORREF](#operator_colorref)||
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor Farbe zugewiesen.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAnimationColor::m_bValue](#m_bvalue)|Die gekapselte Animationsvariable, die blaue Komponente der Animationsfarbe darstellt.|
|[CAnimationColor::m_gValue](#m_gvalue)|Das gekapselte Animationsvariable, die Grünanteils der Animationsfarbe darstellt.|
|[CAnimationColor::m_rValue](#m_rvalue)|Das gekapselte Animationsvariable, die Rotanteils der Animationsfarbe darstellt.|

## <a name="remarks"></a>Hinweise

CAnimationColor-Klasse kapselt drei CAnimationVariable-Objekte und kann in Anwendungen eine Farbe darstellen. Beispielsweise können diese Klasse zum Animieren von Farben eines Objekts auf dem Bildschirm (etwa die Textfarbe, Hintergrundfarbe usw.). Um diese Klasse in der Anwendung verwenden zu können, einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf Rot, Grün und Blau-Komponenten angewendet werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationColor::AddTransition

Fügt die Übergänge für Rot, Grün und Blau-Komponenten hinzu.

```
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Parameter

*pRTransition*<br/>
Übergang für Rotanteil.

*pGTransition*<br/>
Übergang für den Grünanteil.

*pBTransition*<br/>
Übergang für die blaue Komponente.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Hinzufügen der angegebenen Übergänge der internen Liste von Übergängen anzuwendenden Animationsvariablen, die Komponenten der Farbe darstellt. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert werden soll. Übergänge werden angewendet (hinzugefügt zu einem Storyboard für einen bestimmten Wert) beim Aufruf CAnimationController:: AnimateGroup. Wenn Sie keine Übergang auf eine der Komponenten Farbe anwenden müssen, können Sie NULL übergeben.

##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor

Erstellt ein CAnimationColor-Objekt.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
Gibt die Standardfarbe.

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

Das Objekt wird erstellt, mit Standardwerten für Rot, Grün, Blau, Objekt-ID und die Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mithilfe SetDefaultValue und SetID später geändert werden.

##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList

Legt die gekapselten Animationsvariablen in einer Liste an.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
Wenn die Funktion zurückgibt, enthält Zeiger auf drei CAnimationVariable-Objekte, die rote, grüne und blaue Komponenten darstellt.

##  <a name="getb"></a>  CAnimationColor::GetB

Bietet Zugriff auf CAnimationVariable, die blaue Komponente darstellt.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die blaue Komponente darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable darstellt Blauanteils erhalten aufrufen.

##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue

Gibt die Standardwerte für Farbkomponenten zurück.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Rückgabewert

Ein COLORREF-Wert, der Standardwerte für die RGB-Komponenten enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von Standardwert, der zuvor vom Konstruktor oder SetDefaultValue festgelegt wurde.

##  <a name="getg"></a>  CAnimationColor::GetG

Bietet Zugriff auf CAnimationVariable Grünanteils darstellt.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable Darstellung Grünanteil.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable Darstellung Grünanteils erhalten aufrufen.

##  <a name="getr"></a>  CAnimationColor::GetR

Bietet Zugriff auf CAnimationVariable Rotanteils darstellt.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable Rotanteils darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable darstellt Rotanteils erhalten aufrufen.

##  <a name="getvalue"></a>  CAnimationColor::GetValue

Gibt den aktuellen Wert zurück.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den aktuellen Wert der Animationsfarbe abzurufen. Wenn diese Methode schlägt fehl, oder vom zugrunde liegenden COM-Objekte für Farbkomponenten nicht initialisiert wurden, enthält die Farbe Standardwert zugewiesen wurde, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.

##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue

Die gekapselte Animationsvariable, die blaue Komponente der Animationsfarbe darstellt.

```
CAnimationVariable m_bValue;
```

##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue

Das gekapselte Animationsvariable, die Grünanteils der Animationsfarbe darstellt.

```
CAnimationVariable m_gValue;
```

##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue

Das gekapselte Animationsvariable, die Rotanteils der Animationsfarbe darstellt.

```
CAnimationVariable m_rValue;
```

##  <a name="operator_colorref"></a>  CAnimationColor::operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq"></a>  CAnimationColor::operator =

CAnimationColor Farbe zugewiesen.

```
void operator=(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
Gibt an, neuer Wert Animation-Farbe.

### <a name="remarks"></a>Hinweise

Es wird dies vor dem Animationsstart, empfohlen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue

Legt den Standardwert fest.

```
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
Gibt neue Standardwerte für Rot, Grün und Blau-Komponenten an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um einen Standardwert auf "Animation"-Objekts festzulegen. Diese Methoden weisen Standardwerte zu Farbkomponenten Animation-Farbe. Es erstellt auch zugrunde liegende COM-Objekte neu, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
