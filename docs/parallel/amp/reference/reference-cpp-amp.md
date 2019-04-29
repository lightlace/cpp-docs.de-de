---
title: Referenz (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: a334c7873675183dc06abfc2fe51472190996bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351169"
---
# <a name="reference-c-amp"></a>Referenz (C++ AMP)

Dieser Abschnitt enthält Referenzinformationen für die C++ Accelerated Massive Parallelism (C++ AMP)-Laufzeit.

> [!NOTE]
>  In der C++-Standardprogrammiersprache ist die Verwendung von Bezeichnern, die mit einem Unterstrich (`_`) beginnen, auf Implementierungen wie Bibliotheken beschränkt. Verwenden Sie keine Namen, die mit einem Unterstrich im Code beginnen. Die Eindeutigkeit des Verhaltens von Codeelementen mit Namen dieser Art kann nicht gewährleistet werden, und für zukünftige Versionen muss mit Änderungen gerechnet werden. Aus diesen Gründen werden solche Codeelemente in dieser Dokumentation nicht beschrieben.

## <a name="in-this-section"></a>In diesem Abschnitt

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
Stellt Klassen und Funktionen bereit, die eine Beschleunigung von C++-Code auf datenparalleler Hardware ermöglichen.

[Concurrency::direct3d Namespace](concurrency-direct3d-namespace.md)<br/>
Stellt Funktionen bereit, welche die D3D-Interoperabilität unterstützen. Ermöglicht die einfache Verwendung von D3D-Ressourcen für Berechnungen in AMP-Code sowie die Verwendung von in AMP erstellten Ressourcen in D3D-Code, ohne dass redundante Zwischenkopien erstellt werden. Sie können C++ AMP verwenden, um die berechnungsintensiven Abschnitte Ihrer DirectX-Anwendungen inkrementell zu beschleunigen und die D3D-API für Daten nutzen, die aus AMP-Berechnungen resultieren.

[Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)<br/>
Funktionen im `fast_math`-Namespace sind nicht C99-kompatibel. Für jede Funktion werden nur Versionen mit einfacher Genauigkeit bereitgestellt. Diese Funktionen verwenden die intrinsischen DirectX-Funktionen, die schneller als die entsprechenden Funktionen im `precise_math`-Namespace sind und keine erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste benötigen. Sie sind jedoch weniger genau. Für jede Funktion gibt es zwei Versionen für Quellebenenkompatibilität mit Code C99. Beide Versionen akzeptieren und geben Werte mit einfacher Genauigkeit zurück.

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)<br/>
Stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.

[Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)<br/>
Funktionen im `precise_math`-Namespace sind C99-kompatibel. Für jede Funktion sind Versionen mit einfacher und doppelter Genauigkeit enthalten. Diese Funktionen, Funktionen mit einfacher Genauigkeit eingeschlossen, erfordern erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste.

## <a name="related-sections"></a>Verwandte Abschnitte

[C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
C++ AMP beschleunigt die Ausführung von C++-Code, indem die Vorteile Daten parallel verarbeitender Hardware, beispielsweise ein Grafikprozessor (Graphics Processing Unit, GPU) auf einer separaten Grafikkarte, genutzt werden.
