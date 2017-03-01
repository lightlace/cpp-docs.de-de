---
title: regex_iterator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_iterator
- std::regex_iterator
- regex/std::regex_iterator
- std::regex_iterator::operator==
- regex/std::regex_iterator::operator==
- std::regex_iterator::operator!=
- regex/std::regex_iterator::operator!=
- std::regex_iterator::operator*
- regex/std::regex_iterator::operator*
- std::regex_iterator::operator->
- regex/std::regex_iterator::operator->
- std::regex_iterator::operator++
- regex/std::regex_iterator::operator++
dev_langs:
- C++
helpviewer_keywords:
- regex_iterator class
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 8bfed3b74020bce20f18700d30573f01cdfd2adc
ms.lasthandoff: 02/24/2017

---
# <a name="regexiterator-class"></a>regex_iterator-Klasse
Iteratorklasse für Übereinstimmungen.  
  
## <a name="syntax"></a>Syntax  
```
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {  
public:  
   typedef basic_regex<Elem, RXtraits> regex_type;  
   typedef match_results<BidIt> value_type;  
   typedef std::forward_iterator_tag iterator_category;  
   typedef std::ptrdiff_t difference_type;  
   typedef const match_results<BidIt>* pointer;  
   typedef const match_results<BidIt>& reference;  

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,  
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only  
   BidIt end; // exposition only  
   regex_type *pregex;     // exposition only  
   regex_constants::match_flag_type flags; // exposition only  
   match_results<BidIt> match; // exposition only  
   };  
```  
  
### <a name="parameters"></a>Parameter  
 `BidIt`  
 Der Itertatortyp für Teilübereinstimmungen.  
  
 `Elem`  
 Der zu entsprechende Elementtyp.  
  
 `RXtraits`  
 Merkmalklasse für Elemente.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt mit einem konstanten Forward-Iterator. Anschließend extrahiert sie Objekte des Typs `match_results<BidIt>` durch wiederholtes Anwenden seines regulären Ausdrucksobjekts `*pregex` auf die vom Iteratorbereich `[begin, end)`definierte Zeichenfolge.  
  
## <a name="examples"></a>Beispiele  
 Beispiele zu regulären Ausdrücken finden Sie in den folgenden Themen:  
  
- [regex_match-Funktion](../standard-library/regex-functions.md#regex_match_function)  
  
- [regex_replace-Funktion](../standard-library/regex-functions.md#regex_replace_function)  
  
- [regex_search-Funktion](../standard-library/regex-functions.md#regex_search_function)  
  
- [swap-Funktion](../standard-library/regex-functions.md#swap_function)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<regex >  
  
 **Namespace:** std  
  
##  <a name="a-nameregexiteratordifferencetypea--regexiteratordifferencetype"></a><a name="regex_iterator__difference_type"></a> regex_iterator::difference_type  
 Der Typ einer Iteratordifferenz.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `std::ptrdiff_t`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoriteratorcategorya--regexiteratoriteratorcategory"></a><a name="regex_iterator__iterator_category"></a> regex_iterator::iterator_category  
 Der Typ der Iteratorkategorie.  
  
```  
typedef std::forward_iterator_tag iterator_category;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `std::forward_iterator_tag`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_iterator_category.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorneqa--regexiteratoroperator"></a><a name="regex_iterator__operator_neq"></a> regex_iterator::operator!=  
 Vergleicht Iteratoren auf Ungleichheit.  
  
```  
bool operator!=(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der Iterator für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt `!(*this == right)`zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorstara--regexiteratoroperator"></a><a name="regex_iterator__operator_star"></a> regex_iterator::operator*  
 Greift auf die gekennzeichnete Übereinstimmung zu.  
  
```  
const match_results<BidIt>& operator*();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt den gespeicherten Wert `match`zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_operator_star.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoraddadda--regexiteratoroperator"></a><a name="regex_iterator__operator_add_add"></a> regex_iterator::operator++  
 Erhöht den Iterator.  
  
```  
regex_iterator& operator++();
regex_iterator& operator++(int);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die aktuelle Übereinstimmung keine Zeichen enthält, ruft der erste Operator `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`auf. Andernfalls verschiebt er den gespeicherten Wert `begin` so, dass dieser auf das erste Zeichen nach der aktuellen Übereinstimmung zeigt, und ruft dann `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`auf. Schlägt die Suche fehl, legt der Operator in beiden Fällen das Objekt auf einen Sequenzende-Iterator fest. Der Operator gibt das Objekt zurück.  
  
 Der zweite Operator erstellt eine Kopie des Objekts, erhöht das Objekt und gibt dann die Kopie zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_operator_inc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoreqa--regexiteratoroperator"></a><a name="regex_iterator__operator_eq"></a> regex_iterator::operator=  
 Vergleicht Iteratoren auf Gleichheit.  
  
```  
bool operator==(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der Iterator für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „true“ zurück, wenn `*this` und `right` Sequenzende-Iteratoren sind oder wenn keins von beiden ein Sequenzende-Iterator ist und Folgendes zutrifft: `begin == right.begin`, `end == right.end`, `pregex == right.pregex`und `flags == right.flags`. Andernfalls wird „false“ zurückgegeben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperator-gta--regexiteratoroperator-gt"></a><a name="regex_iterator__operator-_gt_"></a> regex_iterator::operator-&gt;  
 Greift auf die gekennzeichnete Übereinstimmung zu.  
  
```  
const match_results<BidIt> * operator->();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Adresse des gespeicherten Werts `match`zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_operator_arrow.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorpointera--regexiteratorpointer"></a><a name="regex_iterator__pointer"></a> regex_iterator::pointer  
 Der Typ eines Zeigers auf eine Übereinstimmung.  
  
```  
typedef match_results<BidIt> *pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `match_results<BidIt>*`, wobei `BidIt` der Vorlagenparameter ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_pointer.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorreferencea--regexiteratorreference"></a><a name="regex_iterator__reference"></a> regex_iterator::reference  
 Der Typ eines Verweises auf eine Übereinstimmung.  
  
```  
typedef match_results<BidIt>& reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `match_results<BidIt>&`, wobei `BidIt` der Vorlagenparameter ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregexiteratora--regexiteratorregexiterator"></a><a name="regex_iterator__regex_iterator"></a> regex_iterator::regex_iterator  
 Erstellt den Iterator.  
  
```  
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,  
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Anfang der Sequenz, die übereinstimmen soll.  
  
 `last`  
 Ende der Sequenz, die übereinstimmen soll.  
  
 `re`  
 Regulärer Ausdruck für Übereinstimmungen.  
  
 `f`  
 Flags für Übereinstimmungen.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt einen Sequenzende-Iterator. Der zweite Konstruktor initialisiert den gespeicherten Wert `begin` mit `first`, den gespeicherten Wert `end` mit `last`, den gespeicherten Wert `pregex` mit `&re`und den gespeicherten Wert `flags` mit `f`. Anschließend wird `regex_search(begin, end, match, *pregex, flags)`aufgerufen. Wenn bei der Suche ein Fehler auftritt, legt der Konstruktor für das Objekt einen Sequenzende-Iterator fest.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregextypea--regexiteratorregextype"></a><a name="regex_iterator__regex_type"></a> regex_iterator::regex_type  
 Der Typ des regulären Ausdrucks, der übereinstimmen soll.  
  
```  
typedef basic_regex<Elem, RXtraits> regex_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Typedef ist ein Synonym für `basic_regex<Elem, RXtraits>`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_regex_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorvaluetypea--regexiteratorvaluetype"></a><a name="regex_iterator__value_type"></a> regex_iterator::value_type  
 Der Typ einer Übereinstimmung.  
  
```  
typedef match_results<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `match_results<BidIt>`, wobei `BidIt` der Vorlagenparameter ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_iterator_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
## <a name="see-also"></a>Siehe auch  
[\<regex>](../standard-library/regex.md)  
[regex_constants-Klasse](../standard-library/regex-constants-class.md)  
[regex_error-Klasse](../standard-library/regex-error-class.md)  
[\<regex>-Funktionen](../standard-library/regex-functions.md)  
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)  
[\<regex>-Operatoren](../standard-library/regex-operators.md)  
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)  
[regex_traits-Klasse](../standard-library/regex-traits-class.md)  
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)  

  

