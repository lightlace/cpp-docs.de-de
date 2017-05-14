---
title: locale-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::locale
- locale
- locale/std::locale::category
- locale/std::locale::combine
- locale/std::locale::name
- locale/std::locale::classic
- locale/std::locale::global
- locale/std::locale::operator( )
- locale/std::locale::facet
- locale/std::locale::id
dev_langs:
- C++
helpviewer_keywords:
- locale class
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 6e33e125d2689d37443bec58c5b01f5b7e72ccfd
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="locale-class"></a>locale-Klasse
Die Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Facet ist ein Zeiger auf ein Objekt einer Klasse, die von der [facet](#facet_class)-Klasse abgeleitet wird. Diese verfügt über ein öffentliches Objekt in folgendem Format:  
  
```  
static locale::id id;  
```  
  
 Sie können einen offenen Satz dieser Facets definieren. Sie können auch ein Gebietsschemaobjekt erstellen, das eine beliebige Anzahl von Facets festgelegt.  
  
 Vordefinierte Gruppen dieser Facets stellen die [locale-Kategorien](#category) dar, die normalerweise in der Standard-C-Bibliothek von der Funktion `setlocale` verwaltet werden.  
  
 Die Kategorie "Sortieren" (LC_COLLATE) umfasst folgende Facets:  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 Die Kategorie "ctype" (LC_CTYPE) umfasst folgende Facets:  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 Die Kategorie "Monetär" (LC_MONETARY) umfasst folgende Facets:  
  
```  
moneypunct<char, false>  
moneypunct<wchar_t, false>  
moneypunct<char, true>  
moneypunct<wchar_t, true>  
money_get<char, istreambuf_iterator<char>>  
money_get<wchar_t, istreambuf_iterator<wchar_t>>  
money_put<char, ostreambuf_iterator<char>>  
money_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 Die Kategorie "numerisch" (LC_NUMERIC) umfasst folgende Facets:  
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 Die Kategorie "Zeit" (LC_TIME) umfasst folgende Facets:  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 Die Kategorie "Meldungen" (LC_MESSAGES) umfasst folgende Facets:  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 (Die letzten Kategorie wird von Posix, jedoch nicht vom C-Standard benötigt.)  
  
 Einige dieser vordefinierten Facets werden von iostreams-Klassen dazu verwendet, die Konvertierung von numerischen Werten in und aus Textsequenzen zu steuern.  
  
 Ein Objekt der locale-Klasse speichert einen Gebietsschemanamen als Objekt der Klasse [string](../standard-library/string-typedefs.md#string). Durch Verwenden eines ungültigen Gebietsschemanamens zur Erstellung eines Gebietsschemafacets oder eines Gebietsschemaobjekts wird ein Objekt der Klasse [runtime_error](../standard-library/runtime-error-class.md) ausgelöst. Der gespeicherte Gebietsschemaname ist `"*"`, wenn das Gebietsschemaobjekt nicht davon ausgehen kann, dass ein Gebietsschema im C-Stil genau dem entspricht, das durch das Objekt repräsentiert wird. Andernfalls können Sie ein entsprechendes Gebietsschema in der Standard-C-Bibliothek für das Gebietsschemaobjekt `Loc` festlegen, indem Sie `setlocale`(LC_ALL `,` `Loc` aufrufen. [name](#name)`().c_str()`).  
  
 In dieser Implementierung können Sie außerdem die statische Memberfunktion aufrufen:  
  
```  
static locale empty();
```  
  
 zur Erstellung eines Gebietsschemaobjekts, das keine Facets hat. Es ist außerdem ein transparentes Gebietsschema. Wenn die Vorlagenfunktionen [has_facet](../standard-library/locale-functions.md#has_facet) und [use_facet](../standard-library/locale-functions.md#use_facet) das angeforderte Facet in einem transparenten Gebietsschema nicht finden können, greifen sie zuerst auf das globale Gebietsschema und anschließend, wenn dies transparent ist, auf das klassische Gebietsschema zurück. So können Sie Folgendes schreiben:  
  
```  
cout.imbue(locale::empty());
```  
  
Nachfolgende Einfügungen in [cout](../standard-library/iostream.md#cout) werden durch den aktuellen Zustand des globalen Gebietsschemas vermittelt. Sie können sogar Folgendes schreiben:  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 Numerische Formatierungsregeln für nachfolgende Einfügungen in `cout` bleiben gleich wie im C-Gebietsschema, auch wenn das globale Gebietsschema Änderungsregeln für das Einfügen von Datumsangaben und Währungswerten bietet.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[locale](#locale)|Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[category](#category)|Ein ganzzahliger Typ, der Bitmaskenwerte bereitstellt, um Standardfacetfamilien anzugeben.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[combine](#combine)|Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.|  
|[name](#name)|Gibt den gespeicherten Gebietsschemanamen zurück.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[classic](#classic)|Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.|  
|[global](#global)|Setzt das Standardgebietsschema für das Programm zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator!=](#op_neq)|Prüft zwei Gebietsschemen auf Ungleichheit.|  
|[operator( )](#op_call)|Vergleicht zwei `basic_string`-Objekte.|  
|[operator==](#op_eq_eq)|Prüft zwei Gebietsschemen auf Gleichheit.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[facet](#facet_class)|Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.|  
|[id](#id_class)|Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="category"></a> locale::category  
 Ein ganzzahliger Typ, der Bitmaskenwerte bereitstellt, um Standardfacetfamilien anzugeben.  
  
```  
typedef int category;  
static const int collate = LC_COLLATE;  
static const int ctype = LC_CTYPE;  
static const int monetary = LC_MONETARY;  
static const int numeric = LC_NUMERIC;  
static const int time = LC_TIME;  
static const int messages = LC_MESSAGES;  
static const int all = LC_ALL;  
static const int none = 0;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für einen `int`-Typ, der eine Gruppe von verschiedenen Elementen eines locale-Bitmaskentyps zur locale-Klasse darstellen kann oder als diese verwendet werden kann, um die entsprechenden C-Gebietsschemakategorien darstellen. Die Elemente sind:  
  
- **collate**, entspricht der C-Kategorie LC_COLLATE  
  
- **ctype**, entspricht der C-Kategorie LC_CTYPE  
  
- **monetary**, entspricht der C-Kategorie LC_MONETARY  
  
- **monetary**, entspricht der C-Kategorie LC_MONETARY  
  
- **time**, entspricht der C-Kategorie LC_TIME  
  
- **messages**, entspricht der Posix-Kategorie LC_MESSAGES  
  
 Zusätzlich gibt es zwei weitere nützliche Werte:  
  
- **none**, entspricht keiner der C-Kategorien  
  
- **all**, entspricht der C-Union aller Kategorien LC_ALL  
  
 Sie können eine beliebige Gruppe von Kategorien darstellen, indem Sie `OR` genauso wie in **monetary** &#124; **time** mit diesen Konstanten verwenden.  
  
##  <a name="classic"></a> locale::classic  
 Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das C-Gebietsschema.  
  
### <a name="remarks"></a>Hinweise  
 Das klassische C-Gebietsschema ist die USA Englischen ASCII-Gebietsschema in der C-Standardbibliothek, der implizit in Programmen verwendet wird, die nicht internationalisiert werden.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_classic.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: " << loc2.name( )  
        << "." << endl;  
   cout << "The name of the current locale is: " << loc1.name( )   
        << "." << endl;  
  
   if (loc2 == locale::classic( ) )  
      cout << "The previous locale was classic." << endl;  
   else  
      cout << "The previous locale was not classic." << endl;  
  
   if (loc1 == locale::classic( ) )  
      cout << "The current locale is classic." << endl;  
   else  
      cout << "The current locale is not classic." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
The previous locale was classic.  
The current locale is not classic.  
```  
  
##  <a name="combine"></a> locale::combine  
 Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.  
  
```  
template <class Facet>  
locale combine(const locale& Loc) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Loc`  
 Das Gebietsschema enthält das Facet, das in das Zielgebietsschema eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das unter `Loc` aufgelistete Facet `Facet` in **\*this** ersetzt oder dieses diesem hinzufügt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_combine.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main() {  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   locale loc2 ( "C" );  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
}  
```  
  
##  <a name="facet_class"></a> facet-Klasse  
 Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.  

```    
class facet { 
protected:    
    explicit facet(size_t _Refs = 0);
   virtual ~facet();
private:    
   facet(const facet&)
   // not defined void operator=(const facet&)
     // not defined    
};  
```  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass Sie ein Objekt der facet-Klasse nicht kopieren oder zuweisen können. Sie können Objekte, die von der Klasse `locale::facet` abgeleitet wurden, erstellen oder zerstören, aber nicht die Objekte der richtigen Basisklasse. In der Regel erstellen Sie ein vom Facet abgeleitetes Objekt `_Myfac`, wenn Sie ein Gebietsschema genauso wie in **localeloc**( `locale::classic`( ), **new**`_Myfac`); erstellen  
  
 In diesem Fall sollte der Konstruktor für das Basisklasse-Facet ein Null-`_Refs`-Argument haben. Wenn das Objekt nicht mehr benötigt wird, wird es gelöscht. Daher geben Sie ein _ *Refs*-Argument, das ungleich null ist, nur in den seltenen Fällen ein, in denen Sie die Verantwortung für die Lebensdauer des Objekts übernehmen.  
  
##  <a name="global"></a> locale::global  
 Setzt das Standardgebietsschema für das Programm zurück. Dies wirkt sich auf das globale Gebietsschema für C und C++ aus.  
  
```  
static locale global(const locale& Loc);
```  
  
### <a name="parameters"></a>Parameter  
 `Loc`  
 Das Gebietsschema, das als Standardgebietsschema vom Programm verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das vorherige Gebietsschema, bevor das Standardgebietsschema zurückgesetzt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Bei Programmstart ist das globale Gebietsschema gleich dem klassischen Gebietsschema. Die `global()`-Funktion ruft `setlocale( LC_ALL, loc.name. c_str())` auf, um ein entsprechendes Gebietsschema in der Standard-C-Bibliothek festzulegen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_global.cpp  
// compile by using: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_germany" );  
   locale loc1;  
   cout << "The initial locale is: " << loc1.name( ) << endl;  
   locale loc2 = locale::global ( loc );  
   locale loc3;  
   cout << "The current locale is: " << loc3.name( ) << endl;  
   cout << "The previous locale was: " << loc2.name( ) << endl;  
}  
```  
  
```Output  
The initial locale is: C  
The current locale is: German_Germany.1252  
The previous locale was: C  
```  
  
##  <a name="id_class"></a> id-Klasse  
 Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.  
  
Klasse id { protected:    id(); private:    id(const id&) // not defined void operator=(const id&)  // not defined    };  
  
### <a name="remarks"></a>Hinweise  
 Die Memberklasse beschreibt das statische Memberobjekt, das von jedem Gebietsschemafacet benötigt wird. Beachten Sie, dass Sie ein Objekt der Klasse **id** nicht kopieren oder zuweisen können.  
  
##  <a name="locale"></a> locale::locale  
 Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde.  
  
```  
locale();

explicit locale(const char* Locname, category Cat = all);
explicit locale(const string& Locname);
locale( const locale& Loc);
locale(const locale& Loc, const locale& Other, category Cat);
locale(const locale& Loc, const char* Locname, category Cat);

template <class Facet>  
locale(const locale& Loc, const Facet* Fac);
```  
  
### <a name="parameters"></a>Parameter  
 `Locname`  
 Der Name eines Gebietsschemas.  
  
 `Loc`  
 Ein Gebietsschema, das zum Erstellen des neuen Gebietsschemas kopiert werden soll.  
  
 `Other`  
 Ein Gebietsschema für die Auswahl einer Kategorie.  
  
 `Cat`  
 Die Kategorie, die im erstellten Gebietsschema ersetzt werden soll.  
  
 `Fac`  
 Das Facet, das im erstellten Gebietsschema ersetzt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert das Objekt, um mit dem globalen Gebietsschema übereinzustimmen. Der zweite und dritte Konstruktor initialisieren alle Gebietsschemakategorien, die ein konsistentes Verhalten mit dem Gebietsschemanamen `Locname` haben sollen. Kopieren Sie die übrigen Konstruktoren `Loc`, mit den folgenden Ausnahmen:  
  
 `locale(const locale& Loc, const locale& Other, category Cat);`  
  
 ersetzt aus `Other` die Facets, die einer Kategorie C entsprechen, für welche C & `Cat` ungleich null sind.  
  
 `locale(const locale& Loc, const char* Locname, category Cat);`  
  
 `locale(const locale& Loc, const string& Locname, category Cat);`  
  
 ersetzt aus `locale(Locname, _All)` die Facets, die einer Kategorie C entsprechen, für welche C & `Cat` ungleich null sind.  
  
 `template<class Facet> locale(const locale& Loc, Facet* Fac);`  
  
 ersetzt in `Loc` das Facet `Fac`, wenn `Fac` kein Nullzeiger ist (oder fügt dieses hinzu).  
  
 Wenn ein Gebietsschema `Locname` ein NULL-Zeiger oder ungültig ist, löst die Funktion [runtime_error](../standard-library/runtime-error-class.md) aus.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_locale.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( ) {  
  
   // Second constructor  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   // The first (default) constructor  
   locale loc2;  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   // Third constructor  
   locale loc3 (loc2,loc, _M_COLLATE );  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
  
   // Fourth constructor  
   locale loc4 (loc2, "German_Germany", _M_COLLATE );  
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;  
}  
```  
  
##  <a name="name"></a> locale::name  
 Gibt den gespeicherten Gebietsschemanamen zurück.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Namen des Gebietsschemas angibt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_name.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: "   
        << loc2.name( ) << "." << endl;  
   cout << "The name of the current locale is: "   
        << loc1.name( ) << "." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
```  
  
##  <a name="op_neq"></a> locale::operator!=  
 Prüft zwei Gebietsschemen auf Ungleichheit.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Eines der Gebietsschemas, die auf Ungleichheit geprüft werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **TRUE** ist, wenn die Gebietsschemas nicht Kopien des gleichen Gebietsschemas sind; **FALSE**, wenn die Gebietsschemas Kopien des gleichen Gebietsschemas sind.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Gebietsschemas entsprechen sich, wenn sie das gleiche Gebietsschema sind oder wenn eines eine Kopie der anderen ist oder ihre Namen identisch sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_op_ne.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 != loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;  
  
   if ( loc1 != loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252) and  
 loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252) and  
 loc3 (English_United States.1252) are not equal.  
```  
  
##  <a name="op_call"></a> locale::operator()  
 Vergleicht zwei `basic_string`-Objekte.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Die linke Zeichenfolge.  
  
 `right`  
 Die rechte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt Folgendes zurück:  
  
-   -1, wenn die erste Sequenz im Vergleich kleiner ist als die zweite Sequenz.  
  
-   +1, wenn die zweite Sequenz im Vergleich kleiner ist als die erste Sequenz.  
  
-   0, wenn die Sequenzen gleichwertig sind.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion führt Folgendes aus:  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```  
  
 Daher können Sie ein Gebietsschemaobjekt als ein Funktionsobjekt verwenden.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_op_compare.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
int main( )   
{  
   using namespace std;  
   wchar_t *sa = L"ztesting";  
   wchar_t *sb = L"\0x00DFtesting";  
   basic_string<wchar_t> a( sa );  
   basic_string<wchar_t> b( sb );  
  
   locale loc( "German_Germany" );  
   cout << loc( a,b ) << endl;  
  
   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );  
   cout << ( fac.compare( sa, sa + a.length( ),  
       sb, sb + b.length( ) ) < 0) << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
##  <a name="op_eq_eq"></a> locale::operator==  
 Prüft zwei Gebietsschemen auf Gleichheit.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Eines der Gebietsschemas, die auf Gleichheit geprüft werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **TRUE** ist, wenn die Gebietsschemas Kopien des gleichen Gebietsschemas sind; **FALSE**, wenn die Gebietsschemas keine Kopien des gleichen Gebietsschemas sind.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Gebietsschemas entsprechen sich, wenn sie das gleiche Gebietsschema sind oder wenn eines eine Kopie der anderen ist oder ihre Namen identisch sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// locale_op_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 == loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."   
      << endl;  
  
   if ( loc1 == loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."   
      << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252)  
 and loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252)  
 and loc3 (English_United States.1252) are not equal.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [<locale>](../standard-library/locale.md)   
 [Codepages](../c-runtime-library/code-pages.md)   
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)


