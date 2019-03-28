---
title: extent-Klasse (C++ AMP)
ms.date: 03/27/2019
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
ms.openlocfilehash: 46af59708ef3f0d91883c52502bce4d09676ca77
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565830"
---
# <a name="extent-class-c-amp"></a>extent-Klasse (C++ AMP)

Stellt einen Vektor von *N* ganzzahlige Werte, die angeben, das die Begrenzungen des ein *N*-dimensionalen Raum mit dem Ursprung 0. Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert.

### <a name="syntax"></a>Syntax

```
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Parameter

*_Rank*<br/>
Der Rang des `extent`-Objekts.

## <a name="requirements"></a>Anforderungen

**Header:** amp.h

**Namespace:** Parallelität

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Extent-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `extent`-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[contains](#contains)|Überprüft, ob das angegebene `extent`-Objekt über den angegebenen Rang verfügt.|
|[size](#size)|Gibt die lineare Gesamtgröße des Wertebereichs zurück (in der Einheit Elemente).|
|[tile](#tile)|Erzeugt ein `tiled_extent`-Objekt mit den Kachelwertebereichen, die durch angegebene Dimensionen festgelegt werden.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator-](#operator_min)|Gibt ein neues `extent`-Objekt zurück, das erstellt wird, indem die `index`-Elemente von den entsprechenden `extent`-Elementen subtrahiert werden.|
|[operator--](#operator_min_min)|Dekrementiert jedes Element des `extent`-Objekts.|
|[operator%=](#operator_mod_eq)|Berechnet den Modul (Rest) jedes Elements im `extent`-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|
|[operator*=](#operator_star_eq)|Multipliziert jedes Element des `extent`-Objekts mit einer Zahl.|
|[operator/=](#operator_min_eq)|Dividiert jedes Element des `extent`-Objekts durch eine Zahl.|
|[extent::operator\[\]](#operator_at)|Gibt das Element am angegebenen Index zurück.|
|[operator+](#operator_add)|Gibt ein neues `extent`-Objekt zurück, das durch Hinzufügen der entsprechenden `index`- und `extent`-Elemente erstellt wird.|
|[operator++](#operator_add_add)|Inkrementiert jedes Element des `extent`-Objekts.|
|[operator+=](#operator_add_eq)|Fügt die angegebene Zahl jedem Element des `extent`-Objekts hinzu.|
|[operator=](#operator_eq)|Kopiert den Inhalt eines anderen `extent`-Objekts in dieses Objekt.|
|[operator-=](#operator_min_eq)|Subtrahiert die angegebene Anzahl von jedem Element des `extent`-Objekts.|

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|Beschreibung|
|----------|-----------------|
|[Rank-Konstante](#rank_constant)|Ruft den Rang des `extent`-Objekts ab.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`extent`

## <a name="contains"></a> Enthält

Gibt an, ob das angegebene [Index](index-class.md) Wert innerhalb des Objekts "Block" enthalten ist.

### <a name="syntax"></a>Syntax

```
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der zu testende `index`-Wert.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn das angegebene *Index* Wert befindet sich der `extent` Objekt; andernfalls **"false"**.

##  <a name="ctor"></a> Wertebereich

Initialisiert eine neue Instanz der Klasse "Block".

### <a name="syntax"></a>Syntax

```
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Array*<br/>
Ein Array mit ganzen `_Rank`-Zahlen, mit dem das neue `extent`-Objekt erstellt wird.

*_I*<br/>
Die Länge des Wertebereichs.

*_I0*<br/>
Die Länge der wichtigsten Dimension.

*_I1*<br/>
Die Länge der zweitwichtigsten Dimension.

*_I2*<br/>
Die Länge der unwichtigsten Dimension.

*_Other*<br/>
Ein `extent`-Objekt, auf dem das neue `extent`-Objekt basiert.

## <a name="remarks"></a>Hinweise

Der parameterlose Konstruktor initialisiert ein `extent`-Objekt, das den Rang 3 hat.

Wenn ein Array verwendet wird, um ein `extent`-Objekt zu erstellen, muss die Länge des Arrays mit dem Rang des `extent`-Objekts übereinstimmen.

##  <a name="operator_mod_eq"></a> Operator% =

Berechnet den Modul (Rest) jedes Elements in der "Block", wenn dieses Element durch eine Zahl dividiert wird.

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die Anzahl der Betrag zu finden.

### <a name="return-value"></a>Rückgabewert

Das `extent`-Objekt.

##  <a name="operator_star_eq"></a> Operator * =

Multipliziert jedes Element in das "Extent"-Objekt, mit der angegebenen Zahl.

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die zu multiplizierende Zahl.

### <a name="return-value"></a>Rückgabewert

Das `extent`-Objekt.

## <a name="operator_add"></a> Operator +-

Gibt ein neues `extent`-Objekt zurück, das durch Hinzufügen der entsprechenden `index`- und `extent`-Elemente erstellt wird.

### <a name="syntax"></a>Syntax

```
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das `index`-Objekt, das die hinzuzufügenden Elemente enthält.

### <a name="return-value"></a>Rückgabewert

Das neue `extent` -Objekt.

##  <a name="operator_add_add"></a> "Operator++"

Inkrementiert jedes Element des Objekts "Block".

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Rückgabewert

Für den Präfixoperator das `extent`-Objekt (`*this`). Für den Suffixoperator ein neues `extent`-Objekt.

##  <a name="operator_add_eq"></a> operator+=

Fügt die angegebene Anzahl auf jedes Element des Objekts "Block".

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die Zahl, der Index oder der Wertebereich, die bzw. der hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Das resultierende `extent`-Objekt.

##  <a name="operator_min"></a> Operator-

Erstellt ein neues `extent`-Objekt durch Subtrahieren der einzelnen Elemente im angegebenen `index`-Objekt vom entsprechenden Element in diesem `extent`-Objekt.

### <a name="syntax"></a>Syntax

```
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das `index`-Objekt, das die zu subtrahierenden Elemente enthält.

### <a name="return-value"></a>Rückgabewert

Das neue `extent` -Objekt.

##  <a name="operator_min_min"></a> Operator--

Dekrementiert jedes Element in das "Extent"-Objekt.

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Rückgabewert

Für den Präfixoperator das `extent`-Objekt (`*this`). Für den Suffixoperator ein neues `extent`-Objekt.

##  <a name="operator_div_eq"></a> Operator / =

Dividiert jedes Element in das "Extent"-Objekt mit der angegebenen Zahl.

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die Zahl, durch die dividiert wird.

### <a name="return-value"></a>Rückgabewert

Das `extent`-Objekt.

##  <a name="operator_min_eq"></a> Operator =

Subtrahiert die angegebene Anzahl von jedem Element des Objekts "Block".

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Die zu subtrahierende Zahl.

### <a name="return-value"></a>Rückgabewert

Das resultierende `extent`-Objekt.

##  <a name="operator_eq"></a> operator=

Kopiert den Inhalt eines anderen "Block"-Objekts in dieses Objekt.

### <a name="syntax"></a>Syntax

```
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
Das `extent`-Objekt, aus dem kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `extent`-Objekt.

##  <a name="operator_at"></a> Extent:: \[\]

Gibt das Element am angegebenen Index zurück.

### <a name="syntax"></a>Syntax

```
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Eine ganze Zahl von 0 durch den Rang minus 1.

### <a name="return-value"></a>Rückgabewert

Das Element am angegebenen Index.

##  <a name="rank_constant"></a> Rang

Speichert den Rang des Objekts "Block".

### <a name="syntax"></a>Syntax

```
static const int rank = _Rank;
```

##  <a name="size"></a> Größe

Gibt die lineare Gesamtgröße der `extent` Objekt (in Einheiten von Elementen).

### <a name="syntax"></a>Syntax

```
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a> Kachel "

Erzeugt ein Tiled_extent-Objekt mit den angegebenen kacheldimensionen.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```

### <a name="parameters"></a>Parameter

*_Dim0*<br/>
Die wichtigste Komponente des unterteilten Wertebereichs.
*_Dim1*<br/>
Die zweitwichtigste Komponente des unterteilten Wertebereichs.
*_Dim2*<br/>
Die unwichtigste Komponente des unterteilten Wertebereichs.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
