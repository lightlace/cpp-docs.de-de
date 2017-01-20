---
title: "array-Klasse"
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
  - "amp/Concurrency::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array-Klasse"
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
caps.handback.revision: "31"
ms.author: "mblome"
manager: "ghogen"
---
# array-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Datencontainer dar, mit dem Daten auf eine Zugriffstaste verschoben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
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
|[Array:: Array-Konstruktor](#array__array_constructor)|Initialisiert eine neue Instanz der `array`-Klasse.|  
|[Array:: ~ array-Destruktor](#array___dtorarray_destructor)|Zerstört das `array`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Array:: copy_to-Methode](#array__copy_to_method)|Kopiert den Inhalt des array-Objekts in ein anderes array-Objekt.|  
|[Array:: Data-Methode](#array__data_method)|Gibt einen Zeiger auf die Rohdaten des array-Objekts zurück.|  
|[Array:: get_accelerator_view-Methode](#array__get_accelerator_view_method)|Gibt die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.|  
|[Array:: get_associated_accelerator_view-Methode](#array__get_associated_accelerator_view_method)|Ruft das zweite [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die [Array](../../../parallel/amp/reference/array-class.md) Objekt.|  
|[Array:: get_cpu_access_type-Methode](#array__get_cpu_access_type_method)|Gibt die [Access_type](access_type%20Enumeration.md) des Arrays. Auf diese Methode kann nur auf der CPU zugegriffen werden.|  
|[Array:: get_extent-Methode](#array__get_extent_method)|Gibt die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) -Objekt des Arrays.|  
|[Array:: reinterpret_as-Methode](#array__reinterpret_as_method)|Gibt ein eindimensionales Array zurück, das alle Elemente im `array`-Objekt enthält.|  
|[Array:: Section-Methode](#array__section_method)|Gibt einen Unterabschnitt der [Array](../../../parallel/amp/reference/array-class.md) -Objekt am angegebenen Ursprung befindet und optional, die den angegebenen Wertebereich hat.|  
|[Array:: view_as-Methode](#array__view_as_method)|Gibt eine [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt, das aus konstruiert ist die `array` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Array:: Std:: vector&lt;Value_type&gt; Operator](#array__operator_std__vector_lt__value_type_gt__operator)|Verwendet `copy(*this, vector)` implizit konvertieren das Array in eine std::[Vektor](vector%20Class.md) Objekt.|  
|[Array::Operator()-Operator](#array__operator___operator)|Gibt den Elementwert zurück, der von den Parametern angegeben wird.|  
|[Array:: Operator []-Operator](#array__operator_at_operator)|Gibt das Element am angegebenen Index zurück.|  
|[Array:: Operator =-Operator](#array__operator_eq_operator)|Kopiert den Inhalt des angegebenen `array`-Objekts in dieses Objekt.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Array:: Rank-Konstante](#array__rank_constant)|Speichert den Rang des Arrays.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Array:: accelerator_view-Datenmember](#array__accelerator_view_data_member)|Ruft die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.|  
|[Array:: associated_accelerator_view-Datenmember](#array__associated_accelerator_view_data_member)|Ruft das zweite [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die [Array](../../../parallel/amp/reference/array-class.md) Objekt.|  
|[Array:: cpu_access_type-Datenmember](#array__cpu_access_type_data_member)|Ruft die [Access_type](access_type%20Enumeration.md) das darstellt, wie die CPU der Speicher des Arrays zugreifen kann.|  
|[Array:: Extent-Datenmember](#array__extent_data_member)|Ruft den Wertebereich ab, der die Form des Arrays definiert.|  
  
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
  
##  <a name="a-namearraydtorarraydestructora-arrayarray-destructor"></a><a name="array___dtorarray_destructor"></a>  Array:: ~ array-Destruktor  
 Zerstört das `array`-Objekt.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-namearrayacceleratorviewdatamembera-arrayacceleratorview-data-member"></a><a name="array__accelerator_view_data_member"></a>  Array:: accelerator_view-Datenmember  
 Ruft die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das die Position darstellt, in dem das Array zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namearrayarrayconstructora-arrayarray-constructor"></a><a name="array__array_constructor"></a>  Array:: Array-Konstruktor  
 Initialisiert eine neue Instanz der dem [array-Klasse](../../../parallel/amp/reference/array-class.md). Für "`array<T,N>`" ist kein Standardkonstruktor vorhanden. Alle Konstruktoren werden nur auf der CPU ausgeführt. Sie können nicht auf einem Direct3D-Ziel ausgeführt werden.  
  
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

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
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

 
array(
    const array& _Other) restrict(cpu);

 
array(
    array&& _Other) restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Associated_Av`  
 Ein accelerator_view-Objekt, das den bevorzugten Zielort des Arrays angibt.  
  
 `_Av`  
 Ein [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das den Speicherort des Arrays angibt.  
  
 `_Cpu_access_type`  
 Die gewünschte [Access_type](access_type%20Enumeration.md)  für das Array auf der CPU. Dieser Parameter hat den Standardwert `access_type_auto` und überlässt die Bestimmung des CPU- `access_type`-Objekts der Laufzeit. Das tatsächliche CPU-`access_type`-Objekt für das Array kann mithilfe der `get_cpu_access_type`-Methode abgefragt werden.  
  
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
  
##  <a name="a-namearrayassociatedacceleratorviewdatamembera-arrayassociatedacceleratorview-data-member"></a><a name="array__associated_accelerator_view_data_member"></a>  Array:: associated_accelerator_view-Datenmember  
 Ruft das zweite [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die [Array](../../../parallel/amp/reference/array-class.md) Objekt.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namearraycopytomethoda-arraycopyto-method"></a><a name="array__copy_to_method"></a>  Array:: copy_to-Methode  
 Kopiert den Inhalt der [Array](../../../parallel/amp/reference/array-class.md) zu einem anderen `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Dest`  
 Die [Array_view](../../../parallel/amp/reference/array-view-class.md) Objekt zu kopieren.  
  
##  <a name="a-namearraycpuaccesstypedatamembera-arraycpuaccesstype-data-member"></a><a name="array__cpu_access_type_data_member"></a>  Array:: cpu_access_type-Datenmember  
 Ruft das für dieses Array zulässige access_type-Objekt für die CPU ab.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namearraydatamethoda-arraydata-method"></a><a name="array__data_method"></a>  Array:: Data-Methode  
 Gibt einen Zeiger auf die unformatierten Daten eines der [Array](../../../parallel/amp/reference/array-class.md).  
  
```  
value_type* data() restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Rohdaten des array-Objekts.  
  
##  <a name="a-namearrayextentdatamembera-arrayextent-data-member"></a><a name="array__extent_data_member"></a>  Array:: Extent-Datenmember  
 Ruft die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) -Objekt, das die Form des definiert die [Array](../../../parallel/amp/reference/array-class.md).  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearraygetacceleratorviewmethoda-arraygetacceleratorview-method"></a><a name="array__get_accelerator_view_method"></a>  Array:: get_accelerator_view-Methode  
 Gibt die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das die Position darstellt, in dem die [Array](../../../parallel/amp/reference/array-class.md) Objekt zugeordnet ist. Auf diese Eigenschaft kann nur auf der CPU zugegriffen werden.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `accelerator_view` -Objekt, das die Position darstellt, in dem die [Array](../../../parallel/amp/reference/array-class.md) Objekt zugeordnet ist.  
  
##  <a name="a-namearraygetassociatedacceleratorviewmethoda-arraygetassociatedacceleratorview-method"></a><a name="array__get_associated_accelerator_view_method"></a>  Array:: get_associated_accelerator_view-Methode  
 Ruft das zweite [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt, das als Parameter übergeben wird, wenn ein stagingkonstruktor aufgerufen wird, instanziiert die [Array](../../../parallel/amp/reference/array-class.md) Objekt.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt an den staging-Konstruktor übergeben.  
  
##  <a name="a-namearraygetcpuaccesstypemethoda-arraygetcpuaccesstype-method"></a><a name="array__get_cpu_access_type_method"></a>  Array:: get_cpu_access_type-Methode  
 Gibt das CPU-access_type-Objekt zurück, das für dieses Array zulässig ist.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-namearraygetextentmethoda-arraygetextent-method"></a><a name="array__get_extent_method"></a>  Array:: get_extent-Methode  
 Gibt die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) Gegenstand der [Array](../../../parallel/amp/reference/array-class.md).  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `extent` Gegenstand der [Array](../../../parallel/amp/reference/array-class.md).  
  
##  <a name="a-namearrayoperatorstdvectorltvaluetypegtoperatora-arrayoperator-stdvectorltvaluetypegt-operator"></a><a name="array__operator_std__vector_lt__value_type_gt__operator"></a>  Array:: Std:: vector&lt;Value_type&gt; Operator  
 Verwendet `copy(*this, vector)` das Array implizit in eine Std:: Vector-Objekt zu konvertieren.  
  
''' Operator Std:: Vector \< Value_type > () const restrict(cpu);
```  
  
### Parameters  
 `value_type`  
 The data type of the elements of the vector.  
  
### Return Value  
 An object of type `vector<T>` that contains a copy of the data that is contained in the array.  
  
##  <a name="array__operator___operator"></a>  array::operator() Operator  
 Returns the element value that is specified by the parameters.  
  
```  
Value_type & operator() (const Index \< _Rank > & _Index) restrict(amp,cpu);

 
const Value_type & operator() (const Index \< _Rank > & _Index) const restrict(amp,cpu);

 
Value_type & restrict(amp,cpu) operator() (_I0 Int, Int _I1);

 
const Value_type & const restrict(amp,cpu) operator() (_I0 Int, Int _I1);

 
Value_type & restrict(amp,cpu) operator() (_I0 Int, Int _I1, Int _I2);

 
const Value_type & const restrict(amp,cpu) operator() (_I0 Int, Int _I1, Int _I2);

 
TypeName details::_Projection_result_type \< Werttyp, _Rank >:: _Result_type operator() (Int _ich) restrict(amp,cpu);

 
TypeName details::_Projection_result_type \< Werttyp, _Rank >:: _Const_result_type operator() (Int _ich) const restrict(amp,cpu);
```  
  
### Parameters  
 `_Index`  
 The location of the element.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_I`  
 The location of the element.  
  
### Return Value  
 The element value specified by the parameters.  
  
##  <a name="array__operator_at_operator"></a>  array::operator[] Operator  
 Returns the element that is at the specified index.  
  
```  
Value_type & -Operator [] (const Index \< _Rank > & _Index) restrict(amp,cpu);

 
const Value_type & -Operator [] (const Index \< _Rank > & _Index) const restrict(amp,cpu);

 
TypeName details::_Projection_result_type \< Werttyp, _Rank >:: Operator _Result_type[](int _I) restrict(amp,cpu);

 
TypeName details::_Projection_result_type \< Werttyp, _Rank >:: Operator _Const_result_type[](int _I) const restrict(amp,cpu);
```  
  
### Parameters  
 `_Index`  
 The index.  
  
 `_I`  
 The index.  
  
### Return Value  
 The element that is at the specified index.  
  
##  <a name="array__operator_eq_operator"></a>  array::operator= Operator  
 Copies the contents of the specified [array](../../../parallel/amp/reference/array-class.md) object.  
  
```  
Array & Operator = (const Array & _Other) restrict(cpu);

 
Operator & Array = (Array & & _Other) restrict(cpu);

 
Array & Operator = (const Array_view \< const Werttyp, _Rank > & _Src) restrict(cpu);
```  
  
### Parameters  
 `_Other`  
 The `array` object to copy from.  
  
 `_Src`  
 The `array` object to copy from.  
  
### Return Value  
 A reference to this `array` object.  
  
##  <a name="array__rank_constant"></a>  array::rank Constant  
 Stores the rank of the [array](../../../parallel/amp/reference/array-class.md).  
  
```  
static const Int-Rank = _Rank;  
```  
  
##  <a name="array__section_method"></a>  array::section Method  
 Returns a subsection of the [array](../../../parallel/amp/reference/array-class.md) object that is at the specified origin and, optionally, that has the specified extent.  
  
```  
Array_view \< Werttyp, _Rank > im Abschnitt (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu);

 
Array_view \< const Werttyp, _Rank > im Abschnitt (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) const restrict(amp,cpu);

 
Array_view \< Werttyp, _Rank > im Abschnitt (const Concurrency::extent \< _Rank > & _Ext) restrict(amp,cpu);

 
Array_view \< const Werttyp, _Rank > im Abschnitt (const Concurrency::extent \< _Rank > & _Ext) const restrict(amp,cpu);

 
Array_view \< Werttyp, _Rank > im Abschnitt (const Index \< _Rank > & _Idx) restrict(amp,cpu);

 
Array_view \< const Werttyp, _Rank > im Abschnitt (const Index \< _Rank > & _Idx) const restrict(amp,cpu);

 
Array_view \< Werttyp, der 1 > Abschnitt (Int _I0,  
    restrict(amp,cpu) Int _E0);

 
Array_view \< const Werttyp, der 1 > Abschnitt (Int _I0,  
    const Int _E0)-restrict(amp,cpu);

 
Array_view \< Werttyp, 2 > Abschnitt (Int _I0,  
    Int-_I1  
    Int-_E0  
    restrict(amp,cpu) Int _E1);

 
Array_view \< const Werttyp, 2 > Abschnitt (Int _I0,  
    Int-_I1  
    Int-_E0  
    const Int _E1)-restrict(amp,cpu);

 
Array_view \< Werttyp, 3 > Abschnitt (Int _I0,  
    Int-_I1  
    Int-_I2  
    Int-_E0  
    Int-_E1  
    restrict(amp,cpu) Int _E2);

 
Array_view \< const Werttyp, 3 > Abschnitt (Int _I0,  
    Int-_I1  
    Int-_I2  
    Int-_E0  
    Int-_E1  
    const Int _E2)-restrict(amp,cpu);
```  
  
### Parameters  
 `_E0`  
 The most significant component of the extent of this section.  
  
 `_E1`  
 The next-to-most-significant component of the extent of this section.  
  
 `_E2`  
 The least significant component of the extent of this section.  
  
 `_Ext`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section. The origin is 0.  
  
 `_Idx`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin. The subsection is the rest of the extent.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_Rank`  
 The rank of the section.  
  
 `_Section_extent`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section.  
  
 `_Section_origin`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin.  
  
 `value_type`  
 The data type of the elements that are copied.  
  
### Return Value  
 Returns a subsection of the `array` object that is at the specified origin and, optionally, that has the specified extent. When only the `index` object is specified, the subsection contains all elements in the associated grid that have indexes that are larger than the indexes of the elements in the `index` object.  
  
##  <a name="array__view_as_method"></a>  array::view_as Method  
 Reinterprets this array as an [array_view](../../../parallel/amp/reference/array-view-class.md) of a different rank.  
  
```  
Vorlage \< Int _New_rank  
>  
Array_view \< Werttyp, _New_rank > View_as (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu);

 
Vorlage \< Int _New_rank  
>  
Array_view \< const Werttyp, _New_rank > View_as (const Concurrency::extent \< _New_rank > & _View_extent) const restrict(amp,cpu);
```  
  
### Parameters  
 `_New_rank`  
 The rank of the `extent` object passed as a parameter.  
  
 `_View_extent`  
 The extent that is used to construct the new [array_view](../../../parallel/amp/reference/array-view-class.md) object.  
  
 `value_type`  
 The data type of the elements in both the original [array](../../../parallel/amp/reference/array-class.md) object and the returned `array_view` object.  
  
### Return Value  
 The [array_view](../../../parallel/amp/reference/array-view-class.md) object that is constructed.  
  
## See Also  
 [Concurrency Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
