---
title: Task_options-Klasse (Concurrency Runtime) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_options
dev_langs:
- C++
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 9b0d7d245ae204fd59715c8142a836adbb63c10a
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="taskoptions-class-concurrency-runtime"></a>task_options-Klasse (Concurrency Runtime)
Stellt die zulässigen Optionen zum Erstellen einer Aufgabe dar  
  
## <a name="syntax"></a>Syntax  
  
```
class task_options;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_options:: task_options-Konstruktor (Concurrency Runtime)](#ctor)|Überladen. Standardliste von Aufgabenerstellungsoptionen|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_options:: get_cancellation_token-Methode (Concurrency Runtime)](#get_cancellation_token)|Gibt das Abbruchtoken zurück.|  
|[task_options:: get_continuation_context-Methode (Concurrency Runtime)](#get_continuation_context)|Gibt den Fortsetzungskontext zurück.|  
|[task_options:: get_scheduler-Methode (Concurrency Runtime)](#get_scheduler)|Gibt den Planer zurück.|  
|[task_options:: has_cancellation_token-Methode (Concurrency Runtime)](#has_cancellation_token)|Gibt an, ob ein Abbruchtoken vom Benutzer angegeben wurde.|  
|[task_options:: has_scheduler-Methode (Concurrency Runtime)](#has_scheduler)|Gibt an, ob ein Planer vom Benutzer angegeben wurde.|  
|[task_options:: set_cancellation_token-Methode (Concurrency Runtime)](#set_cancellation_token)|Legt das angegebene Token in den Optionen fest.|  
|[task_options:: set_continuation_context-Methode (Concurrency Runtime)](#set_continuation_context)|Legt den angegebenen Fortsetzungskontext in den Optionen fest.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_options`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="get_cancellation_token"></a>task_options:: get_cancellation_token-Methode (Concurrency Runtime)  
 Gibt das Abbruchtoken zurück.  
  
```
cancellation_token get_cancellation_token() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="get_continuation_context"></a>task_options:: get_continuation_context-Methode (Concurrency Runtime)  
 Gibt den Fortsetzungskontext zurück.  
  
```
task_continuation_context get_continuation_context() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="get_scheduler"></a>task_options:: get_scheduler-Methode (Concurrency Runtime)  
 Gibt den Planer zurück.  
  
```
scheduler_ptr get_scheduler() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="has_cancellation_token"></a>task_options:: has_cancellation_token-Methode (Concurrency Runtime)  
 Gibt an, ob ein Abbruchtoken vom Benutzer angegeben wurde.  
  
```
bool has_cancellation_token() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="has_scheduler"></a>task_options:: has_scheduler-Methode (Concurrency Runtime)  
 Gibt an, ob ein Planer vom Benutzer angegeben wurde.  
  
```
bool has_scheduler() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="set_cancellation_token"></a>task_options:: set_cancellation_token-Methode (Concurrency Runtime)  
 Legt das angegebene Token in den Optionen fest.  
  
```
void set_cancellation_token(cancellation_token _Token);
```  
  
### <a name="parameters"></a>Parameter  
 `_Token`  
  
##  <a name="set_continuation_context"></a>task_options:: set_continuation_context-Methode (Concurrency Runtime)  
 Legt den angegebenen Fortsetzungskontext in den Optionen fest.  
  
```
void set_continuation_context(task_continuation_context _ContinuationContext);
```  
  
### <a name="parameters"></a>Parameter  
 `_ContinuationContext`  
  
##  <a name="ctor"></a>task_options:: task_options-Konstruktor (Concurrency Runtime)  
 Standardliste von Aufgabenerstellungsoptionen  
  
```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```  
  
### <a name="parameters"></a>Parameter  
 `_SchedType`  
 `_Token`  
 `_ContinuationContext`  
 `_Scheduler`  
 `_TaskOptions`  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
