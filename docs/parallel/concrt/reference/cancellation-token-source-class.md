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
ms.openlocfilehash: 131c4155ad902221d14f90f750f89c31479e2067
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142230"
---
# <a name="cancellation_token_source-class"></a>cancellation_token_source-Klasse

Mit der `cancellation_token_source` -Klasse kann ein abbrechbarer Vorgang abgebrochen werden.

## <a name="syntax"></a>Syntax

```cpp
class cancellation_token_source;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[cancellation_token_source](#ctor)|Ist überladen. Erstellt ein neues `cancellation_token_source`. Die Quelle kann verwendet werden, um den Abbruch eines abbrechbaren Vorgangs zu kennzeichnen.|
|[~ cancellation_token_source-Dekonstruktor](#dtor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[cancel](#cancel)|Bricht das Token ab. Jede `task_group`, `structured_task_group` oder jeder `task`, der das Token nutzt, wird bei diesem Aufruf abgebrochen und löst eine Ausnahme am nächsten Unterbrechungspunkt aus.|
|[create_linked_source](#create_linked_source)|Ist überladen. Erstellt eine `cancellation_token_source`, die abgebrochen wird, wenn das bereitgestellte Token abgebrochen wird.|
|[get_token](#get_token)|Gibt ein Abbruchtoken zurück, das dieser Quelle zugeordnet ist. Das zurückgegebene Token kann für einen Abbruch abgerufen werden oder einen Rückruf bereitstellen, wenn ein Abbruch auftritt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`cancellation_token_source`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** pplcancellation_token. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ cancellation_token_source

```cpp
~cancellation_token_source();
```

## <a name="cancel"></a>Abbrechen

Bricht das Token ab. Jede `task_group`, `structured_task_group` oder jeder `task`, der das Token nutzt, wird bei diesem Aufruf abgebrochen und löst eine Ausnahme am nächsten Unterbrechungspunkt aus.

```cpp
void cancel() const;
```

## <a name="ctor"></a>cancellation_token_source

Erstellt ein neues `cancellation_token_source`. Die Quelle kann verwendet werden, um den Abbruch eines abbrechbaren Vorgangs zu kennzeichnen.

```cpp
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Objekt, das kopiert oder verschoben werden soll.

## <a name="create_linked_source"></a>create_linked_source

Erstellt eine `cancellation_token_source`, die abgebrochen wird, wenn das bereitgestellte Token abgebrochen wird.

```cpp
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```

### <a name="parameters"></a>Parameter

*_Iter*<br/>
Der iteratortyp.

*_Src*<br/>
Ein Token, dessen Abbruch den Abbruch der zurückgegebenen Tokenquelle verursacht. Beachten Sie, dass die zurückgegebene Tokenquelle auch unabhängig von der Quelle in diesem Parameter abgebrochen werden kann.

*_Begin*<br/>
Der C++ standardbibliotheks-Iterator, der dem Anfang des Bereichs von Token entspricht, um auf den Abbruch zu lauschen.

*_End*<br/>
Der C++ standardbibliotheks-Iterator, der dem Ende des Bereichs von Token entspricht, um auf den Abbruch zu lauschen.

### <a name="return-value"></a>Rückgabewert

Eine `cancellation_token_source`, die abgebrochen wird, wenn das vom `_Src`-Parameter bereitgestellte Token abgebrochen wird.

## <a name="get_token"></a>get_token

Gibt ein Abbruchtoken zurück, das dieser Quelle zugeordnet ist. Das zurückgegebene Token kann für einen Abbruch abgerufen werden oder einen Rückruf bereitstellen, wenn ein Abbruch auftritt.

```cpp
cancellation_token get_token() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Abbruchtoken, der dieser Quelle zugeordnet ist.

## <a name="operator_neq"></a>Operator! =

```cpp
bool operator!= (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

## <a name="operator_eq"></a>Operator =

```cpp
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

## <a name="operator_eq_eq"></a>Operator = =

```cpp
bool operator== (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Operand.

### <a name="return-value"></a>Rückgabewert

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
