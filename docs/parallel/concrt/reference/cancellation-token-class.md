---
title: cancellation_token-Klasse
ms.date: 11/04/2016
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
ms.openlocfilehash: 23821c91cd4158f6ec3989cdf537a5d8067e8225
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337517"
---
# <a name="cancellationtoken-class"></a>cancellation_token-Klasse

Mit der `cancellation_token`-Klasse kann bestimmt werden, ob für einen Vorgang ein Abbruch angefordert wurde. Dem angegebenen Token kann `task_group`, `structured_task_group` oder `task` zugeordnet werden, um einen impliziten Abbruch bereitzustellen. Es kann auch zum Abbruch abgerufen oder für einen Rückruf registriert werden, wenn das zugeordnete `cancellation_token_source`-Element abgebrochen wird.

## <a name="syntax"></a>Syntax

```
class cancellation_token;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[cancellation_token](#ctor)||
|[~ Cancellation_token-Destruktor](#dtor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[deregister_callback](#deregister_callback)|Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.|
|[is_cancelable](#is_cancelable)|Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.|
|[is_canceled](#is_canceled)|Gibt **"true"** , wenn das Token abgebrochen wurde.|
|[none](#none)|Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.|
|[register_callback](#register_callback)|Verknüpft eine Rückruffunktion mit dem Token. Wenn das Token abgebrochen wird, wird der Rückruf vorgenommen. Wurde das Token bereits abgebrochen, wenn diese Methode aufgerufen wird, wird der Rückruf sofort und synchron ausgeführt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`cancellation_token`

## <a name="requirements"></a>Anforderungen

**Header:** pplcancellation_token.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~cancellation_token

```
~cancellation_token();
```

##  <a name="ctor"></a> cancellation_token

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Die Cancellation_token kopiert oder verschoben werden.

##  <a name="deregister_callback"></a> deregister_callback

Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.

```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```

### <a name="parameters"></a>Parameter

*_Registration*<br/>
Das `cancellation_token_registration`-Objekt für den Rückruf, dessen Registrierung aufgehoben werden soll. Dieses Token muss zuvor von einem Aufruf der `register`-Methode zurückgegeben worden sein.

##  <a name="is_cancelable"></a> is_cancelable

Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.

```
bool is_cancelable() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Hinweis darauf, ob dieses Token abgebrochen werden kann oder nicht.

##  <a name="is_canceled"></a> is_canceled

Gibt **"true"** , wenn das Token abgebrochen wurde.

```
bool is_canceled() const;
```

### <a name="return-value"></a>Rückgabewert

Der Wert **"true"** Wenn das Token abgebrochen wurde, andernfalls ist der Wert **"false"**.

##  <a name="none"></a> Keine

Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.

```
static cancellation_token none();
```

### <a name="return-value"></a>Rückgabewert

Ein Abbruchtoken, das nicht abgebrochen werden kann.

##  <a name="operator_neq"></a> Operator! =

```
bool operator!= (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Der zu vergleichende `cancellation_token`.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq"></a> operator=

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Die `cancellation_token` zuweisen.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq_eq"></a> Operator ==

```
bool operator== (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Der zu vergleichende `cancellation_token`.

### <a name="return-value"></a>Rückgabewert

##  <a name="register_callback"></a> register_callback

Verknüpft eine Rückruffunktion mit dem Token. Wenn das Token abgebrochen wird, wird der Rückruf vorgenommen. Wurde das Token bereits abgebrochen, wenn diese Methode aufgerufen wird, wird der Rückruf sofort und synchron ausgeführt.

```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das zurückgerufen wird, wenn dieses `cancellation_token` abgebrochen wird.

*_Func*<br/>
Das Funktionsobjekt, das zurückgerufen wird, wenn dieses `cancellation_token` abgebrochen wird.

### <a name="return-value"></a>Rückgabewert

Ein `cancellation_token_registration`-Objekt, das in der `deregister`-Methode verwendet werden kann, um einen bereits registrierten Rückruf aufzuheben, damit er nicht ausgeführt wird. Löst die Methode eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn der Aufruf für eine `cancellation_token` -Objekt, das erstellt wurde, mithilfe der [cancellation_token:: None](#none) Methode.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
