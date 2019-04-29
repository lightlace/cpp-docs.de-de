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
ms.openlocfilehash: c6ca8061181ec057110282fa297666235e898ff6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414190"
---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration-Klasse

Die `cancellation_token_registration`-Klasse stellt eine Rückrufbenachrichtigung von `cancellation_token` dar. Bei Verwendung der `register`-Methode auf `cancellation_token` zum Empfangen von Benachrichtigungen darüber, wann ein Abbruch auftritt, wird ein `cancellation_token_registration`-Objekt als Handle an den Rückruf zurückgegeben, damit der Aufrufer mithilfe der `deregister`-Methode anfordern kann, dass ein bestimmter Rückruf nicht mehr erfolgt.

## <a name="syntax"></a>Syntax

```
class cancellation_token_registration;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~cancellation_token_registration Destructor](#dtor)||

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`cancellation_token_registration`

## <a name="requirements"></a>Anforderungen

**Header:** pplcancellation_token.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~cancellation_token_registration

```
~cancellation_token_registration();
```

##  <a name="ctor"></a> cancellation_token_registration

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Die `cancellation_token_registration` kopieren oder verschieben.

##  <a name="operator_neq"></a> Operator! =

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Der zu vergleichende `cancellation_token_registration`.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq"></a> operator=

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Die `cancellation_token_registration` zuweisen.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq_eq"></a> Operator ==

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Der zu vergleichende `cancellation_token_registration`.

### <a name="return-value"></a>Rückgabewert

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
