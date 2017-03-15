---
title: Reader_writer_lock-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::reader_writer_lock
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
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
ms.openlocfilehash: d5d2fde890b0836621fcd1db5bb87b1933bb2a04
ms.lasthandoff: 02/24/2017

---
# <a name="readerwriterlock-class"></a>reader_writer_lock-Klasse
Eine im Writer festgelegte, warteschlangenbasierte Lese-/Schreibsperre mit ausschließlich lokalem Spinning. Die Sperre gewährt "First In, First Out"-Zugriff (FIFO-Zugriff) auf Writer und blockiert Reader unter einer fortlaufenden Last von Writern.  
  
## <a name="syntax"></a>Syntax  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[reader_writer_lock:: scoped_lock-Klasse](#scoped_lock_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Writer.|  
|[reader_writer_lock:: scoped_lock_read-Klasse](#scoped_lock_read_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Reader.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Reader_writer_lock-Konstruktor](#ctor)|Erstellt ein neues `reader_writer_lock`-Objekt.|  
|[~ Reader_writer_lock-Destruktor](#dtor)|Zerstört das `reader_writer_lock`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Lock-Methode](#lock)|Ruft die Lese-/ Schreibsperre als Writer ab.|  
|[Lock_read-Methode](#lock_read)|Ruft die Lese-/ Schreibsperre als Reader ab. Wenn Writer vorhanden sind, müssen aktive Reader warten, bis sie abgeschlossen sind. Der Reader wird einfach registriert ein Interesse an der Sperre und wartet, bis Writer sie freigeben.|  
|[Try_lock-Methode](#try_lock)|Versucht, die Lese-/ Schreibsperre als Writer ohne Blockierung zu erhalten.|  
|[Try_lock_read-Methode](#try_lock_read)|Versucht, die Lese-/ Schreibsperre als Reader ohne Blockierung zu erhalten.|  
|[Unlock-Methode](#unlock)|Entsperrt die Reader / Writer-Sperre, die basierend auf, die, Reader oder Writer gesperrt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Strukturen für Synchronisierungsdaten](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namelocka-lock"></a><a name="lock"></a>Sperren 

 Ruft die Lese-/ Schreibsperre als Writer ab.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist oft sicherer nutzen die [Scoped_lock](#scoped_lock_class) -Konstrukt zum Abrufen und Freigeben einer `reader_writer_lock` Objekt als Writer eine Ausnahme ausnahmesicher.  
  
 Nachdem ein Writer versucht, die Sperre abzurufen, blockiert alle zukünftigen Reader, bis die Writer erfolgreich abgerufen und die Sperre aufgehoben haben. Diese Sperre ist unvoreingenommen gegenüber Writer und Reader unter einer fortlaufenden Last von Writern blockieren kann.  
  
 Writer werden verkettet, sodass ein Writer, der das Beenden der Sperre der nächsten Writer inline freigibt.  
  
 Wenn die Sperre bereits vom aufrufenden Kontext, aufrechterhalten wird ein [Improper_lock](improper-lock-class.md) Ausnahme ausgelöst.  
  
##  <a name="a-namelockreada-lockread"></a><a name="lock_read"></a>lock_read 

 Ruft die Lese-/ Schreibsperre als Reader ab. Wenn Writer vorhanden sind, müssen aktive Reader warten, bis sie abgeschlossen sind. Der Reader wird einfach registriert ein Interesse an der Sperre und wartet, bis Writer sie freigeben.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist oft sicherer nutzen die [Scoped_lock_read](#scoped_lock_read_class) -Konstrukt zum Abrufen und Freigeben einer `reader_writer_lock` Objekt als Reader eine Ausnahme ausnahmesicher.  
  
 Wenn Writer auf die Sperre warten, wartet der Leser, bis alle Writer in Zeile abgerufen und die Sperre aufgehoben haben. Diese Sperre ist unvoreingenommen gegenüber Writer und Reader unter einer fortlaufenden Last von Writern blockieren kann.  
  
##  <a name="a-namectora-readerwriterlock"></a><a name="ctor"></a>reader_writer_lock 

 Erstellt ein neues `reader_writer_lock`-Objekt.  
  
```
reader_writer_lock();
```  
  
##  <a name="a-namedtora-readerwriterlock"></a><a name="dtor"></a>~ Reader_writer_lock 

 Zerstört das `reader_writer_lock`-Objekt.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird davon ausgegangen, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Ermöglicht Schreibsperre zerstört die Sperre aufrechterhalten Ergebnisse noch nicht definiertem Verhalten.  
  
##  <a name="a-namescopedlockclassa--readerwriterlockscopedlock-class"></a><a name="scoped_lock_class"></a>reader_writer_lock:: scoped_lock-Klasse  
 Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Writer.  
  
```
class scoped_lock;
``` 
## <a name="a-namescopedlockctora-scopedlockscopedlock"></a><a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock 

Erstellt eine `scoped_lock` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als einen Writer. Wenn die Sperre von einem anderen Thread gehalten wird, blockiert dieser Aufruf.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parameter  
 `_Reader_writer_lock`  
 Das `reader_writer_lock` Objekt, das als Writer abgerufen.  
  
## <a name="a-namescopedlockdtora-scopedlockscopedlock"></a><a name="scoped_lock_dtor"></a>Scoped_lock:: ~ Scoped_lock 

Zerstört ein `reader_writer_lock` -Objekt an und hebt die Sperre in seinem Konstruktor bereitgestellt.   

```
~scoped_lock();
```  
  
##  <a name="a-namescopedlockreadclassa--readerwriterlockscopedlockread-class"></a><a name="scoped_lock_read_class"></a>reader_writer_lock:: scoped_lock_read-Klasse  
 Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Reader.  
  
```
class scoped_lock_read;
```  
  
##  <a name="a-nametrylocka-trylock"></a><a name="try_lock"></a>try_lock 

 Versucht, die Lese-/ Schreibsperre als Writer ohne Blockierung zu erhalten.  

## <a name="a-namescopedlockreadctora-scopedlockreadscopedlockread"></a><a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read 

Erstellt eine `scoped_lock_read` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als Reader. Wenn die Sperre von einem anderen Thread als Autor oder wartende Writer vorhanden sind, wird dieser Aufruf gesperrt.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parameter  
 `_Reader_writer_lock`  
 Das `reader_writer_lock` Objekt, das als Reader abgerufen.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock:: scoped_lock_read:: ~ Scoped_lock_read-Destruktor
Zerstört ein `scoped_lock_read` -Objekt an und hebt die Sperre in seinem Konstruktor bereitgestellt.  

```
~scoped_lock_read();
```  
  
## <a name="a-nametrylocka-trylock"></a><a name="try_lock"></a>try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre abgerufen wurde, der Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="a-nametrylockreada-trylockread"></a><a name="try_lock_read"></a>try_lock_read 

 Versucht, die Lese-/ Schreibsperre als Reader ohne Blockierung zu erhalten.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre abgerufen wurde, der Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="a-nameunlocka-unlock"></a><a name="unlock"></a>Entsperren 

 Entsperrt die Reader / Writer-Sperre, die basierend auf, die, Reader oder Writer gesperrt.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Writer auf die Sperre warten, wechselt die Aufhebung der Sperre immer zum nächsten Writer in FIFO-Reihenfolge. Diese Sperre ist unvoreingenommen gegenüber Writer und Reader unter einer fortlaufenden Last von Writern blockieren kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Critical_section-Klasse](critical-section-class.md)

