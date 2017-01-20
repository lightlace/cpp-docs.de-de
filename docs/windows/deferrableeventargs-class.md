---
title: "DeferrableEventArgs-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.  
  
## Syntax  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### Parameter  
 `TEventArgsInterface`  
 Der Schnittstellentyp, der die Argumente für ein zurückgestelltes Ereignis deklariert.  
  
 `TEventArgsClass`  
 Die Klasse, die `TEventArgsInterface` implementiert.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[DeferrableEventArgs::GetDeferral\-Methode](../windows/deferrableeventargs-getdeferral-method.md)|Ruft einen Verweis auf das [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\-Objekt ab, das ein zurückgestelltes Ereignis darstellt.|  
|[DeferrableEventArgs::InvokeAllFinished\-Methode](../windows/deferrableeventargs-invokeallfinished-method.md)|Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.|  
  
## Hinweise  
 Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben.  Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.  
  
 Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt.  Sie können die [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md)\-Methode aufrufen, um das [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\-Objekt mit allen Informationen über das zurückgestellte Ereignis abzurufen.  Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral\-Objekt aufrufen.  Rufen Sie dann [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) am Ende der Ereignishandlermethode auf, wodurch gewährleistet wird, dass der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)