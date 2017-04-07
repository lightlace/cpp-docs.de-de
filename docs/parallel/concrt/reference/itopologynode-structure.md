---
title: ITopologyNode-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: c0a4e8365d7d0ef9912bb84e4a2a4cfe7e9ef0f1
ms.lasthandoff: 03/17/2017

---
# <a name="itopologynode-structure"></a>ITopologyNode-Struktur
Eine Schnittstelle für einen vom Ressourcen-Manager definierten Topologieknoten. Ein Knoten enthält mindestens eine Ausführungsressource.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Itopologynode:: Getexecutionresourcecount](#getexecutionresourcecount)|Gibt die Anzahl von Ressourcen zur Ausführung unter diesem Knoten gruppiert.|  
|[Itopologynode:: Getfirstexecutionresource](#getfirstexecutionresource)|Gibt die erste Ausführungsressource unter diesem Knoten Reihenfolge gruppiert.|  
|[Itopologynode:: GetID](#getid)|Gibt die Ressourcen-Manager eindeutige Bezeichner für diesen Knoten zurück.|  
|[Itopologynode:: GetNext](#getnext)|Gibt eine Schnittstelle zum nächsten Knoten in der Reihenfolge der Topologie.|  
|[Itopologynode:: Getnumanode](#getnumanode)|Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, als vom Ressourcen-Manager überwacht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITopologyNode`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getexecutionresourcecount"></a>Itopologynode:: Getexecutionresourcecount-Methode  
 Gibt die Anzahl von Ressourcen zur Ausführung unter diesem Knoten gruppiert.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Ressourcen zur Ausführung unter diesem Knoten gruppiert.  
  
##  <a name="getfirstexecutionresource"></a>Itopologynode:: Getfirstexecutionresource-Methode  
 Gibt die erste Ausführungsressource unter diesem Knoten Reihenfolge gruppiert.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Ausführungsressource gruppiert unter diesem Knoten in der Reihenfolge.  
  
##  <a name="getid"></a>Itopologynode:: GetID-Methode  
 Gibt die Ressourcen-Manager eindeutige Bezeichner für diesen Knoten zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ressourcen-Manager eindeutige Bezeichner für diesen Knoten.  
  
### <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessorknoten dar. Knoten werden in der Regel von der Hardwaretopologie des Systems abgeleitet. Alle Prozessoren auf einem bestimmten Socket oder einem bestimmten NUMA-Knoten können z. B. auf demselben Prozessorknoten gehören. Der Ressourcen-Manager weist eindeutige Bezeichner zu diesen Knoten ab `0` bis und einschließlich `nodeCount - 1`, wobei `nodeCount` stellt die Gesamtzahl der Prozessorknoten auf dem System.  
  
 Die Anzahl der Knoten abgerufen werden kann, von der Funktion [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="getnext"></a>Itopologynode:: GetNext-Methode  
 Gibt eine Schnittstelle zum nächsten Knoten in der Reihenfolge der Topologie.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schnittstelle für den nächsten Knoten in der Reihenfolge. Wenn die Reihenfolge der Systemtopologie keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert zurück `NULL`.  
  
##  <a name="getnumanode"></a>Itopologynode:: Getnumanode-Methode  
 Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die von Windows zugewiesene NUMA-Knotenzahl, zu der dieser Ressource-Manager-Knoten gehört.  
  
### <a name="remarks"></a>Hinweise  
 Ein Threadproxy, der auf einem virtuellen Prozessorstamm ausgeführt wird, der zu diesem Knoten gehört, verfügt über Affinität zu mindestens der NUMA-Knotenebene für den NUMA-Knoten, der von dieser Methode zurückgegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

