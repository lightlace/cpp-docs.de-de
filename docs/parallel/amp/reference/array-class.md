---
title: Array-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 470918d62357a8dd463db35b4d929e7ec5c2f251
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="array-class"></a>array-Klasse
Stellt einen Datencontainer dar, mit dem Daten auf eine Zugriffstaste verschoben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename value_type, int _Rank>  
friend class array;  
```  
  
#### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Elementtyp der Daten.  
  
 `_Rank`  
 Der Rang des Arrays.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Array-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `array`-Klasse.|  
|[~ array-Destruktor](#dtor)|Zerstört das `array`-Objekt.|  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[copy_to](#copy_to)|Kopiert den Inhalt des array-Objekts in ein anderes array-Objekt.|  
|[data](#data)|Gibt einen Zeiger auf die Rohdaten des array-Objekts zurück.|  
|[get_accelerator_view](#get_accelerator_view)|Gibt die [Accelerator_view](accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Ruft das zweite [Accelerator_view](accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die `array` Objekt.|  
|[get_cpu_access_type](#get_cpu_access_type)|Gibt die [Access_type](concurrency-namespace-enums-amp.md#access_type) des Arrays. Auf diese Methode kann nur auf der CPU zugegriffen werden.|  
|[get_extent](#get_extent)|Gibt die [Block](extent-class.md) -Objekt des Arrays.|  
|[reinterpret_as](#reinterpret_as)|Gibt ein eindimensionales Array zurück, das alle Elemente im `array`-Objekt enthält.|  
|[section](#section)|Gibt einen Unterabschnitt des `array`-Objekts zurück, das sich am angegebenen Ursprung befindet und optional den angegebenen Wertebereich hat.|  
|[view_as](#view_as)|Gibt eine [Array_view](array-view-class.md) -Objekt, das aus konstruiert ist die `array` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator Std:: vector&lt;Value_type&gt;](#operator_vec)|Verwendet `copy(*this, vector)` implizit konvertieren das Array in eine std::[Vektor](../../../standard-library/vector-class.md) Objekt.|  
|[Operator()](#operator_call)|Gibt den Elementwert zurück, der von den Parametern angegeben wird.|  
|[Operator]](#operator_at)|Gibt das Element am angegebenen Index zurück.|  
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `array`-Objekts in dieses Objekt.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Rank-Konstante](#rank)|Speichert den Rang des Arrays.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accelerator_view-Objekt](#accelerator_view)|Ruft die [Accelerator_view](accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.|  
|[associated_accelerator_view](#associated_accelerator_view)|Ruft das zweite [Accelerator_view](accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die `array` Objekt.|  
|[cpu_access_type](#cpu_access_type)|Ruft die [Access_type](concurrency-namespace-enums-amp.md#access_type) , das darstellt, wie die CPU der Speicher des Arrays zugreifen kann.|  
|[extent](#extent)|Ruft den Wertebereich ab, der die Form des Arrays definiert.|  
  
## <a name="remarks"></a>Hinweise  
 Der Typ `array<T,N>` stellt ein dichtes und reguläres (nicht verzweigtes) *N*-dimensionales Array, das in einem bestimmten Ort, z. B. einer Zugriffstaste oder die CPU befindet. Der Datentyp der Elemente im Array ist `T`. Der Typ muss mit der Zielzugriffstaste kompatibel ist. Obwohl der Rang, `N`, des Arrays statisch ermittelt und Teil des Typs ist, wird der Wertebereich des Arrays durch die Laufzeit bestimmt und durch Verwendung der `extent<N>`-Klasse ausgedrückt.  
  
 Ein Array kann eine beliebige Anzahl Dimensionen haben, obwohl einige Funktionen für `array`-Objekte mit dem Rang eins, zwei und drei spezialisiert ist. Wenn Sie das Dimensionsargument weglassen, ist der Standardwert 1.  
  
 Arraydaten grenzen im Arbeitsspeicher aneinander. Elemente, die sich in der unwichtigsten Dimension um eins unterscheiden, grenzen im Arbeitsspeicher aneinander.  
  
 Arrays werden logisch als Werttypen betrachtet, da beim Kopieren eines Arrays in ein anderes eine tiefe Kopie ausgeführt wird. Zwei Arrays zeigen nie auf die gleichen Daten.  
  
 Der `array<T,N>`-Typ wird in verschiedenen Szenarien verwendet:  
  
-   Als Datencontainer, der in Berechnungen auf einer Zugriffstaste verwendet werden kann.  
  
-   Als Datencontainer zum Vorhalten von Arbeitsspeicher auf der Host-CPU (die zum Kopieren in und von anderen Arrays verwendet werden kann).  
  
-   Als Stagingobjekt, um in Kopien vom Host zum Gerät als schneller Vermittler zu fungieren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `array`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a>~ Array 

 Zerstört das `array`-Objekt.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="accelerator_view"></a>accelerator_view-Objekt 

 Ruft die [Accelerator_view](accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="ctor"></a>Array 

 Initialisiert eine neue Instanz der dem [array-Klasse](array-class.md). Für "`array<T,N>`" ist kein Standardkonstruktor vorhanden. Alle Konstruktoren werden nur auf der CPU ausgeführt. Sie können nicht auf einem Direct3D-Ziel ausgeführt werden.  
  
```  
explicit array(  
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);  
  
explicit array(  
    int _E0) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first, 
    _InputIterator _Src_last) restrict(cpu);
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,    
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
explicit array(  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);  
  
array(  
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);  
  
array(const array& _Other) restrict(cpu);  
  
array(array&& _Other) restrict(cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Associated_Av`  
 Ein accelerator_view-Objekt, das den bevorzugten Zielort des Arrays angibt.  
  
 `_Av`  
 Ein [Accelerator_view](accelerator-view-class.md) -Objekt, das den Speicherort des Arrays angibt.  
  
 `_Cpu_access_type`  
 Die gewünschte [Access_type](concurrency-namespace-enums-amp.md#access_type) für das Array auf der CPU. Dieser Parameter hat den Standardwert `access_type_auto` und überlässt die Bestimmung des CPU- `access_type`-Objekts der Laufzeit. Das tatsächliche CPU-`access_type`-Objekt für das Array kann mithilfe der `get_cpu_access_type`-Methode abgefragt werden.  
  
 `_Extent`  
 Der Umfang in jeder Dimension des Arrays.  
  
 `_E0`  
 Die wichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E1`  
 Die zweitwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E2`  
 Die unwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_InputIterator`  
 Der Typ des Eingabeiterators.  
  
 `_Src`  
 Das zu kopierende Objekt.  
  
 `_Src_first`  
 Ein Anfangsiterator in den Quellcontainer.  
  
 `_Src_last`  
 Ein Endeiterator in den Quellcontainer.  
  
 `_Other`  
 Andere Datenquelle.  
  
 `_Rank`  
 Der Rang des Abschnitts.  
  
 `value_type`  
 Der Datentyp der Elemente, die kopiert werden.  
  
##  <a name="associated_accelerator_view"></a>associated_accelerator_view 

 Ruft das zweite [Accelerator_view](accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die `array` Objekt.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a>copy_to 

 Kopiert den Inhalt der `array` zu einem anderen `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Dest`  
 Die [Array_view](array-view-class.md) Objekt zu kopieren.  
  
##  <a name="cpu_access_type"></a>cpu_access_type 

 Ruft das für dieses Array zulässige access_type-Objekt für die CPU ab.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="data"></a>Daten 

 Gibt einen Zeiger auf die Rohdaten des `array`-Objekts zurück.  
  
```  
value_type* data() restrict(amp, cpu);
  
const value_type* data() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Rohdaten des array-Objekts.  
  
##  <a name="extent"></a>Wertebereich 

 Ruft die [Block](extent-class.md) -Objekt, das die Form des definiert die `array`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_accelerator_view"></a>get_accelerator_view 

 Gibt die [Accelerator_view](accelerator-view-class.md) -Objekt, das die Position darstellt, in dem die `array` Objekt zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;  
```    
  
### <a name="return-value"></a>Rückgabewert  
 Die `accelerator_view` -Objekt, das die Position darstellt, in dem die `array` Objekt zugeordnet ist.  
  
##  <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 Ruft das zweite [Accelerator_view](accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die `array` Objekt.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite [Accelerator_view](accelerator-view-class.md) Objekt an den staging-Konstruktor übergeben.  
  
##  <a name="get_cpu_access_type"></a>get_cpu_access_type 

 Gibt das CPU-access_type-Objekt zurück, das für dieses Array zulässig ist.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="get_extent"></a>get_extent 

 Gibt die [Block](extent-class.md) Objekt von der `array`.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `extent` Objekt von der `array`.  
  
##  <a name="operator_vec"></a>Operator Std:: vector&lt;Value_type&gt; 

 Verwendet `copy(*this, vector)` das Array implizit in eine Std:: Vector-Objekt zu konvertieren.  
  
```  
operator std::vector<value_type>() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Datentyp der Elemente des Vektors.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt des Typs `vector<T>`, das eine Kopie der Daten im Array enthält.  
  
##  <a name="operator_call"></a>Operator() 

 Gibt den Elementwert zurück, der von den Parametern angegeben wird.  
  
```  
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);
  
value_type& operator() (int _I0, int _I1) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;
  
value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Speicherort des Elements.  
  
 `_I0`  
 Die wichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I1`  
 Die zweitwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I2`  
 Die unwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I`  
 Der Speicherort des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Elementwert, der von den Parametern angegeben wird.  
  
##  <a name="operator_at"></a>Operator] 

 Gibt das Element am angegebenen Index zurück.  
  
```  
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator[]  
    (const index<_Rank>& _Index) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```  
    
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index.  
  
 `_I`  
 Der Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element am angegebenen Index.  
  
##  <a name="operator_eq"></a>Operator = 

 Kopiert den Inhalt des angegebenen `array` Objekt.  
  
```  
array& operator= (const array& _Other) restrict(cpu);  
   
array& operator= (array&& _Other) restrict(cpu);  
 
array& operator= (  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `array`-Objekt, aus dem kopiert werden soll.  
  
 `_Src`  
 Das `array`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `array`-Objekt.  
  
##  <a name="rank"></a>Rang 

 Speichert den Rang des der `array`.  
  
```  
static const int rank = _Rank;  
```  
## <a name="reinterpret_as"></a>reinterpret_as 

Interpretiert das Array durch ein eindimensionales Array_view, die optional einen anderen Werttyp als das Quellarray haben kann.

### <a name="syntax"></a>Syntax
``` 
template <typename _Value_type2>  
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);  
  
template <typename _Value_type2>  
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);  
``` 
  
### <a name="parameters"></a>Parameter  
`_Value_type2`Der Datentyp der zurückgegebenen Daten.

### <a name="return-value"></a>Rückgabewert
Ein Array_view oder const Array_view-Objekt, das basierend auf das Array, mit dem Elementtyp Typen von T ElementType und der Rang von N auf 1 reduziert.

### <a name="remarks"></a>Hinweise
Manchmal ist es hilfreich, ein mehrdimensionales Array so anzuzeigen, als wäre es ein lineares, eindimensionales Array, möglicherweise mit einem anderen Werttyp als das Quellarray. Sie können dazu diese Methode verwenden.
**Vorsicht** ein Arrayobjekt mithilfe eines anderen Werttyps ist ein potenziell unsicherer Vorgang. Es empfiehlt sich, diese Funktion mit Bedacht zu verwenden. 

Der folgende Code veranschaulicht dies.

```cpp  
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...; 
array_view<float,1> v = a.reinterpret_as<float>(); 

assert(v.extent == 3*a.extent);
```  
  
##  <a name="section"></a>im Abschnitt 

 Gibt einen Unterabschnitt des `array`-Objekts zurück, das sich am angegebenen Ursprung befindet und optional den angegebenen Wertebereich hat.  
  
```  
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);
  
array_view<value_type,1> section(
    int _I0,  
    int _E0) restrict(amp,cpu);
  
array_view<const value_type,1> section(
    int _I0,  
    int _E0) const restrict(amp,cpu);
  
array_view<value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) restrict(amp,cpu);
  
array_view<const value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);
  
array_view<value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) restrict(amp,cpu);
  
array_view<const value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_E0`  
 Die wichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E1`  
 Die zweitwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E2`  
 Die unwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_Ext`  
 Die [Block](extent-class.md) -Objekt, das den Umfang des Abschnitts angibt. Der Ursprung ist 0.  
  
 `_Idx`  
 Die [Index](index-class.md) Objekt, das die Position des Ursprungs angibt. Der Unterabschnitt entspricht dem Rest des Umfangs.  
  
 `_I0`  
 Die wichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I1`  
 Die zweitwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I2`  
 Die unwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_Rank`  
 Der Rang des Abschnitts.  
  
 `_Section_extent`  
 Die [Block](extent-class.md) -Objekt, das den Umfang des Abschnitts angibt.  
  
 `_Section_origin`  
 Die [Index](index-class.md) Objekt, das die Position des Ursprungs angibt.  
  
 `value_type`  
 Der Datentyp der Elemente, die kopiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Unterabschnitt des `array`-Objekts zurück, das sich am angegebenen Ursprung befindet und optional den angegebenen Wertebereich hat. Wenn nur das `index`-Objekt angegeben wird, enthält der Unterabschnitt alle Elemente im zugeordneten Raster, deren Indizes größer sind als die Indizes der Elemente im `index`-Objekt.  
  
##  <a name="view_as"></a>view_as 

 Interpretiert dieses Array als ein [Array_view](array-view-class.md) eines abweichenden Rang.  
  
```  
template <int _New_rank>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

 
template <int _New_rank>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_New_rank`  
 Der Rang des `extent`-Objekts wurde als Parameter übergeben.  
  
 `_View_extent`  
 Der Wertebereich, der verwendet wird, erstellt die [Array_view](array-view-class.md) Objekt.  
  
 `value_type`  
 Der Datentyp der Elemente in den ursprünglichen `array` -Objekt und das zurückgegebene `array_view` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [Array_view](array-view-class.md) -Objekt, das erstellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

