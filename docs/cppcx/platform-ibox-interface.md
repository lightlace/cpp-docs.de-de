---
title: 'Platform:: ibox-Schnittstelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d83afb854aaa400a02f9de95e269f85cfeba1a96
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586871"
---
# <a name="platformibox-interface"></a>Platform::IBox-Schnittstelle
Die [Platform::IBox](../cppcx/platform-ibox-interface.md) -Schnittstelle ist in C++ der Name für die `Windows::Foundation::IReference` -Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des geschachtelten Werts.  
  
### <a name="remarks"></a>Hinweise  
 Die `IBox<T>` -Schnittstelle wird hauptsächlich intern zur Darstellung von Werttypen verwendet, die NULL-Werte zulassen, wie in [Wertklassen und Strukturen (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md)beschrieben. Die Schnittstelle wird auch zum Schachteln von Werttypen verwendet, die an C++-Methoden übergeben werden, die Parameter des Typs `Object^`akzeptieren. Sie können einen Eingabeparameter explizit als `IBox<SomeValueType>`deklarieren. Ein Beispiel finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).  
  
### <a name="requirements"></a>Anforderungen  
  
### <a name="members"></a>Member  
 Die `Platform::IBox` -Schnittstelle erbt von der [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) -Schnittstelle. `IBox` umfasst folgende Member:  
  
 **Eigenschaften**  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Wert](#value)|Gibt den nicht geschachtelten Wer zurück, der zuvor in dieser `IBox` -Instanz gespeichert wurde.|  

## <a name="value"></a> Ibox:: Value-Eigenschaft
Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des geschachtelten Werts.  
  
### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Siehe auch  
 [Platform-namespace](../cppcx/platform-namespace-c-cx.md)