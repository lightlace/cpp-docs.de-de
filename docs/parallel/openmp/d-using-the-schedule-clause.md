---
title: "D. Using the schedule Clause"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# D. Using the schedule Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein paralleler Bereich verfügt über mindestens eine Grenze, am Ende und enthält möglicherweise zusätzliche Barrieren darauf.  An jeder Grenze müssen die anderen Teammitglieder auf den letzten Thread warten anzukommen.  Um diese Wartezeit zu minimieren, sollten gemeinsame Arbeit verteilt werden, damit alle Threads an der Grenze etwa gleichzeitig stammen.  Wenn einige dieser freigegebenen Arbeit in **nach** Konstrukte enthalten ist, kann die `schedule`\-Klausel für diesen Zweck verwendet werden.  
  
 Schreibt wiederholte Verweise auf die gleichen Objekte vorhanden sind, wird die Auswahl Zeitplans für ein **nach** Konstrukt hauptsächlich von Eigenschaften des Arbeitsspeicher systems, wie das Vorhandensein und die Größe der Cache bestimmt, ob sich zugriffsgeschwindigkeiten Arbeitsspeicher ungleichmäßig oder einheitlich sind.  Solche Überlegungen machen sie möglicherweise vorzuziehen, jeden Thread zu den gleichen Satz von Elementen eines Arrays in einer Reihe von Schleifen zugreifen können, selbst wenn mehrere Threads relativ kleiner Arbeit in einigen der Schleifen zugewiesen werden.  Dies kann erfolgen, indem der **static** Zeitplan mit den gleichen Grenzen für alle Schleifen verwendet.  Im folgenden Beispiel werden Sie feststellen, dass keine wie die Untergrenze in der zweiten \- Schleife verwendet wird, obwohl **k** natürlicher wäre, wenn der Zeitplan nicht von Bedeutung sind.  
  
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
  
 In den verbleibenden Beispiele ist es, dass Speicherzugriff nicht die bestimmenden Überlegung ist, und wenn nichts anderes festgelegt angenommen, dass alle Threads vergleichbare Computerressourcen empfangen.  In diesen Fällen hängt die Wahl Zeitplans für ein **nach** Konstrukt von der gesamte freigegebenen Aufgaben ab, die zwischen dem nächsten vorangehenden Grenze ausgeführt werden soll, und die implizite schließenden Grenze oder die nächste folgenden Barriere, wenn eine `nowait`\-Klausel gibt.  Für jede Art von Zeitplan, wird ein kurzes Beispiel veranschaulicht, wie diese Art der Zeitplan wahrscheinlich die beste Wahl sein.  Eine kurze Erläuterung folgt jedem Beispiel.  
  
 Der **static** Zeitplan ist auch für den einfachsten Fall ein paralleler Bereich geeignet, der ein einzelnes **nach** Konstrukt enthält, wobei jede Iteration erfordert denselben Betrag der Arbeit.  
  
```  
#pragma omp parallel for schedule(static)  
for(i=0; i<n; i++) {  
  invariant_amount_of_work(i);  
}  
```  
  
 Der **static** Zeitplan wird durch die Eigenschaften gekennzeichnet, denen jeder Thread über die gleiche Anzahl von Iterationen wie ein beliebiger anderer Thread abruft, und jeder Thread kann bestimmen, die unabhängig voneinander die Iterationen zugewiesen sind.  Daher ist keine Synchronisierung erforderlich, um die Arbeit zu verteilen, und unter der Annahme, dass jede Iteration denselben Betrag der Arbeit erfordert, sollten alle Threads etwa gleichzeitig beenden.  
  
 Für ein Team von `p` Threads, können Sie *n\/p \(Höchstwert\)* ist die ganze Zahl, *q*die *n \= p\*q \- r* mit *0 \<\= r \< P.*erfüllt *.* Eine Implementierung des **static** Zeitplans für dieses Beispiel würde *q\-Iterationen* *p\-1* Threads auf die ersten und dem letzten Thread *q\-r* Iterationen zuweisen.  Eine weitere zulässige Implementierung würde *q\-Iterationen* den ersten *Fotorezeptor\-Threads* und Iterationen *q\-1* auf den übrigen *r\-Threads* zuweisen.  Dies wird, warum ein Programm nicht auf den Details einer bestimmten Implementierung basieren soll.  
  
 Der **dynamic** Zeitplan ist geeignet für den Fall eines **nach** Konstrukt mit Iterationen unvorhersehbar, die den Unterschied Arbeitsaufwände, oder sogar erforderlich sind.  
  
```  
#pragma omp parallel for schedule(dynamic)  
  for(i=0; i<n; i++) {  
    unpredictable_amount_of_work(i);  
}  
```  
  
 Der Zeitplan wird durch **dynamic** auf die Eigenschaft, für die kein Thread an der Grenze länger wartet, in dem sie verwendet einen anderen Thread, um ihre letzte Iteration ausgeführt wird.  Dies erfordert, dass Iterationen einzeln an Threads, sobald sie verfügbar sind, mit Synchronisierung für jede Zuweisung zugewiesen werden.  Der mehraufwand Synchronisierung kann reduziert werden, indem eine minimale Segmentgröße *k* angibt *, die* größer als 1 ist, sodass Threads gleichzeitig *k* zugewiesen werden, wenn weniger als *k* bleiben.  Dadurch wird sichergestellt, dass kein Thread an der Grenze länger wartet, in dem sie verwendet einen anderen Thread, um den endgültigen Ausschnitt aus höchstens \(\) *k\-Iterationen* auszuführen.  
  
 Der **dynamic** Zeitplan kann nützlich sein, wenn die Threads andere Computerressourcen empfangen, der denselben Effekt wie viele unterschiedliche Arbeitsaufwände für jede Iteration verfügt.  Entsprechend kann der dynamische Zeitplan, wenn die Threads zu dem **nach** Konstrukt in unterschiedlichen Zeiten stammen, in einigen Fällen auch nützlich sein, die über die **Einführungs** Zeitplan möglicherweise vorzuziehen ist.  
  
 Der **Einführungs** Zeitplan ist für den Fall, in dem die Threads möglicherweise zu unterschiedlichen Zeiten in einem **nach** Konstrukt mit jeder Iteration stammen, die ungefähr gleichen Arbeitsaufwand erfordert.  Dies kann der Fall sein, wenn z wird das **nach** Konstrukt aus einem oder mehreren Bereichen oder **nach** Konstrukte mit `nowait`\-Klauseln vorangestellt.  
  
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
  
 Wie **dynamic**Zeitplan **Einführungs** der sichergestellt wird, dass kein Thread an der Grenze länger wartet, als er einen anderen Thread benötigt, um ihre letzte Iteration auszuführen, oder abschließende *k\-Iterationen* , wenn eine Segmentgröße von *k* angegeben wird.  Bei solchen Zeitplänen ist der **Einführungs** Zeitplan für die Eigenschaft gekennzeichnet, dass er die wenigsten Synchronisierungen erforderlich ist.  Für Segmentgröße *k*wird eine typische Implementierung *q \= Höchstwert \(n\/p\)* legen Sie Iterationen zum ersten verfügbaren Thread, *n* *n\-q* und den größeren *der* *p\*k*und Wiederholung fest, bis alle Iterationen zugewiesen sind.  
  
 Wenn die Auswahl des optimalen Zeitplans nicht so klar ist, wie sie für diese Beispiele ist, ist der **Laufzeit** Zeitplan für das Experimentieren mit verschiedenen Zeitplänen und Segmentgrößen zweckmäßig, ohne das Programm zu kompilieren und zu ändern.  Es kann hilfreich sein, wenn der optimalen Zeitplans \(auf eine beliebige vorhersagbare Weise\) aus den Eingabedaten abhängt, in denen das Programm angewendet wird.  
  
 Um ein Beispiel der Kompromisse zwischen verschiedenen Zeitplänen zu sehen, sollten Sie 1000 Iterationen unter 8 Threads freizugeben.  Angenommen, es einen invarianten Arbeitsaufwand in jeder Iteration und in der Verwendung gibt, die als Zeiteinheit.  
  
 Wenn alle Threads gleichzeitig starten, wird der **static** Zeitplan in das Konstrukt 125 Einheiten, ohne die Synchronisierung auszuführen.  Es wird angenommen, dass ein Thread 100 Einheiten entspricht, die beim Ankommen spät sind.  warten anschließend die verbleibenden sieben Threads um 100 Einheiten an der Grenze, und die Ausführungszeit für das gesamte konstrukt vergrößert sich bis 225.  
  
 Da **dynamic** und **Einführungs** Zeitpläne sicherstellen, dass kein Thread auf mehr als eine Einheit an der Grenze wird, tritt beim verzögerten Thread deren Ausführungszeiten für das Konstrukt nur für 138 Einheiten zunimmt, möglicherweise auch durch Verzögerungen der Synchronisierung.  Wenn solche Verzögerungen nicht unwesentlich sind, ist es wichtig, dass die Anzahl von Synchronisierungen 1000 für **dynamic** aber nur 41 für **Einführungs**ist und die Segmentgröße aus einer angenommen wird.  Bei einer Segmentgröße **dynamic** beenden, 25 und 150 Einheiten in beide **Einführungs** sowie mögliche Verzögerungen der erforderlichen Synchronisierungen nur Zahlen, die nun 40 bzw. 20 erzeugt.