---
title: 1. Einführung
ms.date: 01/16/2019
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
ms.openlocfilehash: 8c735408bdf9f9a13693bd0ad25df185bb1db42a
ms.sourcegitcommit: 382e247c0f1b4cb7c2dab837b8b6fdff24bff47a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "55087274"
---
# <a name="1-introduction"></a>1. Einführung

Dieses Dokument beschreibt eine Auflistung von Compiler-Direktiven, Bibliotheksfunktionen und Umgebungsvariablen, die Sie verwenden können, um shared Memory-Parallelität in C und C++-Programmen anzugeben. Die in diesem Dokument beschriebene Funktionen werden zusammen als bezeichnet die *OpenMP C/C++-Anwendung die API (Anwendungsprogrammierschnittstelle)*. Das Ziel dieser Spezifikation kann ein Modell bereitstellen, für die parallele Programmierung, die ein Programm über das shared Memory-Architekturen von unterschiedlichen Herstellern portabel sein. Die Compiler von vielen Anbietern unterstützt der OpenMP-C-/C++-API. Weitere Informationen zu OpenMP, einschließlich der *OpenMP Fortran Anwendungsprogrammierschnittstelle*, finden Sie unter der folgenden Website:

[https://www.openmp.org](https://www.openmp.org)

Die Direktiven Bibliotheksfunktionen und Umgebungsvariablen, die in diesem Dokument können Sie erstellen und Verwalten von parallelen Programmen und Portabilität. Die Anweisungen erweitern die C- und C++ sequenzielle Programmiermodell, das mit einzelnen Programm, das mehrere Datenkonstrukte (SPMD) Arbeitsteilungskonstrukte und Synchronisierungskonstrukten. Sie unterstützen außerdem die gemeinsame Nutzung und Privatisierung von Daten. Compiler, die der OpenMP-C- und C++-API unterstützen gehören eine Befehlszeilenoption für den Compiler an, der aktiviert und ermöglicht die Darstellung alle OpenMP Compilerdirektiven.

## <a name="11-scope"></a>1.1 Bereich

In dieser Spezifikation werden nur Benutzer gesteuerte Parallelisierung ermöglicht, in dem Sie explizit die Aktionen definieren den Compiler behandelt und Laufzeitsystem ergreifen, um die Anwendung parallel ausgeführt. OpenMP-C- und C++-Implementierungen nicht erforderlich, um zu prüfen, ob Abhängigkeiten, Konflikte, Deadlocks, Racebedingungen oder andere Probleme, die in der falschen programmausführung. Sie sind dafür verantwortlich, sicherzustellen, dass die Anwendung mithilfe der OpenMP-C- und C++-API-Konstrukte ordnungsgemäß ausgeführt wird. Automatische Parallelisierung vom Compiler generierte und an den Compiler Anweisungen, um solche Parallelisierung zu unterstützen, sind nicht in diesem Dokument behandelt.

## <a name="12-definition-of-terms"></a>1.2. Begriffsdefinition

Die folgenden Begriffe werden in diesem Dokument verwendet:

- barrier

  Ein Synchronisierungspunkt,, den alle Threads in einem Team erreichen muss.  Jeder Thread wartet, bis alle Threads im Team, das an dieser Stelle eingehen. Es sind explizite Barrieren identifizierte Direktiven und implizite Hindernisse, die durch die Implementierung erstellt.

- Konstrukt

  Ein Konstrukt ist eine Anweisung an. Es besteht aus einer Anweisung, gefolgt von einem strukturierten Block. Bestimmte Direktiven sind nicht Teil eines Konstrukts. (Finden Sie unter *-Direktive von Openmp* in [Anhang C](c-openmp-c-and-cpp-grammar.md)).

- Anweisung

  Eine C- oder C++ `#pragma` gefolgt von der `omp` Bezeichner, andere Text und eine neue Zeile. Die Richtlinie gibt Verhalten des Programms an.

- Dynamische Block

  Alle Anweisungen in der *lexikalische Block*, und jede Anweisung innerhalb einer Funktion, die als Ergebnis der Ausführung von Anweisungen innerhalb der lexikalischen Block ausgeführt wird. Einem dynamischen Grad wird auch als bezeichnet ein *Region*.

- lexikalische Block

  Anweisungen lexikalisch frei, die innerhalb einer *vor einem strukturierten Block*.

- Master-thread

  Der Thread, der ein Team erstellt bei einer *parallelen Bereichs* eingegeben wird.

- parallelen Bereichs

  Anweisungen, die an einer parallelen OpenMP-Konstrukt gebunden und können von vielen Threads ausgeführt werden.

- private

  Eine private Variable benennt einen Block von Speicher, der für den Thread, der den Verweis eindeutig ist. Es gibt mehrere Möglichkeiten, um anzugeben, dass eine Variable privat ist: eine Definition innerhalb eines parallelen Bereichs ist, eine `threadprivate` -Direktive einer `private`, `firstprivate`, `lastprivate`, oder `reduction` -Klausel, oder Verwenden der Variablen als eine `for`Schleife Steuerelementvariable in einem `for` -Schleife unmittelbar nach einem `for` oder `parallel for` Richtlinie.

- Bereich

  Eine dynamische Umfang.

- serielle region

  Nur ausgeführte Anweisungen der *master-Thread* außerhalb der dynamischen Wertebereich einer *parallelen Bereichs*.

- Serialisieren

  Um eine parallele Konstrukt mit auszuführen:

  - ein Team von Threads, die mit nur einem einzelnen Thread (der die master-Thread für das parallele Konstrukt ist)

  - Reihenfolge der Ausführung für die Anweisungen in einem strukturierten Block (dem order, als ob der Block nicht als Teil eines parallelen Konstrukts waren), und

  - keine Auswirkung auf den Rückgabewert von `omp_in_parallel()` (abgesehen von den Auswirkungen einer parallele Konstrukten geschachtelt).

- Freigegeben

  Eine freigegebene Variable benennt einen einzelnen Block des Speichers. Alle Threads in einem Team, die auf diese Variable zugreifen zugreifen, auch diese einzelnen Block Storage.

- vor einem strukturierten block

  Ein strukturierter Block ist eine Anweisung aus (einzelne oder zusammengesetzte), die einen einzelnen Eintrag, und eine einzelne beenden. Gibt es ist ein Sprung in oder aus einer Anweisung, die Anweisung einen strukturierten Block. (Diese Regel umfasst einen Aufruf von `longjmp`(3C) oder die Verwendung der `throw`, obwohl ein Aufruf von `exit` ist zulässig.) Wenn die Ausführung immer an das öffnende beginnt `{` und immer endet mit dem schließenden `}`, eine verbundanweisung wird einem strukturierten Block. Eine Ausdrucksanweisung, auswahlanweisung, iterationsanweisung oder `try` Block ist einem strukturierten Block auf, wenn die entsprechende verbundanweisung erworben haben, schließen Sie ihn in `{` und `}` ein strukturierter Block wäre. Eine Jump-Anweisung, die Anweisung mit Bezeichnung oder die deklarationsanweisung keinem strukturierten Block.

- Team

  Ein oder mehrere Threads, die bei der Ausführung eines Konstrukts darstellen.

- Thread

  Eine Ausführung-Entität mit einem seriellen Kontrollfluss, ein Satz von privaten Variablen und Zugriff auf freigegebene Variablen.

- -Variable

  Ein Bezeichner, der optional von Namespace-Namen qualifizierten Namen, die ein Objekt.

## <a name="13-execution-model"></a>1.3 Ausführungsmodell

OpenMP verwendet das Fork / Join-Modell der parallelen Ausführung. Obwohl dieses Fork / Join-Modell zur Lösung verschiedener Probleme hilfreich sein kann, ist es für große Array-basierte Anwendungen zugeschnitten. OpenMP-Programme zu unterstützen, die ordnungsgemäß als paralleler Programme ausgeführt werden (viele Threads und einen vollständigen OpenMP-Unterstützungsbibliothek) dient. Es ist auch für Programme, die ordnungsgemäß als sequenzielle Programme (Anweisungen ignoriert, und eine einfache OpenMP-Stubs-Bibliothek) auszuführen. Allerdings es ist möglich und zulässig, um ein Programm zu entwickeln, die nicht ordnungsgemäß verhält, wenn sequenziell ausgeführt. Darüber hinaus können verschiedene Grade der Parallelität aufgrund von Änderungen an der Zuordnung von numerischen Operationen verschiedene numerische Ergebnisse führen. Z. B. möglicherweise eine Verringerung der seriellen außerdem ein anderes Muster von Zuordnungen hinzufügen, als eine parallele Reduzierung. Diese anderen Zuordnungen können es sich um die Ergebnisse der gleitkommaaddition ändern.

Ein Programm geschrieben, mit der OpenMP-C-/C++-API startet die Ausführung als einzelner Thread der Ausführung mit der Bezeichnung der *master-Thread*. Die master-Thread wird bis das erste parallele-Konstrukt in einer seriellen Region ausgeführt. In der OpenMP-C-/C++-API die `parallel` Richtlinie stellt eine parallele Konstrukt dar. Bei ein paralleles Konstrukts auftreten der master-Thread erstellt, ein Team von Threads, und der Master wird master des Teams. Jeder Thread im Team, das die Anweisungen in der dynamischen Wertebereich eines parallelen Bereichs ist, mit Ausnahme der Arbeitsteilungskonstrukte ausgeführt. Alle Threads in das Team müssen Arbeitsteilungskonstrukte in der gleichen Reihenfolge auftreten und eine oder mehrere Threads führt die Anweisungen in einem zugehörigen strukturierten Block aus. Die Grenze, die am Ende eines Konstrukts ohne Freigabe von Arbeit impliziert eine `nowait` -Klausel von allen Threads im Team, das ausgeführt wird.

Wenn ein Thread auf ein freigegebenes Objekt ändert, wird nicht nur ihrer eigenen ausführungsumgebung, sondern auch die anderen Threads in der Anwendung beeinträchtigt. Die Änderung ist garantiert abgeschlossen ist, aus der Perspektive eines anderen Threads, die am nächsten Sequenz (wie in der Basissprache definiert) werden nur dann, wenn das Objekt als flüchtig deklariert ist. Andernfalls ist die Änderung abgeschlossen sein, nach dem ersten thread ändern, die garantiert. Die anderen Threads dann (oder parallel) finden Sie unter einem `flush` -Direktive, die das Objekt (entweder implizit oder explizit) angibt. Wenn die `flush` Direktiven, die durch andere OpenMP-Anweisungen impliziert werden nicht die richtige Reihenfolge der Nebeneffekte garantieren, ist der Programmierer dafür verantwortlich, geben Sie zusätzliche, explizite `flush` Anweisungen.

Nach Abschluss das parallele Konstrukt wird die Threads im Team synchronisieren, um eine implizite Barriere, und nur die master-Thread wird die Ausführung fortgesetzt. Eine beliebige Anzahl von parallelen Konstrukten kann in einem einzelnen Programm angegeben werden. Daher kann ein Programm erstellen Sie eine Verzweigung und verknüpfen oft während der Ausführung.

OpenMP C-/C++-API ermöglicht es Programmierern, verwenden Sie die Anweisungen in Funktionen, die aus den parallelen Konstrukten aufgerufen. Anweisungen, die nicht im lexikalischen Block eines parallelen Konstrukts angezeigt, aber möglicherweise liegen in der dynamischen Block heißen *verwaiste* Anweisungen. Mit verwaisten-Anweisungen können wichtige Teile ihres Programms Programmierer mit nur minimale Änderungen an der sequenziellen Programm parallel ausgeführt werden. Mit dieser Funktionalität können Sie code auf den oberen Ebenen der Aufrufstruktur der Anwendung den parallele Konstrukten und verwenden Direktiven, um die Ausführung in der aufgerufenen Funktionen zu steuern.

Nicht synchronisierte Aufrufe von C- und C++ ausgegeben, dass Funktionen, die in der gleichen Datei Schreiben in Ausgabe führen können, in dem Daten geschrieben, wenn unterschiedliche Threads nicht deterministischen Reihenfolge angezeigt wird. Auf ähnliche Weise können nicht synchronisierte Aufrufe von Funktionen zu geben, die von der gleichen Datei gelesen, Daten in nicht deterministischen Reihenfolge lesen. Nicht synchronisierte Verwenden von e/a, so, dass jeder Thread eine andere Datei, greift auf die gleichen Ergebnisse wie die serielle Ausführung der e/a-Funktionen erstellt.

## <a name="14-compliance"></a>1.4 Kompatibilität

Eine Implementierung der OpenMP-C-/C++-API ist *OpenMP-kompatible* Wenn es erkennt und behält die Semantik der alle Elemente dieser Spezifikation ist, wie in Kapitel 1, 2, 3, 4, angeordnet und Anhang C. Anhänge A, B, D, E und F für Informationen nur zu Evaluierungszwecken nutzen und sind nicht Teil der Spezifikation. Implementierungen, die nur eine Teilmenge der API enthalten sind, nicht OpenMP-kompatibel.

Das OpenMP-C- und C++-API ist eine Erweiterung für die Basissprache, die durch eine Implementierung unterstützt wird. Wenn die Basissprache unterstützt ein Sprachkonstrukt oder eine Erweiterung, die angezeigt wird in diesem Dokument, die Implementierung von OpenMP muss sich nicht unterstützt.

Alle standardmäßigen C- und C++-Bibliotheksfunktionen und integrierte Funktionen (d. h. Funktionen, die von denen der Compiler verfügt über spezifische Kenntnisse) muss threadsicher sein. Nicht synchronisierte Verwenden von threadsichere Funktionen, wenn unterschiedliche Threads innerhalb eines parallelen Bereichs führen nicht nicht definiertem Verhalten. Allerdings kann das Verhalten sein keiner seriellen Region identisch. (Eine zufällige Zahl Generierungsfunktion ist ein Beispiel.)

OpenMP C-/C++-API gibt an, dass bestimmte Verhalten *Implementierung definiert.* Keine entsprechende Implementierung von OpenMP ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen. Eine Liste der die Implementierung definiertes Verhalten, finden Sie unter [Anhang E](e-implementation-defined-behaviors-in-openmp-c-cpp.md).

## <a name="15-normative-references"></a>1.5 Normative Verweise

- ISO/IEC 9899: 1999, *Technologie - Programmiersprachen - K*. Diese OpenMP-API-Spezifikation bezeichnet ISO/IEC 9899: 1999 als C99.

- ISO/IEC-9899:1990 *Technologie - Programmiersprachen - K*. Diese OpenMP-API-Spezifikation bezeichnet ISO/IEC 9899:1990 als C90.

- ISO/IEC-14882:1998 *Informationen Technologie - Programmiersprachen – C++*. Diese OpenMP-API-Spezifikation, die als C++, ISO/IEC 14882:1998 bezeichnet werden.

Bei dieser OpenMP-API-Spezifikation in C verweist, wird der Verweis auf die Basissprache, die von der Implementierung unterstützt festgelegt.

## <a name="16-organization"></a>1.6 Organization

- [Funktionen der Laufzeitbibliothek](3-run-time-library-functions.md)
- [Umgebungsvariablen](4-environment-variables.md)
- [Die Implementierung definiertes Verhalten in OpenMP C/C++](e-implementation-defined-behaviors-in-openmp-c-cpp.md)
- [Neue Features in OpenMP C/C++-Version 2.0](f-new-features-and-clarifications-in-version-2-0.md)
