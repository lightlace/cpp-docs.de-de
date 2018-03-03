---
title: 'Vorgehensweise: Kombinieren von combinable | Microsoft Docs'
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
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bbd36e9536707bc639e8f80cc019b7fda18f793
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Gewusst wie: Kombinieren von Gruppen mithilfe von combinable
In diesem Thema zeigt, wie die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse, um den Satz von Primzahlen zu berechnen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Primzahlengruppe zweimal berechnet. Jede Berechnung speichert das Ergebnis in einen [Bitset](../../standard-library/bitset-class.md) Objekt. Im Beispiel wird die Primzahlengruppe zunächst seriell und anschließend parallel berechnet. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
 Dieses Beispiel verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus und eine `combinable` Objekt, das Thread-lokalen Threadgruppen. Es verwendet dann die [combine_each](reference/combinable-class.md#combine_each) Methode, um die Thread-lokalen Threadgruppen der abschließende Satz kombinieren.  

  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
```Output  
serial time: 312 ms  
 
parallel time: 78 ms  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-combine-primes.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **/ EHsc / CL.exe Parallel-Combine-primes.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)   
 [combinable:: combine_each-Methode](reference/combinable-class.md#combine_each)


