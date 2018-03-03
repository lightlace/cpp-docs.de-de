---
title: DeferrableEventArgs-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ce2c554ac6d959df868b80c1959a286fb0ef307
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs-Klasse
Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `TEventArgsInterface`  
 Der Schnittstellentyp, der die Argumente für ein zurückgestelltes Ereignis deklariert.  
  
 `TEventArgsClass`  
 Die Klasse, die `TEventArgsInterface` implementiert.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral-Methode](../windows/deferrableeventargs-getdeferral-method.md)|Ruft einen Verweis auf die [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.|  
|[DeferrableEventArgs::InvokeAllFinished-Methode](../windows/deferrableeventargs-invokeallfinished-method.md)|Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.|  
  
## <a name="remarks"></a>Hinweise  
 Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben. Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.  
  
 Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt. Sie erreichen die [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) Methode zum Abrufen der [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt aus dem können Sie alle Informationen über das zurückgestellte Ereignis abzurufen. Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral-Objekt aufrufen. Rufen Sie dann [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) am Ende der Ereignishandlermethode, wodurch sichergestellt wird, dass auf der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)