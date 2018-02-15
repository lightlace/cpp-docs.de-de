---
title: C++ AMP (C++ Accelerated Massive Parallelism) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 514c45599bce85bf66bf473ac597dab255888ba8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)
(C++ AMP Accelerated Massive Parallelism) beschleunigt die Ausführung von C++-Code, indem die Vorteile Daten parallel verarbeitender Hardware, beispielsweise ein Grafikprozessor (Graphics Processing Unit, GPU) auf einer separaten Grafikkarte, genutzt werden. Das C++ AMP-Programmiermodell enthält Unterstützung für mehrdimensionale Arrays, Indizierung, Arbeitsspeicherübertragung und Tiling. Außerdem umfasst es eine Bibliothek mathematischer Funktionen. Mithilfe von C++ AMP-Sprachenerweiterungen können Sie steuern, wie Daten von der CPU auf die GPU bzw. zurück verschoben werden.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Beschreibt die Hauptfunktionen von C++ AMP und der mathematischen Bibliothek.|  
|[Verwenden von Lambdas, Funktionsobjekten und eingeschränkten Funktionen](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Beschreibt, wie Lambdaausdrücke, Funktionsobjekte und eingeschränkte Funktionen in Aufrufen an die [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) Methode.|  
|[Verwenden von Kacheln](../../parallel/amp/using-tiles.md)|Beschreibt, wie Unterteilungen verwendet werden, um den C++ AMP-Code beschleunigen.|  
|[Verwenden von accelerator-Objekten und accelerator_view-Objekten](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Beschreibt, wie die Ausführung des Codes auf der GPU mithilfe von Beschleunigern angepasst werden kann.|  
|[C++ AMP in UWP-Apps](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Beschreibt, wie C++ AMP in apps der universellen Windows-Plattform (UWP), die Windows-Runtime-Typen zu verwenden.|  
|[Grafiken (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Beschreibt, wie die C++ AMP-Grafikbibliothek verwendet wird.|  
|[Exemplarische Vorgehensweise: Matrixmultiplikation](../../parallel/amp/walkthrough-matrix-multiplication.md)|Veranschaulicht die Matrixmultiplikation mithilfe von C++ AMP-Code und Unterteilung.|  
|[Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Erklärt, wie eine Anwendung erstellt und gedebuggt wird, die parallele Reduzierung verwendet, um ein großes Array von ganzen Zahlen aufzusummieren.|  
  
## <a name="reference"></a>Referenz  
 [Referenz (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile_static-Schlüsselwort](../../cpp/tile-static-keyword.md)  
  
 [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)  
  
## <a name="other-resources"></a>Weitere Ressourcen  
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?linkid=238472)  
  
 [C++ AMP-Beispielprojekte herunterladen](http://go.microsoft.com/fwlink/p/?linkid=248508)  
  
 [Analysieren von C++ AMP-Code mit der Parallelitätsschnellansicht](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)

