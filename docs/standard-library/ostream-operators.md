---
title: '&lt;ostream&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 72389624e776a2e8334490c37a5ca628e033ffaa
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt;-Operatoren
||  
|-|  
|[operator&lt;&lt;](#operator_lt__lt_)|  
  
##  <a name="operator_lt__lt_"></a> operator&lt;&lt;  
 Schreibt verschiedene Typen in den Stream.  
  
```
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
 `_Ch`  
 Ein Zeichen.  
  
 `_Elem`  
 Der Elementtyp.  
  
 `_Ostr`  
 Ein `basic_ostream`-Objekt.  
  
 `str`  
 Eine Zeichenfolge.  
  
 `_Tr`  
 Zeichenmerkmale.  
  
 `val`  
 Der Typ  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stream (Datenstrom).  
  
### <a name="remarks"></a>Hinweise  
 Die `basic_ostream`-Klasse definiert außerdem mehrere Einfügeoperatoren. Weitere Informationen finden Sie unter [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt_).  
  
 Die Vorlagenfunktion  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```  
  
 bestimmt die Länge N = `traits_type::`[length](../standard-library/char-traits-struct.md#char_traits__length)( `str`) am Anfang der Sequenz an `str`, und fügt die Sequenz ein. Wenn N < `_Ostr.`[width](../standard-library/ios-base-class.md#ios_base__width), fügt die Funktion auch eine Wiederholung von `_Ostr.``width`-N-Füllzeichen ein. Die Wiederholung geht der Sequenz voraus, wenn ( `_Ostr`. [flags](../standard-library/ios-base-class.md#ios_base__flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). Andernfalls folgt die Wiederholung der Sequenz. Die Funktion gibt `_Ostr` zurück.  
  
 Die Vorlagenfunktion  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 fügt das Element `_Ch` ein. Wenn 1 < `_Ostr.width`, dann fügt die Funktion auch eine Wiederholung von `_Ostr.width`-1 Füllzeichen hinzu. Die Wiederholung geht der Sequenz voraus, wenn ( `_Ostr.flags & adjustfield != left`. Andernfalls folgt die Wiederholung der Sequenz. Er gibt `_Ostr` zurück.  
  
 Die Vorlagenfunktion  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```  
  
 verhält sich so  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```  
  
 mit dem Unterschied, dass jedes Element `_Ch` der Sequenz beginnend bei `str` in ein Objekt vom Typ `Elem` konvertiert wird, indem `_Ostr.`[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `_Ostr.`[widen](../standard-library/basic-ios-class.md#basic_ios__widen)( `_Ch`)) aufgerufen wird.  
  
 Die Vorlagenfunktion  
  
``cpp template <class _Elem, class _Tr> basic_ostream<Elem, _Tr>& operator<<( basic_ostream<Elem, _Tr>& _Ostr, char _Ch);
```  
  
 behaves the same as  
  
```cpp  
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```  
  
 mit der Ausnahme, dass `_Ch` in ein Objekt vom Typ `Elem` konvertiert wird, indem `_Ostr.put`( `_Ostr.widen`( `_Ch`)) aufgerufen wird.  
  
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
  
 (Sie muss die `_Ch` nicht erweitern, bevor sie eingefügt werden.)  
  
 Die Vorlagenfunktion  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```  
  
 gibt `_Ostr` << ( `const char *`) `str` zurück.  
  
 Die Vorlagenfunktion  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```  
  
 gibt `_Ostr` << ( `char`) `_Ch` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```  
  
 gibt `_Ostr` << ( `const char *`) `str` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```  
  
 gibt `_Ostr` << ( `char`) `_Ch` zurück.  
  
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
 [\<ostream>](../standard-library/ostream.md)




