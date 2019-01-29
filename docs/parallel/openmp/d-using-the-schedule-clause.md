---
title: D. Der Schedule-Klausel
ms.date: 01/22/2019
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
ms.openlocfilehash: 89e011784c5cccedc4a75f38d553458ea2e5d7e0
ms.sourcegitcommit: 382e247c0f1b4cb7c2dab837b8b6fdff24bff47a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "55087287"
---
# <a name="d-the-schedule-clause"></a>D. Der Schedule-Klausel

Ein paralleles Bereichs ist mindestens eine Grenze, an deren Ende, und möglicherweise weitere Barrieren darin. Der letzte Thread auf das eintreffen müssen die anderen Mitglieder des Teams an jeder Grenze warten. Um diese Wartezeit zu minimieren, sollte gemeinsamen Arbeit verteilt werden, damit alle Threads auf die Grenze auf etwa zur gleichen Zeit ankommen. Wenn einige der, die freigegeben ist in Arbeit enthalten `for` erstellt, die `schedule` -Klausel kann für diesen Zweck verwendet werden.

Wenn wiederholte Verweise auf dieselben Objekte, die Auswahl der Zeitplan für einen `for` Konstrukt kann ermittelt werden, in erster Linie durch die Merkmale des Speichersystems, z. B. das Vorhandensein und die Größe des Caches und gibt an, ob Arbeitsspeicher Zugriffszeiten uniform sind oder Nonuniform. Punkte, können es besser, die jeder Thread konsistent auf den gleichen Satz von Elementen eines Arrays in einer Reihe von Schleifen, verweisen zu haben, auch wenn einige Threads relativ wenig Arbeit in einigen der Schleifen zugewiesen sind durchführen. Dieses Setup können Sie dazu die `static` Zeitplan mit der gleichen Grenzen für alle den Schleifen. Im folgenden Beispiel ist 0 (null) wird verwendet, als die untere Grenze in der zweiten Schleife, obwohl `k` wäre natürlicher aus, wenn der Zeitplan nicht wichtig sind.

```cpp
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

In den verbleibenden Beispielen wurde davon ausgegangen, dass der Speicher Zugriff ist nicht die vorherrschende Überlegung. Sofern nicht anders angegeben, dass alle Threads vergleichbare Compute-Ressourcen zu erhalten. In diesen Fällen ist die Auswahl der Zeitplan für eine `for` Konstrukt hängt die freigegebenen Schritte, die zwischen dem nächsten vorausgehenden ausgeführt werden soll flächendeckende und entweder die implizite schließende-Grenze oder die nächstgelegenen bevorstehende Grenze liegt eine `nowait` -Klausel. Für jede Art des Zeitplans zeigt ein kurzes Beispiel, wie diese Art von Zeitplan wahrscheinlich die beste Wahl ist. Eine kurze Erläuterung folgt jedes Beispiel.

Die `static` Zeitplan eignet sich auch im einfachsten Fall eines parallelen Bereichs mit einem einzelnen `for` zu erstellen, wobei bei jedem Durchlauf für die gleiche Menge an Arbeit.

```cpp
#pragma omp parallel for schedule(static)
for(i=0; i<n; i++) {
  invariant_amount_of_work(i);
}
```

Die `static` Zeitplan ist gekennzeichnet durch die Eigenschaften, die jeder Thread ungefähr die gleiche Anzahl von Iterationen wie alle anderen Threads abruft, und jeder Thread kann unabhängig voneinander bestimmen, die Iterationen zugewiesen. Daher ist keine Synchronisierung erforderlich, um die Arbeit zu verteilen, und unter der Annahme, dass jeder Iteration die gleiche Menge an Arbeit erforderlich ist, alle Threads beendet werden soll auf etwa zur gleichen Zeit.

Für ein Team aus *p* Threads können *ceiling(n/p)* werden die ganze Zahl *q*, erfüllt die *n = p\*Q - R* mit *0 < = R < p*. Eine Implementierung der `static` Planen für in diesem Beispiel weisen Sie würden *q* Iterationen mit dem ersten *p-1* Threads und *Q-R* Iterationen an, der letzte Thread.  Eine andere zulässige Implementierung würden zuweisen *q* Iterationen mit dem ersten *p-R* Threads und *q-1* Iterationen, um die verbleibenden *r*Threads. Dieses Beispiel zeigt, warum ein Programm auf die Details einer bestimmten Implementierung verlassen dürfen nicht.

Die `dynamic` Zeitplan eignet sich für den Fall einer `for` erstellen, mit der Iterationen, die unterschiedlichen oder sogar unvorhersehbar, eine Menge Arbeit erfordern.

```cpp
#pragma omp parallel for schedule(dynamic)
  for(i=0; i<n; i++) {
    unpredictable_amount_of_work(i);
}
```

Die `dynamic` Zeitplan ist gekennzeichnet durch die Eigenschaft, die kein Thread die Barriere wartet darauf, mehr als ein anderer Thread die letzte Iteration ausgeführt wird. Diese Anforderung bedeutet, dass Iterationen jeweils einzeln an Threads, sobald diese verfügbar, bei der Synchronisierung für jede Zuordnung zugewiesen werden müssen. Der Synchronisierungsaufwand kann reduziert werden, indem Sie eine minimale Blockgröße angeben *k* größer als 1, sodass Threads zugewiesen sind *k* zu einem Zeitpunkt bis weniger als *k* bleiben. Dadurch wird sichergestellt, dass kein Thread, die länger wartet als ein anderer Thread dauert (höchstens) führen Sie die abschließenden Teil der Barriere *k* Iterationen.

Die `dynamic` Zeitplan ist hilfreich, wenn Threads erhalten unterschiedliche Compute-Ressourcen, die nahezu die gleiche Wirkung wie unterschiedliche Mengen an Arbeit für jede Iteration verfügt. Auf ähnliche Weise der dynamischen Zeitplan kann auch nützlich sein, wenn die Threads erhalten die `for` erstellen zu unterschiedlichen Zeitpunkten, aber in einigen Fällen der `guided` Zeitplan kann vorteilhafter sein.

Die `guided` Zeitplan eignet sich für den Fall, in dem die Threads können zu unterschiedlichen Zeiten auf eintreffen, einer `for` mit jeder Iteration erfordert ungefähr die gleiche Menge an Arbeit zu erstellen. Diese Situation kann eintreten, wenn, z. B. die `for` Konstrukt wird von einem oder mehreren Abschnitten vorangestellt oder `for` erstellt mit `nowait` Klauseln.

```cpp
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

Wie `dynamic`, `guided` planen Garantien, die kein Thread, an der Grenze, die länger wartet als ein anderer Thread zum Ausführen der letzten Iteration benötigt oder den abschließenden *k* Iterationen, wenn eine Blockgröße von *k* angegeben ist. Für solche Zeitpläne die `guided` Zeitplan ist gekennzeichnet durch die Eigenschaft, dass es die wenigsten Synchronisierungen erforderlich ist. Für die Größe der Abschnitte *k*, eine typische Implementierung weist *Q = ceiling(n/p)* Iterationen auf den ersten verfügbaren Thread festgelegt *n* der größere der *n-q* und *p\*k*, und wiederholen, bis alle Iterationen zugewiesen sind.

Wenn die Auswahl des optimalen Zeitplans nicht so deutlich wie bei diesen Beispielen wird die `runtime` Zeitplan eignet sich für das Experimentieren mit unterschiedlichen Zeitplänen und Blockgrößen ohne ändern und kompilieren Sie das Programm neu. Es kann auch nützlich sein, wenn Bestimmen des optimalen Zeitplans für die Eingabedaten (auf vorhersagbare Weise) abhängig ist, der die Anwendung angewendet wird.

Um ein Beispiel für die Kompromisse zwischen unterschiedlichen Zeitplänen angezeigt wird, sollten Sie in der Freigabe von 1000 Iterationen auf acht Threads. Angenommen, es ist eine invariante Menge von Arbeit in jeder Iteration, und verwenden, die als Einheit der Zeit.

Wenn alle Threads zur gleichen Zeit, starten die `static` Zeitplan wird dazu führen, dass das Konstrukt in 125-Einheiten, bei der keine Synchronisierung ausgeführt. Aber nehmen wir an, dass ein Thread spät im eingehenden Einheiten von 100 ist. Klicken Sie dann die restlichen sieben Threads warten Sie Einheiten von 100 die Barriere, und die Ausführungszeit für das ganze Konstrukt wird auf 225 erhöht.

Da sowohl die `dynamic` und `guided` Zeitpläne stellen Sie sicher, dass kein Thread wartet auf mehr als eine Einheit, die Barriere, die verzögerte Threads führt dazu, dass ihre Ausführungszeiten für das Konstrukt nur von 138 Einheiten, die möglicherweise Verzögerungen von erhöht erhöhen Synchronisierung. Wenn diese Verzögerungen nicht vernachlässigbar sind, es wichtig, dass die Anzahl der Synchronisierungen 1000 für `dynamic` jedoch nur 41 für `guided`, vorausgesetzt die Standardsegmentgröße eines. Mit der eine Blockgröße von 25 `dynamic` und `guided` beide abgeschlossen in 150 Einheiten sowie keine Verzögerungen über die erforderlichen Synchronisierungen, die jetzt Anzahl nur 40 und 20 bzw.
