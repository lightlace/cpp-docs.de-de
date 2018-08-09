---
title: Struktur implementiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
dev_langs:
- C++
helpviewer_keywords:
- Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31b95901f2c0b7ff210cc8542dce49991a9eef87
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014817"
---
# <a name="implements-structure"></a>Implements-Struktur
Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
### <a name="parameters"></a>Parameter  
 *I0*  
 Die nullte Schnittstellen-ID. (Erforderlich)  
  
 *I1*  
 Die erste Schnittstellen-ID. (Optional)  
  
 *I2*  
 Die zweite Schnittstellen-ID. (Optional)  
  
 *I3*  
 Die dritte Schnittstellen-ID. (Optional)  
  
 *I4*  
 Die vierte Schnittstellen-ID. (Optional)  
  
 *I5*  
 Die fünfte Schnittstellen-ID. (Optional)  
  
 *I6*  
 Die sechste Schnittstellen-ID. (Optional)  
  
 *I7*  
 Die siebte Schnittstellen-ID. (Optional)  
  
 *I8*  
 Die achte Schnittstellen-ID. (Optional)  
  
 *I9*  
 Die neunte Schnittstellen-ID. (Optional)  
  
 *flags*  
 Von konfigurationsflags für die Klasse. Eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationen, die im angegebenen ein [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Aus der Liste der angegebenen Schnittstellen abgeleitet und implementiert Helper-Vorlagen für `QueryInterface` und `GetIid`.  
  
 Jede *I0* über *I9* Schnittstellenparameter muss abgeleitet werden, entweder `IUnknown`, `IInspectable`, oder die [ChainInterfaces](../windows/chaininterfaces-structure.md) Vorlage. Die *Flags* Parameter bestimmt, ob die Unterstützung für generiert wird, `IUnknown` oder `IInspectable`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ClassFlags`|Ein Synonym für `RuntimeClassFlags<WinRt>`.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Implements::CanCastTo-Methode](../windows/implements-cancastto-method.md)|Ruft einen Zeiger auf die angegebene Schnittstelle.|  
|[Implements::CastToUnknown-Methode](../windows/implements-casttounknown-method.md)|Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.|  
|[Implements::FillArrayWithIid-Methode](../windows/implements-fillarraywithiid-method.md)|Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.|  
  
### <a name="protected-constants"></a>Geschützte Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Implements::IidCount-Konstante](../windows/implements-iidcount-constant.md)|Enthält die Anzahl von implementierten Schnittstellen-IDs.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)