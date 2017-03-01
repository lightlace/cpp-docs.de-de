---
title: Tiled_index-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tiled_index
dev_langs:
- C++
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 2c10721f40bd1c90a196ba82655482f35a8e10d8
ms.lasthandoff: 02/24/2017

---
# <a name="tiledindex-class"></a>tiled_index-Klasse
Stellt einen Index in einer [Tiled_extent](tiled-extent-class.md) Objekt. Diese Klasse verfügt über Eigenschaften, über die auf Elemente relativ zum lokalen Kachelursprung und relativ zum globalen Ursprung zugegriffen werden kann. Weitere Informationen zu gekachelten Bereichen finden Sie unter [mithilfe von Kacheln](../../../parallel/amp/using-tiles.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
template <
    int _Dim0,  
    int _Dim1 = 0,  
    int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
 
template <
    int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Dim0`  
 Die Länge der wichtigsten Dimension.  
  
 `_Dim1`  
 Die Länge der zweitwichtigsten Dimension.  
  
 `_Dim2`  
 Die Länge der unwichtigsten Dimension.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Tiled_index-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `tile_index`-Klasse.|  

  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_tile_extent-Methode](#tiled_index__get_tile_extent)|Gibt eine [Block](extent-class.md) -Objekt, das die Werte der hat die `tiled_index` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.|  


  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Barrier-Konstante](#tiled_index__barrier)|Speichert einen [Tile_barrier](tile-barrier-class.md) -Objekt, das eine Grenze in der aktuellen Kachel mit Threads darstellt.|  
|||  
|[Globale Konstanten](#tiled_index__global)|Speichert ein [Index](index-class.md) -Objekt von Rang 1, 2 oder 3, die die globale darstellt Index in einer [Raster](http://msdn.microsoft.com/en-us/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) Objekt.|  
|[lokale Konstante](#tiled_index__local)|Speichert ein `index` -Objekt von Rang 1, 2 oder 3, der die Relative Index in der aktuellen Kachel ein [Tiled_extent](tiled-extent-class.md) Objekt.|  
|[Rank-Konstante](#tiled_index__rank)|Speichert den Rang des `tiled_index`-Objekts.|  
|[anordnungskonstante](#tiled_index__tile)|Speichert ein `index`-Objekt von Rang 1, 2 oder 3, das die Koordinaten der aktuellen Kachel eines `tiled_extent`-Objekts darstellt.|  
|[tile_dim0-Konstante](#tiled_index__tile_dim0)|Speichert die Länge der wichtigsten Dimension.|  
|[tile_dim1-Konstante](#tiled_index__tile_dim1)|Speichert die Länge der zweitwichtigsten Dimension.|  
|[tile_dim2-Konstante](#tiled_index__tile_dim2)|Speichert die Länge der unwichtigsten Dimension.|  
|[Tile_origin-Konstante](#tiled_index__tile_origin)|Speichert ein `index`-Objekt von Rang 1, 2 oder 3, das die globalen Koordinaten des Ursprungs der aktuellen Kachel in einem `tiled_extent`-Objekt darstellt.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Tile_extent-Datenmember](#tile_extent)|Ruft eine [Block](extent-class.md) -Objekt, das die Werte der hat die `tiled_index` Vorlagenargumente `tiled_index` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.|  

  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  


## <a name="a-nametiledindexctora--tiledindex-constructor"></a><a name="tiled_index__ctor"></a>Tiled_index-Konstruktor  
Initialisiert eine neue Instanz der `tiled_index`-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
tiled_index(  
    const index<rank>& _Global,  
    const index<rank>& _Local,  
    const index<rank>& _Tile,  
    const index<rank>& _Tile_origin,  
    const tile_barrier& _Barrier ) restrict(amp,cpu);  
  
tiled_index(  
    const tiled_index& _Other ) restrict(amp,cpu);  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Global`  
 Die globale [Index](index-class.md) des erstellten `tiled_index`.  
  
 `_Local`  
 Die lokale [Index](index-class.md) des erstellten`tiled_index`  
  
 `_Tile`  
 Die Kachel [Index](index-class.md) des erstellten`tiled_index`  
  
 `_Tile_origin`  
 Der kachelursprungs [Index](index-class.md) des erstellten`tiled_index`  
  
 `_Barrier`  
 Die [Tile_barrier](tile-barrier-class.md) des erstellten Objekts `tiled_index`.  
  
 `_Other`  
 Das `tile_index`-Objekt, das in das erstellte `tiled_index`-Objekt kopiert werden soll.  
  
## <a name="overloads"></a>Overloads  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Initialisiert eine neue Instanz der `tile_index`-Klasse aus dem Index der Kachel in den globalen Koordinaten und der relativen Position in der Kachel in lokalen Koordinaten. Die Parameter `_Global` und `_Tile_origin` werden berechnet.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Initialisiert eine neue Instanz der `tile_index`-Klasse, indem das angegebene `tiled_index`-Objekt kopiert wird.|  


## <a name="a-nametiledindexgettileextenta--gettileextent"></a><a name="tiled_index__get_tile_extent"></a>get_tile_extent
Gibt eine [Block](extent-class.md) -Objekt, das die Werte der hat die `tiled_index` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.  
  
## <a name="syntax"></a>Syntax  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein `extent` -Objekt, das die Werte der hat die `tiled_index` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.  

## <a name="a-nametiledindexbarriera--barrier"></a><a name="tiled_index__barrier"></a>Barriere   
Speichert einen [Tile_barrier](tile-barrier-class.md) -Objekt, das eine Grenze in der aktuellen Kachel mit Threads darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
const tile_barrier barrier;  
```  

## <a name="a-nametiledindexglobala--global"></a><a name="tiled_index__global"></a>globale   
Speichert ein [Index](index-class.md) -Objekt von Rang 1, 2 oder 3, die den globalen Index eines Objekts darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
const index<rank> global;  
```  
  
## <a name="a-nametiledindexlocala--local"></a><a name="tiled_index__local"></a>lokale   
Speichert ein [Index](index-class.md) -Objekt von Rang 1, 2 oder 3, der die Relative Index in der aktuellen Kachel ein [Tiled_extent](tiled-extent-class.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
const index<rank> local;  
```  
  
## <a name="a-nametiledindexranka--rank"></a><a name="tiled_index__rank"></a>Rang   
Speichert den Rang des `tiled_index`-Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```  
static const int rank = _Rank;  
```  

## <a name="a-nametiledindextilea--tile"></a><a name="tiled_index__tile"></a>Kachel   
Speichert ein [Index](index-class.md) -Objekt von Rang 1, 2 oder 3, die die Koordinaten der aktuellen Kachel stellt eine [Tiled_extent](tiled-extent-class.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
const index<rank> tile;  
```  
  
## <a name="a-nametiledindextiledim0a--tiledim0"></a><a name="tiled_index__tile_dim0"></a>tile_dim0  
Speichert die Länge der wichtigsten Dimension.  
  
## <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="a-nametiledindextiledim1a--tiledim1"></a><a name="tiled_index__tile_dim1"></a>tile_dim1   
Speichert die Länge der zweitwichtigsten Dimension.  
  
## <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="a-nametiledindextiledim2a--tiledim2"></a><a name="tiled_index__tile_dim2"></a>tile_dim2   
Speichert die Länge der unwichtigsten Dimension.  
  
## <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="a-nametiledindextileorigina--tileorigin"></a><a name="tiled_index__tile_origin"></a>tile_origin   
Speichert ein [Index](index-class.md) -Objekt von Rang 1, 2 oder 3, die die globale darstellt Koordinaten des Ursprungs der aktuellen Kachel in einem [Tiled_extent](tiled-extent-class.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
const index<rank> tile_origin  
```  
## <a name="a-nametileextenta--tileextent"></a><a name="tile_extent"></a>tile_extent
  Ruft eine [Block](extent-class.md) -Objekt, das die Werte der hat die `tiled_index` Vorlagenargumente `tiled_index` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

