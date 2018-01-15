---
title: Reader_writer_lock-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
dev_langs: C++
helpviewer_keywords: reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49cc917ddcd4d7de274a8f6bb1f61c940493a365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="readerwriterlock-class"></a>reader_writer_lock-Klasse
Eine im Writer festgelegte, warteschlangenbasierte Lese-/Schreibsperre mit ausschließlich lokalem Spinning. Die Sperre gewährt "First In, First Out"-Zugriff (FIFO-Zugriff) auf Writer und blockiert Reader unter einer fortlaufenden Last von Writern.  
  
## <a name="syntax"></a>Syntax  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[reader_writer_lock:: scoped_lock-Klasse](#scoped_lock_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Schreiber.|  
|[reader_writer_lock:: scoped_lock_read-Klasse](#scoped_lock_read_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Reader.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|Erstellt ein neues `reader_writer_lock`-Objekt.|  
|[~ Reader_writer_lock-Destruktor](#dtor)|Zerstört das `reader_writer_lock`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[lock](#lock)|Ruft die Lese-/Schreibsperre als Writer ab.|  
|[lock_read](#lock_read)|Ruft die Lese-/Schreibsperre als Reader ab. Wenn Writer, haben aktive Reader warten, bis sie fertig sind. Der Reader einfach registriert ein Interesse an die Sperre und wartet, bis Writer, diese freizugeben.|  
|[try_lock](#try_lock)|Versucht, die Lese-/Schreibsperre als Writer ohne Blockierung zu erhalten.|  
|[try_lock_read](#try_lock_read)|Versucht, die Lese-/Schreibsperre als Reader ohne Blockierung zu erhalten.|  
|[unlock](#unlock)|Entsperrt die Lese-/Schreibsperre basierend auf, die es Reader oder Writer gesperrt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Strukturen für Synchronisierungsdaten](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="lock"></a>Sperre 

 Ruft die Lese-/Schreibsperre als Writer ab.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Häufig ist es sicherer, nutzen die [Scoped_lock](#scoped_lock_class) -Konstrukts Semantiken abrufen und Freigeben einer `reader_writer_lock` Objekts als Schreiber eine Ausnahme ausgelöst sichere Möglichkeit.  
  
 Nachdem ein Writer versucht, die Sperre abzurufen, blockiert alle zukünftigen Reader, bis der Writer erfolgreich abgerufen und die Sperre aufgehoben haben. Diese Sperre ist Blockcontainer Writer und kann .NET-Threadpool blockiert Reader unter einer fortlaufenden Last von Writern.  
  
 Writer werden verkettet, sodass Writer die Sperre beendet den nächsten Writer Zeile frei.  
  
 Wenn die Sperre bereits vom aufrufenden Kontext aufrechterhalten wird ein [Improper_lock](improper-lock-class.md) Ausnahme wird ausgelöst.  
  
##  <a name="lock_read"></a>lock_read 

 Ruft die Lese-/Schreibsperre als Reader ab. Wenn Writer, haben aktive Reader warten, bis sie fertig sind. Der Reader einfach registriert ein Interesse an die Sperre und wartet, bis Writer, diese freizugeben.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Hinweise  
 Häufig ist es sicherer, nutzen die [Scoped_lock_read](#scoped_lock_read_class) -Konstrukts Semantiken abrufen und Freigeben einer `reader_writer_lock` Objekts als ein Leser eine Ausnahme sichere Möglichkeit.  
  
 Wenn Writer auf die Sperre warten, wird der Reader warten Sie, bis alle Writer in Zeile abgerufen und die Sperre aufgehoben haben. Diese Sperre ist Blockcontainer Writer und kann .NET-Threadpool blockiert Reader unter einer fortlaufenden Last von Writern.  
  
##  <a name="ctor"></a>reader_writer_lock 

 Erstellt ein neues `reader_writer_lock`-Objekt.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a>~ Reader_writer_lock 

 Zerstört das `reader_writer_lock`-Objekt.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird erwartet, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Ermöglicht die Schreibsperre zerstört mit der Sperre aufrechterhalten noch Ergebnisse in einem nicht definierten Verhalten.  
  
##  <a name="scoped_lock_class"></a>reader_writer_lock:: scoped_lock-Klasse  
 Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Schreiber.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock 

Erstellt eine `scoped_lock` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als einen Writer. Wenn von einem anderen Thread die Sperre aufrechterhalten wird, wird dieser Aufruf blockiert.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parameter  
 `_Reader_writer_lock`  
 Die `reader_writer_lock` Objekt, das als Writer abgerufen.  
  
## <a name="scoped_lock_dtor"></a>Scoped_lock:: ~ Scoped_lock 

Zerstört ein `reader_writer_lock` Objekt, und hebt die Sperre, die in seinem Konstruktor angegeben.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>reader_writer_lock:: scoped_lock_read-Klasse  
 Eine sichere RAII-Wrapper, die verwendet werden kann, erhalten `reader_writer_lock` Sperren von Objekten als Reader.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a>try_lock 

 Versucht, die Lese-/Schreibsperre als Writer ohne Blockierung zu erhalten.  

## <a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read 

Erstellt eine `scoped_lock_read` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als Reader. Wenn die Sperre von einem anderen Thread als Writer oder ausstehende Writer vorhanden sind, wird dieser Aufruf blockiert.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parameter  
 `_Reader_writer_lock`  
 Die `reader_writer_lock` Objekt, das als Reader abgerufen.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock:: scoped_lock_read:: ~ Scoped_lock_read-Destruktor
Zerstört ein `scoped_lock_read` Objekt, und hebt die Sperre, die in seinem Konstruktor angegeben.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a>try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre eingerichtet wurde, den Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="try_lock_read"></a>try_lock_read 

 Versucht, die Lese-/Schreibsperre als Reader ohne Blockierung zu erhalten.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Sperre eingerichtet wurde, den Wert `true`ist, andernfalls der Wert `false`.  
  
##  <a name="unlock"></a>Entsperren 

 Entsperrt die Lese-/Schreibsperre basierend auf, die es Reader oder Writer gesperrt.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Writer auf die Sperre warten, geht die Aufhebung der Sperre immer in den nächsten Writer in FIFO-Reihenfolge. Diese Sperre ist Blockcontainer Writer und kann .NET-Threadpool blockiert Reader unter einer fortlaufenden Last von Writern.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [critical_section-Klasse](critical-section-class.md)
