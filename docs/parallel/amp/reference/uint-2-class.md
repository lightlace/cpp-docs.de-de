---
title: uint_2-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_2::set_xy
- amp_short_vectors/Concurrency::graphics::uint_2::y
- amp_short_vectors/Concurrency::graphics::uint_2::gr
- amp_short_vectors/Concurrency::graphics::uint_2::operator-
- amp_short_vectors/Concurrency::graphics::uint_2::get_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator-=
- amp_short_vectors/Concurrency::graphics::uint_2::r
- amp_short_vectors/Concurrency::graphics::uint_2::yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator--
- amp_short_vectors/Concurrency::graphics::uint_2::set_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator=
- amp_short_vectors/Concurrency::graphics::uint_2::set_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator+=
- amp_short_vectors/Concurrency::graphics::uint_2::get_y
- amp_short_vectors/Concurrency::graphics::uint_2::xy
- amp_short_vectors/Concurrency::graphics::uint_2::x
- amp_short_vectors/Concurrency::graphics::uint_2::get_xy
- amp_short_vectors/Concurrency::graphics::uint_2::set_y
- amp_short_vectors/Concurrency::graphics::uint_2
- amp_short_vectors/Concurrency::graphics::uint_2::operator*=
- amp_short_vectors/Concurrency::graphics::uint_2::get_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator/=
- amp_short_vectors/Concurrency::graphics::uint_2::g
- amp_short_vectors/Concurrency::graphics::uint_2::operator++
- amp_short_vectors/Concurrency::graphics::uint_2::rg
dev_langs:
- C++
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1116be21d4f65b67ab967b7acedf4859df54a6e7
ms.lasthandoff: 02/24/2017

---
# <a name="uint2-class"></a>uint_2-Klasse
Stellt einen kurzen Vektor von zwei ganze Zahlen ohne Vorzeichen dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class uint_2;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[uint_2-Konstruktor](#ctor)|Überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|uint_2::get_x-Methode||  
|uint_2::get_xy-Methode||  
|uint_2::get_y-Methode||  
|uint_2::get_yx-Methode||  
|uint_2::ref_g_Method||  
|uint_2::ref_r_Method||  
|uint_2::ref_x_Method||  
|uint_2::ref_y_Method||  
|uint_2::set_x-Methode||  
|uint_2::set_xy-Methode||  
|uint_2::set_y-Methode||  
|uint_2::set_yx-Methode||  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|uint_2::operator-- Operator||  
|uint_2::operator%=-Operator||  
|uint_2::operator&=-Operator||  
|uint_2::operator*=-Operator||  
|uint_2::operator/=-Operator||  
|uint_2::operator^=-Operator||  
|uint_2:: | = (Operator)||  
|uint_2::operator~-Operator||  
|uint_2::operator++-Operator||  
|uint_2::operator+=-Operator||  
|uint_2::\<= (Operator)||  
|uint_2::operator=-Operator||  
|uint_2::operator-=-Operator||  
|uint_2:: >> = (Operator)||  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Size-Konstante](#uint_2__size)||  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|uint_2::g-Datenmember||  
|uint_2::gr-Datenmember||  
|uint_2::r-Datenmember||  
|uint_2::rg-Datenmember||  
|uint_2::x-Datenmember||  
|uint_2::xy-Datenmember||  
|uint_2::y-Datenmember||  
|uint_2::yx-Datenmember||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `uint_2`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="a-namectora-uint2"></a><a name="ctor"></a>uint_2 

 Standardkonstruktor, initialisiert alle Elemente mit 0.  
  
```  
uint_2() restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V0,  
    unsigned int _V1) restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V) restrict(amp,
    cpu);

 
uint_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_V0`  
 Der Wert 0-Element zu initialisieren.  
  
 `_V1`  
 Der Wert 1 Element initialisiert werden.  
  
 `_V`  
 Der Wert für die Initialisierung.  
  
 `_Other`  
 Das Objekt, das zum Initialisieren verwendet.  
  
##  <a name="a-nameuint2sizea-size"></a><a name="uint_2__size"></a>Größe 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: Graphics-Namespace](concurrency-graphics-namespace.md)

