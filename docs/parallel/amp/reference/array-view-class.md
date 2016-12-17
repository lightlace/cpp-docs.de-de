---
title: "array_view-Klasse"
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
  - "amp/Concurrency::array_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array_view-Klasse"
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# array_view-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine n-dimensionale Ansicht der Daten dar, die in einem anderen Container vorgehalten werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <
    typename value_type,  
    int _Rank = 1  
>  
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Datentyp der Elemente im `array_view`-Objekt.  
  
 `_Rank`  
 Der Rang des `array_view`-Objekts.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[array_view:: array_view-Konstruktor](#array_view__array_view_constructor)|Initialisiert eine neue Instanz der `array_view`-Klasse. Für "`array<T,N>`" ist kein Standardkonstruktor vorhanden. Alle Konstruktoren sind auf die CPU beschränkt und können nicht auf einem Direct3D-Ziel ausgeführt werden.|  
|[Array_view:: ~ Array_view-Destruktor](#array_view___dtorarray_view_destructor)|Zerstört das `array_view`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[array_view:: copy_to-Methode](#array_view__copy_to_method)|Kopiert den Inhalt des `array_view`-Objekts in das angegebene Ziel durch Aufrufen von `copy(*this, dest)`.|  
|[array_view:: Data-Methode](#array_view__data_method)|Gibt einen Zeiger auf die Rohdaten des `array_view`-Objekts zurück.|  
|[array_view:: discard_data-Methode](#array_view__discard_data_method)|Verwirft die aktuellen Daten, die dieser Ansicht zugrunde liegen.|  
|[array_view:: get_extent-Methode](#array_view__get_extent_method)|Gibt das extent-Objekt des array_view-Objekts zurück.|  
|[array_view:: get_ref-Methode](#array_view__get_ref_method)|Gibt einen Verweis auf das indizierte Element zurück.|  
|[array_view:: get_source_accelerator_view-Methode](#array_view__get_source_accelerator_view_method)|Gibt die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) in dem die Datenquelle der `array_view` befindet.|  
|[array_view:: Refresh-Methode](#array_view__refresh_method)|Benachrichtigt das `array_view`-Objekt, dass sein gebundener Speicher außerhalb der `array_view`-Schnittstelle geändert wurde. Ein Aufruf dieser Methode führt dazu, dass alle zwischengespeicherten Informationen veraltet sind.|  
|[array_view:: reinterpret_as-Methode](#array_view__reinterpret_as_method)|Gibt ein eindimensionales Array zurück, das alle Elemente im `array_view`-Objekt enthält.|  
|[array_view:: Section-Methode](#array_view__section_method)|Gibt einen Unterabschnitt des `array_view`-Objekts zurück, das sich am angegebenen Ursprung befindet und optional den angegebenen Wertebereich hat.|  
|[array_view:: Synchronize-Methode](#array_view__synchronize_method)|Synchronisiert alle Änderungen am `array_view`-Objekt wieder mit den entsprechenden Quelldaten.|  
|[array_view:: synchronize_async-Methode](#array_view__synchronize_async_method)|Synchronisiert asynchron alle Änderungen an der [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt wieder mit seinen Quelldaten.|  
|[array_view:: synchronize_to-Method-Methode](#array_view__synchronize_to_method)|Synchronisiert alle Änderungen an der `array_view` Objekt in den angegebenen [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).|  
|[array_view:: synchronize_to_async-Methode](#array_view__synchronize_to_async_method)|Synchronisiert asynchron alle Änderungen an der `array_view` Objekt in den angegebenen [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).|  
|[array_view:: view_as-Methode](#array_view__view_as_method)|Erzeugt ein `array_view`-Objekt eines abweichenden Rangs mit den Daten dieses `array_view`-Objekts.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[array_view::Operator()-Operator](#array_view__operator___operator)|Gibt den Wert des Elements zurück, das durch den Parameter bzw. die Parameter angegeben wird.|  
|[array_view:: Operator []-Operator](#array_view__operator_at_operator)|Gibt das Element zurück, das von den Parametern angegeben wird.|  
|[array_view:: Operator =-Operator](#array_view__operator_eq_operator)|Kopiert den Inhalt des angegebenen `array_view`-Objekts in dieses Objekt.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[array_view:: Rank-Konstante](#array_view__rank_constant)|Speichert den Rang des `array_view`-Objekts.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[array_view:: Extent-Datenmember](#array_view__extent_data_member)|Ruft das `extent`-Objekt ab, das die Form des `array_view`-Objekts definiert.|  
|[array_view:: source_accelerator_view-Datenmember](#array_view__source_accelerator_view_data_member)|Ruft die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) in dem die Datenquelle der `array_view` befindet|  
|[array_view:: value_type-Datenmember](#array_view__value_type_data_member)|Der Werttyp des `array_view`-Objekts und das gebundene Array.|  
  
## <a name="remarks"></a>Hinweise  
 Die `array_view` Klasse stellt einen Einblick in die Daten, die in enthalten ist ein [Array](../../../parallel/amp/reference/array-class.md) Objekt oder in einem Unterabschnitt ein `array` Objekt.  
  
 Sie können auf das `array_view`-Objekt mit den Quelldaten (lokal) oder über eine andere Zugriffstaste oder eine Kohärenzdomäne (remote) zugreifen. Wenn Sie auf das Objekt remote zugreifen, werden Ansichten ggf. kopiert und zwischengespeichert. Mit Ausnahme der Auswirkungen des automatischen Zwischenspeicherns verfügen `array_view`-Objekte über ein ähnliches Leistungsprofil wie `array`-Objekte. Geringe Leistungseinbußen sind zu verzeichnen, wenn Sie über Ansichten auf die Daten zugreifen.  
  
 Es gibt drei remote Anwendungsszenarios:  
  
-   Eine Ansicht in einem System Speicherzeiger übergeben wird, von einem [Parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each) -Aufrufs einer Zugriffstaste und auf der Zugriffstaste zugegriffen.  
  
-   Eine Ansicht eines Arrays auf einer Zugriffstaste wird mithilfe eines `parallel_for_each`- Aufrufs an eine andere Zugriffstaste übergeben und der Zugriff erfolgt hier.  
  
-   Auf eine Ansicht eines Arrays auf einer Zugriffstaste wird auf der CPU zugegriffen.  
  
 In jedem dieser Szenarien werden die verwiesen Ansichten von der Laufzeit an den Remotespeicherort kopiert und wieder an den lokalen Speicherort kopiert, wenn sie durch die Aufrufe des `array_view`-Objekts geändert werden. Die Laufzeit kann den Prozess des Zurückkopierens von Änderungen optimieren, nur geänderte Elemente kopieren oder auch unveränderte Teile kopieren. Für überlappende `array_view`-Objekte in einer Datenquelle wird keine referenzielle Integrität in einem Remotespeicherort garantiert.  
  
 Sie müssen jeden den Multithreadzugriff die gleiche Datenquelle synchronisieren.  
  
 Die Laufzeit übernimmt im Hinblick auf das Zwischenspeichern von Daten in `array_view`-Objekte folgende Garantien:  
  
-   Alle gut synchronisierten Zugriffe auf ein `array`-Objekt und ein darin enthaltenes `array_view`-Objekt in der Programmreihenfolge unterliegen einer seriellen Happens-Before-Beziehung.  
  
-   Alle gut synchronisierten Zugriffe auf überlappende `array_view`-Objekte auf der gleichen Zugriffstaste eines einzelnen `array`-Objekts werden über das `array`-Objekt mit einem Alias versehen. Sie führen zu einer Occurs-Before-Beziehung, die der Programmreihenfolge unterliegt. Es erfolgt kein Zwischenspeichern. Wenn die `array_view`-Objekte über verschiedene Zugriffstasten ausgeführt werden, ist die Reihenfolge des Zugriffs nicht definiert, was zu einer Racebedingung führt.  
  
 Wenn Sie ein `array_view`-Objekt mithilfe eines Zeigers im Systemspeicher erstellen, können Sie das `array_view`-Ansichtsobjekt nur über den `array_view`-Zeiger ändern. Alternativ müssen Sie `refresh()` für eines der `array_view`-Objekte aufrufen, die dem Systemzeiger angefügt sind, wenn der zugrunde liegende systemeigene Arbeitsspeicher nicht über das `array_view`-Objekt, sondern direkt geändert wird.  
  
 Bei beiden Aktionen wird das `array_view`-Objekt benachrichtigt, dass der zugrunde liegende systemeigene Arbeitsspeicher geändert wird und alle Kopien, die sich auf einer Zugriffstaste befinden, veraltet sind. Wenn Sie diese Richtlinien befolgen, sind die zeigerbasierten Ansichten mit denen identisch, die für die Ansichten von datenparallelen Arrays bereitgestellt werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namearrayviewdtorarrayviewdestructora-arrayviewarrayview-destructor"></a><a name="array_view___dtorarray_view_destructor"></a>  Array_view:: ~ Array_view-Destruktor  
 Zerstört die [Array_view](../../../parallel/amp/reference/array-view-class.md) Objekt.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namearrayviewarrayviewconstructora-arrayviewarrayview-constructor"></a><a name="array_view__array_view_constructor"></a>  array_view:: array_view-Konstruktor  
 Initialisiert eine neue Instanz der dem [Array_view](../../../parallel/amp/reference/array-view-class.md) Klasse.  
  
```  
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view& _Other)restrict(amp,cpu);

 
explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    _Container& _Src) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _Container& _Src);

 
explicit array_view(
    int _E0,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const _Container& _Src) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    const _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const _Container& _Src);

 
array_view(
    int _E0,  
    const value_type* _Src)restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    const value_type* _Src) restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const value_type* _Src) restrict(amp,cpu);

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Arr_type`  
 Der Elementtyp eines Arrays im C-Format, von dem Daten angegeben werden.  
  
 `_Container`  
 Ein Vorlagenargument, das einen linearen Container angeben muss, der `data()`- und `size()`-Member unterstützt.  
  
 `_E0`  
 Die wichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E1`  
 Die zweitwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_E2`  
 Die unwichtigste Komponente des Umfangs dieses Abschnitts.  
  
 `_Extent`  
 Der Umfang in jeder Dimension dieses `array_view`-Objekts.  
  
 `_Other`  
 Ein Objekt des Typs `array_view<T,N>`, von dem das neue `array_view`-Objekt initialisiert werden soll.  
  
 `_Size`  
 Die Größe eines Arrays im C-Format, von dem Daten angegeben werden.  
  
 `_Src`  
 Ein Zeiger auf die Quelldaten, die in das neue Array kopiert werden.  
  
##  <a name="a-namearrayviewcopytomethoda-arrayviewcopyto-method"></a><a name="array_view__copy_to_method"></a>  array_view:: copy_to-Methode  
 Kopiert den Inhalt der [Array_view](../../../parallel/amp/reference/array-view-class.md) Objekt mit dem angegebenen Objekt durch Aufrufen von `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Dest`  
 Das Objekt, in das kopiert werden soll.  
  
##  <a name="a-namearrayviewdatamethoda-arrayviewdata-method"></a><a name="array_view__data_method"></a>  array_view:: Data-Methode  
 Gibt einen Zeiger auf die unformatierten Daten eines der [Array_view](../../../parallel/amp/reference/array-view-class.md).  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die unformatierten Daten eines der `array_view`.  
  
##  <a name="a-namearrayviewdiscarddatamethoda-arrayviewdiscarddata-method"></a><a name="array_view__discard_data_method"></a>  array_view:: discard_data-Methode  
 Verwirft die aktuellen Daten, die dieser Ansicht zugrunde liegen. Dies ist ein Optimierungshinweis zur Laufzeit, die verwendet wird, um den aktuellen Inhalt der Ansicht in ein `accelerator_view`-Zielobjekt zu kopieren, auf das zugegriffen wird. Seine Verwendung wird empfohlen, wenn der aktuelle Inhalt nicht erforderlich ist. Diese Methode hat keine Funktion, wenn sie in einem restrict(amp)-Kontext verwendet wird  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewextentdatamembera-arrayviewextent-data-member"></a><a name="array_view__extent_data_member"></a>  array_view:: Extent-Datenmember  
 Ruft das `extent`-Objekt ab, das die Form des `array_view`-Objekts definiert.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearrayviewgetextentmethoda-arrayviewgetextent-method"></a><a name="array_view__get_extent_method"></a>  array_view:: get_extent-Methode  
 Gibt die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) Objekt von der [Array_view](../../../parallel/amp/reference/array-view-class.md) Objekt.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `extent` Gegenstand der `array_view` Objekt  
  
##  <a name="a-namearrayviewgetrefmethoda-arrayviewgetref-method"></a><a name="array_view__get_ref_method"></a>  array_view:: get_ref-Methode  
 Rufen Sie einen Verweis auf das von _Index indizierte Element ab. Im Gegensatz zu anderen Indizierungsoperatoren für den Zugriff auf das array_view-Objekt auf der CPU synchronisiert diese Methode nicht implizit den Inhalt dieses array_view-Objekts mit der CPU. Nachdem Benutzer auf das array_view-Objekt auf einem Remotespeicherort zugegriffen haben oder ein Kopiervorgang mit diesem array_view-Objekt ausgeführt haben, sind sie dafür verantwortlich, das array_view-Objekt explizit mit der CPU zu synchronisieren, bevor diese Methode aufgerufen wird. Andernfalls kommt es zu nicht definiertem Verhalten.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Verweis auf das von _Index indizierte Element  
  
##  <a name="a-namearrayviewgetsourceacceleratorviewmethoda-arrayviewgetsourceacceleratorview-method"></a><a name="array_view__get_source_accelerator_view_method"></a>  array_view:: get_source_accelerator_view-Methode  
 Gibt das accelerator_view-Objekt zurück, in dem sich die Datenquelle des array_view-Objekts befindet. Wenn das array_view-Objekt über keine Datenquelle verfügt, löst diese API ein runtime_exception-Objekt aus.  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-namearrayviewoperatoroperatora-arrayviewoperator-operator"></a><a name="array_view__operator___operator"></a>  array_view::Operator()-Operator  
 Gibt den Wert des Elements zurück, das durch den Parameter bzw. die Parameter angegeben wird.  
  
```  
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Speicherort des Elements.  
  
 `_I0`  
 Der Index in der ersten Dimension.  
  
 `_I1`  
 Der Index in der zweiten Dimension.  
  
 `_I2`  
 Der Index in der dritten Dimension.  
  
 `_I`  
 Der Speicherort des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des Elements, das durch den bzw. die Parameter angegeben wird.  
  
##  <a name="a-namearrayviewoperatoratoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_at_operator"></a>  array_view:: Operator []-Operator  
 Gibt das Element zurück, das von den Parametern angegeben wird.  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index.  
  
 `_I`  
 Der Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des Elements am Index oder ein `array_view`-Objekt, das auf der wichtigsten Dimension projiziert wird.  
  
##  <a name="a-namearrayviewoperatoreqoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_eq_operator"></a>  array_view:: Operator =-Operator  
 Kopiert den Inhalt des angegebenen [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekts diesem Objekt zu.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `array_view`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `array_view`-Objekt.  
  
##  <a name="a-namearrayviewrankconstanta-arrayviewrank-constant"></a><a name="array_view__rank_constant"></a>  array_view:: Rank-Konstante  
 Speichert den Rang des der [Array_view](../../../parallel/amp/reference/array-view-class.md) Objekt.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namearrayviewrefreshmethoda-arrayviewrefresh-method"></a><a name="array_view__refresh_method"></a>  array_view:: Refresh-Methode  
 Benachrichtigt die [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt, das sein gebundene Speicher außerhalb geändert wurde die `array_view` Schnittstelle. Ein Aufruf dieser Methode führt dazu, dass alle zwischengespeicherten Informationen veraltet sind.  
  
```  
void refresh() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewsectionmethoda-arrayviewsection-method"></a><a name="array_view__section_method"></a>  array_view:: Section-Methode  
 Gibt einen Unterabschnitt der [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt am angegebenen Ursprung befindet und optional, die den angegebenen Wertebereich hat.  
  
```  
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);

 
array_view section(
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
 Die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) -Objekt, das den Umfang des Abschnitts angibt. Der Ursprung ist 0.  
  
 `_Idx`  
 Die [Index](../../../parallel/amp/reference/index-class.md) Objekt, das die Position des Ursprungs angibt. Der Unterabschnitt entspricht dem Rest des Umfangs.  
  
 `_I0`  
 Die wichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I1`  
 Die zweitwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_I2`  
 Die unwichtigste Komponente des Ursprungs dieses Abschnitts.  
  
 `_Rank`  
 Der Rang des Abschnitts.  
  
 `_Section_extent`  
 Die [Block](../../../parallel/amp/reference/extent-class-cpp-amp.md) -Objekt, das den Umfang des Abschnitts angibt.  
  
 `_Section_origin`  
 Die [Index](../../../parallel/amp/reference/index-class.md) Objekt, das die Position des Ursprungs angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Unterabschnitt des `array_view`-Objekts, das sich am angegebenen Ursprung befindet und optional den angegebenen Wertebereich hat. Wenn nur das `index`-Objekt angegeben wird, enthält der Unterabschnitt alle Elemente im zugeordneten Wertebereich, deren Indizes größer sind als die Indizes der Elemente im `index`-Objekt.  
  
##  <a name="a-namearrayviewsourceacceleratorviewdatamembera-arrayviewsourceacceleratorview-data-member"></a><a name="array_view__source_accelerator_view_data_member"></a>  array_view:: source_accelerator_view-Datenmember  
 Ruft das accelerator_view-Quellobjekt ab, dem dieses array_view-Objekt zugeordnet ist.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namearrayviewsynchronizemethoda-arrayviewsynchronize-method"></a><a name="array_view__synchronize_method"></a>  array_view:: Synchronize-Methode  
 Synchronisiert alle Änderungen am `array_view`-Objekt wieder mit den entsprechenden Quelldaten.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Access_type`  
 Der beabsichtigte [Access_type](concurrency%20namespace%20enums.md#access_type) auf dem Ziel [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md). Der Standardwert dieses Parameters ist `access_type_read`.  
  
##  <a name="a-namearrayviewsynchronizeasyncmethoda-arrayviewsynchronizeasync-method"></a><a name="array_view__synchronize_async_method"></a>  array_view:: synchronize_async-Methode  
 Synchronisiert asynchron alle Änderungen an der [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt wieder mit seinen Quelldaten.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Access_type`  
 Der beabsichtigte [Access_type](concurrency%20namespace%20enums.md#access_type) auf dem Ziel [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md). Der Standardwert dieses Parameters ist `access_type_read`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeitpunkt in der Zukunft, bis zu dem auf den Abschluss des Vorgangs gewartet werden soll.  
  
##  <a name="a-namearrayviewsynchronizetomethoda-arrayviewsynchronizeto-method"></a><a name="array_view__synchronize_to_method"></a>  array_view:: synchronize_to-Method-Methode  
 Synchronisiert alle Änderungen an diesem array_view-Objekt mit dem angegebenen accelerator_view-Objekt.  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Accl_view`  
 Das accelerator_view-Zielobjekt zur Synchronisierung.  
  
 `_Access_type`  
 Das gewünschte access_type-Objekt im accelerator_view-Zielobjekt. Dieser Parameter hat den Standardwert access_type_read.  
  
##  <a name="a-namearrayviewsynchronizetoasyncmethoda-arrayviewsynchronizetoasync-method"></a><a name="array_view__synchronize_to_async_method"></a>  array_view:: synchronize_to_async-Methode  
 Synchronisiert asynchron alle Änderungen an diesem array_view-Objekt mit dem angegebenen accelerator_view-Objekt.  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Accl_view`  
 Das accelerator_view-Zielobjekt zur Synchronisierung.  
  
 `_Access_type`  
 Das gewünschte access_type-Objekt im accelerator_view-Zielobjekt. Dieser Parameter hat den Standardwert access_type_read.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeitpunkt in der Zukunft, bis zu dem auf den Abschluss des Vorgangs gewartet werden soll.  
  
##  <a name="a-namearrayviewvaluetypedatamembera-arrayviewvaluetype-data-member"></a><a name="array_view__value_type_data_member"></a>  array_view:: value_type-Datenmember  
 Der Werttyp des array_view-Objekts und des gebundenen Arrays.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-namearrayviewviewasmethoda-arrayviewviewas-method"></a><a name="array_view__view_as_method"></a>  array_view:: view_as-Methode  
 Interpretiert dieses `array_view`-Objekt neu als `array_view`-Objekt eines abweichenden Rang.  
  
```  
template <
    int _New_rank  
>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

 
template <
    int _New_rank  
>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_New_rank`  
 Der Rang des neuen `array_view`-Objekts.  
  
 `_View_extent`  
 Das Umgestaltungs-`extent`-Objekt.  
  
 `value_type`  
 Der Datentyp der Elemente in den ursprünglichen [Array](../../../parallel/amp/reference/array-class.md) -Objekt und das zurückgegebene `array_view` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [Array_view](../../../parallel/amp/reference/array-view-class.md) -Objekt, das erstellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
