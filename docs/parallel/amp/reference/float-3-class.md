---
title: float_3-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_3::get_zyx
- amp_short_vectors/Concurrency::graphics::float_3::set_y
- amp_short_vectors/Concurrency::graphics::float_3::b
- amp_short_vectors/Concurrency::graphics::float_3::operator-=
- amp_short_vectors/Concurrency::graphics::float_3::get_y
- amp_short_vectors/Concurrency::graphics::float_3::set_zy
- amp_short_vectors/Concurrency::graphics::float_3::get_yzx
- amp_short_vectors/Concurrency::graphics::float_3::xz
- amp_short_vectors/Concurrency::graphics::float_3::xyz
- amp_short_vectors/Concurrency::graphics::float_3::operator+=
- amp_short_vectors/Concurrency::graphics::float_3::brg
- amp_short_vectors/Concurrency::graphics::float_3::get_x
- amp_short_vectors/Concurrency::graphics::float_3::get_zx
- amp_short_vectors/Concurrency::graphics::float_3::y
- amp_short_vectors/Concurrency::graphics::float_3::rbg
- amp_short_vectors/Concurrency::graphics::float_3::operator-
- amp_short_vectors/Concurrency::graphics::float_3::get_yz
- amp_short_vectors/Concurrency::graphics::float_3::set_xz
- amp_short_vectors/Concurrency::graphics::float_3::operator/=
- amp_short_vectors/Concurrency::graphics::float_3::zxy
- amp_short_vectors/Concurrency::graphics::float_3::yx
- amp_short_vectors/Concurrency::graphics::float_3::g
- amp_short_vectors/Concurrency::graphics::float_3::r
- amp_short_vectors/Concurrency::graphics::float_3::zy
- amp_short_vectors/Concurrency::graphics::float_3::set_zxy
- amp_short_vectors/Concurrency::graphics::float_3::set_zyx
- amp_short_vectors/Concurrency::graphics::float_3::get_yx
- amp_short_vectors/Concurrency::graphics::float_3
- amp_short_vectors/Concurrency::graphics::float_3::get_xz
- amp_short_vectors/Concurrency::graphics::float_3::get_yxz
- amp_short_vectors/Concurrency::graphics::float_3::set_xy
- amp_short_vectors/Concurrency::graphics::float_3::get_xzy
- amp_short_vectors/Concurrency::graphics::float_3::bgr
- amp_short_vectors/Concurrency::graphics::float_3::zx
- amp_short_vectors/Concurrency::graphics::float_3::gr
- amp_short_vectors/Concurrency::graphics::float_3::set_z
- amp_short_vectors/Concurrency::graphics::float_3::get_zy
- amp_short_vectors/Concurrency::graphics::float_3::gb
- amp_short_vectors/Concurrency::graphics::float_3::set_xzy
- amp_short_vectors/Concurrency::graphics::float_3::set_zx
- amp_short_vectors/Concurrency::graphics::float_3::set_yzx
- amp_short_vectors/Concurrency::graphics::float_3::operator=
- amp_short_vectors/Concurrency::graphics::float_3::x
- amp_short_vectors/Concurrency::graphics::float_3::grb
- amp_short_vectors/Concurrency::graphics::float_3::zyx
- amp_short_vectors/Concurrency::graphics::float_3::set_yxz
- amp_short_vectors/Concurrency::graphics::float_3::get_zxy
- amp_short_vectors/Concurrency::graphics::float_3::set_yz
- amp_short_vectors/Concurrency::graphics::float_3::operator--
- amp_short_vectors/Concurrency::graphics::float_3::set_xyz
- amp_short_vectors/Concurrency::graphics::float_3::operator++
- amp_short_vectors/Concurrency::graphics::float_3::z
- amp_short_vectors/Concurrency::graphics::float_3::xy
- amp_short_vectors/Concurrency::graphics::float_3::rgb
- amp_short_vectors/Concurrency::graphics::float_3::rg
- amp_short_vectors/Concurrency::graphics::float_3::yzx
- amp_short_vectors/Concurrency::graphics::float_3::set_yx
- amp_short_vectors/Concurrency::graphics::float_3::xzy
- amp_short_vectors/Concurrency::graphics::float_3::rb
- amp_short_vectors/Concurrency::graphics::float_3::get_z
- amp_short_vectors/Concurrency::graphics::float_3::br
- amp_short_vectors/Concurrency::graphics::float_3::bg
- amp_short_vectors/Concurrency::graphics::float_3::get_xyz
- amp_short_vectors/Concurrency::graphics::float_3::set_x
- amp_short_vectors/Concurrency::graphics::float_3::yxz
- amp_short_vectors/Concurrency::graphics::float_3::yz
- amp_short_vectors/Concurrency::graphics::float_3::gbr
- amp_short_vectors/Concurrency::graphics::float_3::operator*=
- amp_short_vectors/Concurrency::graphics::float_3::get_xy
dev_langs:
- C++
helpviewer_keywords:
- amp_short_vectors/Concurrency::graphics::float_3
ms.assetid: 209df7a5-08d7-48b4-8ba5-77603642cdd8
caps.latest.revision: 10
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
ms.openlocfilehash: 9e1225c724d2c89dd2a6c4158446b6a4df195f6c
ms.lasthandoff: 02/24/2017

---
# <a name="float3-class"></a>float_3-Klasse
Stellt einen kurzen Vektor aus drei Gleitkommazahlen dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class float_3;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[float_3-Konstruktor](#ctor)|Überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|float_3::get_x-Methode||  
|float_3::get_xy-Methode||  
|float_3::get_xyz-Methode||  
|float_3::get_xz-Methode||  
|float_3::get_xzy-Methode||  
|float_3::get_y-Methode||  
|float_3::get_yx-Methode||  
|float_3::get_yxz-Methode||  
|float_3::get_yz-Methode||  
|float_3::get_yzx-Methode||  
|float_3::get_z-Methode||  
|float_3::get_zx-Methode||  
|float_3::get_zxy-Methode||  
|float_3::get_zy-Methode||  
|float_3::get_zyx-Methode||  
|float_3::ref_b-Methode||  
|float_3::ref_g-Methode||  
|float_3::ref_r-Methode||  
|float_3::ref_x-Methode||  
|float_3::ref_y-Methode||  
|float_3::ref_z-Methode||  
|float_3::set_x-Methode||  
|float_3::set_xy-Methode||  
|float_3::set_xyz-Methode||  
|float_3::set_xz-Methode||  
|float_3::set_xzy-Methode||  
|float_3::set_y-Methode||  
|float_3::set_yx-Methode||  
|float_3::set_yxz-Methode||  
|float_3::set_yz-Methode||  
|float_3::set_yzx-Methode||  
|float_3::set_z-Methode||  
|float_3::set_zx-Methode||  
|float_3::set_zxy-Methode||  
|float_3::set_zy-Methode||  
|float_3::set_zyx-Methode||  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|float_3::operator--Operator||  
|float_3::operator---Operator||  
|float_3::operator*=-Operator||  
|float_3::operator/=-Operator||  
|float_3::operator++-Operator||  
|float_3::operator+=-Operator||  
|float_3::operator=-Operator||  
|float_3::operator-=-Operator||  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Size-Konstante](#float_3__size)||  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|float_3::b-Datenmember||  
|float_3::bg-Datenmember||  
|float_3::bgr-Datenmember||  
|float_3::br-Datenmember||  
|float_3::brg-Datenmember||  
|float_3::g-Datenmember||  
|float_3::gb-Datenmember||  
|float_3::gbr-Datenmember||  
|float_3::gr-Datenmember||  
|float_3::grb-Datenmember||  
|float_3::r-Datenmember||  
|float_3::rb-Datenmember||  
|float_3::rbg-Datenmember||  
|float_3::rg-Datenmember||  
|float_3::rgb-Datenmember||  
|float_3::x-Datenmember||  
|float_3::xy-Datenmember||  
|float_3::xyz-Datenmember||  
|float_3::xz-Datenmember||  
|float_3::xzy-Datenmember||  
|float_3::y-Datenmember||  
|float_3::yx-Datenmember||  
|float_3::yxz-Datenmember||  
|float_3::yz-Datenmember||  
|float_3::yzx-Datenmember||  
|float_3::z-Datenmember||  
|float_3::zx-Datenmember||  
|float_3::zxy-Datenmember||  
|float_3::zy-Datenmember||  
|float_3::zyx-Datenmember||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `float_3`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="a-namectora-float3"></a><a name="ctor"></a>float_3 

 Standardkonstruktor, initialisiert alle Elemente mit 0.  
  
```  
float_3() restrict(amp,
    cpu);

 
float_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
float_3(
    float _V) restrict(amp,
    cpu);

 
float_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_V0`  
 Der Wert 0-Element zu initialisieren.  
  
 `_V1`  
 Der Wert 1 Element initialisiert werden.  
  
 `_V2`  
 Der Wert 2-Element zu initialisieren.  
  
 `_V`  
 Der Wert für die Initialisierung.  
  
 `_Other`  
 Das Objekt, das zum Initialisieren verwendet.  
  
##  <a name="a-namefloat3sizea-size"></a><a name="float_3__size"></a>Größe 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: Graphics-Namespace](concurrency-graphics-namespace.md)

