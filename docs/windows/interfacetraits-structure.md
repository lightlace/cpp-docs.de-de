---
title: InterfaceTraits-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4203fbb639b06e7e421809f9d901c70933d586d1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878683"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits-Struktur
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `I0`  
 Der Name einer Schnittstelle.  
  
 `CloakedType`  
 RuntimeClass, implementiert und "chaininterfaces" unterstützt eine Schnittstelle, die nicht in der Liste der Schnittstellen-IDs.  
  
## <a name="remarks"></a>Hinweise  
 Implementiert Allgemeine Merkmale einer Schnittstelle.  
  
 Die zweite Vorlage ist eine Spezialisierung für verdeckter Schnittstellen. Die dritte Vorlage ist eine Spezialisierung für NULL-Parameter.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Base`|Ein Synonym für den `I0`-Vorlagenparameter.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo-Methode](../windows/interfacetraits-cancastto-method.md)|Gibt an, ob der angegebene Zeiger umgewandelt werden kann, in einen Zeiger auf `Base`.|  
|[InterfaceTraits::CastToBase-Methode](../windows/interfacetraits-casttobase-method.md)|Wandelt den angegebenen Zeiger auf einen Zeiger auf `Base`.|  
|[InterfaceTraits::CastToUnknown-Methode](../windows/interfacetraits-casttounknown-method.md)|Wandelt den angegebenen Zeiger auf ein IUnknown-Zeiger.|  
|[InterfaceTraits::FillArrayWithIid-Methode](../windows/interfacetraits-fillarraywithiid-method.md)|Weist die Schnittstellen-ID des `Base` auf das Arrayelement, das durch die Indexargument angegeben.|  
|[InterfaceTraits::Verify-Methode](../windows/interfacetraits-verify-method.md)|Stellt sicher, dass Base ordnungsgemäß abgeleitet ist.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[InterfaceTraits::IidCount-Konstant](../windows/interfacetraits-iidcount-constant.md)|Enthält die Anzahl der Schnittstelle, die das aktuelle Objekt von InterfaceTraits IDs zugeordnet.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)