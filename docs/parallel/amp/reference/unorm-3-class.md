---
title: unorm_3-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-=
- amp_short_vectors/Concurrency::graphics::unorm_3::xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::rgb
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::br
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::b
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3
- amp_short_vectors/Concurrency::graphics::unorm_3::set_z
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::x
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::z
- amp_short_vectors/Concurrency::graphics::unorm_3::get_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator=
- amp_short_vectors/Concurrency::graphics::unorm_3::yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::gbr
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator--
- amp_short_vectors/Concurrency::graphics::unorm_3::operator/=
- amp_short_vectors/Concurrency::graphics::unorm_3::brg
- amp_short_vectors/Concurrency::graphics::unorm_3::gb
- amp_short_vectors/Concurrency::graphics::unorm_3::zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::rb
- amp_short_vectors/Concurrency::graphics::unorm_3::gr
- amp_short_vectors/Concurrency::graphics::unorm_3::zx
- amp_short_vectors/Concurrency::graphics::unorm_3::r
- amp_short_vectors/Concurrency::graphics::unorm_3::xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::grb
- amp_short_vectors/Concurrency::graphics::unorm_3::bg
- amp_short_vectors/Concurrency::graphics::unorm_3::get_y
- amp_short_vectors/Concurrency::graphics::unorm_3::g
- amp_short_vectors/Concurrency::graphics::unorm_3::yz
- amp_short_vectors/Concurrency::graphics::unorm_3::yx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_z
- amp_short_vectors/Concurrency::graphics::unorm_3::bgr
- amp_short_vectors/Concurrency::graphics::unorm_3::set_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-
- amp_short_vectors/Concurrency::graphics::unorm_3::y
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator++
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator+=
- amp_short_vectors/Concurrency::graphics::unorm_3::xz
- amp_short_vectors/Concurrency::graphics::unorm_3::rg
- amp_short_vectors/Concurrency::graphics::unorm_3::xy
- amp_short_vectors/Concurrency::graphics::unorm_3::operator*=
- amp_short_vectors/Concurrency::graphics::unorm_3::set_y
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::rbg
dev_langs:
- C++
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
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
ms.openlocfilehash: ce64e15c062f04df6c9f7671bd820ee188af0111
ms.lasthandoff: 02/24/2017

---
# <a name="unorm3-class"></a>unorm_3-Klasse
Stellt einen kurzen Vektor aus drei normalen Zahlen ohne Vorzeichen dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class unorm_3;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[unorm_3-Konstruktor](#ctor)|Überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|unorm_3::get_x-Methode||  
|unorm_3::get_xy-Methode||  
|unorm_3::get_xyz-Methode||  
|unorm_3::get_xz-Methode||  
|unorm_3::get_xzy-Methode||  
|unorm_3::get_y-Methode||  
|unorm_3::get_yx-Methode||  
|unorm_3::get_yxz-Methode||  
|unorm_3::get_yz-Methode||  
|unorm_3::get_yzx-Methode||  
|unorm_3::get_z-Methode||  
|unorm_3::get_zx-Methode||  
|unorm_3::get_zxy-Methode||  
|unorm_3::get_zy-Methode||  
|unorm_3::get_zyx-Methode||  
|Unorm_3::ref_b-Methode||  
|Unorm_3::ref_g-Methode||  
|Unorm_3::ref_r-Methode||  
|Unorm_3::ref_x-Methode||  
|Unorm_3::ref_y-Methode||  
|Unorm_3::ref_z-Methode||  
|unorm_3::set_x-Methode||  
|unorm_3::set_xy-Methode||  
|unorm_3::set_xyz-Methode||  
|unorm_3::set_xz-Methode||  
|unorm_3::set_xzy-Methode||  
|unorm_3::set_y-Methode||  
|unorm_3::set_yx-Methode||  
|unorm_3::set_yxz-Methode||  
|unorm_3::set_yz-Methode||  
|unorm_3::set_yzx-Methode||  
|unorm_3::set_z-Methode||  
|unorm_3::set_zx-Methode||  
|unorm_3::set_zxy-Methode||  
|unorm_3::set_zy-Methode||  
|unorm_3::set_zyx-Methode||  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|unorm_3::operator-- Operator||  
|unorm_3::operator*= Operator||  
|unorm_3::operator/= Operator||  
|unorm_3::operator++ Operator||  
|unorm_3::operator+= Operator||  
|unorm_3::operator= Operator||  
|unorm_3::operator-= Operator||  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Size-Konstante](#unorm_3__size)||  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|unorm_3::b-Datenmember||  
|unorm_3::bg-Datenmember||  
|unorm_3::bgr-Datenmember||  
|unorm_3::br-Datenmember||  
|unorm_3::brg-Datenmember||  
|unorm_3::g-Datenmember||  
|unorm_3::gb-Datenmember||  
|unorm_3::gbr-Datenmember||  
|unorm_3::gr-Datenmember||  
|unorm_3::grb-Datenmember||  
|unorm_3::r-Datenmember||  
|unorm_3::rb-Datenmember||  
|unorm_3::rbg-Datenmember||  
|unorm_3::rg-Datenmember||  
|unorm_3::rgb-Datenmember||  
|unorm_3::x-Datenmember||  
|unorm_3::xy-Datenmember||  
|unorm_3::xyz-Datenmember||  
|unorm_3::xz-Datenmember||  
|unorm_3::xzy-Datenmember||  
|unorm_3::y-Datenmember||  
|unorm_3::yx-Datenmember||  
|unorm_3::yxz-Datenmember||  
|unorm_3::yz-Datenmember||  
|unorm_3::yzx-Datenmember||  
|unorm_3::z-Datenmember||  
|unorm_3::zx-Datenmember||  
|unorm_3::zxy-Datenmember||  
|unorm_3::zy-Datenmember||  
|unorm_3::zyx-Datenmember||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `unorm_3`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="a-namectora-unorm3"></a><a name="ctor"></a>unorm_3 

 Standardkonstruktor, initialisiert alle Elemente mit 0.  
  
```  
unorm_3() restrict(amp,
    cpu);

 
unorm_3(
    unorm _V0,  
    unorm _V1,  
    unorm _V2) restrict(amp,
    cpu);

 
unorm_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
unorm_3(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_3(
    float _V) restrict(amp,
    cpu);

 
unorm_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
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
  
##  <a name="a-nameunorm3sizea-size"></a><a name="unorm_3__size"></a>Größe 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: Graphics-Namespace](concurrency-graphics-namespace.md)

