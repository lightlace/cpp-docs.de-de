---
title: SchedulerPolicy-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
dev_langs:
- C++
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f23e95bafa9920c520fa7c01518873769945770
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691780"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy-Klasse
Die `SchedulerPolicy`-Klasse enthält einen Satz von Schlüssel-Wert-Paaren. Einen für jedes Richtlinienelement, von dem das Verhalten einer Planerinstanz gesteuert wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SchedulerPolicy](#ctor)|Überladen. Erstellt eine neue Planerrichtlinie und füllt sie mit Werten für [Richtlinienschlüssel](concurrency-namespace-enums.md) von Concurrency Runtime-Planern und dem Ressourcen-Manager unterstützt werden.|  
|[~ SchedulerPolicy-Destruktor](#dtor)|Zerstört eine Planerrichtlinie.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[GetPolicyValue](#getpolicyvalue)|Ruft den Wert des als `key`-Parameter angegebenen Richtlinienschlüssels ab.|  
|[SetConcurrencyLimits](#setconcurrencylimits)|Legt gleichzeitig die `MinConcurrency`-Richtlinie und die `MaxConcurrency`-Richtlinie des `SchedulerPolicy`-Objekts fest.|  
|[SetPolicyValue](#setpolicyvalue)|Legt den Wert des Richtlinienschlüssels fest, der als `key`-Parameter angegeben wurde, und gibt den alten Wert zurück.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Weist die Planerrichtlinie von einer anderen Planerrichtlinie zu.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über kontrolliert werden können Richtlinien für die `SchedulerPolicy` Klasse, finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `SchedulerPolicy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu, concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getpolicyvalue"></a> GetPolicyValue 

 Ruft den Wert des als `key`-Parameter angegebenen Richtlinienschlüssels ab.  
  
```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Richtlinienschlüssel zum Abrufen eines Werts für.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Schlüssel, wird angegeben die `key` Parameter unterstützt wird, der Richtlinienwert für den Schlüssel umgewandelt ein `unsigned int`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst [Invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) für einen ungültigen Richtlinienschlüssel.  
  
##  <a name="operator_eq"></a> Operator = 

 Weist die Planerrichtlinie von einer anderen Planerrichtlinie zu.  
  
```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```  
  
### <a name="parameters"></a>Parameter  
 `_RhsPolicy`  
 Die Richtlinie für diese Richtlinie zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die Planerrichtlinie.  
  
### <a name="remarks"></a>Hinweise  
 Oft ist die zweckmäßigste Art, eine neue Planerrichtlinie zu definieren, das Kopieren einer vorhandenen Richtlinie und das anschließende Bearbeiten mit der `SetPolicyValue`-Methode oder der `SetConcurrencyLimits`-Methode.  
  
##  <a name="ctor"></a> SchedulerPolicy 

 Erstellt eine neue Planerrichtlinie und füllt sie mit Werten für [Richtlinienschlüssel](concurrency-namespace-enums.md) von Concurrency Runtime-Planern und dem Ressourcen-Manager unterstützt werden.  
  
```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
 ...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```  
  
### <a name="parameters"></a>Parameter  
 `_PolicyKeyCount`  
 Die Anzahl der Schlüssel-Wert-Paare, die dem `_PolicyKeyCount`-Parameter folgen.  
  
 `_SrcPolicy`  
 Die zu kopierende Quellrichtlinie.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt eine neue Planerrichtlinie, bei der alle Richtlinien mit ihren Standardwerten initialisiert werden.  
  
 Der zweite Konstruktor erstellt eine neue Planerrichtlinie, die ein Initialisierungsformat mit benannten Parametern verwendet. Werte, nach dem der `_PolicyKeyCount`-Parameter als Schlüssel-Wert-Paare angegeben wird. Jeder Richtlinienschlüssel, der nicht in diesem Konstruktor angegeben wird, verfügt über seinen Standardwert. Dieser Konstruktor kann die Ausnahmen auslösen [Invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) oder [Invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).  
  
 Der dritte Konstruktor ist ein Kopierkonstruktor. Oft ist die zweckmäßigste Art, eine neue Planerrichtlinie zu definieren, das Kopieren einer vorhandenen Richtlinie und das anschließende Bearbeiten mit der `SetPolicyValue`-Methode oder der `SetConcurrencyLimits`-Methode.  
  
##  <a name="dtor"></a> ~ SchedulerPolicy 

 Zerstört eine Planerrichtlinie.  
  
```
~SchedulerPolicy();
```  
  
##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits 

 Legt gleichzeitig die `MinConcurrency`-Richtlinie und die `MaxConcurrency`-Richtlinie des `SchedulerPolicy`-Objekts fest.  
  
```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```  
  
### <a name="parameters"></a>Parameter  
 `_MinConcurrency`  
 Der Wert für die `MinConcurrency` Richtlinienschlüssel.  
  
 `_MaxConcurrency`  
 Der Wert für die `MaxConcurrency` Richtlinienschlüssel.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst [Invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) Wenn der angegebene Wert für die `MinConcurrency` Richtlinie ist größer als der angegebene für die `MaxConcurrency` Richtlinie.  
  
 Die Methode kann auch Auslösen [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) für andere ungültige Werte.  
  
##  <a name="setpolicyvalue"></a> SetPolicyValue 

 Legt den Wert des Richtlinienschlüssels fest, der als `key`-Parameter angegeben wurde, und gibt den alten Wert zurück.  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Den Richtlinienschlüssel, einen Wert für festzulegen.  
  
 `value`  
 Der Wert auf den Richtlinienschlüssel festgelegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Schlüssel, wird angegeben die `key` Parameter unterstützt wird, der alten Richtlinienwert für den Schlüssel umgewandelt ein `unsigned int`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst [Invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) für einen ungültigen Richtlinienschlüssel oder jeder Richtlinienschlüssel, dessen Wert kann nicht festgelegt werden, indem Sie, die `SetPolicyValue` Methode.  
  
 Die Methode löst [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) für ein Wert, der für den Schlüssel gemäß nicht unterstützt wird die `key` Parameter.  
  
 Beachten Sie, die diese Methode darf nicht festgelegt die `MinConcurrency` oder `MaxConcurrency` Richtlinien. Um diese Werte festzulegen, verwenden die [SetConcurrencyLimits](#setconcurrencylimits) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [CurrentScheduler-Klasse](currentscheduler-class.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



