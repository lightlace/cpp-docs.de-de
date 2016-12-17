---
title: "Referenz (C++ AMP)"
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
  - "amp/Concurrency::Reference (C++ AMP)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, Referenz"
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Referenz (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Dieser Abschnitt enthält Referenzinformationen für die C\+\+ Accelerated Massive Parallelism \(C\+\+ AMP\)\-Laufzeit.  
  
> [!NOTE]
>  In der C\+\+\-Standardprogrammiersprache ist die Verwendung von Bezeichnern, die mit einem Unterstrich \(`_`\) beginnen, auf Implementierungen wie Bibliotheken beschränkt.  Verwenden Sie keine Namen, die mit einem Unterstrich im Code beginnen.  Die Eindeutigkeit des Verhaltens von Codeelementen mit Namen dieser Art kann nicht gewährleistet werden, und für zukünftige Versionen muss mit Änderungen gerechnet werden.  Aus diesen Gründen werden solche Codeelemente in dieser Dokumentation nicht beschrieben.  
  
## In diesem Abschnitt  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)  
 Stellt Klassen und Funktionen bereit, die eine Beschleunigung von C\+\+\-Code auf datenparalleler Hardware ermöglichen.  
  
 [Concurrency::direct3d\-Namespace](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)  
 Stellt Funktionen bereit, welche die D3D\-Interoperabilität unterstützen.  Ermöglicht die einfache Verwendung von D3D\-Ressourcen für Berechnungen in AMP\-Code sowie die Verwendung von in AMP erstellten Ressourcen in D3D\-Code, ohne dass redundante Zwischenkopien erstellt werden.  Sie können C\+\+ AMP verwenden, um die berechnungsintensiven Abschnitte Ihrer DirectX\-Anwendungen inkrementell zu beschleunigen und die D3D\-API für Daten nutzen, die aus AMP\-Berechnungen resultieren.  
  
 [Concurrency::fast\_math\-Namespace](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)  
 Funktionen im `fast_math`\-Namespace sind nicht C99\-kompatibel.  Für jede Funktion werden nur Versionen mit einfacher Genauigkeit bereitgestellt.  Diese Funktionen verwenden die systeminternen DirectX\-Funktionen, die schneller als die entsprechenden Funktionen im `precise_math`\-Namespace sind und keine erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste benötigen. Sie sind jedoch weniger genau.  Für jede Funktion gibt es zwei Versionen für Quellebenenkompatibilität mit Code C99. Beide Versionen akzeptieren und geben Werte mit einfacher Genauigkeit zurück.  
  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)  
 Stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.  
  
 [Concurrency::precise\_math\-Namespace](../../../parallel/amp/reference/concurrency-precise-math-namespace.md)  
 Funktionen im `precise_math`\-Namespace sind C99\-kompatibel.  Für jede Funktion sind Versionen mit einfacher und doppelter Genauigkeit enthalten.  Diese Funktionen, Funktionen mit einfacher Genauigkeit eingeschlossen, erfordern erweiterte Unterstützung doppelter Genauigkeit auf der Zugriffstaste.  
  
## Verwandte Abschnitte  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C\+\+ AMP beschleunigt die Ausführung von C\+\+\-Code, indem die Vorteile Daten parallel verarbeitender Hardware, beispielsweise ein Grafikprozessor \(Graphics Processing Unit, GPU\) auf einer separaten Grafikkarte, genutzt werden.