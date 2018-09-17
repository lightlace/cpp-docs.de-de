---
title: SafeInt-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b765f6393b9bd2d632539abb5fb7cd17c29297b6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701752"
---
# <a name="safeint-class"></a>SafeInt-Klasse

Erweitert die primitiven ganze Zahl, um Ganzzahlüberlauf zu vermeiden, und können Sie verschiedene Arten von ganzen Zahlen vergleichen.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Parameter

|Vorlage|Beschreibung|
|--------------|-----------------|
|T|Der Typ der ganze Zahl oder booleschen Parameter, die **SafeInt** ersetzt.|
|E|Ein Aufzählungsdatentyp, der die fehlerbehandlungsrichtlinie definiert.|
|U|Der Typ der ganze Zahl oder booleschen Parameter für den zweiten Operanden.|

|Parameter|Beschreibung|
|---------------|-----------------|
|*RS*|[in] Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|
|*i*|[in] Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|
|*Bits*|[in] Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Standardkonstruktor|

### <a name="assignment-operators"></a>Zuweisungsoperatoren

|name|Syntax|
|----------|------------|
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|
|=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|
|=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|

### <a name="casting-operators"></a>Umwandlungsoperatoren

|name|Syntax|
|----------|------------|
|bool|`operator bool() throw()`|
|char|`operator char() const`|
|char mit Vorzeichen|`operator signed char() const`|
|unsigned char|`operator unsigned char() const`|
|__int16|`operator __int16() const`|
|unsigned __int16|`operator unsigned __int16() const`|
|__int32|`operator __int32() const`|
|unsigned __int32|`operator unsigned __int32() const`|
|long|`operator long() const`|
|unsigned long|`operator unsigned long() const`|
|__int64|`operator __int64() const`|
|unsigned __int64|`operator unsigned __int64() const`|
|wchar_t|`operator wchar_t() const`|

### <a name="comparison-operators"></a>Vergleichsoperatoren

|name|Syntax|
|----------|------------|
|<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|
|<|`bool operator< (SafeInt<T,E> rhs) const throw()`|
|>=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|
|>=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|
|>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|
|>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|
|<=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|
|<=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|
|==|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|
|==|`bool operator== (bool rhs) const throw()`|
|==|`bool operator== (SafeInt<T,E> rhs) const throw()`|
|!=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|
|!=|`bool operator!= (bool b) const throw()`|
|!=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|

### <a name="arithmetic-operators"></a>Arithmetische Operatoren

|name|Syntax|
|----------|------------|
|+|`const SafeInt<T,E>& operator+ () const throw()`|
|-|`SafeInt<T,E> operator- () const`|
|++|`SafeInt<T,E>& operator++ ()`|
|--|`SafeInt<T,E>& operator-- ()`|
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|
|*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|
|*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|
|*=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|
|/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|
|/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|
|/=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|
|+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|
|+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|
|+=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|
|-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|
|-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|
|-=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|

### <a name="logical-operators"></a>Logische Operatoren

|name|Syntax|
|----------|------------|
|!|`bool operator !() const throw()`|
|~|`SafeInt<T,E> operator~ () const throw()`|
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|
|&=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|
|^=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|
|&#124;=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|

## <a name="remarks"></a>Hinweise

Die **SafeInt** -Klasse schützt vor Ganzzahlüberlauf in mathematischen Operationen. Betrachten Sie beispielsweise das Hinzufügen von zwei 8-Bit-Ganzzahlen: einen Wert von 200 vorhanden, und die zweite hat einen Wert von 100. Die richtige mathematische Operation wäre 200 + 100 = 300. Jedoch aufgrund des Limits 8-Bit-Ganzzahl-oberen Bits verloren, und der Compiler gibt 44 zurück (300-2-<sup>8</sup>) als Ergebnis. Jeder Vorgang, der von diesem mathematische Gleichung abhängig ist, wird unerwartetem Verhalten kommen.

Die **SafeInt** Klasse überprüft, ob ein arithmetischer Überlauf auftritt, oder gibt an, ob der Code versucht, Division durch 0 (null). In beiden Fällen Ruft die Klasse den Fehlerhandler, um die Anwendung des möglichen Problems zu warnen.

Diese Klasse können Sie zwei verschiedene Arten von ganzen Zahlen vergleichen, solange sie sind auch **SafeInt** Objekte. In der Regel, wenn Sie einen Vergleich durchführen, müssen Sie zuerst die Zahlen den gleichen Typ konvertieren. Eine Zahl in einen anderen Typ häufig umwandeln wird überprüft, um sicherzustellen, dass es keinen Verlust von Daten gibt erfordert.

In diesem Thema in die entsprechenden Tabelle listet die mathematischen und Vergleich-Operatoren, die von unterstützt die **SafeInt** Klasse. Die meisten mathematische Operatoren Zurückgeben einer **SafeInt** Objekt des Typs `T`.

Vergleichsvorgänge zwischen einem **SafeInt** und ein ganzzahliger Typ kann in beide Richtungen ausgeführt werden. Z. B. `SafeInt<int>(x) < y` und `y> SafeInt<int>(x)` gültig sind und das gleiche Ergebnis zurückgegeben wird.

Viele binäre Operatoren nicht unterstützen zwei verschiedene **SafeInt** Typen. Ein Beispiel hierfür ist die `&` Operator. `SafeInt<T, E> & int` wird unterstützt, aber `SafeInt<T, E> & SafeInt<U, E>` nicht. Im zweiten Beispiel weiß der Compiler nicht Art der Parameter, um zurückzugeben. Eine Lösung, um dieses Problem ist die Umwandlung des zweiten Parameters für den Basistyp zurück. Verwenden Sie die gleichen Parameter, dies kann erfolgen mit `SafeInt<T, E> & (U)SafeInt<U, E>`.

> [!NOTE]
> Für bitweise Vorgänge aus sollte die beiden anderen Parameter gleich groß sein. Wenn die Größen unterschiedlich sind, löst der Compiler eine [ASSERT](../mfc/reference/diagnostic-services.md#assert) Ausnahme. Die Ergebnisse dieses Vorgangs können nicht garantiert werden, präzise sein. Um dieses Problem zu beheben, wandeln Sie Parameters kleiner, bis sie die gleiche Größe wie der Parameter größer ist.

Für die Shift-Operatoren löst Verschiebung Weitere Bits als für den Vorlagentyp vorhanden sind ASSERT eine Ausnahme. Dies hat keine Auswirkungen im Releasemodus. Das Kombinieren von zwei Arten von SafeInt-Parameter ist der Shift-Operatoren möglich, da der Rückgabetyp, die den ursprünglichen Typ identisch ist. Die Anzahl auf der rechten Seite des Operators gibt nur die Anzahl der zu verschiebenden Bits.

Wenn Sie einen logischen Vergleich mit einem SafeInt-Objekt durchführen, ist der Vergleich streng arithmetische. Betrachten Sie beispielsweise die folgenden Ausdrücke:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

Die erste Anweisung in aufgelöst **"true"**, aber die zweite Anweisung löst in **"false"**. Die bitweise Negation von 0 ist 0xFFFFFFFF. In der zweiten Anweisung wird der standardvergleichsoperator "0xFFFFFFFF", "0xFFFFFFFF" vergleicht, und Sie werden diese gleich sind. Der Vergleichsoperator für die **SafeInt** Klasse erkennt, dass der zweite Parameter negativ ist, während der erste Parameter ohne Vorzeichen ist. Aus diesem Grund, obwohl die Darstellung identisch sind, ist die **SafeInt** logischer Operator erkennt, dass die Ganzzahl ohne Vorzeichen größer als-1 ist.

Seien Sie vorsichtig bei der Verwendung der **SafeInt** -Klasse zusammen mit den `?:` ternärer Operator. Erwägen Sie die folgende Codezeile ein.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Der Compiler konvertiert in dieses:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

Wenn `flag` ist **"false"**, der Compiler löst eine Ausnahme aus, anstatt den Wert von-1 bis `x`. Um dieses Verhalten zu vermeiden, ist daher der korrekte Code verwendet die folgende Zeile an.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` und `U` kann eine Boolean-Typ, Typ oder Integer-Typ zugewiesen werden. Die ganzzahligen Typen mit oder ohne Vorzeichen werden können, und beliebiger Größe von 8 Bits bis 64 Bits.

> [!NOTE]
> Obwohl die **SafeInt** -Klasse akzeptiert beliebige ganze Zahl, führt Sie effizienter mit Typen ohne Vorzeichen.

`E` ist der Mechanismus zur Fehlerbehandlung, **SafeInt** verwendet. Zwei Mechanismen für die Fehlerbehandlung werden mit der SafeInt-Bibliothek bereitgestellt. Die Standardrichtlinie ist `SafeIntErrorPolicy_SafeIntException`, welche löst eine [SafeIntException-Klasse](../windows/safeintexception-class.md) Ausnahme aus, wenn ein Fehler auftritt. Die andere Richtlinie lautet `SafeIntErrorPolicy_InvalidParameter`, wodurch das Programm beendet wird, wenn ein Fehler auftritt.

Es gibt zwei Optionen zur Optimierung der fehlerrichtlinie. Die erste Möglichkeit besteht, den Parameter festzulegende `E` bei der Erstellung einer **SafeInt**. Verwenden Sie diese Option aus, wenn Sie, ändern Sie die fehlerbehandlungsrichtlinie für nur eine möchten **SafeInt**. Die andere Option besteht, definieren Sie _SAFEINT_DEFAULT_ERROR_POLICY, um die benutzerdefinierte Fehlerbehandlung-Klasse sein, bevor Sie Einfügen der **SafeInt** Bibliothek. Verwenden Sie diese Option aus, wenn Sie, ändern Sie die Standard-fehlerbehandlungsrichtlinie für alle Instanzen von möchten der **SafeInt** Klasse in Ihrem Code.

> [!NOTE]
> Eine benutzerdefinierte Klasse, die Fehler aus der SafeInt-Bibliothek behandelt sollten Steuerelement nicht auf den Code zurück, die den Fehlerhandler aufgerufen. Nachdem der Fehlerhandler aufgerufen wird, wird das Ergebnis der **SafeInt** Vorgang kann nicht vertrauenswürdig.

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** MSL:: Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Bibliothek](../windows/safeint-library.md)  
[SafeIntException-Klasse](../windows/safeintexception-class.md)