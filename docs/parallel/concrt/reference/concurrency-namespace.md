---
title: "concurrency-Namespace"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency"
  - "agents/concurrency"
  - "concurrent_vector/concurrency"
  - "concrt/concurrency"
  - "internal_split_ordered_list/concurrency"
  - "concurrent_queue/concurrency"
  - "pplcancellation_token/concurrency"
  - "pplinterface/concurrency"
  - "ppltasks/concurrency"
  - "ppl/concurrency"
  - "concurrent_unordered_map/concurrency"
  - "concrtrm/concurrency"
  - "concurrent_unordered_set/concurrency"
  - "pplconcrt/concurrency"
  - "internal_concurrent_hash/concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency-Namespace"
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
caps.latest.revision: 37
caps.handback.revision: "37"
ms.author: "mblome"
manager: "ghogen"
---
# concurrency-Namespace
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Der `Concurrency`-Namespace stellt Klassen und Funktionen bereit, die Ihnen den Zugriff auf die Concurrency Runtime ermöglichen, ein Framework zur parallelen Programmierung für C++. Weitere Informationen finden Sie unter [Concurrency Runtime](../../../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace concurrency;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="namespaces"></a>Namespaces  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrency::Extensibility Namespace](assetId:///16a86ff2-128e-4edf-89e4-38aac79c81f9)||  
  
### <a name="typedefs"></a>TypeDefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`runtime_object_identity`|Jede Meldungsinstanz verfügt über eine Identität, die ihr beim Klonen folgt und die zwischen Messagingkomponenten übergeben wird. Dies kann nicht die Adresse des Meldungsobjekts sein.|  
|`task_status`|Ein Typ, der den abschließenden Zustand einer Aufgabe darstellt. Gültige Werte sind `completed` und `canceled`.|  
|`TaskProc`|Eine elementare Abstraktion für eine Aufgabe, die definiert ist als `void (__cdecl * TaskProc)(void *)`. Ein `TaskProc` wird aufgerufen, um den Text einer Aufgabe aufzurufen.|  
|`TaskProc_t`|Eine elementare Abstraktion für eine Aufgabe, die definiert ist als `void (__cdecl * TaskProc_t)(void *)`. Ein `TaskProc` wird aufgerufen, um den Text einer Aufgabe aufzurufen.|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Affinity_partitioner-Klasse](../../../parallel/concrt/reference/affinity-partitioner-class.md)|Die `affinity_partitioner`-Klasse ist der `static_partitioner`-Klasse ähnlich, allerdings wird die Cacheaffinität dank der Auswahl, den Arbeitsthreads Unterbereiche zuzuordnen, verbessert. Sie kann die Leistung, bei erneutem Ausführen einer Schleife über dem gleichen Dataset, und wenn die Daten im Cache gespeichert werden können, erheblich verbessern. Beachten Sie, dass das gleiche `affinity_partitioner`-Objekt mit nachfolgenden Iterationen einer parallelen Schleife verwendet werden muss, die für ein bestimmtes Dataset ausgeführt wird, um vom Datenort zu profitieren.|  
|[Agent-Klasse](../../../parallel/concrt/reference/agent-class.md)|Diese Klasse ist als Basisklasse für alle unabhängigen Agents vorgesehen. Sie wird verwendet, um den Zustand von anderen Agents auszublenden und mithilfe von Meldungsübergabe zu interagieren.|  
|[Auto_partitioner-Klasse](../../../parallel/concrt/reference/auto-partitioner-class.md)|Die `auto_partitioner`-Klasse stellt die Standardmethoden `parallel_for`, `parallel_for_each` und `parallel_transform` dar, die verwendet werden, um den Bereich zu partitionieren, den sie durchlaufen. Diese Partitionierungsmethode verwendet Bereichsstealing zum Lastenausgleich sowie Abbruch pro Durchlauf.|  
|[Bad_target-Klasse](../../../parallel/concrt/reference/bad-target-class.md)|Diese Klasse beschreibt eine Ausnahme, die dann ausgelöst wird, wenn einem Meldungsblock ein Zeiger auf ein Ziel zugeordnet wird, das für die auszuführende Operation ungültig ist.|  
|[Call-Klasse](../../../parallel/concrt/reference/call-class.md)|Ein `call`-Meldungsblock ist ein geordneter `target_block` mit mehreren Quellen, der eine bestimmte Funktion aufruft, wenn eine Nachricht empfangen wird.|  
|[Cancellation_token-Klasse](../../../parallel/concrt/reference/cancellation-token-class.md)|Mit der `cancellation_token`-Klasse kann bestimmt werden, ob für einen Vorgang ein Abbruch angefordert wurde. Dem angegebenen Token kann `task_group`, `structured_task_group` oder `task` zugeordnet werden, um einen impliziten Abbruch bereitzustellen. Es kann auch zum Abbruch abgerufen oder für einen Rückruf registriert werden, wenn das zugeordnete `cancellation_token_source`-Element abgebrochen wird.|  
|[Cancellation_token_registration-Klasse](../../../parallel/concrt/reference/cancellation-token-registration-class.md)|Die `cancellation_token_registration`-Klasse stellt eine Rückrufbenachrichtigung von `cancellation_token` dar. Bei Verwendung der `register`-Methode auf `cancellation_token` zum Empfangen von Benachrichtigungen darüber, wann ein Abbruch auftritt, wird ein `cancellation_token_registration`-Objekt als Handle an den Rückruf zurückgegeben, damit der Aufrufer mithilfe der `deregister`-Methode anfordern kann, dass ein bestimmter Rückruf nicht mehr erfolgt.|  
|[Cancellation_token_source-Klasse](../../../parallel/concrt/reference/cancellation-token-source-class.md)|Mit der `cancellation_token_source` -Klasse kann ein abbrechbarer Vorgang abgebrochen werden.|  
|[Choice-Klasse](../../../parallel/concrt/reference/choice-class.md)|Ein `choice`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der eine Kontrollflussinteraktion zwischen mehreren Quellen darstellt. Der Auswahlblock wartet, bis eine von mehreren Quellen eine Meldung erzeugt, und gibt den Index der Quelle, von der die Meldung erzeugt wurde, weiter.|  
|[combinable-Klasse](../../../parallel/concrt/reference/combinable-class.md)|Das `combinable<T>`-Objekt ist dazu gedacht, threadprivate Kopien von Daten bereitzustellen, mit denen sperrenfreie, threadlokale Unterberechnungen in parallelen Algorithmen durchgeführt werden können. Am Ende des Parallelvorgangs können die threadprivaten Unterbrechungen in einem Endergebnis zusammengeführt werden. Diese Klasse kann anstelle einer freigegebenen Variable verwendet werden, und sie kann zu einer Leistungsverbesserung führen, wenn andernfalls Konflikte mit dieser freigegebenen Variable entstehen würden.|  
|[Concurrent_priority_queue-Klasse](../../../parallel/concrt/reference/concurrent-priority-queue-class.md)|Die `concurrent_priority_queue`-Klasse ist ein Container, der es mehreren Threads gleichzeitig ermöglicht, für Elemente die Vorgänge "push" und "pop" auszuführen. Elemente werden in Reihenfolge ihrer Priorität per pop ausgelesen, wenn die Priorität mit einem als Vorlagenargument angegebenen Funktionselement bestimmt wird.|  
|[Concurrent_queue-Klasse](../../../parallel/concrt/reference/concurrent-queue-class.md)|Die `concurrent_queue`-Klasse ist eine Sequenzcontainerklasse, die "First In, First Out"-Zugriff auf ihre Elemente zulässt. Sie aktiviert einen beschränkten Satz von parallelitätssicheren Vorgängen, z. B. `push` und `try_pop`.|  
|[Concurrent_unordered_map-Klasse](../../../parallel/concrt/reference/concurrent-unordered-map-class.md)|Die `concurrent_unordered_map`- Klasse ist ein parallelitätssicherer Container, mit dem eine Folge von Elementen variierender Länge des Typs `std::pair<const K, _Element_type>` gesteuert wird. Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.|  
|[Concurrent_unordered_multimap-Klasse](../../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)|Die `concurrent_unordered_multimap`- Klasse ist ein parallelitätssicherer Container, mit dem eine Folge von Elementen variierender Länge des Typs `std::pair<const K, _Element_type>` steuert. Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.|  
|[Concurrent_unordered_multiset-Klasse](../../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)|Die `concurrent_unordered_multiset` Klasse ist ein parallelitätssicherer Container, der steuert, eine Elementsequenz variabler Länge Sequenz von Elementen des Typs K. Die Sequenz wird so dargestellt, mit denen ermöglicht für anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind.|  
|[Concurrent_unordered_set-Klasse](../../../parallel/concrt/reference/concurrent-unordered-set-class.md)|Die `concurrent_unordered_set` Klasse ist ein parallelitätssicherer Container, der steuert, eine Elementsequenz variabler Länge Sequenz von Elementen des Typs K. Die Sequenz wird so dargestellt, mit denen ermöglicht für anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind.|  
|[Concurrent_vector-Klasse](../../../parallel/concrt/reference/concurrent-vector-class.md)|Die `concurrent_vector`-Klasse ist eine Sequenzcontainerklasse, die zufälligen Zugriff auf jedes Element zulässt. Sie aktiviert parallelitätssichere Operationen für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchlauf.|  
|[Context-Klasse](../../../parallel/concrt/reference/context-class.md)|Stellt eine Abstraktion für einen Ausführungskontext dar.|  
|[Context_self_unblock-Klasse](../../../parallel/concrt/reference/context-self-unblock-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Unblock`-Methode für ein `Context`-Objekt aufgerufen wird, das im gleichen Kontext aufgerufen wird. Das würde den Versuch eines angegebenen Kontexts zum Aufheben der eigenen Blockierung angeben.|  
|[Context_unblock_unbalanced-Klasse](../../../parallel/concrt/reference/context-unblock-unbalanced-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.|  
|[Critical_section-Klasse](../../../parallel/concrt/reference/critical-section-class.md)|Ein nicht wieder eintretender Mutex, der explizit die Concurrency Runtime beachtet.|  
|[CurrentScheduler-Klasse](../../../parallel/concrt/reference/currentscheduler-class.md)|Stellt eine Abstraktion für den aktuellen Planer dar, der dem aufrufenden Kontext zugeordnet ist.|  
|[Default_scheduler_exists-Klasse](../../../parallel/concrt/reference/default-scheduler-exists-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, sobald die `Scheduler::SetDefaultSchedulerPolicy`-Methode aufgerufen wird, sofern ein Standardplaner bereits innerhalb des Prozesses vorhanden ist.|  
|[Event-Klasse](../../../parallel/concrt/reference/event-class.md)|Ein Ereignis für manuelles Zurücksetzen, das explizit die Concurrency Runtime beachtet.|  
|[Improper_lock-Klasse](../../../parallel/concrt/reference/improper-lock-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.|  
|[Improper_scheduler_attach-Klasse](../../../parallel/concrt/reference/improper-scheduler-attach-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Attach`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das bereits an den aktuellen Kontext angefügt wurde.|  
|[Improper_scheduler_detach-Klasse](../../../parallel/concrt/reference/improper-scheduler-detach-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `CurrentScheduler::Detach`-Methode für einen Kontext aufgerufen wird, der nicht mittels der `Attach`-Methode eines `Scheduler`-Objekts an einen Planer angefügt wurde.|  
|[Improper_scheduler_reference-Klasse](../../../parallel/concrt/reference/improper-scheduler-reference-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Reference`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das aus einem Kontext heruntergefahren wird, der nicht Teil dieses Planers ist.|  
|[Invalid_link_target-Klasse](../../../parallel/concrt/reference/invalid-link-target-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `link_target`-Methode eines Meldungsblocks aufgerufen wird und der Meldungsblock keine Verknüpfung mit dem Ziel erstellen kann. Dies kann das Ergebnis vom Überschreiten der Anzahl zulässiger Links für den Meldungsblock sein oder das Ergebnis von Versuchen, ein bestimmtes Ziel zweimal mit der gleichen Quelle zu verknüpfen.|  
|[Invalid_multiple_scheduling-Klasse](../../../parallel/concrt/reference/invalid-multiple-scheduling-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein `task_handle`-Objekt mehrmals mittels der `run`-Methode eines `task_group`-Objekts oder `structured_task_group`-Objekts ohne einen zwischenzeitlichen Aufruf der `wait`-Methode oder `run_and_wait`-Methode geplant wird.|  
|[Invalid_operation-Klasse](../../../parallel/concrt/reference/invalid-operation-class.md)|Diese Klasse beschreibt eine Ausnahme, die bei Ausführen einer ungültigen Operation ausgelöst wird, die nicht genauer von einem anderen von der Concurrency Runtime ausgelösten Ausnahmetyp beschrieben wird.|  
|[Invalid_oversubscribe_operation-Klasse](../../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Context::Oversubscribe`-Methode mit dem auf `_BeginOversubscription` festgelegten `false`-Parameter ohne einen vorherigen Aufruf der `Context::Oversubscribe`-Methode mit dem auf `_BeginOversubscription` festgelegten `true`-Parameter aufgerufen wird.|  
|[Invalid_scheduler_policy_key-Klasse](../../../parallel/concrt/reference/invalid-scheduler-policy-key-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein ungültiger oder unbekannter Schlüssel an einen `SchedulerPolicy`-Objektkonstruktor übergeben wird, oder wenn der `SetPolicyValue`-Methode eines `SchedulerPolicy`-Objekts ein Schlüssel übergeben wird, der auf andere Weise geändert werden muss, z. B. die `SetConcurrencyLimits`-Methode.|  
|[Invalid_scheduler_policy_thread_specification-Klasse](../../../parallel/concrt/reference/invalid-scheduler-policy-thread-specification-class.md)|Diese Klasse beschreibt eine Ausnahme, die bei dem Versuch ausgelöst wird, die Parallelitätsgrenzen eines `SchedulerPolicy`-Objekts so festzulegen, dass der Wert des `MinConcurrency`-Schlüssels kleiner ist, als der Wert des `MaxConcurrency`-Schlüssels.|  
|[Invalid_scheduler_policy_value-Klasse](../../../parallel/concrt/reference/invalid-scheduler-policy-value-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn der Richtlinienschlüssel eines `SchedulerPolicy`-Objekts auf einen ungültigen Wert für diesen Schlüssel festgelegt wird.|  
|[ISource-Klasse](../../../parallel/concrt/reference/isource-class.md)|Die `ISource`-Klasse ist die Schnittstelle für alle Quellblöcke. Quellblöcke geben Meldungen an `ITarget`-Blöcke weiter.|  
|[ITarget-Klasse](../../../parallel/concrt/reference/itarget-class.md)|Die `ITarget`-Klasse ist die Schnittstelle für alle Zielblöcke. Zielblöcke nehmen Meldungen auf, die von `ISource`-Blöcken angeboten werden.|  
|[Join-Klasse](../../../parallel/concrt/reference/join-class.md)|Ein `join`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Quellen und einem einzelnen Ziel, der Meldungen vom Typ `T` aus allen Quellen kombiniert.|  
|[Location-Klasse](../../../parallel/concrt/reference/location-class.md)|Die Abstraktion eines physischen Speicherorts auf der Hardware.|  
|[Message-Klasse](../../../parallel/concrt/reference/message-class.md)|Der grundlegende Nachrichtenumschlag, der die zwischen den Meldungsblöcken übergebene Datennutzlast enthält.|  
|[Message_not_found-Klasse](../../../parallel/concrt/reference/message-not-found-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein Meldungsblock keine angeforderte Meldung finden kann.|  
|[Message_processor-Klasse](../../../parallel/concrt/reference/message-processor-class.md)|Die `message_processor`-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`-Objekten. Für die Reihenfolge der Meldungen besteht keine Garantie.|  
|[Missing_wait-Klasse](../../../parallel/concrt/reference/missing-wait-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn es Aufgaben gibt, die noch für ein `task_group`-Objekt oder `structured_task_group`-Objekt geplant sind, während der Destruktor des Objekts ausgeführt wird. Diese Ausnahme wird nie ausgelöst, wenn der Destruktor aufgrund einer Stapelentladung als Ergebnis einer Ausnahme erreicht wird.|  
|[Multi_link_registry-Klasse](../../../parallel/concrt/reference/multi-link-registry-class.md)|Das `multi_link_registry`-Objekt ist eine `network_link_registry`, die mehrere Quellblöcke oder mehrere Zielblöcke verwaltet.|  
|[Multitype_join-Klasse](../../../parallel/concrt/reference/multitype-join-class.md)|Ein `multitype_join`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der Meldungen verschiedener Typen aus allen Quellen kombiniert und dem Ziel ein Tupel der kombinierten Meldungen bereitstellt.|  
|[Nested_scheduler_missing_detach-Klasse](../../../parallel/concrt/reference/nested-scheduler-missing-detach-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`-Methode für einen Kontext aufzurufen, der mittels der `Attach`-Methode des `Scheduler`-Objekts an einen zweiten Planer angefügt wurde.|  
|[Network_link_registry-Klasse](../../../parallel/concrt/reference/network-link-registry-class.md)|Die abstrakte `network_link_registry`-Basisklasse verwaltet die Verknüpfung zwischen Quell- und Zielblöcken.|  
|[Operation_timed_out-Klasse](../../../parallel/concrt/reference/operation-timed-out-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn das Timeout einer Operation erreicht wurde.|  
|[Ordered_message_processor-Klasse](../../../parallel/concrt/reference/ordered-message-processor-class.md)|Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.|  
|[Overwrite_buffer-Klasse](../../../parallel/concrt/reference/overwrite-buffer-class.md)|Ein `overwrite_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der jeweils eine einzelne Meldung speichern kann. Neue Meldungen überschreiben zuvor Gespeicherte.|  
|[Progress_reporter-Klasse](../../../parallel/concrt/reference/progress-reporter-class.md)|Die Status-Reporter-Klasse ermöglicht Benachrichtigungen zum Status der Berichterstellung eines bestimmten Typs. Jedes progress_reporter-Objekt ist an eine bestimmte asynchrone Aktion bzw. einen Vorgang gebunden.|  
|[Propagator_block-Klasse](../../../parallel/concrt/reference/propagator-block-class.md)|Die `propagator_block`-Klasse ist eine abstrakte Basisklasse für Meldungsblöcke, die sowohl Quelle als auch Ziel sind. Kombiniert die Funktion der `source_block`-Klasse mit der Funktion der `target_block`-Klasse.|  
|[Reader_writer_lock-Klasse](../../../parallel/concrt/reference/reader-writer-lock-class.md)|Eine im Writer festgelegte, warteschlangenbasierte Lese-/Schreibsperre mit ausschließlich lokalem Spinning. Die Sperre gewährt "First In, First Out"-Zugriff (FIFO-Zugriff) auf Writer und blockiert Reader unter einer fortlaufenden Last von Writern.|  
|[ScheduleGroup-Klasse](../../../parallel/concrt/reference/schedulegroup-class.md)|Stellt die Abstraktion für eine Planungsgruppe dar. In Planungsgruppen werden Sätze verwandter Arbeitsaufgaben organisiert, die von einer gemeinsamen Planung profitieren. Die kann entweder zeitlich durch das Ausführen einer anderen Aufgabe in der gleichen Gruppe vor dem Wechsel in eine andere Gruppe, oder räumlich durch das Ausführen mehrerer Elemente innerhalb der gleichen Gruppe auf dem gleichen NUMA-Knoten oder physischem Socket geschehen.|  
|[Scheduler-Klasse](../../../parallel/concrt/reference/scheduler-class.md)|Stellt eine Abstraktion für einen Concurrency Runtime-Planer dar.|  
|[Scheduler_not_attached-Klasse](../../../parallel/concrt/reference/scheduler-not-attached-class.md)|Diese Klasse beschreibt eine Ausnahme, die bei Ausführen eines Vorgangs ausgelöst wird, der erfordert, dass ein Planer an den aktuellen Kontext angefügt wird, und einer nicht.|  
|[Scheduler_resource_allocation_error-Klasse](../../../parallel/concrt/reference/scheduler-resource-allocation-error-class.md)|Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.|  
|[Scheduler_worker_creation_error-Klasse](../../../parallel/concrt/reference/scheduler-worker-creation-error-class.md)|Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers bei der Erstellung eines Workerausführungskontexts in der Concurrency Runtime ausgelöst wird.|  
|[SchedulerPolicy-Klasse](../../../parallel/concrt/reference/schedulerpolicy-class.md)|Die `SchedulerPolicy`-Klasse enthält einen Satz von Schlüssel-Wert-Paaren. Einen für jedes Richtlinienelement, von dem das Verhalten einer Planerinstanz gesteuert wird.|  
|[Simple_partitioner-Klasse](../../../parallel/concrt/reference/simple-partitioner-class.md)|Die `simple_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.|  
|[Single_assignment-Klasse](../../../parallel/concrt/reference/single-assignment-class.md)|Ein `single_assignment`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine einzelne, einmal beschreibbare `message` speichern kann.|  
|[Single_link_registry-Klasse](../../../parallel/concrt/reference/single-link-registry-class.md)|Das `single_link_registry`-Objekt ist eine `network_link_registry`, die nur eine einzige Quelle oder einen einzigen Zielblock verwaltet.|  
|[Source_block-Klasse](../../../parallel/concrt/reference/source-block-class.md)|Die `source_block`-Klasse ist eine abstrakte Basisklasse ausschließlich für Quellblöcke. Die Klasse stellt grundlegende Linkmanagementfunktionalität sowie allgemeine Fehlerüberprüfungen bereit.|  
|[Source_link_manager-Klasse](../../../parallel/concrt/reference/source-link-manager-class.md)|Das `source_link_manager`-Objekt verwaltet Meldungsblock-Netzwerklinks zu `ISource`-Blöcken.|  
|[Static_partitioner-Klasse](../../../parallel/concrt/reference/static-partitioner-class.md)|Die `static_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in so viele Blöcke unterteilt, wie Worker für den zugrunde liegenden Planer verfügbar sind.|  
|[Structured_task_group-Klasse](../../../parallel/concrt/reference/structured-task-group-class.md)|Die `structured_task_group`-Klasse stellt eine stark strukturierte Auflistung paralleler Arbeit dar. Sie können einzelne parallele Aufgaben mithilfe von `structured_task_group`-Objekten in eine `task_handle` stellen und warten, bis sie abgeschlossen werden, oder Sie können die Aufgabengruppe abbrechen, bevor deren Ausführung beendet wird, wodurch auch alle Aufgaben abgebrochen werden, deren Ausführung nicht gestartet wurde.|  
|[Target_block-Klasse](../../../parallel/concrt/reference/target-block-class.md)|Die `target_block`-Klasse ist eine abstrakte Basisklasse, mit der grundlegende Linkmanagementfunktionalität und Fehlerüberprüfung für Nur-Ziel-Blöcke bereitgestellt werden.|  
|[Aufgabenklasse (Concurrency Runtime)](../../../parallel/concrt/reference/task-class-concurrency-runtime.md)|Die Parallel Patterns Library (PPL) `task`-Klasse. Ein `task`-Objekt stellt Arbeit dar, die asynchron und übereinstimmend mit anderen Tasks und paralleler Arbeit , die von parallelen Algorithmen in der Concurrency Runtime erzeugt wird, ausgeführt werden kann. Es enthält bei erfolgreichem Abschluss ein Ergebnis vom Typ `_ResultType`. Tasks des Typs `task<void>` führen zu keinem Ergebnis. Ein Task kann erwartet und unabhängig von anderen Tasks abgebrochen werden. Er kann mit anderen Tasks mithilfe von Continuations (`then`) sowie Join-Muster (`when_all`) und Choise-Muster (`when_any`) erstellt werden.|  
|[Task_canceled-Klasse](../../../parallel/concrt/reference/task-canceled-class.md)|Diese Klasse beschreibt eine Ausnahme, die von den PPL-Aufgaben ausgelöst wird, um das Abbrechen der aktuellen Aufgabe zu erzwingen. Es wird auch ausgelöst, durch die `get()` Methode auf [Aufgabe](assetId:///5389e8a5-5038-40b6-844a-55e9b58ad35f), für eine abgebrochene Aufgabe.|  
|[Task_completion_event-Klasse](../../../parallel/concrt/reference/task-completion-event-class.md)|Mit der `task_completion_event`-Klasse können Sie die Ausführung einer Aufgabe verzögern, bis eine Bedingung erfüllt ist, oder eine Aufgabe als Reaktion auf ein externes Ereignis starten.|  
|[Task_continuation_context-Klasse](../../../parallel/concrt/reference/task-continuation-context-class.md)|Mit der `task_continuation_context`-Klasse können Sie angeben, an welcher Stelle eine Fortsetzung ausgeführt werden soll. Es ist nur sinnvoll, diese Klasse von einer Windows Store-App aus zu verwenden. Bei Apps, die keine Windows Store-Apps sind, wird der Ausführungskontext der Aufgabenfortsetzung von der Laufzeit bestimmt, und kann nicht konfiguriert werden.|  
|[Task_group-Klasse](../Topic/task_group%20Class.md)|Die `task_group`-Klasse stellt eine Auflistung der parallelen Arbeit dar, auf die gewartet oder die abgebrochen werden kann.|  
|[Task_handle-Klasse](../../../parallel/concrt/reference/task-handle-class.md)|Die `task_handle`-Klasse stellt eine einzelne parallele Arbeitsaufgabe dar. Sie kapselt die Anweisungen und die zum Ausführen eines Teils der Arbeit erforderlichen Daten.|  
|[Task_options-Klasse (Concurrency Runtime)](../../../parallel/concrt/reference/task-options-class-concurrency-runtime.md)|Stellt die zulässigen Optionen zum Erstellen einer Aufgabe dar|  
|[Timer-Klasse](../../../parallel/concrt/reference/timer-class.md)|Ein `timer`-Meldungsblock ist ein `source_block` mit einem einzelnen Ziel, der nach Ablauf einer bestimmten Zeitspanne oder in bestimmten Intervallen eine Meldung an sein Ziel senden kann.|  
|[Transformer-Klasse](../../../parallel/concrt/reference/transformer-class.md)|Ein `transformer`-Meldungsblock ist ein geordneter `propagator_block` mit einem einzelnen Ziel und mehreren Quellen, der Meldungen eines Typs akzeptieren und eine unbegrenzte Anzahl von Meldungen eines anderen Typs speichern kann.|  
|[Unbounded_buffer-Klasse](../Topic/unbounded_buffer%20Class.md)|Ein `unbounded_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine unbegrenzte Anzahl von Meldungen speichern kann.|  
|[Unsupported_os-Klasse](../../../parallel/concrt/reference/unsupported-os-class.md)|Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein nicht unterstütztes Betriebssystem verwendet wird.|  
  
### <a name="structures"></a>Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState-Struktur](../../../parallel/concrt/reference/dispatchstate-structure.md)|Die `DispatchState`-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`-Methode verwendet. Sie beschreibt die Umstände, unter denen die `Dispatch`-Methode für eine `IExecutionContext`-Schnittstelle aufgerufen wird.|  
|[IExecutionContext-Struktur](../../../parallel/concrt/reference/iexecutioncontext-structure.md)|Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.|  
|[IExecutionResource-Struktur](../../../parallel/concrt/reference/iexecutionresource-structure.md)|Eine Abstraktion für einen Hardwarethread.|  
|[IResourceManager-Struktur](../../../parallel/concrt/reference/iresourcemanager-structure.md)|Eine Schnittstelle zum Ressourcen-Manager der Concurrency Runtime. Dies ist die Schnittstelle, über die Planer mit dem Ressourcen-Manager kommunizieren.|  
|[IScheduler-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)|Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners. Der Ressourcen-Manager der Concurrency Runtime kommuniziert mithilfe dieser Schnittstelle mit Arbeitsplanern.|  
|[ISchedulerProxy-Struktur](../../../parallel/concrt/reference/ischedulerproxy-structure.md)|Die Schnittstelle, über die Planer mit dem Ressourcen-Manager der Concurrency Runtime kommunizieren, um die Ressourcenzuordnung auszuhandeln.|  
|[IThreadProxy-Struktur](../../../parallel/concrt/reference/ithreadproxy-structure.md)|Eine Abstraktion für einen Thread der Ausführung. Abhängig von dem von Ihnen erstellten `SchedulerType`-Richtlinienschlüssel des Planers, gewährt der Ressourcen-Manager eine Threadproxy, der entweder von einem regulären Win32-Thread oder einem im Benutzermodus planbaren (UMS) Thread unterstützt wird. UMS-Threads werden auf 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.|  
|[ITopologyExecutionResource-Struktur](../../../parallel/concrt/reference/itopologyexecutionresource-structure.md)|Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.|  
|[ITopologyNode-Struktur](../../../parallel/concrt/reference/itopologynode-structure.md)|Eine Schnittstelle für einen vom Ressourcen-Manager definierten Topologieknoten. Ein Knoten enthält mindestens eine Ausführungsressource.|  
|[IUMSCompletionList-Struktur](../../../parallel/concrt/reference/iumscompletionlist-structure.md)|Stellt eine UMS-Vervollständigungsliste dar. Wenn ein UMS-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist. Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann. Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.|  
|[IUMSScheduler-Struktur](../../../parallel/concrt/reference/iumsscheduler-structure.md)|Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen-Manager der Concurrency Runtime im Benutzermodus erwartet. Der Ressourcen-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS-Threadplanern. Die `IUMSScheduler`-Schnittstelle erbt von der `IScheduler`-Schnittstelle.|  
|[IUMSThreadProxy-Struktur](../../../parallel/concrt/reference/iumsthreadproxy-structure.md)|Eine Abstraktion für einen Thread der Ausführung. Wenn dem Planer im Benutzermodus planbare (UMS) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`-Schnittstelle. UMS-Threads werden nur unter 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.|  
|[IUMSUnblockNotification-Struktur](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)|Stellt eine Benachrichtigung vom Ressourcen-Manager darüber dar, dass ein Threadproxy, der blockiert und eine Rückkehr zum festgelegten Planungskontext des Planers ausgelöst hatte, die Blockierung aufgehoben hat und zum Planen bereit ist. Diese Schnittstelle ist ungültig, sobald der zugeordnete Ausführungskontext des Threadproxys, der von der `GetContext`-Methode zurückgegeben wurde, neu geplant wird.|  
|[IVirtualProcessorRoot-Struktur](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)|Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.|  
|[Scheduler_interface-Struktur](../../../parallel/concrt/reference/scheduler-interface-structure.md)|Planerschnittstelle|  
|[Scheduler_ptr-Struktur (Concurrency Runtime)](../../../parallel/concrt/reference/scheduler-ptr-structure-concurrency-runtime.md)|Stellt einen Zeiger auf einen Planer dar. Diese Klasse ist vorhanden, um die Spezifikation einer freigegebenen Lebensdauer mithilfe von "shared_ptr" oder nur eines einfachen Verweises und eines unformatierten Zeigers zu ermöglichen.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Agent_status-Enumeration](../Topic/agent_status%20Enumeration.md)|Die gültigen Zustände für einen `agent`.|  
|[Agents_EventType-Enumeration](../Topic/Agents_EventType%20Enumeration.md)|Die Typen von Ereignissen, die mit der von der Agents Library angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können|  
|[ConcRT_EventType-Enumeration](../Topic/ConcRT_EventType%20Enumeration.md)|Die Typen von Ereignissen, die mit der von der Concurrency Runtime angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können.|  
|[Concrt_TraceFlags-Enumeration](../Topic/Concrt_TraceFlags%20Enumeration.md)|Ablaufverfolgungskennzeichen für die Ereignistypen|  
|[CriticalRegionType-Enumeration](../Topic/CriticalRegionType%20Enumeration.md)|Der Typ eines kritischen Bereichs, in dem sich ein Kontext befindet.|  
|[DynamicProgressFeedbackType-Enumeration](../Topic/DynamicProgressFeedbackType%20Enumeration.md)|Wird von der `DynamicProgressFeedback`-Richtlinie verwendet, um zu beschreiben, ob Ressourcen für den Planer anhand statistischer Informationen neu verteilt werden, die vom Planer oder nur auf Grundlage virtueller Prozessoren erfasst wurden, die wegen der Aufrufe der `Activate`-Methode und der `Deactivate`-Methode für die `IVirtualProcessorRoot`-Schnittstelle in den und aus dem Leerlauf wechseln. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](../Topic/PolicyElementKey%20Enumeration.md).|  
|[Join_type-Enumeration](../Topic/join_type%20Enumeration.md)|Der Typ eines `join`-Meldungsblocks.|  
|[Message_status-Enumeration](../Topic/message_status%20Enumeration.md)|Die gültigen Antworten für das Angebot eines `message`-Objekts für einen Block.|  
|[PolicyElementKey-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)|Richtlinienschlüssel, die Aspekte des Planerverhaltens beschreiben. Jedes Richtlinienelement wird mit einem Schlüssel-Wert-Paar beschrieben. Weitere Informationen zu Planerrichtlinien und deren Auswirkungen auf Planer finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|  
|[SchedulerType-Enumeration](../Topic/SchedulerType%20Enumeration.md)|Wird von der `SchedulerKind`-Richtlinie verwendet, um den Typ der Threads zu beschreiben, die der Planer für zugrunde liegende Ausführungskontexte verwenden soll. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](../Topic/PolicyElementKey%20Enumeration.md).|  
|[SchedulingProtocolType-Enumeration](../Topic/SchedulingProtocolType%20Enumeration.md)|Wird von der `SchedulingProtocol`-Richtlinie verwendet, um zu beschreiben, welcher Planungsalgorithmus für den Planer verwendet wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](../Topic/PolicyElementKey%20Enumeration.md).|  
|[SwitchingProxyState-Enumeration](../Topic/SwitchingProxyState%20Enumeration.md)|Wird verwendet, um den Zustand zu bezeichnen, in dem sich ein Threadproxy befindet, wenn er einen kooperativen Kontextwechsel zu einem anderen Threadproxy ausführt.|  
|[Task_group_status-Enumeration](../Topic/task_group_status%20Enumeration.md)|Beschreibt den Ausführungsstatus eines `task_group`-Objekts oder eines `structured_task_group`-Objekts. Ein Wert dieses Typs wird von zahlreichen Methoden zurückgegeben, die auf den Abschluss von Aufgaben warten, die für eine Aufgabengruppe geplant wurden.|  
|[WinRTInitializationType-Enumeration](../Topic/WinRTInitializationType%20Enumeration.md)|Wird von der `WinRTInitialization`-Richtlinie verwendet, um zu beschreiben, ob und wie die Windows Runtime auf Planerthreads für eine Anwendung initialisiert wird, die auf Windows-Betriebssystemen ab Version 8 ausgeführt wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](../Topic/PolicyElementKey%20Enumeration.md).|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Alloc-Funktion](../Topic/Alloc%20Function.md)|Reserviert einen Speicherblock mit der in der Unterbelegungsfunktion für die Zwischenspeicherung der Concurrency Runtime angegebenen Größe.|  
|[Asend-Funktion](../Topic/asend%20Function.md)|Überladen. Ein asynchroner Sendevorgang, der eine Aufgabe zum Weitergeben der Daten an den Zielblock plant.|  
|[Cancel_current_task-Funktion](../Topic/cancel_current_task%20Function.md)|Bricht die gerade ausgeführte Aufgabe ab. Diese Funktion kann aus dem Text einer Aufgabe aufgerufen werden, um die Ausführung der Aufgabe abzubrechen und ihn dabei in den `canceled` Zustand übergehen zu lassen.<br /><br /> Der Aufruf dieser Funktion, wenn Sie sich nicht innerhalb des Texts von einem `task` befinden, ist kein unterstütztes Szenario. Dies würde zu nicht definiertem Verhalten, wie einem Absturz oder einem Hänger in der Anwendung, führen.|  
|[Create_async-Funktion](../Topic/create_async%20Function.md)|Erstellt ein asynchrones Konstrukt der Windows Runtime auf einem vom Benutzer angegebenes Lambda oder Funktionsobjekt. Der Rückgabetyp von `create_async` ist entweder `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` oder `IAsyncOperationWithProgress<TResult, TProgress>^` auf Grundlage der Signatur des Lambda-Ausdrucks, der an die Methode übergeben wurde.|  
|[Create_task-Funktion](../Topic/create_task%20Function.md)|Überladen. Erstellt ein PPL- [Aufgabe](assetId:///5389e8a5-5038-40b6-844a-55e9b58ad35f) Objekt. Das Element `create_task` kann überall dort verwendet werden, wo Sie einen Aufgabenkonstruktor verwendet hätten. Es wird hauptsächlich der Einfachheit halber bereitgestellt, da es beim Erstellen eines Tasks die Verwendung des `auto`-Schlüsselwort ermöglicht.|  
|[CreateResourceManager-Funktion](../Topic/CreateResourceManager%20Function.md)|Gibt eine Schnittstelle zurück, die die Singletoninstanz des Ressourcen-Managers der Concurrency Runtime darstellt. Der Ressourcen-Manager ist für das Zuweisen von Ressourcen für Planer, die miteinander kooperieren möchten, zuständig.|  
|[DisableTracing-Funktion](../Topic/DisableTracing%20Function.md)|Deaktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung standardmäßig aufgehoben wird.|  
|[EnableTracing-Funktion](../Topic/EnableTracing%20Function.md)|Aktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung jetzt standardmäßig erfolgt.|  
|[Free-Funktion](../Topic/Free%20Function.md)|Gibt einen Speicherblock frei, der zuvor mit der `Alloc`-Methode der Unterbelegungsfunktion für die Zwischenspeicherung der Concurrency Runtime reserviert wurde.|  
|[Get_ambient_scheduler-Funktion (Concurrency Runtime)](../Topic/get_ambient_scheduler%20Function%20\(Concurrency%20Runtime\).md)||  
|[GetExecutionContextId-Funktion](../Topic/GetExecutionContextId%20Function.md)|Gibt einen eindeutigen Bezeichner zurück, der einem Ausführungskontext zugewiesen werden kann, der die `IExecutionContext`-Schnittstelle implementiert.|  
|[GetOSVersion-Funktion](../Topic/GetOSVersion%20Function.md)|Gibt die Betriebssystemversion zurück.|  
|[GetProcessorCount-Funktion](../Topic/GetProcessorCount%20Function.md)|Gibt die Anzahl von Hardwarethreads des zugrunde liegenden Systems zurück.|  
|[GetProcessorNodeCount-Funktion](../Topic/GetProcessorNodeCount%20Function.md)|Gibt die Anzahl von NUMA-Knoten oder Prozessorpaketen des zugrunde liegenden Systems zurück.|  
|[GetSchedulerId-Funktion](../Topic/GetSchedulerId%20Function.md)|Gibt einen eindeutigen Bezeichner zurück, der einem Planer zugewiesen werden kann, der die `IScheduler`-Schnittstelle implementiert.|  
|[Interruption_point-Funktion](../Topic/interruption_point%20Function.md)|Erstellt einen Unterbrechungspunkt für den Abbruch. Wenn ein Abbruch im Kontext, in dem diese Funktion aufgerufen wird, ausgeführt wird, löst diese eine interne Ausnahme aus, mit der die Ausführung der aktuell ausgeführten parallelen Verarbeitung abgebrochen wird. Wenn kein Abbruch ausgeführt wird, bleibt die Funktion untätig.|  
|[Is_current_task_group_canceling-Funktion](../Topic/is_current_task_group_canceling%20Function.md)|Gibt zurück, ob die Aufgabengruppe, die gerade inline auf dem aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt. Beachten Sie, dass `false` zurückgegeben wird, wenn auf dem aktuellen Kontext zurzeit inline keine Aufgabengruppe ausgeführt wird.|  
|[Make_choice-Funktion](../Topic/make_choice%20Function.md)|Überladen. Erstellt einen `choice`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.|  
|[Make_greedy_join-Funktion](../Topic/make_greedy_join%20Function.md)|Überladen. Erstellt einen `greedy multitype_join`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.|  
|[Make_join-Funktion](../Topic/make_join%20Function.md)|Überladen. Erstellt einen `non_greedy multitype_join`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.|  
|[Make_task-Funktion](../Topic/make_task%20Function.md)|Eine Factorymethode zum Erstellen eines `task_handle`-Objekts.|  
|[Parallel_buffered_sort-Funktion](../Topic/parallel_buffered_sort%20Function.md)|Überladen. Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat parallel angegeben wird. Diese Funktion entspricht `std::sort` semantisch darin, dass sie eine vergleichsbasierte, instabile, direkte Sortierung ist, abgesehen von den zusätzlich erforderlichen `O(n)`-Leerzeichen und er notwendigen Standardinitialisierung für die sortierten Elemente.|  
|[Parallel_for-Funktion](../Topic/parallel_for%20Function.md)|Überladen. `parallel_for` durchläuft einen Bereich von Indizes und führt bei jeder Iteration parallel eine vom Benutzer bereitgestellte Funktion aus.|  
|[Parallel_for_each-Funktion](../Topic/parallel_for_each%20Function.md)|Überladen. `parallel_for_each` wendet eine angegebene Funktion parallel auf jedes Element innerhalb eines Bereichs an. Sie entspricht semantisch der `for_each`-Funktion im `std`-Namespace, außer dass die Iteration über die Elemente parallel ausgeführt wird und die Reihenfolge der Iteration nicht angegeben ist. Das Argument `_Func` muss einen Funktionsaufrufoperator in der Form `operator()(T)` unterstützen, wobei der Parameter `T` der Elementtyp des durchlaufenen Containers ist.|  
|[Parallel_invoke-Funktion](../Topic/parallel_invoke%20Function.md)|Überladen. Führt die als Parameter angegebenen Funktionsobjekte parallel aus, und blockiert, bis die Ausführung beendet ist. Jedes Funktionsobjekt kann ein Lambda-Ausdruck, ein Zeiger auf eine Funktion oder ein anderes Objekt sein, das den Funktionsaufrufoperator mit der Signatur `void operator()()` unterstützt.|  
|[Parallel_radixsort-Funktion](../Topic/parallel_radixsort%20Function.md)|Überladen. Ordnet Elemente in einem angegebenen Bereich mithilfe eines Basis-Sortieralgorithmus in einer absteigenden Reihenfolge an. Dies ist eine stabile Sortierfunktion, die eine Projektionsfunktion erfordert, mit der Elemente zur Sortierung in Schlüssel, die ganzen Zahlen ohne Vorzeichen ähneln, projiziert werden können. Standardinitialisierung ist für die zu sortierenden Elemente erforderlich.|  
|[Parallel_reduce-Funktion](../Topic/parallel_reduce%20Function.md)|Überladen. Berechnet die Summe aller Elemente in einem angegebenen Bereich, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die auf ähnliche Weise mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden parallel. `parallel_reduce` entspricht `std::accumulate` semantisch, außer dass der binäre Vorgang assoziativ sein muss und ein Identitätswert anstelle eines Anfangswerts erforderlich ist.|  
|[Parallel_sort-Funktion](../Topic/parallel_sort%20Function.md)|Überladen. Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat parallel angegeben wird. Diese Funktion entspricht `std::sort` semantisch insofern, dass sie eine vergleichsbasierte, instabile, direkte Sortierung ist.|  
|[Parallel_transform-Funktion](../Topic/parallel_transform%20Function.md)|Überladen. Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts parallel in einen Zielbereich. Diese Funktion entspricht semantisch `std::transform`.|  
|[Receive-Funktion](../Topic/receive%20Function.md)|Überladen. Eine allgemeine Empfangsimplementierung, mit der ein Kontext auf Daten von genau einer Quelle warten und die akzeptierten Werte filtern kann.|  
|[Run_with_cancellation_token-Funktion](../Topic/run_with_cancellation_token%20Function.md)|Führt sofort synchron ein Funktionsobjekt im Kontext eines angegebenen Abbruchtokens aus.|  
|[Send-Funktion](../Topic/send%20Function.md)|Überladen. Ein synchroner Sendevorgang, der wartet, bis das Ziel die Meldung akzeptiert oder ablehnt.|  
|[Set_ambient_scheduler-Funktion (Concurrency Runtime)](../Topic/set_ambient_scheduler%20Function%20\(Concurrency%20Runtime\).md)||  
|[Set_task_execution_resources-Funktion](../Topic/set_task_execution_resources%20Function.md)|Überladen. Schränkt die Ausführungsressourcen, die von den internen Arbeitsthreads der Concurrency Runtime verwendet werden, auf den angegebenen Affinitätssatz ein.<br /><br /> Es ist nur gültig, diese Methode vor Erstellung des Ressourcen-Managers oder zwischen der Lebensdauer zweier Ressourcen-Manager aufzurufen. Sie kann mehrmals aufgerufen werden, solange der Ressourcen-Manager zum Zeitpunkt des Aufrufs nicht vorhanden ist. Nachdem eine Affinitätsgrenze eingerichtet wurde, bleibt diese bis zum nächsten gültigen Aufruf der `set_task_execution_resources`-Methode bestehen.<br /><br /> Die bereitgestellte Affinitätsmaske muss keine Teilmenge der Prozessaffinitätsmaske sein. Die Prozessaffinität wird bei Bedarf aktualisiert.|  
|[Swap-Funktion](../Topic/swap%20Function.md)|Tauscht die Elemente zweier `concurrent_vector`-Objekte.|  
|[Task_from_exception-Funktion (Concurrency Runtime)](../Topic/task_from_exception%20Function%20\(Concurrency%20Runtime\).md)||  
|[Task_from_result-Funktion (Concurrency Runtime)](../Topic/task_from_result%20Function%20\(Concurrency%20Runtime\).md)||  
|[Trace_agents_register_name-Funktion](../Topic/Trace_agents_register_name%20Function.md)|Ordnet den angegebenen Namen dem Nachrichtenblock oder dem Agent in der ETW-Ablaufverfolgung zu.|  
|[Try_receive-Funktion](../Topic/try_receive%20Function.md)|Überladen. Eine allgemeine try-receive-Implementierung, mit der ein Kontext Daten von genau einer Quelle suchen und die akzeptierten Werte filtern kann. Wenn die Daten nicht bereit sind, gibt die Methode "false" zurück.|  
|[Wait-Funktion](../Topic/wait%20Function.md)|Hält den aktuellen Kontext für eine bestimmte Zeit an.|  
|[Funktion "when_all"](../Topic/when_all%20Function.md)|Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn alle als Argumente angegeben Aufgaben erfolgreich abgeschlossen werden.|  
|[Funktion "when_any"](../Topic/when_any%20Function.md)|Überladen. Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.|  
  
### <a name="operators"></a>Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator! =-Operator](../Topic/operator!=%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator ungleich dem `concurrent_vector`-Objekt rechts vom Operator ist.|  
|[Operator & &-Operator](../Topic/operator&&%20Operator.md)|Überladen. Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn beide als Argumente angegeben Aufgaben erfolgreich abgeschlossen werden.|  
|[Operator &#124; &#124; Operator](../Topic/operator%7C%7C%20Operator.md)|Überladen. Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.|  
|[Operator <-Operator](../Topic/operator%3C%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner als das `concurrent_vector`-Objekt auf der rechten Seite ist.|  
|[Operator < =-Operator](../Topic/operator%3C=%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.|  
|[Operator ==-Operator](../Topic/operator==%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator gleich dem `concurrent_vector`-Objekt rechts vom Operator ist.|  
|[Operator >-Operator](../Topic/operator%3E%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator größer als das `concurrent_vector`-Objekt auf der rechten Seite ist.|  
|[Operator > =-Operator](../Topic/operator%3E=%20Operator.md)|Testet, ob das `concurrent_vector`-Objekt links vom Operator größer oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.|  
  
### <a name="constants"></a>Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AgentEventGuid-Konstante](../Topic/AgentEventGuid%20Constant.md)|Ein Kategorie-GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07}), die von der Agents Library in der Concurrency Runtime ausgelöste ETW-Ereignisse beschreibt.|  
|[ChoreEventGuid-Konstante](../Topic/ChoreEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf Arbeiten oder Aufgaben beziehen.|  
|[ConcRT_ProviderGuid-Konstante](../Topic/ConcRT_ProviderGuid%20Constant.md)|Der ETW-Anbieter-GUID für die Concurrency Runtime.|  
|[CONCRT_RM_VERSION_1-Konstante](../Topic/CONCRT_RM_VERSION_1%20Constant.md)|Gibt die Unterstützung der in Visual Studio 2010 definierten Ressourcen-Manager-Schnittstelle an.|  
|[ConcRTEventGuid-Konstante](../Topic/ConcRTEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und nicht in eine der anderen Kategorien fallen.|  
|[ContextEventGuid-Konstante](../Topic/ContextEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf Kontexte beziehen.|  
|[COOPERATIVE_TIMEOUT_INFINITE-Konstante](../Topic/COOPERATIVE_TIMEOUT_INFINITE%20Constant.md)|Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.|  
|[COOPERATIVE_WAIT_TIMEOUT-Konstante](../Topic/COOPERATIVE_WAIT_TIMEOUT%20Constant.md)|Ein Wert, der angibt, dass ein Wartevorgang durch einen Timeout beendet wurde.|  
|[INHERIT_THREAD_PRIORITY-Konstante](../Topic/INHERIT_THREAD_PRIORITY%20Constant.md)|Ein besonderer Wert für den Richtlinienschlüssel `ContextPriority`, der angibt, dass die Threadpriorität aller Kontexte im Planer die gleiche wie die des Threads sein sollte, der den Planer erstellt hat.|  
|[LockEventGuid-Konstante](../Topic/LockEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf Sperren beziehen.|  
|[MaxExecutionResources-Konstante](../Topic/MaxExecutionResources%20Constant.md)|Ein besonderer Wert für die Richtlinienschlüssel `MinConcurrency` und `MaxConcurrency`. Wird, falls keine anderen Einschränkungen vorliegen, standardmäßig auf die Anzahl von Hardwarethreads auf dem Computer festgelegt.|  
|[PPLParallelForeachEventGuid-Konstante](../Topic/PPLParallelForeachEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf die Verwendung der `parallel_for_each`-Funktion beziehen.|  
|[PPLParallelForEventGuid-Konstante](../Topic/PPLParallelForEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf die Verwendung der `parallel_for`-Funktion beziehen.|  
|[PPLParallelInvokeEventGuid-Konstante](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf die Verwendung der `parallel_invoke`-Funktion beziehen.|  
|[ResourceManagerEventGuid-Konstante](../Topic/ResourceManagerEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf den Ressourcen-Manager beziehen.|  
|[ScheduleGroupEventGuid-Konstante](../Topic/ScheduleGroupEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf Planungsgruppen beziehen.|  
|[SchedulerEventGuid-Konstante](../Topic/SchedulerEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf Planeraktivitäten beziehen.|  
|[VirtualProcessorEventGuid-Konstante](../Topic/VirtualProcessorEventGuid%20Constant.md)|Ein Kategorie-GUID, die ETW-Ereignisse beschreibt, die von der Concurrency Runtime ausgelöst werden und sich direkt auf virtuelle Prozessoren beziehen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h, concrt.h hinzu, concrtrm.h, concurrent_priority_queue.h, concurrent_queue.h, concurrent_unordered_map.h, concurrent_unordered_set.h, concurrent_vector.h, internal_concurrent_hash.h, internal_split_ordered_list.h, ppl.h, pplcancellation_token.h, pplconcrt.h, pplinterface.h, "ppltasks.h"  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz](../../../parallel/concrt/reference/reference-concurrency-runtime.md)

