---
title: Platform::String-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: ef9838fa8a6a34eac1d2d3531ff93fb124c81d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607037"
---
# <a name="platformstring-class"></a>Platform::String-Klasse

Stellt eine sequenzielle Auflistung von Unicode-Zeichen dar, die zum Darstellen von Text verwendet werden. Weitere Informationen und Beispiele finden Sie unter [Zeichenfolgen](../cppcx/strings-c-cx.md).

## <a name="syntax"></a>Syntax

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Iterators

Zwei Iteratorfunktionen, die nicht Member der Zeichenfolgenklasse sind, können mit der Vorlagenfunktion `std::for_each` verwendet werden, um die Zeichen in einem Zeichenfolgenobjekt aufzulisten.

|Member|Beschreibung|
|------------|-----------------|
|`const char16* begin(String^ s)`|Gibt einen Zeiger auf den Anfang des angegebenen Zeichenfolgenobjekts zurück.|
|`const char16* end(String^ s)`|Gibt einen Zeiger nach dem Ende des angegebenen Zeichenfolgenobjekts zurück.|

### <a name="members"></a>Member

Die Zeichenfolgenklasse erbt vom Objekt und den Schnittstellen IDisposable, IEquatable und IPrintable.

Die Zeichenfolgenklasse verfügt auch über die folgenden Typen von Membern.

**Konstruktoren**

|Member|Beschreibung|
|------------|-----------------|
|[String::String](#ctor)|Initialisiert eine neue Instanz der Zeichenfolgenklasse.|

**Methoden**

Die Zeichenfolgenklasse erbt die Methoden Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() und ToString() von [Platform::Object Class](../cppcx/platform-object-class.md). Die Zeichenfolge hat auch die folgenden Methoden.

|Methode|Beschreibung|
|------------|-----------------|
|[String:: begin](#begin)|Gibt einen Zeiger auf den Anfang der aktuellen Zeichenfolge zurück.|
|[String::CompareOrdinal](#compareordinal)|Vergleicht zwei `String` -Objekte durch Auswertung der numerischen Werte der entsprechenden Zeichen in den beiden Zeichenfolgenwerten, die durch die Objekte dargestellt werden.|
|[String::Concat](#concat)|Verkettet die Werte von zwei Zeichenfolgenobjekten.|
|[String:: Data](#data)|Gibt einen Zeiger auf den Anfang der aktuellen Zeichenfolge zurück.|
|[String:: Dispose](#dispose)|Gibt Ressourcen frei.|
|[String:: End](#end)|Gibt einen Zeiger nach dem Ende der aktuellen Zeichenfolge zurück.|
|[String::Equals](#equals)|Gibt an, ob das angegebene Objekt gleich dem aktuellen Objekt ist.|
|[String::GetHashCode](#gethashcode)|Gibt den Hashcode für diese Instanz zurück.|
|[String::IsEmpty](#isempty)|Gibt an, ob das aktuelle String-Objekt leer ist.|
|[String::IsFastPass](#isfastpass)|Gibt an, ob das aktuelle String-Objekt beteiligt ist eine *Schnelldurchlauf* Vorgang. Bei einem Fast-Pass-Vorgang wird die Verweiszählung angehalten.|
|[String::Length](#length)|Ruft die Länge des aktuellen Zeichenfolgenobjekts ab.|
|[String::ToString](#tostring)|Gibt ein neues Zeichenfolgenobjekt zurück, dessen Wert mit der aktuellen Zeichenfolge identisch ist.|

**Operatoren**

Die Zeichenfolgenklasse hat die folgenden Operatoren.

|Member|Beschreibung|
|------------|-----------------|
|[String:: Operator ==-Operator](#operator-equality)|Gibt an, ob zwei angegebene Zeichenfolgenobjekte denselben Wert haben.|
|[operator+-Operator](#operator-plus)|Verkettet zwei Zeichenfolgeobjekte in ein neues Zeichenfolgeobjekt.|
|[String:: Operator >-Operator](#operator-greater-than)|Gibt an, ob der Wert eines Zeichenfolgenobjekts größer als der Wert eines zweiten Zeichenfolgenobjekts ist.|
|[String:: Operator > =-Operator](#operator-greater-than-or-equals)|Gibt an, ob der Wert eines String-Objekts größer oder gleich dem Wert eines zweiten String-Objekts ist.|
|[String:: Operator! =-Operator](#operator-inequality)|Gibt an, ob zwei angegebene Zeichenfolgenobjekte unterschiedliche Werte haben.|
|[String:: Operator <-Operator](#operator-less-than)|Gibt an, ob der Wert eines Zeichenfolgenobjekts kleiner als der Wert eines zweiten Zeichenfolgenobjekts ist.|

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Header** vccorlib.h (standardmäßig eingeschlossen)

## <a name="begin"></a>  String:: Begin-Methode

Gibt einen Zeiger auf den Anfang der aktuellen Zeichenfolge zurück.

### <a name="syntax"></a>Syntax

```cpp
char16* Begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Anfang der aktuellen Zeichenfolge.

## <a name="compareordinal"></a>  String:: CompareOrdinal-Methode

Vergleicht zwei `String` -Objekte durch Auswertung der numerischen Werte der entsprechenden Zeichen in den beiden Zeichenfolgenwerten, die durch die Objekte dargestellt werden.

### <a name="syntax"></a>Syntax

```cpp
int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste String-Objekt.

*str2*<br/>
Das zweite String-Objekt.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die lexikalische Beziehung zwischen den beiden Vergleichswerten angibt. In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:

|Wert|Bedingung|
|-----------|---------------|
|-1|`str1` ist kleiner als `str2`.|
|0|`str1` ist gleich `str2`.|
|1|`str1` ist größer als `str2`.|

## <a name="concat"></a>  String:: concat-Methode

Verkettet die Werte von zwei Zeichenfolgenobjekten.

### <a name="syntax"></a>Syntax

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste Zeichenfolgenobjekt oder `null`.

*str2*<br/>
Das zweite Zeichenfolgenobjekt oder `null`.

### <a name="return-value"></a>Rückgabewert

Ein neues Zeichenfolgen^-Objekt, dessen Wert die Verkettung der Werte von `str1` und `str2` ist.

Wenn `str1` `null` und `str2` ungleich null ist, wird `str1` zurückgegeben. Wenn `str2` `null` und `str1` ungleich null ist, wird `str2` zurückgegeben. Wenn `str1` und `str2` beide `null` sind, wird die leere Zeichenfolge (L "") zurückgegeben.

## <a name="data"></a>  String:: Data-Methode

Gibt einen Zeiger zum Anfang des Datenpuffers des Objekts als ein Array im C-Format mit `char16`-Elementen (`wchar_t`) zurück.

### <a name="syntax"></a>Syntax

```
const char16* Data();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Anfang einer `const char16` Array von Unicode-Zeichen (`char16` ist eine Typedef für `wchar_t`).

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Konvertieren von `Platform::String^` zu `wchar_t*`. Wenn das `String`-Objekt den Gültigkeitsbereich verlässt, ist die Gültigkeit des Datenzeigers nicht mehr sichergestellt. Zum Speichern der Daten nach Ablauf der Lebensdauer des ursprünglichen `String` -Objekts [Wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) das Array in den Speicher zu kopieren, die Sie selbst zugeordnet haben.

## <a name="dispose"></a>  String:: Dispose-Methode

Gibt Ressourcen frei.

### <a name="syntax"></a>Syntax

```cpp
virtual override void Dispose();
```

## <a name="end"></a>  String:: End-Methode

Gibt einen Zeiger nach dem Ende der aktuellen Zeichenfolge zurück.

### <a name="syntax"></a>Syntax

```cpp
char16* End();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger zur Übergabe des Endes der aktuellen Zeichenfolge.

### <a name="remarks"></a>Hinweise

End() gibt Begin() + Länge zurück.

## <a name="equals"></a>  String:: Equals-Methode

Gibt an, ob die angegebene Zeichenfolge über den gleichen Wert wie das aktuelle Objekt verfügt.

### <a name="syntax"></a>Syntax

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn `str` ist gleich dem aktuellen Objekt ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Diese Methode entspricht der [String:: CompareOrdinal](#compareordinal). In der ersten Überladung wird erwartet, dass der Parameter `str` zu einem String^-Objekt umgewandelt werden kann.

## <a name="gethashcode"></a>  String:: GetHashCode-Methode

Gibt den Hashcode für diese Instanz zurück.

### <a name="syntax"></a>Syntax

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Rückgabewert

Der Hashcode für diese Instanz.

## <a name="isempty"></a>  String:: isEmpty-Methode

Gibt an, ob das aktuelle String-Objekt leer ist.

### <a name="syntax"></a>Syntax

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `String` Objekt **null** oder eine leere Zeichenfolge (L"") ist, andernfalls **"false"**.

## <a name="isfastpass"></a>  String:: isfastpass-Methode

Gibt an, ob das aktuelle String-Objekt beteiligt ist eine *Schnelldurchlauf* Vorgang. Bei einem Fast-Pass-Vorgang wird die Verweiszählung angehalten.

### <a name="syntax"></a>Syntax

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `String` Objekt ist Fast-Pass; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Beim Aufruf einer Funktion, bei der ein Objekt mit Verweiszählung ein Parameter ist und die aufgerufene Funktion nur dieses Objekt liest, kann der Compiler die Verweiszählung sicher anhalten und die Aufrufleistung verbessern. Es gibt nichts nützliches, das Ihr Code mit dieser Eigenschaft ausführen kann. Das System behandelt alle Details.

## <a name="length"></a>  String:: Length-Methode

Ruft die Anzahl der Zeichen in der aktuellen `String` Objekt.

### <a name="syntax"></a>Syntax

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichen in der aktuellen `String` Objekt.

### <a name="remarks"></a>Hinweise

Die Länge einer Zeichenfolge ohne Zeichen ist null. Die Länge der folgenden Zeichenfolge ist 5:

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Das Zeichenarray, das zurückgegeben werden, indem die [String:: Data](#data) verfügt über ein zusätzliches Zeichen, das das abschließende NULL oder '\0' ist. Dieses Zeichen ist ebenfalls zwei Bytes lang.

## <a name="operator-plus"></a>  String:: Operator +-Operator

Verkettet die beiden [Zeichenfolge](../cppcx/platform-string-class.md) Objekte in ein neues [Zeichenfolge](../cppcx/platform-string-class.md) Objekt.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste `String`-Objekt.

*str2*<br/>
Das zweite `String`-Objekt, dessen Inhalt `str1` angefügt wird.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn *str1* gleich *str2*ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Dieser Operator erstellt ein `String^`-Objekt mit den Daten aus den zwei Operanden. Verwenden Sie es zur Vereinfachung, wenn nicht unbedingt extreme Leistung gefordert ist. Einige Aufrufe von "`+`" in einer Funktion werden sich wahrscheinlich nicht bemerkbar machen. Wenn Sie jedoch große Objekte oder Textdaten in einer kurzen Schleife bearbeiten, sollten Sie die standardmäßigen C++-Mechanismen und -typen verwenden.

##  <a name="operator-equality"></a> String:: Operator ==-Operator

Gibt an, ob zwei angegebene Zeichenfolgenobjekte denselben Textwert haben.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste zu vergleichende `String`-Objekt.

*str2*<br/>
Das zweite zu vergleichende `String`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der Inhalt des `str1` gleich `str2`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Dieser Operator entspricht [String:: CompareOrdinal](#compareordinal).

##  <a name="operator-greater-than"></a>  String:: Operator&gt;

Gibt an, ob der Wert eines `String` -Quellobjekt ist größer als der Wert eines zweiten `String` Objekt.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste `String`-Objekt.

*str2*<br/>
Das zweite `String`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der Wert des `str1` ist größer als der Wert des `str2`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Dieser Operator entspricht beim expliziten Aufruf [String:: CompareOrdinal](#compareordinal) und erhalten ein Ergebnis größer als 0 (null).

## <a name="operator-greater-than-or-equals"></a> String:: Operator&gt;=

Gibt an, ob der Wert eines `String` Objekt ist größer als oder gleich dem Wert eines zweiten `String` Objekt.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste `String`-Objekt.

*str2*<br/>
Das zweite `String`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der Wert des `str1` ist größer als oder gleich dem Wert des `str2`ist, andernfalls **"false"**.

## <a name="operator-inequality"></a> String:: Operator! =

Gibt an, ob zwei angegebene `String` -Objekte verschiedene Werte haben.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste zu vergleichende `String`-Objekt.

*str2*<br/>
Das zweite zu vergleichende `String`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn `str1` ist nicht gleich `str2`ist, andernfalls **"false"**.

## <a name="operator-less-than"></a> String:: Operator&lt;

Gibt an, ob der Wert eines `String` Objekt ist kleiner als der Wert eines zweiten `String` Objekt.

### <a name="syntax"></a>Syntax

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Das erste `String`-Objekt.

*str2*<br/>
Das zweite `String`-Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der Wert des *str1* ist kleiner als der Wert des *str2*ist, andernfalls **"false"**.

## <a name="ctor"></a> String:: String-Konstruktor

Initialisiert eine neue Instanz der dem `String` Klasse mit einer Kopie der eingabezeichenfolgendaten.

### <a name="syntax"></a>Syntax

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Parameter

*s*<br/>
Eine Reihe von Breitzeichen, die die Zeichenfolge initialisieren. char16

*n*<br/>
Eine Zahl, die die Länge der Zeichenfolge angibt.

### <a name="remarks"></a>Hinweise

Wenn Leistung wichtig ist, und Sie die Lebensdauer der Quellzeichenfolge steuern, können Sie [Platform:: stringreference](../cppcx/platform-stringreference-class.md) anstelle der Zeichenfolge.
### <a name="example"></a>Beispiel

```cpp
String^ s = L"Hello!";
```

## <a name="tostring"></a> String:: ToString

Gibt eine `String` Objekt, dessen Wert der aktuellen Zeichenfolge identisch.

### <a name="syntax"></a>Syntax

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Rückgabewert

Ein `String` Objekt, dessen Wert der aktuellen Zeichenfolge identisch.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)