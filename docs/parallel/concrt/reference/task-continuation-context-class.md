---
title: Task_continuation_context-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8afd599e5ee489500d7f8c498d03c91ace6b99ed
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context-Klasse
Mit der `task_continuation_context`-Klasse können Sie angeben, an welcher Stelle eine Fortsetzung ausgeführt werden soll. Es ist nur sinnvoll, diese Klasse von einer Windows Store-App aus zu verwenden. Bei Apps, die keine Windows Store-Apps sind, wird der Ausführungskontext der Aufgabenfortsetzung von der Laufzeit bestimmt, und kann nicht konfiguriert werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Gibt ein Kontextobjekt für Fortsetzung, die den aktuellen Kontext des Threads Winrt darstellt.|  
|[use_arbitrary](#use_arbitrary)|Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.|  
|[use_current](#use_current)|Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.|  
|[Standardeinstellung verwenden](#use_default)|Erstellt den standardmäßigen Aufgabenfortsetzungskontext.|  
|[use_synchronous_execution](#use_synchronous_execution)|Gibt ein Kontextobjekt für Fortsetzung, die den synchronen Ausführungskontext darstellt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  

## <a name="get_current_winrt_context"></a>get_current_winrt_context
 Gibt ein Kontextobjekt für Fortsetzung, die den aktuellen Kontext des Threads WinRT darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der aktuelle Kontext des Windows-Runtime-Thread. Gibt eine leere Task_continuation_context zurück, wenn von einem nicht - Windows-Runtime-Kontext aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Die `get_current_winrt_context` Methode erfasst den Kontext des Aufrufers Windows-Runtime-Thread. Einen leeren Kontext zurückgegeben an nicht - Windows-Runtime-Aufrufer.  
  
 Der von zurückgegebene Wert `get_current_winrt_context` kann die Common Language Runtime an, dass die Fortsetzung in dem Apartmentmodell der erfassten Kontext (STA Vs MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgängeraufgabe apartmentfähig verwendet werden. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.  
  
 Diese Methode ähnelt der `use_current` Methode, allerdings steht auch für systemeigenen C++-Code ohne C++ / CX-Unterstützung. Sie dient der Verwendung durch Benutzer das Schreiben von C++ zu erweiterten c++ / CX-agnostischen Bibliothekscode für den einheitlichen und den Windows-Runtime-Aufrufer. Wenn Sie diese Funktion benötigen, empfehlen wir die `use_current` -Methode, die nur für C++ verfügbar ist c++ / CX-Clients.  
  
  
##  <a name="use_arbitrary"></a>use_arbitrary 

 Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Aufgabenfortsetzungskontext, der einen beliebigen Ort darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieser Fortsetzungskontext verwendet wird, wird die Fortsetzung in einem Kontext ausgeführt, den die Laufzeit selbst auswählt, auch wenn die Vorgängeraufgabe apartmentfähig ist.  
  
 `use_arbitrary` kann verwendet werden, um das Standardverhalten für eine Fortsetzung einer apartmentfähigen Aufgabe zu deaktivieren, die in einem STA erstellt wurde.  
  
 Diese Methode ist nur für Windows Store-Apps verfügbar.  
  
##  <a name="use_current"></a>use_current 

 Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Ausführungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erfasst den Windows-Runtime-Kontext des Aufrufers, sodass Fortsetzungen im richtigen Apartment ausgeführt werden können.  
  
 Der Wert, der von `use_current` zurückgegeben wird, teilt der Runtime mit, dass die Fortsetzung im erfassten Kontext (STA oder MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgängeraufgabe apartmentfähig ist. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.  
  
 Diese Methode ist nur für Windows Store-Apps verfügbar.  
  
##  <a name="use_default"></a>Standardeinstellung verwenden 

 Erstellt den standardmäßigen Aufgabenfortsetzungskontext.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der standardmäßige Fortsetzungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkontext wird verwendet, wenn Sie beim Aufrufen der `then`-Methode keinen Fortsetzungskontext angeben. In Windows-Anwendungen für Windows 7 und älter sowie in Desktopanwendungen für Windows 8 und höher bestimmt die Laufzeit, wo Aufgabenfortsetzungen ausgeführt werden. In einer Windows Store-App ist der standardmäßige Fortsetzungskontext für eine Fortsetzung einer apartmentfähigen Aufgabe das Apartment, in dem `then` aufgerufen wird.  
  
 Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird. Wenn Sie eine Fortsetzung einer apartmentfähigen Aufgabe in einem Windows-Runtime-STA planen, wird die Fortsetzung daher in diesem STA ausgeführt.  
  
 Eine Fortsetzung einer nicht apartmentfähigen Aufgabe wird in einem Kontext ausgeführt, den die Laufzeit auswählt.  

## <a name="use_synchronous_execution"></a>task_continuation_context::use_synchronous_execution  
Gibt ein Kontextobjekt für Fortsetzung, die den synchronen Ausführungskontext darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der synchrone Ausführungskontext.  
  
## <a name="remarks"></a>Hinweise  
 Die `use_synchronous_execution` -Methode erzwingt, dass die Fortsetzungsaufgabe synchron auf den Kontext, verursacht der Vorgängeraufgabe Abschluss ausgeführt.  
  
 Wenn die vorangehende Aufgabe bereits abgeschlossen wurde, wenn die Fortsetzung angefügt ist, wird die Fortsetzung synchron auf den Kontext, der die Fortsetzung fügt ausgeführt.  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

