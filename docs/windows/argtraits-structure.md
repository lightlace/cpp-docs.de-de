---
title: ArgTraits-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
dev_langs:
- C++
helpviewer_keywords:
- ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64ec29d674f6213992fbb1424093931b20ed45b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="argtraits-structure"></a>ArgTraits-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `TMemberFunction`  
 TypeName-Parameter für eine ArgTraits-Struktur, die alle Invoke-Methodensignatur zuordnen kann.  
  
 `TDelegateInterface`  
 Ein Delegat-Schnittstelle.  
  
 `TArg1`  
 Der Typ des ersten Arguments der Invoke-Methode.  
  
 `TArg2`  
 Der Typ des zweiten Arguments der Invoke-Methode.  
  
 `TArg3`  
 Der Typ des dritten Arguments der Invoke-Methode.  
  
 `TArg4`  
 Der Typ des vierten Arguments der Invoke-Methode.  
  
 `TArg5`  
 Der Typ des fünften Arguments der Invoke-Methode.  
  
 `TArg6`  
 Der Typ des sechsten Arguments der Invoke-Methode.  
  
 `TArg7`  
 Der Typ des siebten Arguments der Invoke-Methode.  
  
 `TArg8`  
 Der Typ des das achte Argument für die Invoke-Methode.  
  
 `TArg9`  
 Der Typ des neunten Arguments der Invoke-Methode.  
  
## <a name="remarks"></a>Hinweise  
 Die `ArgTraits` Struktur deklariert einen Delegaten angegebenen Schnittstelle und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern verfügt.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Arg1Type`|Die Typedef für TArg1.|  
|`Arg2Type`|Die Typedef für TArg2.|  
|`Arg3Type`|Die Typedef für TArg3.|  
|`Arg4Type`|Die Typedef für TArg4.|  
|`Arg5Type`|Die Typedef für TArg5.|  
|`Arg6Type`|Die Typedef für TArg6.|  
|`Arg7Type`|Die Typedef für TArg7.|  
|`Arg8Type`|Die Typedef für TArg8.|  
|`Arg9Type`|Die Typedef für TArg9.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ArgTraits::args-Konstante](../windows/argtraits-args-constant.md)|Behält die Anzahl von Parametern auf die Invoke-Methode einer Schnittstelle des Delegaten.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ArgTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)