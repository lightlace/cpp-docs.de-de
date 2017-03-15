---
title: duration-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration
dev_langs:
- C++
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 843e4954b3a5b20d504dd5c8bf582dc56d4cbcbd
ms.lasthandoff: 02/24/2017

---
# <a name="duration-class"></a>duration-Klasse
Beschreibt einen Typ, der ein *Zeitintervall* enthält, bei dem es sich um die verstrichene Zeit zwischen zwei Situationen handelt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Rep, class Period = ratio<1>>  
class duration;  
template <class Rep, class Period>  
class duration;  
template <class Rep, class Period1, class Period2>  
class duration <duration<Rep, Period1>, Period2>;  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit dem Vorlagenargument `Rep` wird der Typ beschrieben, der zum Aufnehmen der Anzahl von Zeiteinheiten im Intervall verwendet wird. Das template-Argument `Period` ist eine Instanziierung von [ratio](../standard-library/ratio.md), mit dem die Größe des von jeder Zeiteinheit dargestellten Intervalls beschrieben wird.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|duration::period Typedef|Stellt ein Synonym für den Vorlagenparameter `Period` dar.|  
|duration::rep Typedef|Stellt ein Synonym für den Vorlagenparameter `Rep` dar.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[duration::duration-Konstruktor](#duration__duration_constructor)|Erstellt ein `duration`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[duration::count](#duration__count_method)|Gibt die Anzahl von Zeiteinheiten im Zeitintervall zurück.|  
|[duration::max](#duration__max_method)|Statisch Gibt den maximal zulässigen Wert des Vorlagenparameters `Ref` zurück.|  
|[duration::min](#duration__min_method)|Statisch Gibt den niedrigsten zulässigen Wert des Vorlagenparameters `Ref` zurück.|  
|[duration::zero](#duration__zero_method)|Statisch Tatsächlich wird `Rep`(0) zurückgegeben.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[duration::operator-](#duration__operator-)|Gibt eine Kopie des `duration`-Objekts zusammen mit einer negierten Taktanzahl zurück.|  
|[duration::operator--](#duration__operator--)|Verringert die gespeicherte Taktanzahl.|  
|[duration::operator=](#duration__operator_eq)|Reduziert die gespeicherte Taktanzahl-Modulo um einen angegebenen Wert.|  
|[duration::operator*=](#duration__operator_star_eq)|Multipliziert die gespeicherte Taktanzahl mit einem angegebenen Wert.|  
|[duration::operator/=](#duration__operator__eq)|Dividiert die gespeicherte Taktanzahl durch die Taktanzahl eines angegebenen `duration`-Objekts.|  
|[duration::operator+](#duration__operator_add)|Gibt `*this`zurück.|  
|[duration::operator++](#duration__operator_add_add)|Erhöht die gespeicherte Taktanzahl.|  
|[duration::operator+=](#duration__operator_add_eq)|Fügt der gespeicherten Taktanzahl die Taktanzahl eines angegebenen `duration`-Objekts hinzu.|  
|[duration::operator-=](#duration__operator-_eq)|Subtrahiert die Taktanzahl eines angegebenen `duration`-Objekts von der gespeicherten Taktanzahl.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
##  <a name="a-namedurationcountmethoda--durationcount"></a><a name="duration__count_method"></a> duration::count  
 Ruft die Anzahl von Zeiteinheiten im Zeitintervall ab.  
  
```  
constexpr Rep count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Zeiteinheiten im Zeitintervall.  
  
##  <a name="a-namedurationdurationconstructora--durationduration-constructor"></a><a name="duration__duration_constructor"></a> duration::duration-Konstruktor  
 Erstellt ein `duration`-Objekt.  
  
```  
constexpr duration() = default;  
 
template <class Rep2>  
constexpr explicit duration(const Rep2& R);

 
template <class Rep2, class Period2>  
constexpr duration(const duration<Rep2, Period2>& Dur);
```  
  
### <a name="parameters"></a>Parameter  
 `Rep2`  
 Ein arithmetischer Typ, der die Anzahl von Zeiteinheiten darstellt.  
  
 `Period2`  
 Eine `std::ratio`-Vorlagenspezialisierung zur Darstellung des Zeitraums von Zeiteinheiten in Sekunden.  
  
 `R`  
 Die Anzahl der Zeiteinheiten der Standardperiode.  
  
 `Dur`  
 Die Anzahl von Zeiteinheiten des durch `Period2` angegebenen Zeitraums.  
  
### <a name="remarks"></a>Hinweise  
 Vom Standardkonstruktor wird ein nicht initialisiertes Objekt erstellt. Durch die Wertinitialisierung mithilfe von leeren Klammern wird ein Objekt initialisiert, das ein Zeitintervall mit null Zeiteinheiten darstellt.  
  
 Der zweite Konstruktor, der ein template-Argument akzeptiert, erzeugt ein Objekt, das unter Verwendung einer Standardperiode von `std::ratio<1>` ein Zeitintervall mit `R` Zeiteinheiten darstellt. Um das Abrunden der Taktanzahl zu vermeiden, ist das Erstellen eines Dauerobjekts des Darstellungstyps `Rep2`, das als Gleitkommatyp behandelt werden kann, wenn `duration::rep` nicht als Gleitkommatyp behandelt werden kann, ein Fehler.  
  
 Der dritte Konstruktor, der zwei template-Argumente akzeptiert, erzeugt ein Objekt, das ein Zeitintervall darstellt, dessen Länge dem von `Dur` angegebenen Zeitintervall entspricht. Um die Verkürzung von Taktanzahlen zu vermeiden, ist das Erstellen eines Dauerobjekts aus einem anderen Dauerobjekt, dessen Typ mit dem Zieltyp *unvereinbar* ist, ein Fehler.  
  
 Ein `D1`-Dauertyp ist mit einem anderen Dauertyp `D2` *unvereinbar*, wenn `D2` nicht als Gleitkommatyp behandelt werden kann und [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) nicht 1 ist.  
  
 Sofern `Rep2` nicht implizit in `rep` konvertiert werden kann und `treat_as_floating_point<rep>` nicht *TRUE* oder `treat_as_floating_point<Rep2>` nicht *FALSE* ist, wird der zweite Konstruktor nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).  
  
 Sofern kein Überlauf in die Konvertierung induziert wurde und `treat_as_floating_point<rep>` nicht *TRUE* ist bzw. beide `ratio_divide<Period2, period>::den` nicht 1 entsprechen und `treat_as_floating_point<Rep2>` nicht *FALSE* ist, wird der dritte Konstruktor nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-namedurationmaxmethoda--durationmax"></a><a name="duration__max_method"></a> duration::max  
 Statische Methode, von der die Obergrenze für Werte vom Vorlagenparametertyp `Ref` zurückgegeben wird.  
  
```  
static constexpr duration max();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `duration(duration_values<rep>::max())` zurückgegeben.  
  
##  <a name="a-namedurationminmethoda--durationmin"></a><a name="duration__min_method"></a> duration::min  
 Statische Methode, von der die Untergrenze für Werte vom Vorlagenparametertyp `Ref` zurückgegeben wird.  
  
```  
static constexpr duration min();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Tatsächlich wird `duration(duration_values<rep>::min())` zurückgegeben.  
  
##  <a name="a-namedurationoperator-a--durationoperator-"></a><a name="duration__operator-"></a> duration::operator-  
 Gibt eine Kopie des `duration`-Objekts zusammen mit einer negierten Taktanzahl zurück.  
  
```  
constexpr duration operator-() const;
```  
  
##  <a name="a-namedurationoperator--a--durationoperator--"></a><a name="duration__operator--"></a> duration::operator--  
 Verringert die gespeicherte Taktanzahl.  
  
```  
duration& operator--();

duration operator--(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Methode gibt `*this` zurück.  
  
 Die zweite Methode gibt eine Kopie von `*this` zurück, die vor dem Verringern erstellt wird.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator_eq"></a> duration::operator=  
 Reduziert die gespeicherte Taktanzahl-Modulo um einen angegebenen Wert.  
  
```  
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Parameter  
 `Div`  
 Für die erste Methode stellt `Div` eine Taktanzahl dar. Für die zweite Methode ist `Div` ein `duration`-Objekt, das eine Taktanzahl enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `duration`-Objekt nach dem Modulo-Vorgang wird ausgeführt.  
  
##  <a name="a-namedurationoperatorstareqa--durationoperator"></a><a name="duration__operator_star_eq"></a> duration::operator*=  
 Multipliziert die gespeicherte Taktanzahl mit einem angegebenen Wert.  
  
```  
duration& operator*=(const rep& Mult);
```  
  
### <a name="parameters"></a>Parameter  
 `Mult`  
 Ein Wert des von `duration::rep` angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `duration`-Objekt nach Ausführung der Multiplikation.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator__eq"></a> duration::operator/=  
 Dividiert die gespeicherte Taktanzahl mit einem angegebenen Wert.  
  
```  
duration& operator/=(const rep& Div);
```  
  
### <a name="parameters"></a>Parameter  
 `Div`  
 Ein Wert des von `duration::rep` angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `duration`-Objekt nach Ausführung der Division.  
  
##  <a name="a-namedurationoperatoradda--durationoperator"></a><a name="duration__operator_add"></a> duration::operator+  
 Gibt `*this`zurück.  
  
```  
constexpr duration operator+() const;
```  
  
##  <a name="a-namedurationoperatoraddadda--durationoperator"></a><a name="duration__operator_add_add"></a> duration::operator++  
 Erhöht die gespeicherte Taktanzahl.  
  
```  
duration& operator++();

duration operator++(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Methode gibt `*this` zurück.  
  
 Die zweite Methode gibt eine Kopie von `*this` zurück, die vor dem Inkrementieren erstellt wird.  
  
##  <a name="a-namedurationoperatoraddeqa--durationoperator"></a><a name="duration__operator_add_eq"></a> duration::operator+=  
 Fügt der gespeicherten Taktanzahl die Taktanzahl eines angegebenen `duration`-Objekts hinzu.  
  
```  
duration& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>Parameter  
 `Dur`  
 Ein `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `duration`-Objekt nach Ausführung der Addition.  
  
##  <a name="a-namedurationoperator-eqa--durationoperator-"></a><a name="duration__operator-_eq"></a> duration::operator-=  
 Subtrahiert die Taktanzahl eines angegebenen `duration`-Objekts von der gespeicherten Taktanzahl.  
  
```  
duration& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>Parameter  
 `Dur`  
 Ein `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `duration`-Objekt nach Ausführung der Subtraktion.  
  
##  <a name="a-namedurationzeromethoda--durationzero"></a><a name="duration__zero_method"></a> duration::zero  
 Gibt `duration(duration_values<rep>::zero())`zurück.  
  
```  
static constexpr duration zero();
```  
  
##  <a name="a-namedurationoperatormodeqa--durationoperator-mod"></a><a name="duration__operator_mod_eq"></a> duration::operator mod=  
 Reduziert die gespeicherte Taktanzahl-Modulo Div oder Div.count().  
  
```  
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Parameter  
 `Div`  
 Der Divisor, der ein Duration-Objekt oder ein Wert ist, der Taktzähler darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion reduziert die gespeicherte Taktanzahl-Modulo Div und gibt *dies zurück. Die zweite Memberfunktion reduziert die gespeicherte Taktanzahl-Modulo Div.count() und gibt \*dies zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [duration_values-Struktur](../standard-library/duration-values-structure.md)

