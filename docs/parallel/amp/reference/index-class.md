---
title: index-Klasse
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 06a5fa9a2d7e645c46b90ace957d31251baed81c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127802"
---
# <a name="index-class"></a>index-Klasse

Definiert einen *N*-dimensionalen Index Vektor.

## <a name="syntax"></a>Syntax

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Parameter

*_Rank*<br/>
Der Rang oder die Anzahl von Dimensionen.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[indexkonstruktor](#index_ctor)|Initialisiert eine neue Instanz der Klasse `index`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator--](#operator--)|Dekrementiert jedes Element des `index`-Objekts.|
|[operator%=](#operator_mod_eq)|Berechnet den Modul (Rest) jedes Elements im `index`-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|
|[operator*=](#operator_star_eq)|Multipliziert jedes Element des `index`-Objekts mit einer Zahl.|
|[operator/=](#operator_div_eq)|Dividiert jedes Element des `index`-Objekts durch eine Zahl.|
|[Index:: Operator\[\]](#operator_at)|Gibt das Element am angegebenen Index zurück.|
|[operator++](#operator_add_add)|Inkrementiert jedes Element des `index`-Objekts.|
|[operator+=](#operator_add_eq)|Fügt die angegebene Zahl jedem Element des `index`-Objekts hinzu.|
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `index`-Objekts in dieses Objekt.|
|[operator-=](#operator_-_eq)|Subtrahiert die angegebene Anzahl von jedem Element des `index`-Objekts.|

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Rank-Konstante](#rank)|Speichert den Rang des `index`-Objekts.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`index`

## <a name="remarks"></a>Bemerkungen

Die `index`-Struktur stellt einen Koordinaten Vektor von *N* ganzen Zahlen dar, der eine eindeutige Position in einem *n*-dimensionalen Raum angibt. Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert. Sie können die Werte der Komponenten mithilfe von [Operator =](#operator_eq)abrufen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp.h

**Namespace:** Parallelität

## <a name="index_ctor"></a>indexkonstruktor

Initialisiert eine neue Instanz der index-Klasse.

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Array*<br/>
Ein eindimensionales Array mit den Rangwerten.

*_I*<br/>
Die Indexposition in einem eindimensionalen Index.

*_I0*<br/>
Die Länge der wichtigsten Dimension.

*_I1*<br/>
Die Länge der zweitwichtigsten Dimension.

*_I2*<br/>
Die Länge der unwichtigsten Dimension.

*_Other*<br/>
Ein Index Objekt, auf dem das neue Index Objekt basiert.

## <a name="operator--"></a>Operator--

Dekrementiert jedes Element des index-Objekts.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Rückgabewerte

Für den Prefix-Operator das Index Objekt (* this). Für den Suffix-Operator ein neues Index Objekt.

## <a name="operator_mod_eq"></a>Operator% =

Berechnet den Modulo (Rest) jedes Elements im Index Objekt, wenn dieses Element durch die angegebene Zahl dividiert wird.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die Zahl, durch die dividiert wird, um den Modulus zu ermitteln.

## <a name="return-value"></a>Rückgabewert

Das Index Objekt.

## <a name="operator_star_eq"></a>Operator * =

Multipliziert jedes Element im index-Objekt mit der angegebenen Zahl.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die zu multiplizierende Zahl.

## <a name="operator_div_eq"></a>Operator/=

Dividiert jedes Element im Index-Objekt durch die angegebene Anzahl.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die Zahl, durch die dividiert wird.

## <a name="operator_at"></a> Operator\[\]

Gibt die Komponente des Index an der angegebenen Position zurück.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Eine ganze Zahl von 0 durch den Rang minus 1.

### <a name="return-value"></a>Rückgabewert

Das Element am angegebenen Index.

### <a name="remarks"></a>Bemerkungen

Im folgenden Beispiel werden die Komponentenwerte des Index angezeigt.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>Operator + +

Inkrementiert jedes Element des index-Objekts.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Rückgabewert

Für den Prefix-Operator das Index Objekt (* this). Für den Suffix-Operator ein neues Index Objekt.

## <a name="operator_add_eq"></a>Operator + =

Fügt die angegebene Zahl jedem Element des Index-Objekts hinzu.

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die hinzuzufügende Zahl.

### <a name="return-value"></a>Rückgabewert

Das Index Objekt.

## <a name="operator_eq"></a> operator=

Kopiert den Inhalt des angegebenen index-Objekts in dieses Objekt.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
Das Index Objekt, aus dem kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf dieses Index Objekt.

## <a name="operator_-_eq"></a>Operator-=

Subtrahiert die angegebene Anzahl von jedem Element des index-Objekts.

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die zu subtrahierende Zahl.

### <a name="return-value"></a>Rückgabewert

Das Index Objekt.

## <a name="rank"></a>Gehören

Ruft den Rang des Index Objekts ab.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
