---
title: "CType &lt; Char &gt;-Klasse"
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
  - "ctype<char>"
  - "locale/std::ctype<char>"
  - "std::ctype<char>"
  - "std.ctype<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CType < Char >-Klasse"
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# CType &lt; Char &gt;-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse ist eine explizite Spezialisierung der Vorlagenklasse **Ctype \< CharType**> eingeben `char`, beschreibt ein Objekt, das als gebietsschemafacet zur verschiedene Eigenschaften eines Zeichens vom Typ charakterisieren dienen kann `char`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <>  
class ctype<char>  
: public ctype_base  
{  
public:  
    typedef char _Elem;  
    typedef _Elem char_type;  
    bool is(
    mask _Maskval,  
    _Elem _Ch) const;

 
    const _Elem* is(
    const _Elem* first,  
    const _Elem* last,  
    mask* dest) const;

 
    const _Elem* scan_is(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    const _Elem* scan_not(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    _Elem tolower(
    _Elem _Ch) const;

 
    const _Elem* tolower(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem toupper(
    _Elem _Ch) const;

 
    const _Elem* toupper(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem widen(
    char _Byte) const;

 
    const _Elem* widen(
    const char* first,  
    const char* last,  
    _Elem* dest) const;

 
    const _Elem* _Widen_s(
    const char* first,  
    const char* last,  
    _Elem* dest,  
    size_t dest_size) const;

 
    _Elem narrow(
    _Elem _Ch,  
    char _Dflt = '\0') const;

 
    const _Elem* narrow(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest) const;

 
    const _Elem* _Narrow_s(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest,  
    size_t dest_size) const;

 
    static locale::id& id;  
    explicit ctype(
    const mask* _Table = 0,  
    bool _Deletetable = false,  
    size_t _Refs = 0);

protected:  
    virtual ~ctype();
//other protected members  
};  
```  
  
## <a name="remarks"></a>Hinweise  
 Die explizite Spezialisierung unterscheidet sich von der Vorlagenklasse auf verschiedene Weise:  
  
-   Ein Objekt der Klasse Ctype < `char`> speichert einen Zeiger auf das erste Element einer Ctype Mask-Tabelle, ein Array von UCHAR_MAX + 1 Elementen des Typs **ctype_base::mask**. Es speichert auch eine Boolean-Objekt, der angibt, ob das Array gelöscht werden soll (mit `operator delete[]`) beim Ctype \< **Elem**>-Objekt zerstört wird.  
  
-   Die einzige öffentliche Konstruktor können Sie angeben **Registerkarte**, die Ctype-Maske-Tabelle und **del**, Boolean-Objekt, das ist "true", wenn das Array werden soll gelöscht, sobald Ctype < `char`> Objekt zerstört wird, sowie den Verweiszähler dieser Planergruppe Parameter Refs.  
  
-   Die geschützte Memberfunktion **Tabelle** Gibt die gespeicherte Ctype Maske Tabelle zurück.  
  
-   Der statische Member-Objekt **Table_size** Gibt die minimale Anzahl von Elementen in einer Ctype-Maske-Tabelle.  
  
-   Die geschützte statische Memberfunktion **Classic_table**(Ctype Maske gibt die Tabelle zurück, die das Gebietsschema "C".  
  
-   Es sind keine geschützten virtuellen Memberfunktionen [Do_is](../standard-library/ctype-class.md#ctype__do_is), [Do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is), oder [Do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not). Die entsprechende öffentliche Memberfunktionen führen Sie die entsprechenden Vorgänge selbst.  
  
 Die Memberfunktionen [Do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) und [Do_widen](../standard-library/ctype-class.md#ctype__do_widen) Elemente ohne Änderungen kopiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Facet-Klasse](../Topic/facet%20Class.md)   
 [Ctype_base-Klasse](../standard-library/ctype-base-class.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

