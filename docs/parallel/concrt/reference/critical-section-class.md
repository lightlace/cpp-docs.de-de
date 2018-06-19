---
title: Critical_section-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0287c74155e7b4fe827bb015b43cfca3384f3b1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693561"
---
# <a name="criticalsection-class"></a>critical_section-Klasse
Ein nicht wieder eintretender Mutex, der explizit die Concurrency Runtime beachtet.  
  
## <a name="syntax"></a>Syntax  
  
```
class critical_section;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`native_handle_type`|Ein Verweis auf ein `critical_section`-Objekt.|  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[critical_section:: scoped_lock-Klasse](#critical_section__scoped_lock_class)|Eine Ausnahme sichere RAII-Wrapper für ein `critical_section` Objekt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[critical_section](#ctor)|Erstellt einen neuen kritischen Abschnitt.|  
|[~ Critical_section-Destruktor](#dtor)|Zerstört ein kritischen Abschnitts.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[lock](#lock)|Ruft dieser kritischen Abschnitt ab.|  
|[native_handle](#native_handle)|Sofern vorhanden, wird ein bestimmte systemeigene Plattform-Handle zurück.|  
|[try_lock](#try_lock)|Versucht, die Sperre abzurufen, ohne zu blockieren.|  
|[try_lock_for](#try_lock_for)|Versucht, die Sperre abzurufen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.|  
|[unlock](#unlock)|Entsperrt den kritischen Abschnitt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Strukturen für Synchronisierungsdaten](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `critical_section`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> critical_section 

 Erstellt einen neuen kritischen Abschnitt.  
  
```
critical_section();
```  
  
##  <a name="dtor"></a> ~critical_section 

 Zerstört ein kritischen Abschnitts.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird erwartet, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Der kritische Abschnitt, mit der Sperre zerstört aufrechterhalten noch Ergebnisse in einem nicht definierten Verhalten.  
  
##  <a name="lock"></a> Sperre 

 Ruft dieser kritischen Abschnitt ab.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Häufig ist es sicherer, nutzen die [Scoped_lock](#critical_section__scoped_lock_class) -Konstrukts Semantiken abrufen und Freigeben einer `critical_section` Objekt in eine Ausnahme sichere Möglichkeit.  
  
 Wenn die Sperre bereits vom aufrufenden Kontext aufrechterhalten wird ein [Improper_lock](improper-lock-class.md) Ausnahme wird ausgelöst.  
  
##  <a name="native_handle"></a> native_handle 

 Sofern vorhanden, wird ein bestimmte systemeigene Plattform-Handle zurück.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den kritischen Abschnitt.  
  
### <a name="remarks"></a>Hinweise  
 Ein `critical_section` Objekt ist nicht Plattform systemeigene Handle für das Windows-Betriebssystem zugeordnet. Die Methode gibt einfach einen Verweis auf das Objekt selbst.  
  
##  <a name="critical_section__scoped_lock_class"></a>  critical_section:: scoped_lock-Klasse  
 Eine Ausnahme sichere RAII-Wrapper für ein `critical_section` Objekt.  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock 

 Erstellt eine `scoped_lock` Objekt, und ruft die `critical_section` Objekt übergeben, der `_Critical_section` Parameter. Wenn der kritische Abschnitt von einem anderen Thread gehalten wird, wird dieser Aufruf blockiert.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>Parameter  
 `_Critical_section`  
 Der kritische Abschnitt sperren.  
  
##  <a name="critical_section__scoped_lock_dtor"></a> Scoped_lock:: ~ Scoped_lock 

 Zerstört ein `scoped_lock` -Objekt und gibt den im Konstruktor bereitgestellten kritischen Abschnitt frei.  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a> try_lock 

 Versucht, die Sperre abzurufen, ohne zu blockieren.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre eingerichtet wurde, den Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="try_lock_for"></a> try_lock_for 

 Versucht, die Sperre abzurufen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>Parameter  
 `_Timeout`  
 Die Anzahl der Millisekunden wartet, bevor ein Timeout auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre eingerichtet wurde, den Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="unlock"></a> Entsperren 

 Entsperrt den kritischen Abschnitt.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [reader_writer_lock-Klasse](reader-writer-lock-class.md)
