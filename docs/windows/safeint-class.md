---
title: "SafeInt-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt-Klasse"
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 16
---
# SafeInt-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erweitert die ganzzahligen Primitiv, um zu helfen, Ganzzahlüberlauf zu hindern können Sie verschiedene Typen von ganzen Zahlen vergleichen.  
  
## Syntax  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### Parameter  
  
|Vorlage|**Beschreibung**|  
|-------------|----------------------|  
|T|Der Typ der ganzzahligen oder eines booleschen Parameters, den `SafeInt` ersetzt.|  
|E|Ein aufgelisteter Datentyp, der die Fehlerbehandlungsrichtlinie definiert.|  
|U|Der Typ der ganzzahligen oder eines booleschen Parameters für den sekundären Operanden.|  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|\[in\] rechte Seite|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehreren eigenständigen Funktionen darstellt.|  
|\[in i\]|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehreren eigenständigen Funktionen darstellt.|  
|\[in\] Bits|Ein Eingabeparameter, der den Wert auf der rechten Seite des Operators in mehreren eigenständigen Funktionen darstellt.|  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Standardkonstruktor.|  
  
### Zuweisungsoperatoren  
  
|Name|Syntax|  
|----------|------------|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### Umwandlungs\-Operatoren  
  
|Name|Syntax|  
|----------|------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|char mit Vorzeichen|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|\_\_int16|`operator __int16() const`|  
|unsigned \_\_int16|`operator unsigned __int16() const`|  
|\_\_int32|`operator __int32() const`|  
|unsigned \_\_int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|\_\_int64|`operator __int64() const`|  
|unsigned \_\_int64|`operator unsigned __int64() const`|  
|wchar\_t|`operator wchar_t() const`|  
  
### Vergleichsoperatoren  
  
|Name|Syntax|  
|----------|------------|  
|\<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|\<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|\>\=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|\>\=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|\>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|\>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|\<\=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|\<\=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|\=\=|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|\=\=|`bool operator== (bool rhs) const throw()`|  
|\=\=|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|\!\=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|\!\=|`bool operator!= (bool b) const throw()`|  
|\!\=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### Arithmetische Operatoren  
  
|Name|Syntax|  
|----------|------------|  
|\+|`const SafeInt<T,E>& operator+ () const throw()`|  
|\-|`SafeInt<T,E> operator- () const`|  
|\+\+|`SafeInt<T,E>& operator++ ()`|  
|\-\-|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|\*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|\*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|\*\=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|\/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|\/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|\/\=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|\+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|\+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|\+\=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|\-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|\-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|\-\=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### Logische Operatoren  
  
|Name|Syntax|  
|----------|------------|  
|\!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&\=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^\=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;\=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## Hinweise  
 Die `SafeInt`\-Klasse schützt vor Ganzzahlüberlauf in den mathematischen Operationen.  Beispielsweise sollten Sie erwägen, zwei 8\-Bit\-Ganzzahlen hinzuzufügen: ein den Wert 200 und das zweite über den Wert 100.  Der richtige mathematische Operation würde 200 \+ 100 \= 300 lauten.  Aufgrund der 8\-Bit\-Ganzzahl\-Grenze, ist das obere Bits verloren und der Compiler gibt 44 zurück \(300 \- 2\)<sup>8</sup> als das Ergebnis.  Jeder Vorgang, der von dieser mathematischen Formel abhängt, generiert unerwartetes Verhalten.  
  
 Die `SafeInt`\-Klasse überprüft, ob ein arithmetischer Überlauf auftritt, oder ob der Code versucht, einen Wert durch null zu dividieren.  In beiden Fällen wird die Klasse den Fehlerhandler auf, um das Programm des potenziellen Problems zu warnen.  
  
 Diese Klasse ermöglicht auch zwei verschiedene Typen Ganzzahlen vergleichen, solange sie `SafeInt`\-Objekte sind.  Normalerweise wenn Sie einen Vergleich ausführen, müssen Sie zuerst die Zahlen konvertieren, um der gleiche Typ.  Das Umwandeln einer Zahl in einen anderen Typ erfordert häufig Überprüfungen, sicherzustellen, dass kein Verlust von Daten gibt.  
  
 Die Operatortabelle in diesem Thema zeigt das mathematische auf die und Vergleichsoperatoren, die von `SafeInt` unterstützt werden, Klasse.  Die meisten mathematischen Operatoren geben ein `SafeInt`\-Objekt des Typs `T` zurück.  
  
 Vergleichsoperationen zwischen `SafeInt` und einen ganzzahligen Typ kann in jede Richtung ausgeführt werden.  Beispielsweise `SafeInt<int>(x) < y` und `y > SafeInt<int>(x)` sind gültig und werden demselben Ergebnis zurückgeben.  
  
 Viele binären Operatoren unterstützen nicht mit zwei verschiedenen `SafeInt`\-Typen.  Ein Beispiel dafür ist der Operator `&`.  `SafeInt<T, E> & int` wird unterstützt, `SafeInt<T, E> & SafeInt<U, E>` ist jedoch nicht.  Im letzten Beispiel der Compiler nicht weiß, welcher Typ des Parameters die zurückgegeben.  Eine Lösung dieses Problems besteht, den zweiten Parameter an eine Umwandlung.  Indem die gleichen Parameter verwendet, kann dies mit `SafeInt<T, E> & (U)SafeInt<U, E>` abgeschlossen werden.  
  
> [!NOTE]
>  Für alle bitweisen Operationen sollten den beiden verschiedenen Parameter die gleiche Größe sein.  Wenn Sie die Größen unterscheiden, löst der Compiler eine Ausnahme aus [ASSERT](../Topic/ASSERT%20\(MFC\).md).  Die Ergebnisse dieses Vorgangs können nicht festgelegt werden, um genau zu sein.  So beheben Sie dieses Problem, kleineren Parameter der Umwandlung ist, bis die gleiche Größe wie desto größer Parameter ist.  
  
 Für die Schiebeoperatoren anderem sind mehr Bits als für den Vorlagentyp auslösen eine ASSERTIONSausnahme.  Dies hat keinerlei Auswirkung im Releasemodus.  Zwei Typen SafeInt\-Parameter zu kombinieren ist für die Schiebeoperatoren möglich, da der Rückgabetyp dem ursprüngliche Typ ist.  Die Zahl auf der rechten Seite des Operators wird nur die Anzahl der Bits, um sich zu verschieben.  
  
 Wenn Sie einen Vergleich mit einem logischen SafeInt\-Objekt ausführen, ist der Vergleich ausschließlich arithmetisch.  Angenommen diese Ausdrücke:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 Die erste Anweisung ändert sich in `true`, aber an den zweiten Anweisungsbeschlüssen von `false`.  Die bitweise Negation von 0 ist 0xFFFFFFFF.  In der zweiten Anweisung vergleicht der Standardvergleichsoperator 0xFFFFFFFF zu 0xFFFFFFFF und betrachtet diese als gleich.  Der Vergleichsoperator für die `SafeInt`\-Klasse stellt fest, dass der zweite Parameter negativ ist, während der erste Parameter ohne Vorzeichen ist.  Daher obwohl die Bitdarstellung, überein realisiert der logische Operator `SafeInt`, dass die ganze Zahl ohne Vorzeichen größer als \-1 ist.  
  
 Seien Sie vorsichtig, wenn Sie die `SafeInt`\-Klasse zusammen mit dreifachen dem Operator `?:` verwenden.  Betrachten Sie die folgende Codezeile.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Der Compiler konvertiert sie in:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Wenn `flag``false` ist, löst der Compiler eine Ausnahme aus, anstatt, den Wert \-1 zuweisen `x`.  Um dieses Verhalten zu vermeiden, ist der richtige Code, um zu verwenden die folgende Zeile.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` und `U` können einen booleschen Typ, einem Zeichentyp oder ganzzahlige Typ zugewiesen werden.  Die ganzzahligen Typen können mit oder ohne Vorzeichen und jede Größe von 8 Bits auf 64 Bits sein.  
  
> [!NOTE]
>  Obwohl `SafeInt` die Klasse beliebige ganze Zahl akzeptiert, führt sie effizienter mit Typen ohne Vorzeichen aus.  
  
 `E` ist der Fehlerbehandlungsmechanismus, den `SafeInt` verwendet.  Zwei Fehlerbehandlungsmechanismen sind der SafeInt\-Bibliothek bereitgestellt.  Gemäß Standardrichtlinie ist `SafeIntErrorPolicy_SafeIntException`, die eine [SafeIntException\-Klasse](../windows/safeintexception-class.md) Ausnahme auslöst, wenn ein Fehler auftritt.  Die weitere Beibehaltungsrichtlinie ist `SafeIntErrorPolicy_InvalidParameter`, die das Programm beendet, wenn ein Fehler auftritt.  
  
 Es gibt zwei Optionen, die Fehlerrichtlinie anzupassen.  Die erste Option besteht darin, den Parameter `E` festzulegen, wenn Sie `SafeInt` erstellen.  Verwenden Sie diese Option, wenn Sie die Fehlerbehandlungsrichtlinie für nur ein `SafeInt` ändern möchten.  Die andere Option ist, `_SAFEINT_DEFAULT_ERROR_POLICY` zu definieren, um die benutzerdefinierte Fehlerbehandlungsklasse sein, bevor Sie die Bibliothek `SafeInt` einschließen.  Verwenden Sie diese Option, wenn Sie die Standardfehlerbehandlungsrichtlinie für alle Instanzen der `SafeInt`\-Klasse im Code ändern möchten.  
  
> [!NOTE]
>  Eine benutzerdefinierte Klasse, Fehler der SafeInt\-Bibliothek behandelt, sollte Steuerelement nicht an den Code zurückgegeben, der den Fehlerhandler aufgerufen wurden.  Nachdem der Fehlerhandler aufgerufen wurde, kann das Ergebnis des Vorgangs `SafeInt` nicht vertrauenswürdig.  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## Siehe auch  
 [Miscellaneous Support Libraries Classes](assetId:///406fd46e-d53f-4096-ab40-36aa754c7a5c)   
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeIntException\-Klasse](../windows/safeintexception-class.md)