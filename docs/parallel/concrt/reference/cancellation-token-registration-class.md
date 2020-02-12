---
title: cancellation_token_registration-Klasse
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: 9342841e207c93b66521c2fc742c1b1114682f78
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142242"
---
# <a name="cancellation_token_registration-class"></a>cancellation_token_registration-Klasse

Die `cancellation_token_registration`-Klasse stellt eine Rückrufbenachrichtigung von `cancellation_token` dar. Bei Verwendung der `register`-Methode auf `cancellation_token` zum Empfangen von Benachrichtigungen darüber, wann ein Abbruch auftritt, wird ein `cancellation_token_registration`-Objekt als Handle an den Rückruf zurückgegeben, damit der Aufrufer mithilfe der `deregister`-Methode anfordern kann, dass ein bestimmter Rückruf nicht mehr erfolgt.

## <a name="syntax"></a>Syntax

```cpp
class cancellation_token_registration;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration-Dekonstruktor](#dtor)||

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`cancellation_token_registration`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** pplcancellation_token. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ cancellation_token_registration

```cpp
~cancellation_token_registration();
```

## <a name="ctor"></a>cancellation_token_registration

```cpp
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Der `cancellation_token_registration`, der kopiert oder verschoben werden soll.

## <a name="operator_neq"></a>Operator! =

```cpp
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das zu vergleichende `cancellation_token_registration`-Element.

### <a name="return-value"></a>Rückgabewert

## <a name="operator_eq"></a>Operator =

```cpp
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Der zuzuweisende `cancellation_token_registration`.

### <a name="return-value"></a>Rückgabewert

## <a name="operator_eq_eq"></a>Operator = =

```cpp
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das zu vergleichende `cancellation_token_registration`-Element.

### <a name="return-value"></a>Rückgabewert

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
