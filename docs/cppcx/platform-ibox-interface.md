---
title: 'Platform:: ibox-Schnittstelle | Microsoft Docs'
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7894eceb2f345303400eec9b0490db58b3c3583f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)