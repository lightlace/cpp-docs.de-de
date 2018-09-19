---
title: Context-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
dev_langs:
- C++
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4a62f6e569e123b9612e922e2d7c70787371afc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136178"
---
# <a name="context-class"></a>Context-Klasse
Stellt eine Abstraktion für einen Ausführungskontext dar.  
  
## <a name="syntax"></a>Syntax  
  
```
class Context;
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ Context-Destruktor](#dtor)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Block](#block)|Blockiert den aktuellen Kontext.|  
|[CurrentContext](#currentcontext)|Gibt einen Zeiger auf den aktuellen Kontext zurück.|  
|[GetId](#getid)|Gibt einen Bezeichner für den Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.|  
|[GetScheduleGroupId](#getschedulegroupid)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der Kontext gerade arbeitet.|  
|[GetVirtualProcessorId](#getvirtualprocessorid)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.|  
|[Id](#id)|Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.|  
|[IsCurrentTaskCollectionCanceling](#iscurrenttaskcollectioncanceling)|Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt.|  
|[IsSynchronouslyBlocked](#issynchronouslyblocked)|Bestimmt, ob der Kontext synchron blockiert ist. Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.|  
|[Überzeichnen](#oversubscribe)|Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.|  
|[ScheduleGroupId](#schedulegroupid)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.|  
|[Entsperren](#unblock)|Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.|  
|[VirtualProcessorId](#virtualprocessorid)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.|  
|[Yield](#yield)|Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime-Planer (finden Sie unter [Scheduler](scheduler-class.md)) verwendet Ausführungskontexte, führen Sie die Arbeit in die Warteschlange eingereiht, von der Anwendung. Ein Win32-Thread ist ein Beispiel für einen Ausführungskontext auf einem Windows-Betriebssystem.  
  
 Die Nebenläufigkeitsebene eines Planers ist immer gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager gewährt wurden. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Der Planer ist grundsätzlich kooperativ, und ein Ausführungskontext kann seinen virtuellen Prozessor jederzeit für einen anderen Kontext freigeben, wenn er in einen Wartezustand wechseln möchte. Wenn der Wartevorgang erfüllt wurde, kann solange keine Fortsetzung erfolgen, bis ein verfügbarer virtueller Prozessor vom Planer mit der Ausführung beginnt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Context`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="block"></a> Block 

 Blockiert den aktuellen Kontext.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Wenn auf einem virtuellen Prozessor im aufrufende Kontext ausgeführt wird, findet der virtuelle Prozessor anderen ausführbaren Kontext zum Ausführen oder möglicherweise kann ein neues erstellen.  
  
 Nach der `Block` Methode aufgerufen wurde oder aufgerufen wird, müssen Sie es mit einem Aufruf von koppeln der [Unblock](#unblock) Methode über einen anderen Ausführungskontext in der Reihenfolge dafür erneut ausführen. Werden Sie bemerken, dass es ein kritischen Zeitraum zwischen dem Code, in dem der Kontext für einen anderen Thread veröffentlicht aufrufen, kann die `Unblock` Methode und der Punkt, in dem die Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen, die wiederum blockieren und entsperren eine eigene Gründen (z. B. Sperren) können. Aufrufe von der `Block` und `Unblock` Methode nicht die Ursache für das Blockieren und wiederzulassen von nachverfolgen. Nur ein Objekt müssen den Besitz einer `Block` -  `Unblock` Paar.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md).  
  
##  <a name="dtor"></a> ~ Kontext 

```
virtual ~Context();
```  
  
##  <a name="currentcontext"></a> CurrentContext 

 Gibt einen Zeiger auf den aktuellen Kontext zurück.  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Kontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
##  <a name="getid"></a> GetId 

 Gibt einen Bezeichner für den Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für den Kontext, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.  
  
##  <a name="getschedulegroupid"></a> GetScheduleGroupId 

 Gibt einen Bezeichner für die Planungsgruppe zurück, an der der Kontext gerade arbeitet.  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für die Planungsgruppe Kontext arbeitet derzeit an.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist eine sofortige Stichprobe der Schedule-Gruppe, der den Kontext ausgeführt wird. Wenn diese Methode auf einem anderen Kontext als dem aktuellen Kontext aufgerufen wird, kann der Wert veraltet derzeit werden zurückgegeben, und es kann nicht als zuverlässig betrachtet werden. In der Regel wird diese Methode zum Debuggen oder Ablaufverfolgung Zwecken verwendet.  
  
##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Kontext zurzeit auf einem virtuellen Prozessor, einen Bezeichner für den virtuellen Prozessor ausgeführt wird, die der Kontext gerade ausgeführt wird; andernfalls den Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist eine sofortige Stichprobe für den virtuellen Prozessor, dem den Kontext ausgeführt wird. Dieser Wert kann veraltete Moment sein zurückgegeben wird, und kann nicht als zuverlässig betrachtet werden. In der Regel wird diese Methode zum Debuggen oder Ablaufverfolgung Zwecken verwendet.  
  
##  <a name="id"></a> ID 

 Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext, der einem Planer, der einen Bezeichner für den aktuellen Kontext, die innerhalb des Planers eindeutig ist angefügt ist, zu der der aktuelle Kontext gehört; andernfalls den Wert `-1`.  
  
##  <a name="iscurrenttaskcollectioncanceling"></a> IsCurrentTaskCollectionCanceling 

 Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt.  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Planer an den aufrufenden Kontext angefügt ist, und eine Aufgabengruppe dieses Kontexts eine Aufgabe Inline ausgeführt, Angabe, ob diese Aufgabengruppe ist in einen Abbruch (oder werden in Kürze); andernfalls den Wert `false`.  
  
##  <a name="issynchronouslyblocked"></a> IsSynchronouslyBlocked 

 Bestimmt, ob der Kontext synchron blockiert ist. Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob der Kontext synchron blockiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat. Auf den Threadplaner, würde dies einen direkten Aufruf der `Context::Block` Methode oder ein Synchronisierungsobjekt, das erstellt wurde, mithilfe der `Context::Block` Methode.  
  
 Der Rückgabewert dieser Methode ist ein Beispiel für eine sofortige der gibt an, ob der Kontext synchron blockiert wird. Dieser Wert veraltete derzeit möglicherweise er zurückgegeben wird, und kann nur unter ganz bestimmten Situationen verwendet werden.  
  
##  <a name="operator_delete"></a> Delete-Operator 

 Ein `Context` -Objekt intern von der Laufzeit zerstört wird. Es kann nicht explizit gelöscht werden.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Parameter  
*_PObject*<br/>
Ein Zeiger auf das Objekt, das gelöscht werden.  
  
##  <a name="oversubscribe"></a> Überzeichnen 

 Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Parameter  
*_BeginOversubscription*<br/>
Wenn `true`, ein Hinweis, dass ein weiterer virtueller Prozessor für die Dauer der Überzeichnung hinzugefügt werden soll. Wenn `false`, ein Hinweis, dass die Überzeichnung beendet und der zuvor hinzugefügte virtuelle Prozessor entfernt werden soll.  
  
##  <a name="schedulegroupid"></a> ScheduleGroupId 

 Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext, der einem Planer angefügt wird und an eine Planungsgruppe arbeiten, ein Bezeichner für das Zeitplanungsmodul gruppieren, die funktioniert auf der aktuelle Kontext; andernfalls den Wert `-1`.  
  
##  <a name="unblock"></a> Entsperren 

 Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist durchaus zulässig für einen Aufruf der `Unblock` Methode vor einen zugehörigen Aufruf an die [Block](#block) Methode. So lange, wie Aufrufe der `Block` und `Unblock` Methoden sind nicht richtig paarweise angegeben, die Runtime ordnungsgemäß behandelt das natürliche Rennen entweder Sortierung. Ein `Unblock` Aufruf, der vor einem `Block` Aufruf einfach negiert die Wirkung der `Block` aufrufen.  
  
 Es gibt mehrere Ausnahmen, die von dieser Methode ausgelöst werden können. Wenn ein Kontext aufrufen, versucht der `Unblock` Methode selbst eine [Context_self_unblock](context-self-unblock-class.md) Ausnahme wird ausgelöst. Wenn Aufrufe von `Block` und `Unblock` nicht ordnungsgemäß zugeordnet (z. B. die beiden Aufrufe von `Unblock` erfolgen für einen Kontext, der derzeit ausgeführt wird), ein [Context_unblock_unbalanced](context-unblock-unbalanced-class.md) Ausnahme ausgelöst.  
  
 Werden Sie bemerken, dass es ein kritischen Zeitraum zwischen dem Code, in dem der Kontext für einen anderen Thread veröffentlicht aufrufen, kann die `Unblock` Methode und der Punkt, in dem die Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen, die wiederum blockieren und entsperren eine eigene Gründen (z. B. Sperren) können. Aufrufe von der `Block` und `Unblock` Methode nicht die Ursache für das Blockieren und wiederzulassen von nachverfolgen. Nur ein Objekt müssen den Besitz einer `Block` und `Unblock` Paar.  
  
##  <a name="virtualprocessorid"></a> VirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext, der einem Planer, der einen Bezeichner für den virtuellen Prozessor verbunden ist, die der aktuelle Kontext ausgeführt wird; andernfalls den Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist eine sofortige Stichprobe für den virtuellen Prozessor, dem der aktuelle Kontext ausgeführt wird. Dieser Wert kann veraltete Moment sein zurückgegeben wird, und kann nicht als zuverlässig betrachtet werden. In der Regel wird diese Methode zum Debuggen oder Ablaufverfolgung Zwecken verwendet.  
  
##  <a name="yield"></a> "yield" 

 Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
##  <a name="yieldexecution"></a> YieldExecution 

 Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Diese Funktion ist neu in Visual Studio 2015 und ist identisch mit der [Yield](#yield) funktionieren, aber nicht mit dem Yield-Makro in Windows.h in Konflikt steht.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [Aufgabenplanung](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



