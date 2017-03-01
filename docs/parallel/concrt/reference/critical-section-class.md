---
title: Critical_section-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::critical_section
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 20a150c1aedbd9d78c84187bf29e6284a248fbc7
ms.lasthandoff: 02/24/2017

---
# <a name="criticalsection-class"></a>critical_section-Klasse
Ein nicht wieder eintretender Mutex, der explizit die Concurrency Runtime beachtet.  
  
## <a name="syntax"></a>Syntax  
  
```
class critical_section;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`native_handle_type`|Ein Verweis auf ein `critical_section`-Objekt.|  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[critical_section:: scoped_lock-Klasse](#critical_section__scoped_lock_class)|Ein safe RAII-Wrapper für ein `critical_section` Objekt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Critical_section-Konstruktor](#ctor)|Erstellt einen neuen kritischen Abschnitt.|  
|[~ Critical_section-Destruktor](#dtor)|Zerstört einen kritischen Abschnitt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Lock-Methode](#lock)|Ruft diesen kritischen Abschnitt ab.|  
|[Native_handle-Methode](#native_handle)|Gibt ein plattformspezifischen systemeigenen Handle, zurück, sofern vorhanden.|  
|[Try_lock-Methode](#try_lock)|Versucht, die Sperre ohne Blockierung zu erhalten.|  
|[Try_lock_for-Methode](#try_lock_for)|Versucht, die Sperre abzurufen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.|  
|[Unlock-Methode](#unlock)|Hebt die Sperre des kritischen Abschnitts.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Strukturen für Synchronisierungsdaten](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `critical_section`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-criticalsection"></a><a name="ctor"></a>critical_section 

 Erstellt einen neuen kritischen Abschnitt.  
  
```
critical_section();
```  
  
##  <a name="a-namedtora-criticalsection"></a><a name="dtor"></a>~ Critical_section 

 Zerstört einen kritischen Abschnitt.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird davon ausgegangen, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Der kritische Abschnitt zerstört die Sperre aufrechterhalten weiterhin Ergebnisse in einem nicht definierten Verhalten.  
  
##  <a name="a-namelocka-lock"></a><a name="lock"></a>Sperren 

 Ruft diesen kritischen Abschnitt ab.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist oft sicherer nutzen die [Scoped_lock](#critical_section__scoped_lock_class) -Konstrukt zum Abrufen und freigeben ein `critical_section` -Objekt ausnahmesicher.  
  
 Wenn die Sperre bereits vom aufrufenden Kontext, aufrechterhalten wird ein [Improper_lock](improper-lock-class.md) Ausnahme ausgelöst.  
  
##  <a name="a-namenativehandlea-nativehandle"></a><a name="native_handle"></a>native_handle 

 Gibt ein plattformspezifischen systemeigenen Handle, zurück, sofern vorhanden.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den kritischen Abschnitt.  
  
### <a name="remarks"></a>Hinweise  
 Ein `critical_section` Objekt ist nicht plattformspezifischen systemeigenen Handle für das Windows-Betriebssystem zugeordnet. Die Methode gibt einfach einen Verweis auf das Objekt selbst zurück.  
  
##  <a name="a-namecriticalsectionscopedlockclassa--criticalsectionscopedlock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section:: scoped_lock-Klasse  
 Ein safe RAII-Wrapper für ein `critical_section` Objekt.  
  
```
class scoped_lock;
```  
  
##  <a name="a-namecriticalsectionscopedlockctora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 Erstellt eine `scoped_lock` Objekt, und ruft die `critical_section` Objekt übergeben, der `_Critical_section` Parameter. Wenn der kritische Abschnitt von einem anderen Thread gehalten wird, blockiert dieser Aufruf.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>Parameter  
 `_Critical_section`  
 Der zu sperrende kritische Abschnitt.  
  
##  <a name="a-namecriticalsectionscopedlockdtora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_dtor"></a>Scoped_lock:: ~ Scoped_lock 

 Zerstört ein `scoped_lock` -Objekt und gibt den im Konstruktor bereitgestellten kritischen Abschnitt frei.  
  
```
~scoped_lock();
```  
  
##  <a name="a-nametrylocka-trylock"></a><a name="try_lock"></a>try_lock 

 Versucht, die Sperre ohne Blockierung zu erhalten.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre abgerufen wurde, der Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="a-nametrylockfora-trylockfor"></a><a name="try_lock_for"></a>try_lock_for 

 Versucht, die Sperre abzurufen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>Parameter  
 `_Timeout`  
 Die Anzahl der Millisekunden, bevor ein Timeout gewartet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre abgerufen wurde, der Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="a-nameunlocka-unlock"></a><a name="unlock"></a>Entsperren 

 Hebt die Sperre des kritischen Abschnitts.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Reader_writer_lock-Klasse](reader-writer-lock-class.md)

