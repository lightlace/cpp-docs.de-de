---
title: Short_vector_traits-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- short_vector_traits
- AMP_SHORT_VECTORS/short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::size Constant
dev_langs:
- C++
ms.assetid: cd9492da-9e02-4a6e-9d50-b61252cdb460
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21f249a464cd9f55d8cbb4aea79bcb705104306b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="shortvectortraits-structure"></a>short_vector_traits-Struktur
Short_vector_traits ermöglicht das Abrufen von der zugrunde liegenden Länge des Vektors und skalaren Typ von einem kurzen vektortyp entspricht oder einen skalaren Typ  
  
## <a name="syntax"></a>Syntax  
  
```  
template<
    typename T  
>  
struct short_vector_traits;  
template<>  
struct short_vector_traits<unsigned int>;  
template<>  
struct short_vector_traits<uint_2>;  
template<>  
struct short_vector_traits<uint_3>;  
template<>  
struct short_vector_traits<uint_4>;  
template<>  
struct short_vector_traits<int>;  
template<>  
struct short_vector_traits<int_2>;  
template<>  
struct short_vector_traits<int_3>;  
template<>  
struct short_vector_traits<int_4>;  
template<>  
struct short_vector_traits<float>;  
template<>  
struct short_vector_traits<float_2>;  
template<>  
struct short_vector_traits<float_3>;  
template<>  
struct short_vector_traits<float_4>;  
template<>  
struct short_vector_traits<unorm>;  
template<>  
struct short_vector_traits<unorm_2>;  
template<>  
struct short_vector_traits<unorm_3>;  
template<>  
struct short_vector_traits<unorm_4>;  
template<>  
struct short_vector_traits<norm>;  
template<>  
struct short_vector_traits<norm_2>;  
template<>  
struct short_vector_traits<norm_3>;  
template<>  
struct short_vector_traits<norm_4>;  
template<>  
struct short_vector_traits<double>;  
template<>  
struct short_vector_traits<double_2>;  
template<>  
struct short_vector_traits<double_3>;  
template<>  
struct short_vector_traits<double_4>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[short_vector_traits:: short_vector_traits-Konstruktor](#ctor)||  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[short_vector_traits:: size-Konstante](#size)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `short_vector_traits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor">short_vector_traits:: short_vector_traits-Konstruktor</a>  
  
```  
short_vector_traits();
```  
  
##  <a name="size">short_vector_traits:: size-Konstante</a>  
  
```  
static int const size = 1;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
