---
title: DeferrableEventArgs-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 72f5ee2beca3a3985258b12cea9091665eb74cfa
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571261"
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
 *TEventArgsInterface*  
 Der Schnittstellentyp, der die Argumente für ein zurückgestelltes Ereignis deklariert.  
  
 *TEventArgsClass*  
 Implementiert die Klasse, *TEventArgsInterface*.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral-Methode](../windows/deferrableeventargs-getdeferral-method.md)|Ruft einen Verweis auf die [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.|  
|[DeferrableEventArgs::InvokeAllFinished-Methode](../windows/deferrableeventargs-invokeallfinished-method.md)|Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.|  
  
## <a name="remarks"></a>Hinweise  
 Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben. Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.  
  
 Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt. Rufen Sie die [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) -Methode zum Abrufen der [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt aus dem Sie alle Informationen über das zurückgestellte Ereignis erhalten. Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral-Objekt aufrufen. Rufen Sie dann [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) am Ende der Ereignishandlermethode, die sicherstellt, dass es sich bei der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)