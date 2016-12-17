---
title: "locale-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::locale"
  - "std::locale"
  - "std.locale"
  - "locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale-Klasse"
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# locale-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Facet ist ein Zeiger auf ein Objekt einer Klasse abgeleiteten Klasse [Facet](#facet_class) bei dem ein öffentliches Objekt in der Form:  
  
```  
static locale::id id;  
```  
  
 Sie können einen offenen Satz dieser Facets definieren. Sie können auch ein Gebietsschemaobjekt erstellen, das eine beliebige Anzahl von Facets festgelegt.  
  
 Vordefinierte Gruppen dieser Facets stellen die [gebietsschemakategorien](#locale__category) traditionell in der C-Standardbibliothek verwalteten von der Funktion `setlocale`.  
  
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
  
 Ein Objekt der Klasse Locale speichert einen Gebietsschemanamen als Objekt der Klasse [Zeichenfolge](../Topic/%3Cstring%3E%20typedefs.md#string). Ein Objekt der Klasse löst unter Verwendung eines ungültigen Gebietsschemanamens zum Erstellen eines gebietsschemafacets oder eines Gebietsschemaobjekts [Runtime_error](../standard-library/runtime-error-class.md). Der gespeicherte Gebietsschemaname ist `"*"`, wenn das Gebietsschemaobjekt nicht davon ausgehen kann, dass ein Gebietsschema im C-Stil genau dem entspricht, das durch das Objekt repräsentiert wird. Andernfalls können Sie ein entsprechendes Gebietsschema in die Standard-C-Bibliothek für das lokale Objekt einrichten `_Loc`, durch Aufrufen von `setlocale`(LC_ALL `,` `_Loc`. [Name](#locale__name)`().c_str()`).  
  
 In dieser Implementierung können Sie außerdem die statische Memberfunktion aufrufen:  
  
```  
static locale empty();
```  
  
 zur Erstellung eines Gebietsschemaobjekts, das keine Facets hat. Es ist auch ein transparentes Gebietsschema. Wenn die Vorlagenfunktionen [Has_facet](../Topic/%3Clocale%3E%20functions.md#has_facet) und [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) das angeforderte Facet wurde nicht gefunden in einem transparenten Gebietsschema, konsultieren sie zunächst das globale Gebietsschema und, wenn dies transparent ist das klassische Gebietsschema. So können Sie Folgendes schreiben:  
  
```  
cout.imbue(locale::empty());
```  
  
 Nachfolgende einfügungen in [Cout](../Topic/%3Ciostream%3E%20functions.md#cout) werden durch den aktuellen Zustand des globalen Gebietsschemas vermittelt. Sie können sogar Folgendes schreiben:  
  
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
|[Gebietsschema](#locale__locale)|Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[Kategorie](#locale__category)|Ein ganzzahliger Typ, der Bitmaskenwerte bereitstellt, um Standardfacetfamilien anzugeben.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Kombinieren](#locale__combine)|Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.|  
|[Name](#locale__name)|Gibt den gespeicherten Gebietsschemanamen zurück.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[Standardansicht](#locale__classic)|Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.|  
|[globale](#locale__global)|Setzt das Standardgebietsschema für das Programm zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator! =](#locale__operator_neq)|Prüft zwei Gebietsschemen auf Ungleichheit.|  
|[Funktionsaufrufoperator)](#locale__operator__)|Vergleicht zwei `basic_string`-Objekte.|  
|[Operator ==](#locale__operator_eq_eq)|Prüft zwei Gebietsschemen auf Gleichheit.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[Facet](#facet_class)|Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.|  
|[ID](#id_class)|Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namelocalecategorya-localecategory"></a><a name="locale__category"></a>  locale:: Category  
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
 Der Typ ist ein Synonym für ein `int` Typ, der eine Gruppe von verschiedenen Elementen einer Bitmaske darstellen kann geben lokale Klasse Gebietsschema oder können verwendet werden, um den entsprechenden C-Gebietsschema-Kategorien darstellen. Die Elemente sind:  
  
- **COLLATE**, entsprechend der Kategorie C LC_COLLATE  
  
- **CType**, entsprechend der Kategorie C LC_CTYPE  
  
- **monetäre**, entsprechend der Kategorie C LC_MONETARY  
  
- **numerische**, entsprechend der Kategorie C LC_NUMERIC  
  
- **Zeit**, entsprechend der Kategorie C LC_TIME  
  
- **Nachrichten**, entsprechend der Posix-Kategorie LC_MESSAGES  
  
 Darüber hinaus sind zwei nützliche Werte ein:  
  
- **keine**, entsprechend auf keine der Kategorien C  
  
- **alle**, entsprechend der C-Union aller Kategorien LC_ALL  
  
 Sie können eine beliebige Gruppe von Kategorien darstellen, mit `OR` Diese Konstanten, wie im **monetären** &#124; **Zeit**.  
  
##  <a name="a-namelocaleclassica-localeclassic"></a><a name="locale__classic"></a>  locale:: Classic  
 Die statische Memberfunktion gibt ein Gebietsschemaobjekt zurück, das das klassische C-Gebietsschema darstellt.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das C-Gebietsschema.  
  
### <a name="remarks"></a>Hinweise  
 Das klassische C-Gebietsschema wird den USA Englische ASCII-Gebietsschema in der C-Standardbibliothek, der implizit in Programmen verwendet wird, die nicht die internationale sind.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namelocalecombinea-localecombine"></a><a name="locale__combine"></a>  locale:: Combine  
 Fügt ein Facet eines angegebenen Gebietsschemas in ein Zielgebietsschema ein.  
  
```  
template <class Facet>  
locale combine(const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Loc`  
 Das Gebietsschema, enthält das Facet in das Zielgebietsschema eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt eine Gebietsschemaobjekt, das ersetzt oder hinzugefügt **\*dies** Facets `Facet` gemäß `_Loc`.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namefacetclassa-facet-class"></a><a name="facet_class"></a>  Facet-Klasse  
 Eine Klasse, die als Basisklasse für alle Gebietsschemafacets dient.  
  
Klasse Facet {geschützt: explizite Facet (Size_t _Refs = 0), virtuelle ~ facet(); Private: Facet(const facet&) / / void-Operator nicht definiert =(const facet&) / / nicht definierte};  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass nicht kopieren oder ein Objekt der Klasse Facet zuweisen. Sie erstellen und Zerstören von-Klasse abgeleiteten Objekte `locale::facet` aber nicht die Objekte der richtigen Basisklasse. In der Regel erstellen Sie ein Objekt `_Myfac` Facet abgeleitet, wenn Sie ein Gebietsschema, wie in erstellen **Localeloc**( `locale::classic`(), **neue**`_Myfac`);  
  
 In diesem Fall müsste der Konstruktor für die Basisklasse Facet eine NULL `_Refs` Argument. Wenn das Objekt nicht mehr benötigt wird, wird sie gelöscht. Daher geben Sie einen Wert ungleich NULL _ *Refs* Argument nur in den seltenen Fällen, in denen Sie die Verantwortung für die Lebensdauer des Objekts übernehmen.  
  
##  <a name="a-namelocaleglobala-localeglobal"></a><a name="locale__global"></a>  locale:: Global  
 Setzt das Standardgebietsschema für die Anwendung zurück. Dies wirkt sich auf das globale Gebietsschema für C und C++.  
  
```  
static locale global(const locale& _Loc);
```  
  
### <a name="parameters"></a>Parameter  
 `_Loc`  
 Das Gebietsschema als das Standardgebietsschema von der Anwendung verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Gebietsschema des vorherigen, bevor das Standardgebietsschema zurückgesetzt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Bei Programmstart ist das globale Gebietsschema das klassische Gebietsschema identisch. Die `global()` Funktionsaufrufe `setlocale( LC_ALL, loc.name. c_str())` ein entsprechendes Gebietsschema in der Standard-C-Bibliothek herstellen.  
  
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
  
##  <a name="a-nameidclassa-id-class"></a><a name="id_class"></a>  ID-Klasse  
 Die Memberklasse stellt eine einzigartige Facetidentifikation bereit, die als Index zum Suchen von Facets in einem Gebietsschema verwendet wird.  
  
Klassen-Id {geschützt: id(); Private: Id(const id&) / / void-Operator nicht definiert =(const id&) / / nicht definierte};  
  
### <a name="remarks"></a>Hinweise  
 Die Memberklasse beschreibt jede eindeutige gebietsschemafacet erforderlichen statischen Member-Objekts. Beachten Sie, dass Sie nicht kopiert oder weisen Sie ein Objekt der Klasse **Id**.  
  
##  <a name="a-namelocalelocalea-localelocale"></a><a name="locale__locale"></a>  locale:: Locale  
 Erstellt ein Gebietsschema, eine Kopie eines Gebietsschemas oder eine Kopie des Gebietsschemas, in dem ein Facet oder eine Kategorie durch ein Facet oder eine Kategorie eines anderen Gebietsschemas ersetzt wurde.  
  
```  
locale();

explicit locale(
    const char* _Locname,  
    category _Cat = all);

explicit locale(
    const string& _Locname);

locale(
    const locale& _Loc);

locale(
    const locale& _Loc,   
    const locale& _Other,  
    category _Cat);

locale(
    const locale& _Loc,   
    const char* _Locname,  
    category _Cat);

template <class Facet>  
locale(
 const locale& _Loc,   
    const Facet* _Fac);
```  
  
### <a name="parameters"></a>Parameter  
 `_Locname`  
 Der Name eines Gebietsschemas.  
  
 `_Loc`  
 Ein Gebietsschema, das zum Erstellen des neuen Gebietsschemas kopiert werden soll.  
  
 `_Other`  
 Ein Gebietsschema für die Auswahl einer Kategorie.  
  
 `_Cat`  
 Die Kategorie in der erstellten Gebietsschema ersetzt werden.  
  
 `_Fac`  
 Das Facet in der erstellten Gebietsschema ersetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert das Objekt, um das globale Gebietsschema entsprechen. Die zweiten und dritten Konstruktoren initialisieren die gebietsschemakategorien zum Verhalten konsistent mit dem Gebietsschemanamen `_Locname`. Kopieren Sie die übrigen Konstruktoren `_Loc`, mit den Ausnahmen:  
  
 `locale(const locale& _Loc, const locale& _Other, category _Cat);`  
  
 ersetzt vom `_Other` diese Facets entsprechend einer Kategorie C für die C & `_Cat` ungleich NULL ist.  
  
 `locale(const locale& _Loc, const char* _Locname, category _Cat);`  
  
 `locale(const locale& _Loc, const string& _Locname, category _Cat);`  
  
 ersetzt vom `locale(_Locname, _All)` diese Facets entsprechend einer Kategorie C für die C & `_Cat`ungleich NULL ist.  
  
 `template<class Facet> locale(const locale& _Loc, Facet* _Fac);`  
  
 ersetzt in (oder hinzugefügt) `_Loc` Facets `_Fac`, wenn `_Fac` ist kein null-Zeiger.  
  
 Wenn ein Gebietsschema `_Locname` ist ein null-Zeiger oder andernfalls ungültig ist, löst die Funktion [Runtime_error](../standard-library/runtime-error-class.md).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namelocalenamea-localename"></a><a name="locale__name"></a>  locale:: Name  
 Gibt den gespeicherten Gebietsschemanamen zurück.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Namen des Gebietsschemas.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namelocaleoperatorneqa-localeoperator"></a><a name="locale__operator_neq"></a>  locale:: Operator! =  
 Prüft zwei Gebietsschemen auf Ungleichheit.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Zu den Gebietsschemas auf Ungleichheit getestet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **true** Wenn die Gebietsschemas nicht Kopien der gleichen Gebietsschema; **false** Wenn die Gebietsschemas Kopien der gleichen Gebietsschema.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Gebietsschemas sind gleich, wenn sie das gleiche Gebietsschema verwenden, sind, wenn eine Kopie der anderen ist oder ihre Namen identisch sind.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namelocaleoperatora-localeoperator"></a><a name="locale__operator__"></a>  Locale::Operator()  
 Vergleicht zwei `basic_string`-Objekte.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Die linken Zeichenfolge.  
  
 ` right`  
 Die Rechte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt Folgendes zurück:  
  
-   – 1, wenn die erste Sequenz kleiner als der zweiten Sequenz verglichen.  
  
-   + 1, wenn die zweite Sequenz kleiner als der ersten Sequenz vergleicht.  
  
-   0, wenn die Sequenzen gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Funktion führt Folgendes aus:  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) <0);
```  
  
 Daher können Sie ein Locale-Objekt als ein Function-Objekt.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namelocaleoperatoreqeqa-localeoperator"></a><a name="locale__operator_eq_eq"></a>  locale:: Operator ==  
 Prüft zwei Gebietsschemen auf Gleichheit.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Zu den Gebietsschemas auf Gleichheit getestet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **true** Wenn die Gebietsschemas Kopien der gleichen Gebietsschema; **false** Wenn die Gebietsschemas nicht Kopien der gleichen Gebietsschema.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Gebietsschemas sind gleich, wenn sie das gleiche Gebietsschema verwenden, sind, wenn eine Kopie der anderen ist oder ihre Namen identisch sind.  
  
### <a name="example"></a>Beispiel  
  
```  
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
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Codepages](../c-runtime-library/code-pages.md)   
 [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

