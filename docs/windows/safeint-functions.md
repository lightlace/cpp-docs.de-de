---
title: SafeInt-Funktionen
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt functions
- SafeAdd
- SafeCast
- SafeDivide
- SafeEquals
- SafeGreaterThan
- SafeGreaterThanEquals
- SafeLessThan
- SafeLessThanEquals
- SafeModulus
- SafeMultiply
- SafeNotEquals
- SafeSubtract
helpviewer_keywords:
- functions, SafeInt
- SafeAdd function
- SafeCast function
- SafeDivide function
- SafeEquals function
- SafeGreaterThan function
- SafeGreaterThanEquals function
- SafeLessThan function
- SafeLessThanEquals function
- SafeModulus function
- SafeMultiply function
- SafeNotEquals function
- SafeSubtract function
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
ms.openlocfilehash: 0cf1418e3bf00c037faaa67de2bc76ad2b7cc5e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578398"
---
# <a name="safeint-functions"></a>SafeInt-Funktionen

Die SafeInt-Bibliothek stellt mehrere Funktionen, die Sie verwenden können, ohne eine Instanz des der [SafeInt-Klasse](../windows/safeint-class.md). Wenn Sie einen einzelnen mathematischen Vorgang vor Ganzzahlüberlauf schützen möchten, können Sie diese Funktionen. Wenn Sie mehrere mathematische Vorgänge schützen möchten, sollten Sie erstellen `SafeInt` Objekte. Es ist jedoch effizienter erstellen `SafeInt` Objekte, anstatt diese Funktionen mehrmals.

Diese Funktionen können Sie vergleichen oder die mathematische Operationen für zwei verschiedene Arten von Parametern ausführen, ohne sie zuerst auf den gleichen Typ konvertieren zu müssen.

Jede dieser Funktionen hat zwei Vorlagentypen: `T` und `U`. Jeder dieser Typen kann ein boolescher Wert, Zeichen oder ganzzahliger Typ sein. Ganzzahltypen mit oder ohne Vorzeichen werden können und beliebiger Größe von 8 Bits bis 64 Bits.

> [!NOTE]
> Die neueste Version dieser Bibliothek befindet sich unter [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

## <a name="in-this-section"></a>In diesem Abschnitt

Funktion                      | Beschreibung
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | Addiert zwei Zahlen und schützt vor Ganzzahlüberlauf.
[safecast](#safecast)         | Wandelt einen Typ des Parameters in einen anderen Typ.
[SafeDivide](#safedivide)     | Dividiert zwei Zahlen und schützt vor Division durch 0 (null).
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [ SafeNotEquals](#safenotequals) | Vergleicht zwei Zahlen. Diese Funktionen können Sie zwei verschiedene Arten von Zahlen zu vergleichen, ohne ihre Typen ändern.
[SafeModulus](#safemodulus)   | Führt die Modulo-Operation für zwei Zahlen.
[SafeMultiply](#safemultiply) | Multipliziert zwei Zahlen zusammen und schützt vor Ganzzahlüberlauf.
[SafeSubtract](#safesubtract) | Subtrahiert zwei Zahlen und schützt vor Ganzzahlüberlauf.

## <a name="related-sections"></a>Verwandte Abschnitte

Bereich                                                  | Beschreibung
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../windows/safeint-class.md)                   | Der `SafeInt`-Klasse.
[SafeIntException](../windows/safeintexception-class.md) | Die Exception-Klasse, die spezifisch für die SafeInt-Bibliothek.

## <a name="safeadd"></a>SafeAdd

Addiert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf an.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu addierende Zahl. Dies muss vom Typ "t".

*n*<br/>
[in] Die zweite zu addierende Zahl. Dies muss u sein.

*Ergebnis*<br/>
[out] Der Parameter, in denen `SafeAdd` speichert das Ergebnis.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="safecast"></a>SafeCast

Wandelt einen Typ der Zahl in einen anderen Typ.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parameter

*From*<br/>
[in] Die Quelle zu konvertierende Zahl. Dies muss vom Typ `T`.

*Aktion*<br/>
[out] Ein Verweis auf die neue Zahlentyp. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="safedivide"></a>SafeDivide

Dividiert zwei Zahlen in einer Weise, die Division durch 0 (null) schützt.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Der Divisor. Dies muss vom Typ "t".

*n*<br/>
[in] Der Dividend. Dies muss u sein.

*Ergebnis*<br/>
[out] Der Parameter, in denen `SafeDivide` speichert das Ergebnis.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="safeequals"></a>SafeEquals

Vergleicht zwei Zahlen, um festzustellen, ob diese gleich sind.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ "t".

*n*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss u sein.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* und *u* gleich sind; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Die Methode verbessert `==` da `SafeEquals` ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen zu vergleichen.

## <a name="safegreaterthan"></a>SafeGreaterThan

Vergleicht zwei Zahlen.

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* ist größer als *u*andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

`SafeGreaterThan` Erweitert den regulären Vergleichsoperator ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen verglichen werden soll.

## <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

Vergleicht zwei Zahlen.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* ist größer als oder gleich *u*andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

`SafeGreaterThanEquals` den standard-Vergleichsoperator verbessert, da Sie zwei verschiedene Arten von Zahlen vergleichen können.

## <a name="safelessthan"></a>SafeLessThan

Bestimmt, ob eine Zahl kleiner als ein anderes ist.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite Anzahl. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* ist kleiner als *u*andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Diese Methode wird den standard-Vergleichsoperator verbessert, da `SafeLessThan` ermöglicht es Ihnen, zwei verschiedene Arten von Zahl verglichen werden soll.

## <a name="safelessthanequals"></a>SafeLessThanEquals

Vergleicht zwei Zahlen.

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* ist kleiner als oder gleich *u*andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

`SafeLessThanEquals` Erweitert den regulären Vergleichsoperator ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen verglichen werden soll.

## <a name="safemodulus"></a>SafeModulus

Führt die Modulo-Operation für zwei Zahlen.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Der Divisor. Dies muss vom Typ `T`.

*n*<br/>
[in] Der Dividend. Dies muss vom Typ `U`.

*Ergebnis*<br/>
[out] Der Parameter, in denen `SafeModulus` speichert das Ergebnis.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="safemultiply"></a>SafeMultiply

Multipliziert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf zusammen.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu multiplizierende Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite zu multiplizierende Zahl. Dies muss vom Typ `U`.

*Ergebnis*<br/>
[out] Der Parameter, in denen `SafeMultiply` speichert das Ergebnis.

### <a name="return-value"></a>Rückgabewert

`true` Wenn kein Fehler auftritt. `false` Wenn ein Fehler auftritt.

## <a name="safenotequals"></a>SafeNotEquals

Bestimmt, ob zwei Zahlen ungleich sind.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* und *u* nicht gleich sind; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Die Methode verbessert `!=` da `SafeNotEquals` ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen zu vergleichen.

## <a name="safesubtract"></a>SafeSubtract

Subtrahiert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf an.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste Zahl in der Subtraktion. Dies muss vom Typ `T`.

*n*<br/>
[in] Die zu subtrahierende Zahl *t*. Dies muss vom Typ `U`.

*Ergebnis*<br/>
[out] Der Parameter, in denen `SafeSubtract` speichert das Ergebnis.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.
