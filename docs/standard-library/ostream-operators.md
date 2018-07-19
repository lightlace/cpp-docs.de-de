---
title: '&lt;ostream&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::operator&lt;&lt;
dev_langs:
- C++
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4819f5b5d5d6a16720bce29dd176fd0eb873014a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955932"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt;-Operatoren

||
|-|
|[operator&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a> operator&lt;&lt;

Schreibt verschiedene Typen in den Stream.

```cpp
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```

### <a name="parameters"></a>Parameter

*_Ch* ein Zeichen.

*_Elem* Typ des Elements.

*_Ostr* ein `basic_ostream` Objekt.

*Str* einer Zeichenfolge.

*_Tr* "traits"-Zeichen.

*Val* den Typ

### <a name="return-value"></a>Rückgabewert

Der Stream (Datenstrom).

### <a name="remarks"></a>Hinweise

Die `basic_ostream`-Klasse definiert außerdem mehrere Einfügeoperatoren. Weitere Informationen finden Sie unter [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Die Vorlagenfunktion

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

Bestimmt die Länge N = `traits_type::` [Länge](../standard-library/char-traits-struct.md#length)(`str`) am Anfang der Sequenz *str*, und fügt die Sequenz. Wenn N < `_Ostr.`[width](../standard-library/ios-base-class.md#width), fügt die Funktion auch eine Wiederholung von `_Ostr.width`-N-Füllzeichen ein. Die Wiederholung geht der Sequenz voraus, wenn (`_Ostr`. [flags](../standard-library/ios-base-class.md#flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). Andernfalls folgt die Wiederholung der Sequenz. Die Funktion gibt *_Ostr*.

Die Vorlagenfunktion

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

fügt das Element `_Ch` ein. Wenn 1 < `_Ostr.width`, dann fügt die Funktion auch eine Wiederholung von `_Ostr.width`-1 Füllzeichen hinzu. Die Wiederholung geht der Sequenz voraus, wenn ( `_Ostr.flags & adjustfield != left`. Andernfalls folgt die Wiederholung der Sequenz. Es gibt *_Ostr*.

Die Vorlagenfunktion

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

verhält sich so wie

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

mit dem Unterschied, dass jedes Element *_Ch* am Anfang der Sequenz *str* wird in ein Objekt des Typs konvertiert `Elem` durch Aufrufen von `_Ostr.` [put](../standard-library/basic-ostream-class.md#put)(`_Ostr.` [widen](../standard-library/basic-ios-class.md#widen)(`_Ch`)).

Die Vorlagenfunktion

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

verhält sich so wie

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

mit dem Unterschied, dass *_Ch* wird in ein Objekt des Typs konvertiert `Elem` durch Aufrufen von `_Ostr.put`( `_Ostr.widen`( `_Ch`)).

Die Vorlagenfunktion

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

verhält sich so wie

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(Sie muss die Elemente nicht erweitern, bevor sie eingefügt werden.)

Die Vorlagenfunktion

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

verhält sich so wie

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(Es muss keine widen *_Ch* vor dem Einfügen.)

Die Vorlagenfunktion

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

Gibt `_Ostr` << (`const char *`) `str`.

Die Vorlagenfunktion

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

Gibt `_Ostr` << (`char`) `_Ch`.

Die Vorlagenfunktion:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

Gibt `_Ostr` << (`const char *`) `str`.

Die Vorlagenfunktion:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

Gibt `_Ostr` << (`char`) `_Ch`.

Die Vorlagenfunktion:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

gibt `_Ostr` `<<` `val` zurück (und konvertiert einen [RValue-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md) zu `_Ostr` zu einem lvalue im Prozess).

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator<<` finden Sie unter [flush](../standard-library/ostream-functions.md#flush).

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)<br/>
