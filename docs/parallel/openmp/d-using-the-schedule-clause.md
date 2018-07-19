---
title: D. Unter Berücksichtigung des Zeitplans Klausel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8987c4505adfde8534d57346cd6725231efa022f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694939"
---
# <a name="d-using-the-schedule-clause"></a>D. Unter Berücksichtigung des Zeitplans-Klausel
Ein paralleler Bereich verfügt über mindestens eine Grenze, auf das Ende und möglicherweise zusätzliche Barrieren darin. Bei jeder Grenze müssen der letzte Thread auf das Eintreffen der anderen Mitgliedern des Teams warten. Um diese Wartezeit zu minimieren, sollten gemeinsam genutzte verteilt werden, damit alle Threads mit der Barriere auf etwa zur gleichen Zeit ankommen. Wenn ein Teil, freigegeben in Arbeit enthaltenen **für** erstellt, die `schedule` -Klausel kann für diesen Zweck verwendet werden.  
  
 Bei wiederholten Verweise auf dieselben Objekte, die Auswahl des Zeitplans für einen **für** Konstrukt kann bestimmt werden, in erster Linie durch die Merkmale des Speicher-Systems, z. B. das Vorhandensein und die Größe des Caches und Arbeitsspeicher, ob der Zugriff werden die Zeiten uniform oder Non-Uniform. Solche Überlegungen können jeder Thread konsistent verweisen auf den gleichen Satz von Elementen eines Arrays in einer Reihe von Schleifen, haben, auch wenn einige Threads relativ weniger Arbeitsschritte in einigen der Schleifen zugewiesen sind vorzuziehen erleichtern. Dies kann geschehen, indem Sie mit der **statische** Zeitplan mit der gleichen Grenzen für alle Schleifen. Im folgenden Beispiel beachten Sie, dass 0 (null) als die untere Grenze in der zweiten Schleife verwendet wird, obwohl **k** wäre besser, wenn der Zeitplan nicht wichtig sind.  
  
```  
#pragma omp parallel  
{  
#pragma omp for schedule(static)  
  for(i=0; i<n; i++)  
    a[i] = work1(i);  
#pragma omp for schedule(static)  
  for(i=0; i<n; i++)  
    if(i>=k) a[i] += work2(i);  
}  
```  
  
 In den verbleibenden Beispielen wird davon ausgegangen, dass der Arbeitsspeicher der Zugriff ist nicht der bestimmende Faktor und, sofern nicht anders angegeben, dass alle Threads vergleichbare Verarbeitungsressourcen erhalten. In diesen Fällen ist die Wahl des Zeitplans für eine **für** Konstrukt hängt die gemeinsame Arbeit, die zwischen den nächstgelegenen ausgeführt werden soll Barriere und entweder die implizite schließende Barriere oder die nächste nachfolgende Barriere, wenn vorhanden ist eine `nowait` Klausel. Für jede Art des Zeitplans zeigt ein kurzes Beispiel, wie diese Plantyp wahrscheinlich die beste Wahl ist. Eine kurze Erläuterung folgt jedes dieser Beispiele.  
  
 Die **statische** Zeitplan eignet sich auch für den einfachsten Fall eines parallelen Bereichs mit einem einzelnen **für** erstellen, wobei bei jedem Durchlauf die gleiche Menge an Arbeit.  
  
```  
#pragma omp parallel for schedule(static)  
for(i=0; i<n; i++) {  
  invariant_amount_of_work(i);  
}  
```  
  
 Die **statische** Zeitplan ist gekennzeichnet durch die Eigenschaften, die jeder Thread ungefähr die gleiche Anzahl von Iterationen als ein anderer Thread ruft und jeder Thread kann unabhängig bestimmen, die Iterationen zugewiesen. Daher ist keine Synchronisierung erforderlich, um die Arbeit verteilen, und unter der Annahme, dass jeder Iteration die gleiche Menge an Arbeit erforderlich ist, alle Threads auf etwa zur gleichen Zeit enden soll.  
  
 Für ein Team von `p` Threads können *ceiling(n/p)* die ganze Zahl sein *q*, die erfüllt *n = p\*Q - R* mit *0 < = R < p* . Eine Implementierung der **statische** geplant werden für dieses Beispiel zugewiesen würde *q* Iterationen mit dem ersten *p-1* Threads und *q-r* Iterationen, um den letzten Thread.  Eine andere zulässige Implementierung Enhanced *q* Iterationen mit dem ersten *p-R* Threads und *q-1* Iterationen, um die verbleibenden *r*Threads. Dies zeigt, warum ein Programm nicht auf die Details einer bestimmten Implementierung überlassen.  
  
 Die **dynamische** Zeitplan eignet sich für die Groß-/Kleinschreibung einer **für** erstellen, mit der Iterationen, erfordern unterschiedliche oder sogar unvorhersehbare Datenmengen arbeiten.  
  
```  
#pragma omp parallel for schedule(dynamic)  
  for(i=0; i<n; i++) {  
    unpredictable_amount_of_work(i);  
}  
```  
  
 Die **dynamische** Zeitplan ist gekennzeichnet durch die Eigenschaft, die kein Thread die Barriere wartet länger als es einem anderen Thread zum Ausführen der letzten Iteration benötigt. Dies erfordert, dass Iterationen jeweils einzeln an Threads zugewiesen werden, wie sie bei der Synchronisierung für jede Zuordnung verfügbar. Der Synchronisierungsaufwand kann reduziert werden, indem Sie eine minimale Segmentgröße angeben *k* größer als 1 ist, sodass Threads zugewiesen sind *k* zu einem Zeitpunkt bis maximal *k* bleiben. Dadurch wird sichergestellt, dass kein Thread, die länger wartet als ein anderer Thread dauert (höchstens) führen Sie die letzte Gruppe von Barriere *k* Iterationen.  
  
 Die **dynamische** Zeitplan ist hilfreich, wenn die Threads empfangen varying Verarbeitungsressourcen, die hat dieselbe Wirkung als unterschiedliche Mengen von Arbeit pro Iteration. Entsprechend der dynamischen Zeitplan kann auch nützlich sein, wenn die Threads erreicht die **für** erstellen zu unterschiedlichen Zeitpunkten, obwohl in einigen Fällen die **geführtes** Zeitplan möglicherweise vorzuziehen.  
  
 Die **geführtes** Zeitplan eignet sich für den Fall, in dem die Threads zu unterschiedlichen Zeiten auf kommen eventuell, eine **für** mit jeder Iteration erfordern ungefähr die gleiche Menge an Arbeit zu erstellen. Dies kann geschehen, wenn, z. B. die **für** Konstrukt ist eine oder mehrere Abschnitte vorangestellt oder **für** mit erstellt `nowait` Klauseln.  
  
```  
#pragma omp parallel  
{  
  #pragma omp sections nowait  
  {  
    // ...  
  }  
  #pragma omp for schedule(guided)  
  for(i=0; i<n; i++) {  
    invariant_amount_of_work(i);  
  }  
}  
```  
  
 Wie **dynamische**, **geführtes** planen Garantien, die kein Thread auf die Grenze, die länger wartet als ein anderer Thread zum Ausführen der letzten Iteration benötigt oder den abschließenden *k* Iterationen, wenn eine Blockgröße von *k* angegeben ist. Für solche Zeitpläne der **geführtes** Zeitplan ist gekennzeichnet durch die Eigenschaft, dass sie die wenigsten Synchronisierungen erfordert. Für Segmentgröße *k*, weist eine typische Implementierung *Q = ceiling(n/p)* Iterationen an, die den ersten verfügbaren Thread festlegen *n* der größere der *n-q* und *p\*k*, und wiederholen Sie, bis alle Iterationen zugewiesen sind.  
  
 Wenn die Auswahl des optimalen Zeitplans nicht als klar ist, wie es für diese Beispiele ist die **Runtime** Zeitplan eignet sich für unterschiedliche Zeitpläne und Blockgrößen experimentieren, ohne zu ändern und kompilieren Sie das Programm erneut. Es kann auch nützlich sein, wenn des optimalen Zeitplans (in einer vorhersagbaren Weise) für die Eingabedaten abhängt, der die Anwendung angewendet wird.  
  
 Um ein Beispiel für den Ausgleich zwischen verschiedenen Zeitplänen angezeigt wird, sollten Sie in der Freigabe von 1000 Iterationen auf 8 Threads. Angenommen, es ist eine invariante Arbeitsaufwand, der in jeder Iteration, und verwenden Sie diese als die Zeiteinheit.  
  
 Wenn alle Threads zur gleichen Zeit starten der **statische** Zeitplan wird dazu führen, dass das Konstrukt in 125 Einheiten, bei der keine Synchronisierung ausgeführt. Aber nehmen wir an, dass ein Thread 100 Einheiten spät im, die empfangen wird. Warten Sie dann die restlichen sieben Threads 100 Einheiten auf die Grenze, und die Ausführungszeit für das gesamte-Konstrukt auf 225 erhöht.  
  
 Da sowohl die **dynamische** und **geführtes** Zeitpläne stellen Sie sicher, dass kein Thread wartet auf mehr als eine Einheit der Barriere, die verzögerte Threads bewirkt, dass ihre Ausführungszeiten für das Konstrukt nur auf 138 erhöhen Einheiten, um Verzögerungen bei der Synchronisierung möglicherweise erhöht. Wenn solche Verzögerungen nicht unerheblich sind, ist wichtig, dass die Anzahl der Synchronisierungen 1.000 ist **dynamische** jedoch nur 41 für **geführtes**, vorausgesetzt die Standardblockgröße eines. Mit einer Größe von 25 **dynamische** und **geführtes** sowohl beendet 150 Einheiten sowie Verzögerungen bei der über die erforderlichen Synchronisierungen, welche Anzahl jetzt nur 40 und 20 bzw.