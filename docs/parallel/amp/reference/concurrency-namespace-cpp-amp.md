---
title: "Concurrency-Namespace (C++ AMP)"
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
  - "amp/Concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency-Namespace"
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency-Namespace (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt Klassen und Funktionen bereit, die die Ausführung von C++-Code auf datenparalleler Hardware beschleunigen. Weitere Informationen finden Sie unter [Übersicht über C++ AMP](../../../parallel/amp/cpp-amp-overview.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="namespaces"></a>Namespaces  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrency:: Direct3D-Namespace](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)|Stellt Funktionen bereit, welche die D3D-Interoperabilität unterstützen. Ermöglicht die einfache Verwendung von D3D-Ressourcen für Berechnungen in AMP-Code sowie die Verwendung von in AMP erstellten Ressourcen in D3D-Code, ohne dass redundante Zwischenkopien erstellt werden. Sie können C++ AMP verwenden, um die berechnungsintensiven Abschnitte Ihrer DirectX-Anwendungen inkrementell zu beschleunigen und die D3D-API für Daten nutzen, die aus AMP-Berechnungen resultieren.|  
|[Concurrency:: fast_math-Namespace](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)|Funktionen im `fast_math`-Namespace sind nicht C99-kompatibel. Für jede Funktion werden nur Versionen mit einfacher Genauigkeit bereitgestellt. Diese Funktionen verwenden die systeminternen DirectX-Funktionen, die schneller als die entsprechenden Funktionen im `precise_math`-Namespace sind und keine erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste benötigen. Sie sind jedoch weniger genau. Für jede Funktion gibt es zwei Versionen für Quellebenenkompatibilität mit Code C99. Beide Versionen akzeptieren und geben Werte mit einfacher Genauigkeit zurück.|  
|[Concurrency:: Graphics-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)|Stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.|  
|[Concurrency:: precise_math-Namespace](../../../parallel/amp/reference/concurrency-precise-math-namespace.md)|Funktionen im `precise_math`-Namespace sind C99-kompatibel. Für jede Funktion sind Versionen mit einfacher und doppelter Genauigkeit enthalten. Diese Funktionen, Funktionen mit einfacher Genauigkeit eingeschlossen, erfordern erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste.|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[zugriffstastenklasse](../../../parallel/amp/reference/accelerator-class.md)|Stellt eine Abstraktion eines physischen DP-optimierten Berechnungsknotens dar.|  
|[Accelerator_view-Klasse](../../../parallel/amp/reference/accelerator-view-class.md)|Stellt die Abstraktion eines virtuellen Geräts für einen datenparallelen C++ AMP-Beschleuniger dar.|  
|[Accelerator_view_removed-Klasse](../../../parallel/amp/reference/accelerator-view-removed-class.md)|Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX-Aufruf aufgrund des Windows-TDR-Mechanismus (Timeout Detection and Recovery) fehlschlägt.|  
|[Array-Klasse](../../../parallel/amp/reference/array-class.md)|Ein Datenaggregat auf einem `accelerator_view`-Objekt in der Rasterdomäne. Es ist eine Auflistung von Variablen, eine für jedes Element in einer "grid"-Domäne. Jede Variable enthält einen Wert, der einem C++-Typ entspricht.|  
|[Array_view-Klasse](../../../parallel/amp/reference/array-view-class.md)|Stellt eine Ansicht in die Daten in einem array\<T,N> dar.|  
|[Completion_future-Klasse](../../../parallel/amp/reference/completion-future-class.md)|Stellt ein "future"-Objekt dar, das einem asynchronen C++ AMP-Vorgang entspricht.|  
|[Extent-Klasse](../../../parallel/amp/reference/extent-class-cpp-amp.md)|Stellt einen Vektor von n ganzzahligen Werten dar, die die Grenzen eines n-dimensionalen Raums mit dem Ursprung 0 angeben. Die Werte im Koordinatenvektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert. Im kartesischen 3-dimensionalen Raum stellt der "extent"-Vektor (7,5,3) beispielsweise einen Raum dar, in dem die z-Koordinate im Bereich von 0 bis 7, die y-Koordinate im Bereich von 0 bis 5 und die x-Koordinate im Bereich von 0 bis 3 liegt.|  
|[Index-Klasse](../../../parallel/amp/reference/index-class.md)|Definiert einen n-dimensionalen Indexpunkt.|  
|[Invalid_compute_domain-Klasse](../../../parallel/amp/reference/invalid-compute-domain-class.md)|Die Ausnahme, die ausgelöst wird, wenn die Laufzeit einen Kernel nicht mithilfe der "compute"-Domäne starten kann, die auf der `parallel_for_each`-Aufrufsite angegeben wird.|  
|[Out_of_memory-Klasse](../../../parallel/amp/reference/out-of-memory-class.md)|Die Ausnahme, die ausgelöst wird, wenn eine Methode aufgrund unzureichenden System- oder Gerätearbeitsspeichers fehlschlägt.|  
|[Runtime_exception-Klasse](../../../parallel/amp/reference/runtime-exception-class.md)|Der Basistyp für Ausnahmen in der C++ AMP-Bibliothek.|  
|[Tile_barrier-Klasse](../../../parallel/amp/reference/tile-barrier-class.md)|Eine Funktionsklasse, die vom System nur erstellt werden kann und einem unterteilten `parallel_for_each`-Lambda als Teil des `tiled_index`-Parameters übergeben wird. Sie stellt eine einzige Methode, die Methode `wait()`, bereit, die dazu dient, die Ausführung von Threads zu synchronisieren, die in der Threadgruppe (Kachel) ausgeführt werden.|  
|[Tiled_extent-Klasse](../../../parallel/amp/reference/tiled-extent-class.md)|Ein `tiled_extent`-Objekt ist ein `extent`-Objekt einer bis drei Dimensionen, das den "extent"-Bereich in ein-, zwei- oder dreidimensionale Kacheln unterteilt.|  
|[Tiled_index-Klasse](../../../parallel/amp/reference/tiled-index-class.md)|Stellt einen Index für ein `tiled_grid`-Objekt bereit. Diese Klasse verfügt über Eigenschaften, über die auf ein Element relativ zum lokalen Kachelursprung und relativ zum globalen Ursprung zugegriffen werden kann.|  
|[Uninitialized_object-Klasse](../../../parallel/amp/reference/uninitialized-object-class.md)|Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.|  
|[Unsupported_feature-Klasse](../../../parallel/amp/reference/unsupported-feature-class.md)|Die Ausnahme, die ausgelöst wird, wenn eine nicht unterstützte Funktion verwendet wird.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Access_type-Enumeration](../Topic/access_type%20Enumeration.md)|Gibt den Datenzugriffstyp an.|  
|[Queuing_mode-Enumeration](../../../parallel/amp/reference/queuing-mode-enumeration.md)|Gibt die Modi für das Hinzufügen zur Warteschlange an, die auf dem Beschleuniger unterstützt werden.|  
  
### <a name="operators"></a>Operatoren  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[Operator ==-Operator (C++-AMP)](../Topic/operator==%20Operator%20\(C++%20AMP\).md)|Bestimmt, ob die angegebenen Datenstrukturen gleich sind.|  
|[Operator! =-Operator (C++-AMP)](../Topic/operator!=%20Operator%20\(C++%20AMP\).md)|Bestimmt, ob die angegebenen Datenstrukturen ungleich sind.|  
|[Operator +-Operator (C++-AMP)](../Topic/operator+%20Operator%20\(C++%20AMP\).md)|Berechnet die komponentenbezogene Summe der angegebenen Argumente.|  
|[Operator-Operator (C++-AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)1.md)|Berechnet die Differenz zwischen den angegebenen Argumenten pro Komponente.|  
|[Operator *-Operator (C++-AMP)](../Topic/operator*%20Operator%20\(C++%20AMP\).md)|Berechnet das komponentenbezogene Produkt der angegebenen Argumente.|  
|[Operator /-Operator (C++-AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)2.md)|Berechnet den komponentenbezogenen Quotienten der angegebenen Argumente.|  
|[Operator%-Operator (C++-AMP)](../Topic/operator%25%20Operator%20\(C++%20AMP\).md)|Berechnet den Modul des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[All_memory_fence-Funktion](../Topic/all_memory_fence%20Function.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind.|  
|[Amp_uninitialize-Funktion](../Topic/amp_uninitialize%20Function.md)|Hebt die Initialisierung der C++ AMP-Laufzeit auf.|  
|[Atomic_compare_exchange-Funktion](../Topic/atomic_compare_exchange%20Function.md)|Überladen. Wenn der Wert, der am angegebenen Speicherort abgelegt ist, mit dem ersten angegebenen Wert übereinstimmt, wird der zweite angegebene Wert als atomischen Vorgang an demselben Speicherort abgelegt.|  
|[Atomic_exchange-Funktion](../Topic/atomic_exchange%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf den angegebenen Wert fest.|  
|[Atomic_fetch_add-Funktion](../Topic/atomic_fetch_add%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf die Summe dieses Werts und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_and-Funktion](../Topic/atomic_fetch_and%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `and` dieses Werts und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_dec-Funktion](../Topic/atomic_fetch_dec%20Function.md)|Überladen. Dekrementiert den Wert, der am angegebenen Speicherort abgelegt ist, und speichert das Ergebnis als atomischen Vorgang an demselben Speicherort.|  
|[Atomic_fetch_inc-Funktion](../Topic/atomic_fetch_inc%20Function.md)|Überladen. Inkrementiert den Wert, der am angegebenen Speicherort abgelegt ist, und speichert das Ergebnis als atomischen Vorgang an demselben Speicherort.|  
|[Atomic_fetch_max-Funktion](../Topic/atomic_fetch_max%20Function.md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang größer als diesen Wert und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_min-Funktion](../Topic/atomic_fetch_min%20Function.md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang kleiner als diesen Wert und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_or-Funktion](../Topic/atomic_fetch_or%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `or` dieses Werts und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_sub-Funktion](../Topic/atomic_fetch_sub%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf die Differenz dieses Werts und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_xor-Funktion](../Topic/atomic_fetch_xor%20Function%20\(C++%20AMP\).md)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `xor` dieses Werts und auf einen angegebenen Wert fest.|  
|[Copy-Funktion](../Topic/copy%20Function.md)|Kopiert ein C++ AMP-Objekt. Alle Anforderungen der synchronen Datenübertragung werden erfüllt. Es können keine Daten kopiert werden, wenn auf einer Zugriffstaste Code ausgeführt wird. Das allgemeine Format dieser Funktion ist `copy(src, dest)`.|  
|[Copy_async-Funktion](../Topic/copy_async%20Function.md)|Kopiert ein C++ AMP-Objekt und gibt [Completion_future](../../../parallel/amp/reference/completion-future-class.md) können auf das gewartet werden. Es können keine Daten kopiert werden, wenn auf einer Zugriffstaste Code ausgeführt wird. Das allgemeine Format dieser Funktion ist `copy(src, dest)`.|  
|[direct3d_abort-Funktion](../Topic/direct3d_abort%20Function.md)|Bricht die Ausführung einer Funktion mit der Einschränkungsklausel `restrict(amp)` ab.|  
|[direct3d_errorf-Funktion](../Topic/direct3d_errorf%20Function.md)|Gibt eine formatierte Zeichenfolge im Visual Studio **Ausgabe** Fenster und löst eine [Runtime_exception](../../../parallel/amp/reference/runtime-exception-class.md) Ausnahme, die die gleiche Formatierung hat eine Zeichenfolge.|  
|[direct3d_printf-Funktion](../Topic/direct3d_printf%20Function.md)|Gibt eine formatierte Zeichenfolge im Visual Studio **Ausgabe** Fenster. Sie wird von einer Funktion mit der Einschränkungsklausel `restrict(amp)` aufgerufen.|  
|[Global_memory_fence-Funktion](../Topic/global_memory_fence%20Function.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind.|  
|[Parallel_for_each-Funktion (C++-AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)|Führt eine Funktion übergreifend über die "compute"-Domäne aus.|  
|[Tile_static_memory_fence-Funktion](../Topic/tile_static_memory_fence%20Function.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe vom Typ `tile_static` abgeschlossen sind.|  
  
## <a name="constants"></a>Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS-Konstante](../Topic/HLSL_MAX_NUM_BUFFERS%20Constant.md)|Die maximale Anzahl der von DirectX zugelassenen Puffer.|  
|[MODULENAME_MAX_LENGTH-Konstante](../Topic/MODULENAME_MAX_LENGTH%20Constant.md)|Speichert die maximale Länge des Modulnamens. Dieser Wert muss für den Compiler und die Laufzeit identisch sein.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz (C++-AMP)](../../../parallel/amp/reference/reference-cpp-amp.md)



