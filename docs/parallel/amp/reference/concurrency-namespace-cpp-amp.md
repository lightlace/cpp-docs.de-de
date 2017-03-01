---
title: Concurrency-Namespace (C++-AMP) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
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
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: a62955c94771320a64027f4f820434dd5e7984a1
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-c-amp"></a>Concurrency-Namespace (C++ AMP)
Stellt Klassen und Funktionen bereit, die die Ausführung von C++-Code auf datenparalleler Hardware beschleunigen. Weitere Informationen finden Sie unter [Übersicht über C++ AMP](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="namespaces"></a>Namespaces  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrency:: Direct3D-Namespace](concurrency-direct3d-namespace.md)|Stellt Funktionen bereit, welche die D3D-Interoperabilität unterstützen. Ermöglicht die einfache Verwendung von D3D-Ressourcen für Berechnungen in AMP-Code sowie die Verwendung von in AMP erstellten Ressourcen in D3D-Code, ohne dass redundante Zwischenkopien erstellt werden. Sie können C++ AMP verwenden, um die berechnungsintensiven Abschnitte Ihrer DirectX-Anwendungen inkrementell zu beschleunigen und die D3D-API für Daten nutzen, die aus AMP-Berechnungen resultieren.|  
|[Concurrency:: fast_math-Namespace](concurrency-fast-math-namespace.md)|Funktionen im `fast_math`-Namespace sind nicht C99-kompatibel. Für jede Funktion werden nur Versionen mit einfacher Genauigkeit bereitgestellt. Diese Funktionen verwenden die systeminternen DirectX-Funktionen, die schneller als die entsprechenden Funktionen im `precise_math`-Namespace sind und keine erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste benötigen. Sie sind jedoch weniger genau. Für jede Funktion gibt es zwei Versionen für Quellebenenkompatibilität mit Code C99. Beide Versionen akzeptieren und geben Werte mit einfacher Genauigkeit zurück.|  
|[Concurrency:: Graphics-Namespace](concurrency-graphics-namespace.md)|Stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.|  
|[Concurrency:: precise_math-Namespace](concurrency-precise-math-namespace.md)|Funktionen im `precise_math`-Namespace sind C99-kompatibel. Für jede Funktion sind Versionen mit einfacher und doppelter Genauigkeit enthalten. Diese Funktionen, Funktionen mit einfacher Genauigkeit eingeschlossen, erfordern erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste.|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[zugriffstastenklasse](accelerator-class.md)|Stellt eine Abstraktion eines physischen DP-optimierten Berechnungsknotens dar.|  
|[Accelerator_view-Klasse](accelerator-view-class.md)|Stellt die Abstraktion eines virtuellen Geräts für einen datenparallelen C++ AMP-Beschleuniger dar.|  
|[Accelerator_view_removed-Klasse](accelerator-view-removed-class.md)|Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX-Aufruf aufgrund des Windows-TDR-Mechanismus (Timeout Detection and Recovery) fehlschlägt.|  
|[Array-Klasse](array-class.md)|Ein Datenaggregat auf einem `accelerator_view`-Objekt in der Rasterdomäne. Es ist eine Auflistung von Variablen, eine für jedes Element in einer "grid"-Domäne. Jede Variable enthält einen Wert, der einem C++-Typ entspricht.|  
|[Array_view-Klasse](array-view-class.md)|Stellt eine Ansicht der Daten in ein Array\<T, N >.|  
|[Completion_future-Klasse](completion-future-class.md)|Stellt ein "future"-Objekt dar, das einem asynchronen C++ AMP-Vorgang entspricht.|  
|[extent-Klasse](extent-class.md)|Stellt einen Vektor von n ganzzahligen Werten dar, die die Grenzen eines n-dimensionalen Raums mit dem Ursprung 0 angeben. Die Werte im Koordinatenvektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert. Im kartesischen 3-dimensionalen Raum stellt der "extent"-Vektor (7,5,3) beispielsweise einen Raum dar, in dem die z-Koordinate im Bereich von 0 bis 7, die y-Koordinate im Bereich von 0 bis 5 und die x-Koordinate im Bereich von 0 bis 3 liegt.|  
|[Index-Klasse](index-class.md)|Definiert einen n-dimensionalen Indexpunkt.|  
|[Invalid_compute_domain-Klasse](invalid-compute-domain-class.md)|Die Ausnahme, die ausgelöst wird, wenn die Laufzeit einen Kernel nicht mithilfe der "compute"-Domäne starten kann, die auf der `parallel_for_each`-Aufrufsite angegeben wird.|  
|[Out_of_memory-Klasse](out-of-memory-class.md)|Die Ausnahme, die ausgelöst wird, wenn eine Methode aufgrund unzureichenden System- oder Gerätearbeitsspeichers fehlschlägt.|  
|[Runtime_exception-Klasse](runtime-exception-class.md)|Der Basistyp für Ausnahmen in der C++ AMP-Bibliothek.|  
|[Tile_barrier-Klasse](tile-barrier-class.md)|Eine Funktionsklasse, die vom System nur erstellt werden kann und einem unterteilten `parallel_for_each`-Lambda als Teil des `tiled_index`-Parameters übergeben wird. Sie stellt eine einzige Methode, die Methode `wait()`, bereit, die dazu dient, die Ausführung von Threads zu synchronisieren, die in der Threadgruppe (Kachel) ausgeführt werden.|  
|[Tiled_extent-Klasse](tiled-extent-class.md)|Ein `tiled_extent`-Objekt ist ein `extent`-Objekt einer bis drei Dimensionen, das den "extent"-Bereich in ein-, zwei- oder dreidimensionale Kacheln unterteilt.|  
|[Tiled_index-Klasse](tiled-index-class.md)|Stellt einen Index für ein `tiled_grid`-Objekt bereit. Diese Klasse verfügt über Eigenschaften, über die auf ein Element relativ zum lokalen Kachelursprung und relativ zum globalen Ursprung zugegriffen werden kann.|  
|[Uninitialized_object-Klasse](uninitialized-object-class.md)|Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.|  
|[Unsupported_feature-Klasse](unsupported-feature-class.md)|Die Ausnahme, die ausgelöst wird, wenn eine nicht unterstützte Funktion verwendet wird.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Access_type-Enumeration](concurrency-namespace-enums-amp.md#access_type)|Gibt den Datenzugriffstyp an.|  
|[Queuing_mode-Enumeration](concurrency-namespace-enums-amp.md#queuing_mode)|Gibt die Modi für das Hinzufügen zur Warteschlange an, die auf dem Beschleuniger unterstützt werden.|  
  
### <a name="operators"></a>Operatoren  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[Operator ==-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Bestimmt, ob die angegebenen Datenstrukturen gleich sind.|  
|[Operator! =-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Bestimmt, ob die angegebenen Datenstrukturen ungleich sind.|  
|[Operator +-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_add)|Berechnet die komponentenbezogene Summe der angegebenen Argumente.|  
|[Operator-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator-)|Berechnet die Differenz zwischen den angegebenen Argumenten pro Komponente.|  
|[Operator *-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_star)|Berechnet das komponentenbezogene Produkt der angegebenen Argumente.|  
|[Operator /-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_div)|Berechnet den komponentenbezogenen Quotienten der angegebenen Argumente.|  
|[Operator%-Operator (C++-AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Berechnet den Modul des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[All_memory_fence-Funktion](concurrency-namespace-functions-amp.md#all_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind.|  
|[Amp_uninitialize-Funktion](concurrency-namespace-functions-amp.md#amp_uninitialize)|Hebt die Initialisierung der C++ AMP-Laufzeit auf.|  
|[Atomic_compare_exchange-Funktion](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Überladen. Wenn der Wert, der am angegebenen Speicherort abgelegt ist, mit dem ersten angegebenen Wert übereinstimmt, wird der zweite angegebene Wert als atomischen Vorgang an demselben Speicherort abgelegt.|  
|[atomic_exchange-Funktion](concurrency-namespace-functions-amp.md#atomic_exchange)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf den angegebenen Wert fest.|  
|[atomic_fetch_add-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf die Summe dieses Werts und auf einen angegebenen Wert fest.|  
|[atomic_fetch_and-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `and` dieses Werts und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_dec-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Überladen. Dekrementiert den Wert, der am angegebenen Speicherort abgelegt ist, und speichert das Ergebnis als atomischen Vorgang an demselben Speicherort.|  
|[Atomic_fetch_inc-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Überladen. Inkrementiert den Wert, der am angegebenen Speicherort abgelegt ist, und speichert das Ergebnis als atomischen Vorgang an demselben Speicherort.|  
|[Atomic_fetch_max-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang größer als diesen Wert und auf einen angegebenen Wert fest.|  
|[Atomic_fetch_min-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang kleiner als diesen Wert und auf einen angegebenen Wert fest.|  
|[atomic_fetch_or-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `or` dieses Werts und auf einen angegebenen Wert fest.|  
|[atomic_fetch_sub-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf die Differenz dieses Werts und auf einen angegebenen Wert fest.|  
|[atomic_fetch_xor-Funktion](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Überladen. Legt den Wert, der am angegebenen Speicherort abgelegt ist, als atomischen Vorgang auf das bitweise `xor` dieses Werts und auf einen angegebenen Wert fest.|  
|[Copy-Funktion](concurrency-namespace-functions-amp.md#copy)|Kopiert ein C++ AMP-Objekt. Alle Anforderungen der synchronen Datenübertragung werden erfüllt. Es können keine Daten kopiert werden, wenn auf einer Zugriffstaste Code ausgeführt wird. Das allgemeine Format dieser Funktion ist `copy(src, dest)`.|  
|[Copy_async-Funktion](concurrency-namespace-functions-amp.md#copy_async)|Kopiert ein C++ AMP-Objekt und gibt [Completion_future](completion-future-class.md) , die auf gewartet werden kann. Es können keine Daten kopiert werden, wenn auf einer Zugriffstaste Code ausgeführt wird. Das allgemeine Format dieser Funktion ist `copy(src, dest)`.|  
|[direct3d_abort-Funktion](concurrency-namespace-functions-amp.md#direct3d_abort)|Bricht die Ausführung einer Funktion mit der Einschränkungsklausel `restrict(amp)` ab.|  
|[direct3d_errorf-Funktion](concurrency-namespace-functions-amp.md#direct3d_errorf)|Gibt eine formatierte Zeichenfolge im Visual Studio **Ausgabe** Fenster und löst eine [Runtime_exception](runtime-exception-class.md) -Ausnahme mit derselben Formatierungszeichenfolge.|  
|[direct3d_printf-Funktion](concurrency-namespace-functions-amp.md#direct3d_printf)|Gibt eine formatierte Zeichenfolge im Visual Studio **Ausgabe** Fenster. Sie wird von einer Funktion mit der Einschränkungsklausel `restrict(amp)` aufgerufen.|  
|[Global_memory_fence-Funktion](concurrency-namespace-functions-amp.md#global_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind.|  
|[Parallel_for_each-Funktion (C++-AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Führt eine Funktion übergreifend über die "compute"-Domäne aus.|  
|[Tile_static_memory_fence-Funktion](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe vom Typ `tile_static` abgeschlossen sind.|  
  
## <a name="constants"></a>Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS-Konstante](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Die maximale Anzahl der von DirectX zugelassenen Puffer.|  
|[MODULENAME_MAX_LENGTH-Konstante](concurrency-namespace-constants-amp.md#modulename_max_length)|Speichert die maximale Länge des Modulnamens. Dieser Wert muss für den Compiler und die Laufzeit identisch sein.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
## <a name="see-also"></a>Siehe auch  
 [(Referenz (c++ AMP)](reference-cpp-amp.md)




