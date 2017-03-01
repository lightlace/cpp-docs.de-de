---
title: Tiled_extent-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tiled_extent
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
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
ms.openlocfilehash: c2f7ebdb9c82ae24cf74064e710ddfb177670359
ms.lasthandoff: 02/24/2017

---
# <a name="tiledextent-class"></a>tiled_extent-Klasse
Ein `tiled_extent`-Objekt ist ein `extent`-Objekt einer bis drei Dimensionen, das den "extent"-Bereich in ein-, zwei- oder dreidimensionale Kacheln unterteilt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template <
    int _Dim0,  
    int _Dim1,  
    int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
 
template <
    int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
### <a name="parameters"></a>Parameter  
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
|[Tiled_extent-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `tiled_extent`-Klasse.|  

  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_tile_extent-Methode](#tiled_extent__get_tile_extent)|Gibt ein `extent`-Objekt zurück, das die Werte der `tiled_extent`-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|  
|[Pad-Methode](#tiled_extent__pad)|Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die aufgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|  
|[TRUNCATE-Methode](#tiled_extent__truncate)|Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =-Operator](#operator_eq)|Kopiert den Inhalt des angegebenen `tiled_index`-Objekts in dieses Objekt.|  

  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[tile_dim0-Konstante](#tiled_extent__tile_dim0)|Speichert die Länge der wichtigsten Dimension.|  
|[tile_dim1-Konstante](#tiled_extent__tile_dim1)|Speichert die Länge der zweitwichtigsten Dimension.|  
|[tile_dim2-Konstante](#tiled_extent__tile_dim2)|Speichert die Länge der unwichtigsten Dimension.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Tile_extent-Datenmember](#tiled_extent__tile_extent)|Ruft ein `extent`-Objekt ab, das die Werte der `tiled_extent`-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  

## <a name="tiled_extent__ctor"></a> Tiled_extent-Konstruktor  
Initialisiert eine neue Instanz der `tiled_extent`-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
tiled_extent();  
  
tiled_extent(  
    const Concurrency::extent<rank>& _Other );  
  
tiled_extent(  
    const tiled_extent& _Other );  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `extent`- oder `tiled_extent`-Objekt, in das kopiert werden soll.  
  

  

## <a name="tiled_extent__get_tile_extent"></a> Get_tile_extent   
Gibt eine `extent` -Objekt, das die Werte der erfasst die `tiled_extent` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.  
  
### <a name="syntax"></a>Syntax  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `extent`-Objekt, das die Dimensionen dieser `tiled_extent`-Instanz erfasst.  
  

## <a name="tiled_extent__pad"></a>  pad   
Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die aufgerundet werden, um durch die Kacheldimensionen teilbar zu sein.  
  
### <a name="syntax"></a>Syntax  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das neue `tiled_extent`-Objekts, nach Wert. 
## <a name="tiled_extent__truncate"></a> Abschneiden   
Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.  
  
### <a name="syntax"></a>Syntax  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.  

## <a name="tiled_extent__operator_eq"></a> Operator =   
Kopiert den Inhalt des angegebenen `tiled_index`-Objekts in dieses Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `tiled_index`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf diese `tiled_index`-Instanz.  

## <a name="tiled_extent__tile_dim0"></a> tile_dim0   
Speichert die Länge der wichtigsten Dimension.  
  
### <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tiled_extent__tile_dim1"></a> tile_dim1   
Speichert die Länge der zweitwichtigsten Dimension.  
  
### <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_extent__tile_dim2"></a> tile_dim2   
Speichert die Länge der unwichtigsten Dimension.  
  
### <a name="syntax"></a>Syntax  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_extent__tile_extent"></a> Tile_extent   
  Ruft eine `extent` -Objekt, das die Werte der erfasst die `tiled_extent` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

