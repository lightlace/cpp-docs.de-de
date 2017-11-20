---
title: float_3-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 2cd5e44d60ce02a1acf781812a0cc72e1e7657cf
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|float_3:: get_X||  
|float_3:: get_xy||  
|float_3:: get_xyz||  
|float_3:: get_xz||  
|float_3:: get_xzy||  
|float_3:: get_Y||  
|float_3:: get_yx||  
|float_3:: get_yxz||  
|float_3:: get_yz||  
|float_3:: get_yzx||  
|float_3:: get_z||  
|float_3:: get_zx||  
|float_3:: get_zxy||  
|float_3:: get_zy||  
|float_3:: get_zyx||  
|float_3:: ref_b||  
|float_3:: ref_g||  
|float_3:: ref_r||  
|float_3:: ref_x||  
|float_3:: ref_y||  
|float_3:: ref_z||  
|float_3:: set_X||  
|float_3:: set_xy||  
|float_3:: set_xyz||  
|float_3:: set_xz||  
|float_3:: set_xzy||  
|float_3:: set_y||  
|float_3:: set_yx||  
|float_3:: set_yxz||  
|float_3:: set_yz||  
|float_3:: set_yzx||  
|float_3:: set_z||  
|float_3:: set_zx||  
|float_3:: set_zxy||  
|float_3:: set_zy||  
|float_3:: set_zyx||  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|float_3-||  
|float_3::--||  
|float_3:: * =||  
|float_3:: Operator / =||  
|float_3:: Operator++||  
|float_3:: Operator +=||  
|float_3:: =||  
|float_3:: Operator-=||  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Size-Konstante](#float_3__size)||  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|float_3:: b||  
|float_3:: BG||  
|float_3:: BGR||  
|float_3:: br||  
|float_3:: brg||  
|float_3:: g||  
|float_3:: GB||  
|float_3:: GBR||  
|float_3:: Gr||  
|float_3:: grb||  
|float_3:: r||  
|float_3:: RB||  
|float_3:: RBG||  
|float_3:: RG||  
|float_3:: RGB||  
|float_3:: x||  
|float_3:: XY||  
|float_3:: XYZ||  
|float_3:: XZ||  
|float_3:: xzy||  
|float_3:: y||  
|float_3:: YX||  
|float_3:: yxz||  
|float_3:: YZ||  
|float_3:: yzx||  
|float_3:: z||  
|float_3:: ZX||  
|float_3:: zxy||  
|float_3:: ZY||  
|float_3:: ZYX||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `float_3`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor"></a>float_3 

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
  
##  <a name="float_3__size"></a>Größe 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
