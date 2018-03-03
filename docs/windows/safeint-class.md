---
title: SafeInt-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea076ea092257fd5bf6acd6d597f79ef42dd96f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="safeint-class"></a>SafeInt-Klasse
Erweitert die ganze Zahl primitiven zur Vermeidung von Ganzzahlüberlauf und können Sie verschiedene Typen von ganzen Zahlen zu vergleichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Vorlage|Beschreibung|  
|--------------|-----------------|  
|T|Der Typ des ganze Zahl oder einen booleschen Parameter, die `SafeInt` ersetzt.|  
|E|Enumerierten Datentyps, der den Fehler bei der Verarbeitung der Richtlinie definiert.|  
|U|Der Typ der ganze Zahl oder einen booleschen Parameter für den zweiten Operanden.|  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] rhs|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|  
|[in] ich|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|  
|[in] bits|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehrere eigenständige Funktionen darstellt.|  
  
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
 Die `SafeInt` -Klasse schützt vor Ganzzahlüberlauf in mathematischen Operationen. Betrachten Sie beispielsweise das Hinzufügen von zwei 8-Bit-Ganzzahlen: eine hat einen Wert von 200 und der zweites Wert 100. Die richtige mathematische Operation wäre 200 + 100 = 300. Jedoch aufgrund der Grenzwert 8-Bit-Ganzzahl-obere Bit verloren, und der Compiler gibt 44 zurück (300 2<sup>8</sup>) als Ergebnis. Jeder Vorgang, der von dieser mathematischen Gleichung abhängt generiert ein unerwartetes Verhalten.  
  
 Die `SafeInt` -Klasse überprüft, ob ein arithmetischer Überlauf auftritt, oder gibt an, ob der Code versucht, Division durch Null auszuführen. In beiden Fällen Ruft die Klasse der Fehlerhandler das Programm die potenziellen Problem warnt.  
  
 Diese Klasse ermöglicht Ihnen, zwei verschiedene Arten von ganzen Zahlen zu vergleichen, solange sie sind auch `SafeInt` Objekte. In der Regel, wenn Sie einen Vergleich durchzuführen, müssen Sie zuerst die Zahlen, um die vom selben Typ sein konvertieren. Eine Zahl in einen anderen Typ häufig Umwandlung erfordert überprüft, um sicherzustellen, dass kein Verlust der Daten vorhanden ist.  
  
 In die entsprechenden Tabelle in diesem Thema listet die Vergleich und mathematischen Operatoren, die von unterstützt die `SafeInt` Klasse. Die meisten mathematische Operatoren geben eine `SafeInt` Objekt des Typs `T`.  
  
 Vergleichsvorgänge zwischen einem `SafeInt` und ein ganzzahliger Typ in beide Richtungen erfolgen kann. Beispielsweise beide `SafeInt<int>(x) < y` und `y > SafeInt<int>(x)` gültig sind, und gibt das gleiche Ergebnis zurück.  
  
 Viele binäre Operatoren nicht unterstützen zwei verschiedene `SafeInt` Typen. Ein Beispiel hierfür ist die `&` Operator. `SafeInt<T, E> & int`wird unterstützt, aber `SafeInt<T, E> & SafeInt<U, E>` nicht. Im letzteren Beispiel weiß der Compiler nicht Art des zurückzugebenden Parameters. Eine Lösung für dieses Problem ist den zweiten Parameter wieder auf den Basistyp umgewandelt. Verwenden Sie die gleichen Parameter, dies erreichen Sie mit `SafeInt<T, E> & (U)SafeInt<U, E>`.  
  
> [!NOTE]
>  Für alle bitweisen Operationen sollten die zwei verschiedenen Parameter genauso groß sein. Wenn die Größen unterschiedlich sind, löst der Compiler eine [ASSERT](../mfc/reference/diagnostic-services.md#assert) Ausnahme. Die Ergebnisse dieses Vorgangs können nicht garantiert werden, genau sein. Um dieses Problem zu beheben, wandeln Sie den kleineren Parameter, bis sie die gleiche Größe wie der Parameter größer ist.  
  
 Für die Schiebeoperatoren löst verschieben mehr Bits, als für den Vorlagentyp vorhanden ASSERT eine Ausnahme. Dies wird im Releasemodus keine Auswirkungen haben. Kombinieren von zwei Arten von SafeInt-Parameter ist für Shift-Operatoren möglich, da der Rückgabetyp identisch mit den ursprünglichen Typ ist. Die Anzahl auf der rechten Seite des Operators gibt nur die Anzahl der zu verschiebenden Bits.  
  
 Wenn Sie einen logischen Vergleich mit einem SafeInt-Objekt ausführen, ist der Vergleich streng arithmetische. Betrachten Sie beispielsweise diese Ausdrücke aus:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 Die erste Anweisung löst in `true`, aber die zweite Anweisung löst in `false`. Die bitweise Negation von 0 ist 0xFFFFFFFF. In der zweiten Anweisung wird der standardvergleichsoperator 0xFFFFFFFF auf 0xFFFFFFFF vergleicht, und Sie werden als gleich betrachtet. Der Vergleichsoperator für die `SafeInt` Klasse erkennt, dass der zweite Parameter negativ ist, während der erste Parameter nicht signiert ist. Aus diesem Grund, obwohl die Darstellung identisch sind, ist die `SafeInt` logischer Operator erkennt, dass die Ganzzahl ohne Vorzeichen größer als-1 ist.  
  
 Achten Sie bei der Verwendung der `SafeInt` -Klasse zusammen mit der `?:` ternärer Operator. Betrachten Sie die folgende Codezeile ein.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Der Compiler konvertiert in diese:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Wenn `flag` ist `false`, der Compiler löst eine Ausnahme aus, statt den Wert von-1 bis zuweisen `x`. Um dieses Verhalten zu vermeiden, ist daher der richtige Code verwendet die folgende Zeile an.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T`und `U` kann ein Boolean-Typ, Zeichentyp oder Integer-Typ zugewiesen werden. Die ganzzahligen Typen mit oder ohne Vorzeichen sein können und beliebiger Größe von 8 Bit zu 64 Bit.  
  
> [!NOTE]
>  Obwohl die `SafeInt` Klasse akzeptiert alle Arten von Integer, arbeitet effizienter, mit dem Typen ohne Vorzeichen.  
  
 `E`ist der Mechanismus zur Behandlung von Fehler, `SafeInt` verwendet. Zwei Mechanismen für die Fehlerbehandlung werden mit der SafeInt-Bibliothek bereitgestellt. Die Standardrichtlinie ist `SafeIntErrorPolicy_SafeIntException`, wodurch eine [SafeIntException-Klasse](../windows/safeintexception-class.md) -Ausnahme aus, wenn ein Fehler auftritt. Die andere Richtlinie ist `SafeIntErrorPolicy_InvalidParameter`, die das Programm beendet wird, wenn ein Fehler auftritt.  
  
 Es gibt zwei Optionen, um die Richtlinie Fehler anpassen. Die erste Möglichkeit besteht in der Parametersatz `E` beim Erstellen einer `SafeInt`. Verwenden Sie diese Option aus, wenn Sie den Fehler bei der Verarbeitung der Richtlinie für nur einen ändern möchten `SafeInt`. Die andere Möglichkeit besteht darin zu definieren `_SAFEINT_DEFAULT_ERROR_POLICY` Ihrer benutzerdefinierten Fehlerbehandlungs-Klasse sein, bevor Sie Einfügen der `SafeInt` Bibliothek. Verwenden Sie diese Option aus, wenn Sie die Richtlinie für alle Instanzen der standardmäßige Fehlerbehandlung ändern möchten die `SafeInt` Klasse in Ihrem Code.  
  
> [!NOTE]
>  Eine benutzerdefinierte Klasse, die Fehler aus der SafeInt-Bibliothek behandelt sollte kein Steuerelement an den Code zurück, die den Fehlerhandler aufgerufen. Nachdem der Fehlerhandler aufgerufen wird, wird das Ergebnis der `SafeInt` Vorgang kann nicht vertraut werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeIntException-Klasse](../windows/safeintexception-class.md)