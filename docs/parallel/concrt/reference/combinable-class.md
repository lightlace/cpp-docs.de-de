---
title: combinable-Klasse
ms.date: 11/04/2016
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
ms.openlocfilehash: b392a46c3aafac9ab5f3ca2b626f5f78daebc85d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630749"
---
# <a name="combinable-class"></a>combinable-Klasse

Das `combinable<T>`-Objekt ist dazu gedacht, threadprivate Kopien von Daten bereitzustellen, mit denen sperrenfreie, threadlokale Unterberechnungen in parallelen Algorithmen durchgeführt werden können. Am Ende des Parallelvorgangs können die threadprivaten Unterbrechungen in einem Endergebnis zusammengeführt werden. Diese Klasse kann anstelle einer freigegebenen Variable verwendet werden, und sie kann zu einer Leistungsverbesserung führen, wenn andernfalls Konflikte mit dieser freigegebenen Variable entstehen würden.

## <a name="syntax"></a>Syntax

```
template<typename T>
class combinable;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp des Endergebnisses zusammengeführt werden soll. Der Typ muss es sich um einen Kopierkonstruktor und einen Standardkonstruktor verfügen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[mit den flexibel kombinierbaren](#ctor)|Überladen. Erstellt ein neues `combinable`-Objekt.|
|[~ combinable-Destruktor](#dtor)|Zerstört ein `combinable`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[clear](#clear)|Löscht alle Compute-Zwischenergebnisse aus einer früheren Verwendung.|
|[combine](#combine)|Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch das angegebene kombinieren Funktionselement aufrufen.|
|[combine_each](#combine_each)|Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung. Das Endergebnis werden vom Funktionsobjekt gesammelt.|
|[local](#local)|Überladen. Gibt einen Verweis auf die privaten untergeordnete Berechnung.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator=](#operator_eq)|Weist eine `combinable` Objekt von einem anderen `combinable` Objekt.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`combinable`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="clear"></a> Deaktivieren

Löscht alle Compute-Zwischenergebnisse aus einer früheren Verwendung.

```
void clear();
```

##  <a name="ctor"></a> mit den flexibel kombinierbaren

Erstellt ein neues `combinable`-Objekt.

```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Initialisierung Functor-Objekts.

*_FnInitialize*<br/>
Eine Funktion, die aufgerufen wird, initialisiert jeder neue Thread-Private-Wert des Typs `T`. Es muss einen Funktionsaufrufoperator mit der Signatur unterstützen `T ()`.

*"_Copy"*<br/>
Eine vorhandene `combinable` Objekt, das in dieses Objekt kopiert werden.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die neue Elemente mit dem Standardkonstruktor für den Typ `T`.

Der zweite Konstruktor initialisiert die neue Elemente, die die Initialisierung Funktionselement wie angegeben mit der `_FnInitialize` Parameter.

Der dritte Konstruktor ist der Kopierkonstruktor.

##  <a name="dtor"></a> ~ combinable

Zerstört ein `combinable`-Objekt.

```
~combinable();
```

##  <a name="combine"></a> Kombinieren

Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch das angegebene kombinieren Funktionselement aufrufen.

```
template<typename _Function>
T combine(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das aufgerufen wird, um zwei threadlokale unterberechnungen kombinieren.

*_FnCombine*<br/>
Die Funktionselement ist, das verwendet wird, um die untergeordneten Berechnungen kombinieren. Ihre Signatur ist `T (T, T)` oder `T (const T&, const T&)`, und assoziativ und kommutativ sein.

### <a name="return-value"></a>Rückgabewert

Das endgültige Ergebnis der Kombination aller privaten teilberechnungen.

##  <a name="combine_each"></a> combine_each

Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung. Das Endergebnis werden vom Funktionsobjekt gesammelt.

```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das aufgerufen wird, um eine einzelne untergeordnete Thread-Local-Berechnung zu kombinieren.

*_FnCombine*<br/>
Die Funktionselement ist, das verwendet wird, um eine untergeordnete Berechnung zu kombinieren. Ihre Signatur ist `void (T)` oder `void (const T&)`, assoziativ und kommutativ sein muss.

##  <a name="local"></a> lokale

Gibt einen Verweis auf die privaten untergeordnete Berechnung.

```
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>Parameter

*_Exists*<br/>
Ein Verweis auf einen booleschen Wert. Der boolesche Wert, der auf die dieses Argument verweist auf festgelegt **"true"** , wenn die untergeordnete Berechnung bereits auf diesem Thread vorhanden war, und legen Sie auf **"false"** war dies die erste untergeordnete Berechnung für diesen Thread.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die privaten untergeordnete Berechnung.

##  <a name="operator_eq"></a> Operator =

Weist eine `combinable` Objekt von einem anderen `combinable` Objekt.

```
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>Parameter

*"_Copy"*<br/>
Eine vorhandene `combinable` Objekt, das in dieses Objekt kopiert werden.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `combinable`-Objekt.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
