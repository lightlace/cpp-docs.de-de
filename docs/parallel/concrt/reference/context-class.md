---
title: Context-Klasse | Microsoft Docs
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
ms.openlocfilehash: 4bf574fc679b879e2fa9084ed6fbd4ed82e66f70
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
|[Oversubscribe](#oversubscribe)|Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.|  
|[ScheduleGroupId](#schedulegroupid)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.|  
|[Blockierung aufheben](#unblock)|Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.|  
|[VirtualProcessorId](#virtualprocessorid)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.|  
|[Yield](#yield)|Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime-Planer (siehe [Planer](scheduler-class.md)) verwendet Ausführungskontexte zum Ausführen der Arbeit in die Warteschlange gestellt, von der Anwendung. Ein Win32-Thread ist ein Beispiel für einen Ausführungskontext auf einem Windows-Betriebssystem.  
  
 Die Nebenläufigkeitsebene eines Planers ist immer gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager gewährt wurden. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Der Planer ist grundsätzlich kooperativ, und ein Ausführungskontext kann seinen virtuellen Prozessor jederzeit für einen anderen Kontext freigeben, wenn er in einen Wartezustand wechseln möchte. Wenn der Wartevorgang erfüllt wurde, kann solange keine Fortsetzung erfolgen, bis ein verfügbarer virtueller Prozessor vom Planer mit der Ausführung beginnt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Context`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="block"></a> Blockieren 

 Blockiert den aktuellen Kontext.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Wenn auf einem virtuellen Prozessor im aufrufende Kontext ausgeführt wird, findet der virtuelle Prozessor ausgeführt oder kann potenziell ein anderer ausführbaren Kontext ein neues erstellen.  
  
 Nach der `Block` Methode aufgerufen wurde oder aufgerufen wird, müssen Sie es mit einem Aufruf von koppeln der [zum Aufheben der Sperre](#unblock) Methode über einen anderen Ausführungskontext, damit er auf erneut ausführen. Beachten Sie, dass es ein kritischen Zeitraum zwischen dem Code veröffentlicht, in dem der Kontext für einen anderen Thread aufrufen können werden die `Unblock` Methode und der Punkt, in denen die aktuelle Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen, die wiederum sperren und Entsperren von eigenen Gründen (z. B. Sperren) können. Aufrufe von der `Block` und `Unblock` Methode nicht die Ursache für das Blockieren und wiederzulassen nachverfolgen. Nur ein Objekt müssen den Besitz von einem `Block` -  `Unblock` Paar.  
  
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
 Ein Bezeichner für die Planungsgruppe, der der Kontext gerade arbeitet.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode wird eine sofortige Stichprobe der Gruppe "Zeitplan", die den Kontext ausgeführt wird. Wenn diese Methode auf einem anderen Kontext als den aktuellen Kontext aufgerufen wird, kann der Wert veraltet Moment werden zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode verwendet, für das Debuggen und Ablaufverfolgung dienen lediglich der Veranschaulichung.  
  
##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Kontext zurzeit auf einem virtuellen Prozessor, einen Bezeichner für den virtuellen Prozessor ausgeführt wird, der der Kontext gerade ausgeführt wird; andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode wird eine sofortige Stichprobe für den virtuellen Prozessor, dem den Kontext ausgeführt wird. Dieser Wert kann veraltete Moment sein zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode verwendet, für das Debuggen und Ablaufverfolgung dienen lediglich der Veranschaulichung.  
  
##  <a name="id"></a> ID 

 Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer ein Bezeichner für den aktuellen Kontext, die innerhalb des Planers eindeutig ist angefügt wird, zu dem der aktuelle Kontext gehört; andernfalls der Wert `-1`.  
  
##  <a name="iscurrenttaskcollectioncanceling"></a> IsCurrentTaskCollectionCanceling 

 Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt.  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Planer an den aufrufenden Kontext angefügt ist, und eine Aufgabengruppe Inline eine Aufgabe auf diesem Kontext ausgeführt wird, ein Hinweis darauf, ob diese Aufgabengruppe wird in einen Abbruch (oder Kürze); andernfalls der Wert `false`.  
  
##  <a name="issynchronouslyblocked"></a> IsSynchronouslyBlocked 

 Bestimmt, ob der Kontext synchron blockiert ist. Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob der Kontext synchron blockiert ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat. Im Zeitplanungsmodul Thread würde dies einen direkten Aufruf der `Context::Block` Methode oder ein Synchronisierungsobjekt, das die erstellt wurde, mit der `Context::Block` Methode.  
  
 Der Rückgabewert dieser Methode ist eine sofortige Beispiel gibt an, ob der Kontext synchron blockiert ist. Dieser Wert möglicherweise veraltete Moment sein zurückgegeben, und es kann nur unter bestimmten Umständen verwendet werden.  
  
##  <a name="operator_delete"></a> Delete-Operator 

 Ein `Context` Objekt wird intern von der Laufzeit zerstört. Er kann nicht explizit gelöscht werden.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Parameter  
 `_PObject`  
 Ein Zeiger auf das Objekt gelöscht werden soll.  
  
##  <a name="oversubscribe"></a> Oversubscribe 

 Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Parameter  
 `_BeginOversubscription`  
 Wenn `true`, ein Hinweis, dass ein weiterer virtueller Prozessor für die Dauer der Überzeichnung hinzugefügt werden soll. Wenn `false`, ein Hinweis, dass die Überzeichnung beendet und der zuvor hinzugefügte virtuelle Prozessor entfernt werden soll.  
  
##  <a name="schedulegroupid"></a> ScheduleGroupId 

 Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer angefügt ist und für eine Planungsgruppe arbeiten, ein Bezeichner für den Planer gruppieren, die funktioniert auf der aktuelle Kontext; andernfalls der Wert `-1`.  
  
##  <a name="unblock"></a> Blockierung aufheben 

 Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist durchaus zulässig, für einen Aufruf der `Unblock` Methode vor der zugehörigen Aufruf an die [Block](#block) Methode. So lange als Aufrufe an die `Block` und `Unblock` Methoden ordnungsgemäß zugeordnet sind, die Common Language Runtime ordnungsgemäß behandelt das natürliche Rennen entweder Anordnung. Ein `Unblock` Aufruf, der vor einem `Block` Aufruf negiert den Effekt des der `Block` aufrufen.  
  
 Es gibt einige Ausnahmen, die von dieser Methode ausgelöst werden können. Wenn ein Kontext versucht, rufen Sie die `Unblock` Methode auf, die selbst eine [Context_self_unblock](context-self-unblock-class.md) Ausnahme wird ausgelöst. Wenn Aufrufe von `Block` und `Unblock` nicht ordnungsgemäß zugeordnet (z. B. die beiden Aufrufe von `Unblock` erfolgen für einen Kontext, der derzeit ausgeführt wird), ein [Context_unblock_unbalanced](context-unblock-unbalanced-class.md) Ausnahme wird ausgelöst.  
  
 Beachten Sie, dass es ein kritischen Zeitraum zwischen dem Code veröffentlicht, in dem der Kontext für einen anderen Thread aufrufen können werden die `Unblock` Methode und der Punkt, in denen die aktuelle Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen, die wiederum sperren und Entsperren von eigenen Gründen (z. B. Sperren) können. Aufrufe von der `Block` und `Unblock` Methode nicht die Ursache für das Blockieren und wiederzulassen nachverfolgen. Nur ein Objekt müssen den Besitz von einem `Block` und `Unblock` Paar.  
  
##  <a name="virtualprocessorid"></a> VirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer ein Bezeichner für den virtuellen Prozessor verbunden ist, die den aktuellen Kontext ausgeführt wird; andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode wird eine sofortige Stichprobe für den virtuellen Prozessor, dem den aktuellen Kontext ausgeführt wird. Dieser Wert kann veraltete Moment sein zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode verwendet, für das Debuggen und Ablaufverfolgung dienen lediglich der Veranschaulichung.  
  
##  <a name="yield"></a> Yield 

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
  
 Diese Funktion ist neu in [!INCLUDE[vs_dev14](../../../ide/includes/vs_dev14_md.md)] und identisch mit der [Yield](#yield) funktionsfähig, jedoch keine Konflikte mit dem Yield-Makro in Windows.h dar.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



