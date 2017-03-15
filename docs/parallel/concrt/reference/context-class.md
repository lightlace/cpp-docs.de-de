---
title: Context-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::Context
dev_langs:
- C++
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
caps.latest.revision: 20
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
ms.openlocfilehash: 11d8252afdfe9c02869b14f976f8f348513c46b8
ms.lasthandoff: 02/24/2017

---
# <a name="context-class"></a>Context-Klasse
Stellt eine Abstraktion für einen Ausführungskontext dar.  
  
## <a name="syntax"></a>Syntax  
  
```
class Context;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ Context-Destruktor](#dtor)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Block-Methode](#block)|Blockiert den aktuellen Kontext.|  
|[CurrentContext-Methode](#currentcontext)|Gibt einen Zeiger auf den aktuellen Kontext zurück.|  
|[GetId-Methode](#getid)|Gibt einen Bezeichner für den Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.|  
|[GetScheduleGroupId-Methode](#getschedulegroupid)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der Kontext gerade arbeitet.|  
|[GetVirtualProcessorId-Methode](#getvirtualprocessorid)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.|  
|[ID-Methode](#id)|Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.|  
|[IsCurrentTaskCollectionCanceling-Methode](#iscurrenttaskcollectioncanceling)|Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt.|  
|[IsSynchronouslyBlocked-Methode](#issynchronouslyblocked)|Bestimmt, ob der Kontext synchron blockiert ist. Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.|  
|[Oversubscribe-Methode](#oversubscribe)|Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.|  
|[ScheduleGroupId-Methode](#schedulegroupid)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.|  
|[Unblock-Methode](#unblock)|Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.|  
|[VirtualProcessorId-Methode](#virtualprocessorid)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.|  
|[Yield-Methode](#yield)|Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.|  
  
## <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime-Planer (siehe [Scheduler](scheduler-class.md)) verwendet Ausführungskontexte zum Ausführen der Arbeit in die Warteschlange eingereiht, von der Anwendung. Ein Win32-Thread ist ein Beispiel für einen Ausführungskontext auf einem Windows-Betriebssystem.  
  
 Die Nebenläufigkeitsebene eines Planers ist immer gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager gewährt wurden. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Der Planer ist grundsätzlich kooperativ, und ein Ausführungskontext kann seinen virtuellen Prozessor jederzeit für einen anderen Kontext freigeben, wenn er in einen Wartezustand wechseln möchte. Wenn der Wartevorgang erfüllt wurde, kann solange keine Fortsetzung erfolgen, bis ein verfügbarer virtueller Prozessor vom Planer mit der Ausführung beginnt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Context`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameblocka-block"></a><a name="block"></a>Block 

 Blockiert den aktuellen Kontext.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Wenn der aufrufende Kontext auf einem virtuellen Prozessor ausgeführt wird, der virtuelle Prozessor findet die anderen ausführbaren Kontext zum Ausführen oder kann möglicherweise eine neue erstellen.  
  
 Nach der `Block` Methode aufgerufen wurde, oder aufgerufen wird, müssen Sie es mit einem Aufruf von koppeln der [zulassen](#unblock) Methode über einen anderen Ausführungskontext in der Reihenfolge danach erneut ausführen. Beachten Sie, dass es ein kritischen Zeitraum zwischen dem Punkt, in dem Ihr Code seinen Kontext veröffentlicht, ein anderer Thread aufgerufen werden können, die `Unblock` Methode und dem Punkt, wo die Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen können wiederum blockieren und zulassen eigene Gründen (z. B. eine Sperre des Typs). Aufrufe von der `Block` und `Unblock` -Methode verfolgen den Grund für die Blockierung und das Aufheben der Sperre. Nur ein Objekt müssen den Besitz einer `Block` -  `Unblock` Paar.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen auslösen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md).  
  
##  <a name="a-namedtora-context"></a><a name="dtor"></a>~ Kontext 

```
virtual ~Context();
```  
  
##  <a name="a-namecurrentcontexta-currentcontext"></a><a name="currentcontext"></a>CurrentContext 

 Gibt einen Zeiger auf den aktuellen Kontext zurück.  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Kontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
##  <a name="a-namegetida-getid"></a><a name="getid"></a>GetId 

 Gibt einen Bezeichner für den Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für den Kontext, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.  
  
##  <a name="a-namegetschedulegroupida-getschedulegroupid"></a><a name="getschedulegroupid"></a>GetScheduleGroupId 

 Gibt einen Bezeichner für die Planungsgruppe zurück, an der der Kontext gerade arbeitet.  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für die Planungsgruppe, der der Kontext gerade arbeitet.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist ein einleuchtendes Beispiel für die Planungsgruppe, der den Kontext ausgeführt wird. Wenn diese Methode auf einem anderen Kontext als den aktuellen Kontext aufgerufen wird, kann der Wert veraltete Moment sein zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode zum Debuggen oder für Nachverfolgungszwecke verwendet nur.  
  
##  <a name="a-namegetvirtualprocessorida-getvirtualprocessorid"></a><a name="getvirtualprocessorid"></a>GetVirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Kontext gerade auf einem virtuellen Prozessor, einen Bezeichner für den virtuellen Prozessor ausgeführt wird, der der Kontext gerade ausgeführt wird; andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist ein einleuchtendes Beispiel für den virtuellen Prozessor, dem den Kontext ausgeführt wird. Dieser Wert kann veraltete Moment werden zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode zum Debuggen oder für Nachverfolgungszwecke verwendet nur.  
  
##  <a name="a-nameida-id"></a><a name="id"></a>ID 

 Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer ein Bezeichner für den aktuellen Kontext, der innerhalb des Planers eindeutig ist angefügt wird, zu dem der aktuelle Kontext gehört; andernfalls der Wert `-1`.  
  
##  <a name="a-nameiscurrenttaskcollectioncancelinga-iscurrenttaskcollectioncanceling"></a><a name="iscurrenttaskcollectioncanceling"></a>IsCurrentTaskCollectionCanceling 

 Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt.  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Planer an den aufrufenden Kontext angefügt wird und eine Aufgabengruppe Inline eine Aufgabe auf diesem Kontext ausgeführt wird, Angabe, ob diese Aufgabengruppe in einen Abbruch (oder in Kürze); andernfalls der Wert `false`.  
  
##  <a name="a-nameissynchronouslyblockeda-issynchronouslyblocked"></a><a name="issynchronouslyblocked"></a>IsSynchronouslyBlocked 

 Bestimmt, ob der Kontext synchron blockiert ist. Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob der Kontext synchron blockiert ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat. Auf dem Threadplaner würde dies einen direkten Aufruf der `Context::Block` Methode oder ein Synchronisierungsobjekt, das erstellt wurde, mit der `Context::Block` Methode.  
  
 Der Rückgabewert dieser Methode ist eine sofortige Beispiel gibt an, ob der Kontext synchron blockiert ist. Dieser Wert möglicherweise veraltete Moment sein, den er zurückgegeben wird, und kann nur unter bestimmten Umständen verwendet werden.  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>Delete-Operator 

 Ein `Context` -Objekt wird intern von der Laufzeit zerstört. Er kann nicht explizit gelöscht werden.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Parameter  
 `_PObject`  
 Ein Zeiger auf das Objekt gelöscht werden soll.  
  
##  <a name="a-nameoversubscribea-oversubscribe"></a><a name="oversubscribe"></a>Oversubscribe 

 Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Parameter  
 `_BeginOversubscription`  
 Wenn `true`, ein Hinweis, dass für die Dauer der Überzeichnung ein weiterer virtueller Prozessor hinzugefügt werden soll. Wenn `false`, ein Hinweis, dass die Überzeichnung beendet und der zuvor hinzugefügte virtuelle Prozessor entfernt werden soll.  
  
##  <a name="a-nameschedulegroupida-schedulegroupid"></a><a name="schedulegroupid"></a>ScheduleGroupId 

 Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer angefügt ist und für eine Planungsgruppe arbeiten, ein Bezeichner für den Planer gruppieren, wird der aktuelle Kontext ausgeführt wird. andernfalls der Wert `-1`.  
  
##  <a name="a-nameunblocka-unblock"></a><a name="unblock"></a>Blockierung aufheben 

 Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist durchaus zulässig, für einen Aufruf der `Unblock` -Methode vor einem entsprechenden Aufruf der [Block](#block) Methode. So lange als Aufrufe an die `Block` und `Unblock` Methoden ordnungsgemäß zugeordnet sind, die Common Language Runtime ordnungsgemäß behandelt die natürlichen Race entweder zu bestellen. Ein `Unblock` Aufruf, der vor einer `Block` Aufruf wird einfach die Auswirkung der `Block` aufrufen.  
  
 Es gibt mehrere Ausnahmen, die von dieser Methode ausgelöst werden können. Wenn ein Kontext versucht, rufen Sie die `Unblock` -Methode für sich selbst, einen [Context_self_unblock](context-self-unblock-class.md) Ausnahme ausgelöst. Wenn Aufrufe von `Block` und `Unblock` nicht ordnungsgemäß zugeordnet (z. B. zwei Aufrufe von `Unblock` erfolgen für einen Kontext, der derzeit ausgeführt wird), ein [Context_unblock_unbalanced](context-unblock-unbalanced-class.md) Ausnahme ausgelöst.  
  
 Beachten Sie, dass es ein kritischen Zeitraum zwischen dem Punkt, in dem Ihr Code seinen Kontext veröffentlicht, ein anderer Thread aufgerufen werden können, die `Unblock` Methode und dem Punkt, wo die Methode aufrufen, um `Block` erfolgt. Während dieses Zeitraums müssen Sie keine Methode aufrufen können wiederum blockieren und zulassen eigene Gründen (z. B. eine Sperre des Typs). Aufrufe von der `Block` und `Unblock` -Methode verfolgen den Grund für die Blockierung und das Aufheben der Sperre. Nur ein Objekt müssen den Besitz einer `Block` und `Unblock` Paar.  
  
##  <a name="a-namevirtualprocessorida-virtualprocessorid"></a><a name="virtualprocessorid"></a>VirtualProcessorId 

 Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der aktuelle Kontext an einen Planer ein Bezeichner für den virtuellen Prozessor verbunden ist, die den aktuelle Kontext ausgeführt wird; andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert dieser Methode ist ein einleuchtendes Beispiel für den virtuellen Prozessor, dem den aktuelle Kontext ausgeführt wird. Dieser Wert kann veraltete Moment werden zurückgegeben, und nicht zuverlässig. In der Regel wird diese Methode zum Debuggen oder für Nachverfolgungszwecke verwendet nur.  
  
##  <a name="a-nameyielda-yield"></a><a name="yield"></a>Rendite 

 Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
##  <a name="a-nameyieldexecutiona-yieldexecution"></a><a name="yieldexecution"></a>YieldExecution 

 Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann. Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Diese Funktion ist neu in [!INCLUDE[vs_dev14](../../../ide/includes/vs_dev14_md.md)] und identisch mit der [ergeben](#yield) funktionieren jedoch nicht zu Konflikten mit dem Yield-Makro in Windows.h dar.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




