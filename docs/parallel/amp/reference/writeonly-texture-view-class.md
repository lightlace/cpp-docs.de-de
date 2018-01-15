---
title: Writeonly_texture_view-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
dev_langs: C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 594a23113159c7d4afa9e3119952b001f8ee7ed4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view-Klasse
Bietet lesegeschützten Zugriff auf eine Textur.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Typ der Elemente in der Textur.  
  
 `_Rank`  
 Der Rang der Textur.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`scalar_type`||  
|`value_type`|Der Typ der Elemente in der Textur.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Writeonly_texture_view-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `writeonly_texture_view`-Klasse.|  
|[~ Writeonly_texture_view-Destruktor](#ctor)|Zerstört das `writeonly_texture_view`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[set](#set)|Legt den Wert des Elements am angegebenen Index ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Kopiert das angegebene `writeonly_texture_view` -Objekts in dieses Objekt.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Rank-Konstante](#rank)|Ruft den Rang des `writeonly_texture_view`-Objekts ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_graphics.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="dtor"></a>~ Writeonly_texture_view 

 Zerstört das `writeonly_texture_view`-Objekt.  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="operator_eq"></a>Operator = 

 Kopiert das angegebene `writeonly_texture_view` -Objekts in dieses Objekt.  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 `writeonly_texture_view`Objekt, das kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `writeonly_texture_view`-Objekt.  
  
##  <a name="rank"></a>Rang 

 Ruft den Rang des `writeonly_texture_view`-Objekts ab.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="set"></a>Festlegen 

 Legt den Wert des Elements am angegebenen Index ab.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index des Elements.  
  
 `value`  
 Der neue Wert des Elements.  
  
##  <a name="ctor"></a>writeonly_texture_view 

 Initialisiert eine neue Instanz der `writeonly_texture_view`-Klasse.  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Rank`  
 Der Rang der Textur.  
  
 `value_type`  
 Der Typ der Elemente in der Textur.  
  
 `_Src`  
 Die Struktur, die zum Erstellen der `writeonly_texture_view`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
