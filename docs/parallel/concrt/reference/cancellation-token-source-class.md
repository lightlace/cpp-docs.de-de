---
title: cancellation_token_source-Klasse
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
ms.openlocfilehash: 330473db1011af661e2cfa2c5861987bce786e40
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296786"
---
# <a name="cancellationtokensource-class"></a>cancellation_token_source-Klasse

Mit der `cancellation_token_source` -Klasse kann ein abbrechbarer Vorgang abgebrochen werden.

## <a name="syntax"></a>Syntax

```
class cancellation_token_source;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[cancellation_token_source](#ctor)|Überladen. Erstellt eine neue `cancellation_token_source`. Die Quelle kann verwendet werden, um den Abbruch eines abbrechbaren Vorgangs zu kennzeichnen.|
|[~ Cancellation_token_source-Destruktor](#dtor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[cancel](#cancel)|Bricht das Token ab. Jede `task_group`, `structured_task_group` oder jeder `task`, der das Token nutzt, wird bei diesem Aufruf abgebrochen und löst eine Ausnahme am nächsten Unterbrechungspunkt aus.|
|[create_linked_source](#create_linked_source)|Überladen. Erstellt eine `cancellation_token_source`, die abgebrochen wird, wenn das bereitgestellte Token abgebrochen wird.|
|[get_token](#get_token)|Gibt ein Abbruchtoken zurück, das dieser Quelle zugeordnet ist. Das zurückgegebene Token kann für einen Abbruch abgerufen werden oder einen Rückruf bereitstellen, wenn ein Abbruch auftritt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`cancellation_token_source`

## <a name="requirements"></a>Anforderungen

**Header:** pplcancellation_token.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~cancellation_token_source

```
~cancellation_token_source();
```

##  <a name="cancel"></a> Abbrechen

Bricht das Token ab. Jede `task_group`, `structured_task_group` oder jeder `task`, der das Token nutzt, wird bei diesem Aufruf abgebrochen und löst eine Ausnahme am nächsten Unterbrechungspunkt aus.

```
void cancel() const;
```

##  <a name="ctor"></a> cancellation_token_source

Erstellt eine neue `cancellation_token_source`. Die Quelle kann verwendet werden, um den Abbruch eines abbrechbaren Vorgangs zu kennzeichnen.

```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Objekt, das Kopieren oder verschieben.

##  <a name="create_linked_source"></a> create_linked_source

Erstellt eine `cancellation_token_source`, die abgebrochen wird, wenn das bereitgestellte Token abgebrochen wird.

```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```

### <a name="parameters"></a>Parameter

*_Iter*<br/>
Iteratortyp.

*_Src*<br/>
Ein Token, dessen Abbruch den Abbruch der zurückgegebenen Tokenquelle verursacht. Beachten Sie, dass die zurückgegebene Tokenquelle auch unabhängig von der Quelle in diesem Parameter abgebrochen werden kann.

*_Begin*<br/>
Die C++-Standardbibliothek Iterator am Anfang des tokenbereichs, der auf einen Abbruch überwacht.

*_End*<br/>
Die C++-Standardbibliothek Iterator für das Ende des tokenbereichs, der auf einen Abbruch überwacht.

### <a name="return-value"></a>Rückgabewert

Eine `cancellation_token_source`, die abgebrochen wird, wenn das vom `_Src`-Parameter bereitgestellte Token abgebrochen wird.

##  <a name="get_token"></a> get_token

Gibt ein Abbruchtoken zurück, das dieser Quelle zugeordnet ist. Das zurückgegebene Token kann für einen Abbruch abgerufen werden oder einen Rückruf bereitstellen, wenn ein Abbruch auftritt.

```
cancellation_token get_token() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Abbruchtoken, der dieser Quelle zugeordnet ist.

##  <a name="operator_neq"></a> Operator! =

```
bool operator!= (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq"></a> operator=

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq_eq"></a> Operator ==

```
bool operator== (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
