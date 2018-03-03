---
title: 'Vorgehensweise: Schreiben einer Parallel_for-Schleife | Microsoft Docs'
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
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60ae6b7f496f86bde91801e486315587fb693436
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-parallelfor-loop"></a>Gewusst wie: Schreiben einer parallel_for-Schleife
In diesem Beispiel wird veranschaulicht, wie [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) um das Produkt von zwei Matrizen zu berechnen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die `matrix_multiply`-Funktion, die das Produkt von zwei quadratischen Matrizen berechnet.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die `parallel_matrix_multiply`-Funktion, die den `parallel_for`-Algorithmus zur parallelen Ausführung der äußeren Schleife verwendet.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 In diesem Beispiel wird nur die äußere Schleife parallelisiert, da diese genügend Arbeitsvorgänge ausführt, um von dem zusätzlichen Aufwand für die parallele Verarbeitung zu profitieren. Durch die Parallelisierung der inneren Schleife erzielen Sie keine Leistungssteigerung, da die innere Schleife nicht genügend Arbeitsvorgänge ausführt, um den zusätzlichen Aufwand für die parallele Verarbeitung zu kompensieren. Daher ist eine Parallelisierung der äußeren Schleife die beste Möglichkeit, die Vorteile der Parallelität in den meisten Systemen zu maximieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden ausführlicheren Beispiel wird die Leistung der `matrix_multiply`-Funktion mit der Leistung der `parallel_matrix_multiply`-Funktion verglichen.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
```Output  
serial: 3853  
parallel: 1311  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-matrix-multiply.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **/ EHsc / CL.exe Parallel-Matrix-multiply.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)


