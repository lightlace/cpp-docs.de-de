---
title: ChainInterfaces-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9417b3950e4df98ed4e13ea1bb40e76c383868e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces-Struktur
Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `I0`  
 (Erforderlich) Schnittstellen-ID 0.  
  
 `I1`  
 (Erforderlich) Schnittstellen-ID 1.  
  
 `I2`  
 (Optional) Schnittstellen-ID 2.  
  
 `I3`  
 (Optional) Schnittstellen-ID 3.  
  
 `I4`  
 (Optional) Schnittstellen-ID 4.  
  
 `I5`  
 (Optional) Schnittstellen-ID 5.  
  
 `I6`  
 (Optional) Schnittstellen-ID 6.  
  
 `I7`  
 (Optional) Schnittstellen-ID 7.  
  
 `I8`  
 (Optional) Schnittstellen-ID 8.  
  
 `I9`  
 (Optional) Schnittstellen-ID 9.  
  
 `DerivedType`  
 Ein abgeleiteter Typ.  
  
 `BaseType`  
 Der Basistyp eines abgeleiteten Typs.  
  
 `hasImplements`  
 Ein boolescher Wert, auch wenn `true`, können keine bedeutet eine ["mixin"](../windows/mixin-structure.md) Struktur mit einer Klasse, die nicht von abgeleitet ist die [implementiert](../windows/implements-structure.md) Struktur.  
  
## <a name="members"></a>Member  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo-Methode](../windows/chaininterfaces-cancastto-method.md)|Gibt an, ob die angegebene Schnittstellen-ID an jeden der von den Vorlagenparametern ChainInterface definiert spezialisierungen umgewandelt werden kann.|  
|[ChainInterfaces::CastToUnknown-Methode](../windows/chaininterfaces-casttounknown-method.md)|Wandelt den Schnittstellenzeiger des Typs definiert, indem die `I0` Vorlagenparameter in einen Zeiger auf IUnknown.|  
|[ChainInterfaces::FillArrayWithIid-Methode](../windows/chaininterfaces-fillarraywithiid-method.md)|Speichert die Schnittstellen-ID, indem definiert die `I0` Vorlagenparameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.|  
|[ChainInterfaces::Verify-Methode](../windows/chaininterfaces-verify-method.md)|Stellt sicher, dass jede Schnittstelle durch den Vorlagenparameter definiert `I0` über `I9` erbt von IUnknown und/oder "iinspectable", und dass `I0` erbt von `I1` über `I9`.|  
  
### <a name="protected-constants"></a>Geschützte Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[ChainInterfaces::IidCount-Konstante](../windows/chaininterfaces-iidcount-constant.md)|Die Gesamtanzahl der Schnittstellen-IDs enthalten, die in den Schnittstellen, die vom Vorlagenparameter angegeben `I0` über `I9`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)