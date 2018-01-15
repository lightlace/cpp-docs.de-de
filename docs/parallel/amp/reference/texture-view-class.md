---
title: Texture_view-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
dev_langs: C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ed3f9adb564676d54e06152bfd7d277c4a5d952
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="textureview-class"></a>texture_view-Klasse
Stellt einer Textur Lese- und Schreibzugriff zur Verfügung. `texture_view` kann nur verwendet werden, um Texturen zu lesen, deren Werttyp `int`, `unsigned int` oder `float` mit 32-Bit-Standard ist. Verwenden Sie zum Lesen anderer Texturformate `texture_view<const value_type, _Rank>`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename value_type,int _Rank>  
class texture_view;  
 
template<typename value_type, int _Rank>  
class texture_view 
   : public details::_Texture_base<value_type, _Rank>;  
 
template<typename value_type, int _Rank>  
class texture_view<const value_type, _Rank> 
   : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Typ der Elemente im Texturaggregat.  
  
 `_Rank`  
 Der Rang des `texture_view`-Objekts.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`value_type`|Der Typ der Elemente in den Texturaggregaten.|  
|`coordinates_type`|Der Koordinatentyp, mit dem ein Texel im `texture_view`-Objekt angegeben wird, d. h. ein `short_vector`-Objekt, das den gleichen Rang wie die zugeordnete Textur mit dem Werttyp `float` hat.|  
|`gather_return_type`|Der Rückgabetyp, der für Erfassungsvorgänge verwendet wird, d. h. ein `short_vector`-Objekt mit Rang 4, das die vier homogenen Farbkomponenten enthält, die von den vier geprüften Texelwerten erfasst wurden.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Texture_view-Konstruktor](#ctor)|Überladen. Erstellt eine `texture_view`-Instanz.|  
|[~ Texture_view-Destruktor](#ctor)|Zerstört die `texture_view`-Instanz.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[gather_alpha](#gather_alpha)|Überladen. Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen (w)-Komponenten der vier geprüften Texel zurück.|  
|[gather_blue](#gather_blue)|Überladen. Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen (z)-Komponenten der vier geprüften Texel zurück.|  
|[gather_green](#gather_green)|Überladen. Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die grünen (y)-Komponenten der vier geprüften Texel zurück.|  
|[gather_red](#gather_red)|Überladen. Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die roten (x)-Komponenten der vier geprüften Texel zurück.|  
|[get](#get)|Überladen. Ruft den Elementwert durch Index ab.|  
|[Beispiel](#sample)|Überladen. Prüft die Textur an den festgelegten Koordinaten und den Detailgrad mithilfe der angegebenen Samplingkonfiguration.|  
|[set](#set)|Legt den Wert eines Elements mithilfe des Index fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator()](#operator_call)|Überladen. Ruft den Elementwert durch Index ab.|  
|[[]-Operator](#operator_at)|Überladen. Ruft den Elementwert durch Index ab.|  
|[operator=](#operator_eq)|Überladen. Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[value_type](#value_type)|Der Werttyp der Elemente des `texture_view`-Objekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_graphics.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="dtor"></a>~ Texture_view 

 Zerstört die `texture_view`-Instanz.  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="ctor"></a>texture_view 

 Erstellt eine `texture_view`-Instanz.  
  
```  
texture_view(// [1] constructor  
    texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [2] constructor  
    texture<value_type, _Rank>& _Src,  
    unsigned int _Mipmap_level = 0) restrict(cpu);

 
texture_view(// [3] constructor  
    const texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [4] constructor  
    const texture<value_type, _Rank>& _Src,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);

 
texture_view(// [5] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [6] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [7] copy constructor  
    const texture_view<const value_type, _Rank>& _Other,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
 [1, 2]-Konstruktor  
 Das `texture`-Objekt, auf dem das schreibbare `texture_view`-Objekt erstellt wird.  
  
 [3, 4] Konstruktor  
 Das `texture`-Objekt, auf dem das nicht schreibbare `texture_view`-Objekt erstellt wird.  
  
 `_Other`  
 [5]-Kopierkonstruktor  
 Das schreibbare `texture_view`-Quellobjekt.  
  
 [6, 7] Copy-Konstruktor  
 Das nicht schreibbare `texture_view`-Quellobjekt.  
  
 `_Mipmap_level`  
 Die bestimmte MipMap-Ebene auf dem `texture`-Quellobjekt, an das dieses schreibbare `texture_view`-Objekt gebunden wird. Der Standardwert ist 0, was die oberste (ausführlichste) MIP-Ebene darstellt.  
  
 `_Most_detailed_mip`  
 Die oberste (ausführlichste) Mip-Ebene für die Ansicht, relativ zum angegebenen `texture_view`-Objekt.  
  
 `_Mip_levels`  
 Die Anzahl von MipMap-Ebenen, die über das `texture_view`-Objekt verfügbar sind.  
  
##  <a name="gather_red"></a>gather_red 

 Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die roten (x)-Komponenten der vier geprüften Texel zurück.  
  
```  
const gather_return_type gather_red(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Address_mode`  
 Der Adressmodus zum Prüfen des `texture_view`-Objekts. Der Adressmodus ist für alle Dimensionen identisch.  
  
 `_Sampler`  
 Die Samplerkonfiguration zur Prüfung des `texture_view`-Objekts.  
  
 `_Coord`  
 Die Koordinaten, an denen die Stichprobe genommen werden soll. Bruchkoordinatenwerte werden verwendet, um zwischen Beispieltexeln zu interpolieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein kurzer Vektor des Rangs 4, der die rote (x)-Komponente der 4 geprüften Texelwerte enthält.  
  
##  <a name="gather_green"></a>gather_green 

 Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die grünen (y)-Komponenten der vier geprüften Texel zurück.  
  
```  
const gather_return_type gather_green(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Address_mode`  
 Der Adressmodus zum Prüfen des `texture_view`-Objekts. Der Adressmodus ist für alle Dimensionen identisch.  
  
 `_Sampler`  
 Die Samplerkonfiguration zur Prüfung des `texture_view`-Objekts.  
  
 `_Coord`  
 Die Koordinaten, an denen die Stichprobe genommen werden soll. Bruchkoordinatenwerte werden verwendet, um zwischen Beispieltexeln zu interpolieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein kurzer Vektor des Rangs 4, der die grüne (y)-Komponente der 4 geprüften Texelwerte enthält.  
  
##  <a name="gather_blue"></a>gather_blue 

 Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen (z)-Komponenten der vier geprüften Texel zurück.  
  
```  
const gather_return_type gather_blue(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Address_mode`  
 Der Adressmodus zum Prüfen des `texture_view`-Objekts. Der Adressmodus ist für alle Dimensionen identisch.  
  
 `_Sampler`  
 Die Samplerkonfiguration zur Prüfung des `texture_view`-Objekts.  
  
 `_Coord`  
 Die Koordinaten, an denen die Stichprobe genommen werden soll. Bruchkoordinatenwerte werden verwendet, um zwischen Beispieltexeln zu interpolieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein kurzer Vektor des Rangs 4, der die rote (x)-Komponente der 4 geprüften Texelwerte enthält.  
  
##  <a name="gather_alpha"></a>gather_alpha 

 Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen (w)-Komponenten der vier geprüften Texel zurück.  
  
```  
const gather_return_type gather_alpha(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Address_mode`  
 Der Adressmodus zum Prüfen des `texture_view`-Objekts. Der Adressmodus ist für alle Dimensionen identisch.  
  
 `_Sampler`  
 Die Samplerkonfiguration zur Prüfung des `texture_view`-Objekts.  
  
 `_Coord`  
 Die Koordinaten, an denen die Stichprobe genommen werden soll. Bruchkoordinatenwerte werden verwendet, um zwischen Beispieltexeln zu interpolieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein kurzer Vektor des Rangs 4, der die Alpha-(w)-Komponente der 4 geprüften Texelwerte enthält.  
  
##  <a name="get"></a>Erhalten 

 Ruft den Wert des Elements am angegebenen Index ab.  
  
```  
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

 
value_type get(
    const index<_Rank>& _Index,  
    unsigned int _Mip_level = 0) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index des abzurufenden Elements, möglicherweise mehrdimensional.  
  
 `_Mip_level`  
 Die MipMap-Ebene, von der der Wert abgerufen werden soll. Der Standardwert 0 stellt die ausführlichste MipMap-Ebene dar.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des Elements.  
  
##  <a name="operator_eq"></a>Operator = 

 Weist dieser `texture_view`-Instanz eine Ansicht der gleichen Textur wie die angegebene `texture_view` zu.  
  
```  
texture_view<value_type, _Rank>& operator= (// [1] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view<const value_type, _Rank>& operator= (// [2] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

 
texture_view<const value_type, _Rank>& operator= (// [3] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 [1, 2]-Kopierkonstruktor  
 Ein `texture_view`-Objekt, in das geschrieben werden kann.  
  
 [3]-Kopierkonstruktor  
 Ein `texture_view`-Objekt, in das nicht geschrieben werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf diese `texture_view`-Instanz.  
  
##  <a name="operator_at"></a>[]-Operator 

 Gibt den Elementwert durch Index zurück.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);

 
value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index, möglicherweise mehrdimensional.  
  
 `_I0`  
 Der eindimensionale Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Der durch `_Index` indizierte Elementwert.  
  
##  <a name="operator_call"></a>Operator() 

 Gibt den Elementwert durch Index zurück.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);

 
value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
value_type operator() (
    int _I0) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index, möglicherweise mehrdimensional.  
  
 `_I0`  
 Die wichtigste Komponente des Index.  
  
 `_I1`  
 Die zweitwichtigste Komponente des Index.  
  
 `_I2`  
 Die unwichtigste Komponente des Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Der durch `_Index` indizierte Elementwert.  
  
##  <a name="sample"></a>Beispiel 

 Prüft die Textur an den festgelegten Koordinaten und den Detailgrad mithilfe der angegebenen Samplingkonfiguration.  
  
```  
value_type sample(
    const sampler& _Sampler,  
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);

 
template<
    filter_mode _Filter_mode = filter_linear,  
    address_mode _Address_mode = address_clamp  
>  
value_type sample(
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter_mode`  
 Der Filtermodus, der für das Sampling des texture_view-Objekts verwendet werden soll. Der Filtermodus ist für die Reduzierung, die Maximierung und die MipMap-Filter derselbe.  
  
 `_Address_mode`  
 Der Adressmodus, der zum Sampling des texture_view-Objekts verwendet werden soll. Der Adressmodus ist für alle Dimensionen identisch.  
  
 `_Sampler`  
 Die Samplerkonfiguration, die zum Sampling des texture_view-Objekts verwendet werden soll.  
  
 `_Coord`  
 Die Koordinaten, an denen die Stichprobe genommen werden soll. Bruchkoordinatenwerte werden verwendet, um zwischen Texelwerten zu interpolieren.  
  
 `_Level_of_detail`  
 Der Wert gibt die MipMap-Ebene für das Sampling an. Bruchwerte werden verwendet, um zwischen zwei MipMap-Ebenen zu interpolieren. Das Standarddetailniveau ist 0, was die ausführlichste MIP-Ebene darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der interpolierte Beispielwert.  
  
##  <a name="set"></a>Festlegen 

 Legt den Wert des Elements am angegebenen Index auf den angegebenen Wert fest.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index des festzulegenden Elements, möglicherweise mehrdimensional.  
  
 `value`  
 Der Wert, auf den das Element festgelegt werden soll.  
  
##  <a name="value_type"></a>value_type 

 Der Werttyp der Elemente des texture_view-Objekts.  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
