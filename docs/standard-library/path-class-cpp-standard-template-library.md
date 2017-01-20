---
title: "path-Klasse (C++-Standardvorlagenbibliothek)"
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
  - "filesystem/std::tr2::sys::path"
dev_langs: 
  - "C++"
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
caps.latest.revision: 14
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# path-Klasse (C++-Standardvorlagenbibliothek)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die **path**\-Klasse speichert ein Objekt vom Typ „string\_type“ namens „myname“. Dies erfolgt hier zum Zweck der Darstellung, die zur Verwendung als Pfadname geeignet ist. „string\_type“ ist ein Synonym für „basic\_string\<value\_type\>“, wobei „value\_type“ unter Windows ein Synonym für „char“ oder unter Posix ein Synonym für „wchar\_t“ ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Syntax  
  
```  
class path;  
```  
  
## path::append  
  
```  
template<class Source>  
    path& append(const Source& source);  
template<class InIt>  
    path& append(InIt first, InIt last);  
```  
  
 Die Memberfunktionen fügen die angegebene \(und bei Bedarf konvertierte\) Sequenz an „mypath“ an und fügen bei Bedarf ein „preferred\_separator“ ein.  
  
## path::assign  
  
```  
template<class Source>  
    path& assign(const Source& source);  
template<class InIt>  
    path& assign(InIt first, InIt last);  
```  
  
 Die Memberfunktionen ersetzen „mypath“ durch die angegebene Sequenz, die bei Bedarf konvertiert wird.  
  
## path::begin  
  
```  
iterator begin() const;  
```  
  
 Gibt ein „path::iterator“ zurück, das das erste Pfadelement im Pfadnamen bezeichnet, sofern dieses vorhanden ist.  
  
## path::c\_str  
  
```  
const value_type& *c_str() const noexcept;  
```  
  
 Gibt einen Zeiger auf das erste Zeichen in „mypath“ zurück.  
  
## path::clear  
  
```  
void clear() noexcept;  
```  
  
 Die Memberfunktion führt „mypath.clear\(\)“ aus.  
  
## path::compare  
  
```  
int compare(const path& pval) const noexcept;  
int compare(const string_type& str) const;  
int compare(const value_type *ptr) const;  
```  
  
 Die erste Funktion gibt „mypath.compare\(pval.native\(\)\)“ zurück. Die zweite Funktion gibt „mypath.compare\(str\)“ zurück. Die dritte Funktion gibt „mypath.compare\(ptr\)“ zurück.  
  
## path::concat  
  
```  
template<class Source>  
    path& concat(const Source& source);  
template<class InIt>  
    path& concat(InIt first, InIt last);  
```  
  
 Die Memberfunktionen fügen die angegebene und bei Bedarf konvertierte Sequenz an „mypath“ an \(aber fügen kein Trennzeichen ein\).  
  
## path::const\_iterator  
  
```  
typedef iterator const_iterator;  
```  
  
 Der Typ ist ein Synonym für Iterator.  
  
## path::empty  
  
```  
bool empty() const noexcept;  
```  
  
 Gibt „mypath.empty\(\)“ zurück.  
  
## path::end  
  
```  
iterator end() const;  
```  
  
 Gibt einen Sequenzende\-Iterator vom Typ „iterator“ zurück.  
  
## path::extension  
  
```  
path extension() const;  
```  
  
 Gibt das Suffix von „filename\(\) X“ zurück. Beispiel:  
  
 Bei „X \=\= path\("."\) &#124;&#124; X \=\= path\(".."\)“ oder wenn „X“ keinen Punkt enthält, ist das Suffix leer.  
  
 Andernfalls beginnt das Suffix mit dem rechten Punkt \(und umfasst diesen\).  
  
## path::filename  
  
```  
path filename() const;  
```  
  
 Gibt die Stammverzeichniskomponente von „myname“ zurück, insbesondere `empty() ? path() : *--end()`. Die Komponente kann leer sein.  
  
## path::generic\_string  
  
```  
template<class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
    basic_string<Elem, Traits, Alloc>  
        generic_string(const Alloc& al = Alloc()) const;  
STD string generic_string() const;  
```  
  
 Gibt `this->string<Elem, Traits, Alloc>(_Al)` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird \(unter Windows\).  
  
## path::generic\_u16string  
  
```  
STD u16string generic_u16string() const;  
```  
  
 Gibt „u16string\(\)“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird \(unter Windows\).  
  
## path::generic\_u32string  
  
```  
STD u32string generic_u32string() const;  
```  
  
 Gibt „u32string\(\)“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird \(unter Windows\).  
  
## path::generic\_u8string  
  
```  
STD string generic_u8string() const;  
```  
  
 Gibt „u8string\(\)“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird \(unter Windows\).  
  
## path::generic\_wstring  
  
```  
STD wstring generic_wstring() const;  
```  
  
 Gibt „wstring\(\)“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird \(unter Windows\).  
  
## path::has\_extension  
  
```  
bool has_extension() const;  
```  
  
 Gibt „\!extension\(\).empty\(\)“ zurück.  
  
## path::has\_filename  
  
```  
bool has_filename() const;  
```  
  
 Gibt „\!filename\(\).empty\(\)“ zurück.  
  
## path::has\_parent\_path  
  
```  
  
bool has_parent_path() const;  
  
```  
  
 Gibt „\!parent\_path\(\).empty\(\)“ zurück.  
  
## path::has\_relative\_path  
  
```  
bool has_relative_path() const;  
  
```  
  
 Gibt „\!relative\_path\(\).empty\(\)“ zurück.  
  
## path::has\_root\_directory  
  
```  
bool has_root_directory() const;  
  
```  
  
 Gibt „\!root\_directory\(\).empty\(\)“ zurück.  
  
## path::has\_root\_name  
  
```  
bool has_root_name() const;  
```  
  
 Gibt „\!root\_name\(\).empty\(\)“ zurück.  
  
## path::has\_root\_path  
  
```  
bool has_root_path() const;  
  
```  
  
 Gibt „\!root\_path\(\).empty\(\)“ zurück.  
  
## path::has\_stem  
  
```  
bool has_stem() const;  
```  
  
 Gibt „\!stem\(\).empty\(\)“ zurück.  
  
## path::is\_absolute  
  
```  
bool is_absolute() const;  
```  
  
 Für Windows gibt die Funktion „has\_root\_name\(\) && has\_root\_directory\(\)“ zurück. Für Posix gibt die Funktion „has\_root\_directory\(\)“ zurück.  
  
## path::is\_relative  
  
```  
bool is_relative() const;  
```  
  
 Gibt „\!is\_absolute\(\)“ zurück.  
  
## path::iterator  
  
```  
class iterator  
    {// bidirectional iterator for path  
    typedef bidirectional_iterator_tag iterator_category;  
    typedef path_type value_type;  
    typedef ptrdiff_t difference_type;  
    typedef const value_type *pointer;  
    typedef const value_type& reference;  
    .....  
    };  
  
```  
  
 Die Klasse beschreibt einen bidirektionalen konstanten Iterator, der die Pfadkomponenten von „myname“ in der Sequenz bezeichnet:  
  
1.  den Stammnamen, falls vorhanden  
  
2.  das Stammverzeichnis, falls vorhanden  
  
3.  die übrigen Verzeichniselemente des übergeordneten Pfads, falls vorhanden, die mit dem Dateinamen enden, falls vorhanden  
  
4.  
  
5.  
  
 Für „pval“ ein Objekt vom Typ „path“:  
  
1.  „path::iterator X \= pval.begin\(\)“ bezeichnet das erste Pfadelement im Pfadnamen, falls vorhanden.  
  
2.  „X \=\= pval.end\(\)“ ist „true“, wenn „X“ nur hinter das Ende der Sequenz der Komponenten zeigt.  
  
3.  „\*X“ gibt eine Zeichenfolge zurück, die mit der aktuellen Komponente übereinstimmt.  
  
4.  „\+\+X“ legt die nächste Komponente in der Sequenz fest, falls vorhanden.  
  
5.  „\-\-X“ legt die vorhergehende Komponente in der Sequenz fest, falls vorhanden.  
  
6.  Durch die Änderung von „myname“ werden alle Iteratoren ungültig, die Elemente in „myname“ bezeichnen.  
  
## path::make\_preferred  
  
```  
path& make_preferred();  
  
```  
  
 Die Memberfunktion konvertiert bei Bedarf jedes Trennzeichen in ein „preferred\_separator“.  
  
## path::native  
  
```  
const string_type& native() const noexcept;  
```  
  
 Gibt „myname“ zurück.  
  
## path::operator\=  
  
```  
path& operator=(const path& right);  
path& operator=(path&& right) noexcept;  
template<class Source>  
    path& operator=(const Source& source);  
  
```  
  
 Der erste Memberoperator kopiert „right.myname“ zu „myname“. Der zweite Memberoperator verschiebt „right.myname“ zu „myname“. Die dritte Memberoperator verhält sich wie „\*this \= path\(source\)“.  
  
## path::operator\+\=  
  
```  
path& operator+=(const path& right);  
path& operator+=(const string_type& str);  
path& operator+=(const value_type *ptr);  
path& operator+=(value_type elem);  
template<class Source>  
    path& operator+=(const Source& source);  
template<class Elem>  
    path& operator+=(Elem elem);  
```  
  
 Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:  
  
1.  concat\(right\);  
  
2.  concat\(path\(str\)\);  
  
3.  concat\(ptr\);  
  
4.  concat\(string\_type\(1, elem\)\);  
  
5.  concat\(source\);  
  
6.  concat\(path\(basic\_string\<Elem\>\(1, elem\)\)\);  
  
## path::operator\/\=  
  
```  
path& operator/=(const path& right);  
template<class Source>  
    path& operator/=(const Source& source);  
  
```  
  
 Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:  
  
1.  append\(right\);  
  
2.  append\(source\);  
  
## path::operator string\_type  
  
```  
operator string_type() const;  
```  
  
 Der Memberoperator gibt „myname“ zurück.  
  
## path::parent\_path  
  
```  
path parent_path() const;  
  
```  
  
 Gibt die übergeordnete Pfadkomponente von „myname“ zurück, insbesondere das Präfix von „myname“ nach dem Entfernen von „filename\(\).native\(\)“ und aller unmittelbar vorangehenden Verzeichnistrennzeichen. \(Bei „begin\(\) \!\= end\(\)“ werden gleichermaßen alle Elemente im Bereich „\[begin\(\), \-\-end\(\)\)“ kombiniert, indem „operator\/\=“ fortlaufend angewendet wird.\) Die Komponente kann leer sein.  
  
## path::path  
  
```  
path();  
path(const path& right);  
path(path&& right) noexcept;  
template<class Source>  
    path(const Source& source);  
template<class Source>  
    path(const Source& source, const locale& loc);  
template<class InIt>  
    path(InIt first, InIt last);  
template<class InIt>  
    path(InIt first, InIt last, const locale& loc);  
  
```  
  
 Die Konstruktoren erstellen „myname“ alle auf verschiedene Weise:  
  
 Für „path\(\)“ ist es „myname\(\)“.  
  
 Für „path\(const path& right\)“ ist es „myname\(right.myname\)“.  
  
 Für „path\(path&& right\)“ ist es „myname\(right.myname\)“.  
  
 Für „template\<class Source\> path\(const Source& source\)“ ist es „myname\(source\)“.  
  
 Für „template\<class Source\> path\(const Source& source, const locale& loc\)“ ist es „myname\(source\)“, wobei alle erforderlichen „codecvt“\-Facets von „loc“ abgerufen werden.  
  
 Für „template\<class InIt\> path\(InIt first, InIt last\)“ ist es „myname\(first, last\)“.  
  
 Für „template\<class InIt\> path\(InIt first, InIt last, const locale& loc\)“ ist es „myname\(first, last\)“, wobei alle erforderlichen „codecvt“\-Facets von „loc“ abgerufen werden.  
  
## path::preferred\_separator  
  
```  
#if _WIN32_C_LIB  
static constexpr value_type preferred_separator == L'\\';  
#else // assume Posix  
static constexpr value_type preferred_separator == '/';  
#endif // filesystem model now defined  
  
```  
  
 Das konstante Objekt gibt je nach Betriebssystem des Hosts das bevorzugte Zeichen zum Trennen von Pfadkomponenten zurück. Beachten Sie, dass es in den meisten Kontexten unter Windows gleichermaßen zulässig ist, an dieser Stelle „L'\/'“ zu verwenden.  
  
## path::relative\_path  
  
```  
path relative_path() const;  
  
```  
  
 Gibt die relative Pfadkomponente von „myname“ zurück, insbesondere das Suffix von „myname“ nach dem Entfernen von „root\_path\(\).native\(\)“ und aller unmittelbar nachfolgenden redundanten Verzeichnistrennzeichen. Die Komponente kann leer sein.  
  
## path::remove\_filename  
  
```  
path& remove_filename();  
  
```  
  
## path::replace\_extension  
  
```  
path& replace_extension(const path& newext = path());  
  
```  
  
 Die Memberfunktion entfernt zuerst das Suffix „extension\(\).native\(\)“ aus „myname“. Dann wird bei „\!newext.empty\(\) && newext\[0\] \!\= dot“ \(wobei „dot“ dem Wert „\*path\("."\).c\_str\(\)“ entspricht\) „dot“ an „myname“ angehängt. Dann wird „newext“ an „myname“ angefügt.  
  
## path::replace\_filename  
  
```  
  
path& replace_filename(const path& pval);  
  
```  
  
 Die Memberfunktion führt Folgendes aus:  
  
```  
remove_filename();  
*this /= pval;  
return (*this);  
```  
  
## path::root\_directory  
  
```  
path root_directory() const;  
  
```  
  
 Gibt die Stammverzeichniskomponente von „myname“ zurück. Die Komponente kann leer sein.  
  
## path::root\_name  
  
```  
path root_name() const;  
  
```  
  
 Gibt die Stammnamenkomponente von „myname“ zurück. Die Komponente kann leer sein.  
  
## path::root\_path  
  
```  
  
path root_path() const;  
  
```  
  
 Gibt die Stammpfadkomponente von „myname“ zurück, insbesondere „root\_name\(\) \/ root\_directory“. Die Komponente kann leer sein.  
  
## path::stem  
  
```  
  
path stem() const;  
  
```  
  
 Gibt die Stammkomponente von „myname“ zurück, insbesondere „filename\(\).native\(\)“, wobei jedes nachfolgende „extension\(\).native\(\)“ entfernt wird. Die Komponente kann leer sein.  
  
## path::string  
  
```  
template<class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
    basic_string<Elem, Traits, Alloc>  
        string(const Alloc& al = Alloc()) const;  
STD string string() const;  
  
```  
  
 Die erste \(Vorlagen\-\) Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz genauso wie:  
  
1.  string\(\) für string\<char, Traits, Alloc\>\(\)  
  
2.  wstring\(\) für string\<wchar\_t, Traits, Alloc\>\(\)  
  
3.  u16string\(\) für string\<char16\_t, Traits, Alloc\>\(\)  
  
4.  u32string\(\) für string\<char32\_t, Traits, Alloc\>\(\)  
  
 Die zweite Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in die Codierung, die vom Hostsystem für eine char\-Sequenz bevorzugt wird, und gibt diese in einem Objekt vom Typ „string“ gespeichert zurück.  
  
## path::string\_type  
  
```  
typedef basic_string<value_type> string_type;  
  
```  
  
 Der Typ ist ein Synonym für „basic\_string\<value\_type\>“.  
  
## path::swap  
  
```  
void swap(path & right) noexcept;  
  
```  
  
 Führt „swap\(mypath, right.mypath\)“ aus.  
  
## path::u16string  
  
```  
STD u16string u16string() const;  
  
```  
  
 Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF\-16, und gibt diese in einem Objekt vom Typ „u16string“ gespeichert zurück.  
  
## path::u32string  
  
```  
STD u32string u32string() const;  
  
```  
  
 Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF\-32, und gibt diese in einem Objekt vom Typ „u32string“ gespeichert zurück.  
  
## path::u8string  
  
```  
STD string u8string() const;  
  
```  
  
 Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF\-8, und gibt diese in einem Objekt vom Typ „u8string“ gespeichert zurück.  
  
## path::value\_type  
  
```  
  
#if _WIN32_C_LIB  
typedef wchar_t value_type;  
#else // assume Posix  
typedef char value_type;  
#endif // filesystem model now defined  
  
```  
  
 Der Typ beschreibt die Pfadelemente, die vom Hostbetriebssystem bevorzugt werden.  
  
## path::wstring  
  
```  
STD wstring wstring() const;  
```  
  
 Konvertiert die in „mypath“ gespeicherte Sequenz in die Codierung, die vom Hostsystem für eine wchar\_t\-Sequenz bevorzugt wird, und gibt diese in einem Objekt vom Typ „wstring“ gespeichert zurück.  
  
## Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::tr2::sys  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)