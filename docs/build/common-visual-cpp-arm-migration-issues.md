---
title: Häufig auftretende ARM-Migrationsprobleme bei Visual C++
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 78d87000240acd394edf823a778ae29060c6d09c
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220883"
---
# <a name="common-visual-c-arm-migration-issues"></a>Häufig auftretende ARM-Migrationsprobleme bei Visual C++

Bei Verwendung von Microsoft C++ Compiler (MSVC), die gleiche C++ Quellcode möglicherweise zu unterschiedlichen Ergebnissen auf der ARM-Architektur führen, als auf X86 oder X64 Architekturen.

## <a name="sources-of-migration-issues"></a>Quellen von Migrationsproblemen

Viele Probleme, die auftreten können, wenn Sie Code aus den X86 oder X64 Architekturen der ARM-Architektur migrieren beziehen sich auf Quellcode-Konstrukte, die nicht definiert, implementierungsdefinierte oder nicht angegebene Verhalten aufrufen kann.

*Ein nicht definiertes Verhalten* Verhalten, das der C++-Standard nicht definiert ist, und, wird verursacht, wenn ein Vorgang, der kein angemessener Ergebnis hat: z. B. Konvertieren von Wert einer Gleitkommazahl in ganze Zahl ohne Vorzeichen oder das Verschieben eines Werts durch eine Anzahl von Positionen ist negativ oder überschreitet die Anzahl der Bits im sein höhergestufter Typ.

*Die Implementierung definiertes Verhalten* trifft, die der C++-Standard erfordert die Compiler-Anbieter zum Definieren und dokumentieren. Ein Programm kann die Implementierung definiertes Verhalten, verlassen, obwohl dies also nicht portabel sein kann. Beispiele für die Implementierung definiertes Verhalten sind die Größen der integrierten Datentypen und ihrer ausrichtungsanforderungen. Ein Beispiel für einen Vorgang, der durch die Implementierung definiertes Verhalten betroffen sein könnten greift auf die Variable Argumentliste.

*Ohne Angabe von Verhalten* Verhalten, das bewirkt, der C++-Standard absichtlich nicht deterministisch dass ist. Obwohl das Verhalten nicht deterministisch erachtet wird, werden bestimmte Aufrufe von nicht definiertes Verhalten durch die compilerimplementierung bestimmt. Allerdings besteht keine Notwendigkeit für eine Compiler-Anbieter festlegen, das das Ergebnis Netzwerkkonto oder garantiert konsistentes Verhalten zwischen vergleichbare aufrufen, und besteht keine Notwendigkeit für die Dokumentation. Ein Beispiel für nicht angegebene Verhalten ist die Reihenfolge, in der untergeordnete Ausdrücke, die Argumente für einen Funktionsaufruf enthalten, ausgewertet werden.

Andere Probleme bei der Paketmigration können zugeschrieben werden, auf Hardwareunterschiede zwischen ARM und X86 oder X64 Architekturen, die mit dem C++-standard anders zu interagieren. Z. B. das strenge Speichermodell der X86- und X64-Architektur bietet `volatile`-qualifizierten Variablen einige zusätzlichen Eigenschaften, die verwendet wurden, um bestimmte Arten von Kommunikation zwischen Threads in der Vergangenheit zu ermöglichen. Schwache Speichermodell der ARM-Architektur unterstützt diese Verwendung nicht, aber noch der C++-Standard erfordert es.

> [!IMPORTANT]
>  Obwohl `volatile` bieten einige Eigenschaften, die verwendet werden können, implementieren Sie eingeschränkte Formen der Kommunikation zwischen Threads auf X86- und X64, diese zusätzlichen Eigenschaften nicht ausreichend zum Implementieren sind Kommunikation zwischen Threads Kommunikation im Allgemeinen. Der C++-Standard empfiehlt, dass eine solche Kommunikation stattdessen mit der entsprechenden Synchronisierungsprimitiven implementiert werden.

Da verschiedene Plattformen dieser Art von Verhalten unterschiedlich darstellen können, kann der Software zwischen Plattformen Portieren sein, schwierig und fehleranfällig, wenn sie das Verhalten von einer bestimmten Plattform abhängig ist. Obwohl viele dieser Arten von Verhalten beobachtet werden können, und stabile wird möglicherweise angezeigt, der vertrauenden Seite, auf diesen mindestens nicht portabel ist, und in den Fällen nicht definiert wurde oder nicht angegebene Verhalten ist auch ein Fehler. Auch das Verhalten, das in diesem Dokument genannten ist sollten nicht die Parameterübergabe genutzt werden, und kann in Zukunft ändern, Compiler oder CPU-Implementierungen.

## <a name="example-migration-issues"></a>Beispiel-Migrationsprobleme

Der Rest dieses Dokuments wird beschrieben, wie das unterschiedliche Verhalten dieser Elemente der C++-Sprache unterschiedliche Ergebnisse auf verschiedenen Plattformen erstellen kann.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>Konvertierung von Gleitkomma in Ganzzahl ohne Vorzeichen

Sättigt auf der ARM-Architektur und die Konvertierung eines Gleitkommawerts in eine 32-Bit-Ganzzahl auf den nächsten Wert, den die ganze Zahl darstellen kann, wenn der Gleitkommawert außerhalb des Bereichs liegt, die die ganze Zahl darstellen kann. Auf die Architekturen X86- und X64 umschließt die Konvertierung Wenn die ganze Zahl ohne Vorzeichen ist oder auf-2147483648 festgelegt ist, wenn die ganze Zahl signiert ist. Keines dieser Architekturen unterstützen direkt die Konvertierung von Gleitkommawerten in kleinere ganzzahlige Typen. Stattdessen werden die Konvertierungen werden durchgeführt, um 32-Bit, und die Ergebnisse werden auf eine kleinere Größe abgeschnitten.

Der ARM-Architektur, die Kombination von Überlastung des Netzwerks und Abschneiden bedeutet, dass die Konvertierung in Typen ohne Vorzeichen ordnungsgemäß kleineren Typen ohne Vorzeichen sättigt sättigt 32-Bit-Ganzzahl, jedoch abgeschnittene Ergebnis für Werte, die größer sind die kleineren Typ kann jedoch zu klein darstellen, auf die 32-Bit-Ganzzahl auslasten. Konvertierung auch sättigt ordnungsgemäß für 32-Bit-Ganzzahlen mit Vorzeichen, die Kürzung von gesättigte, signierten Ganzzahlen-1 für Werte werde, positiv ausgelastet und 0 für Werte sich negativ auf erschöpft führt jedoch. Die Konvertierung in eine kleinere Ganzzahl mit Vorzeichen Ergebnis abgeschnitten, die nicht vorhersagbar ist.

Für die X86- und X64-Architekturen die Kombination von umbrechende Verhalten für ganze Zahl ohne Vorzeichen Konvertierungen und explizite Ressourcen für ganze Zahl mit Vorzeichen Konvertierungen, bei einem Überlauf zusammen mit abschneiden, werden die Ergebnisse für die meisten Verschiebungen unvorhersehbar, wenn sie sich befinden zu groß.

Diese Plattformen unterscheiden sich auch in, wie sie die Konvertierung von NaN (Not a Number) in ganzzahlige Typen behandeln. Auf ARM konvertiert NaN, 0 x 00000000; auf X86- und X64 konvertiert in 0 x 80000000.

Gleitkommakonvertierung kann nur zuverlässig, wenn Sie wissen, dass der Wert innerhalb des Bereichs des ganzzahligen Typs ist, die sie in konvertiert wird.

### <a name="shift-operator---behavior"></a>Shift-Operator (\< \< >>) Verhalten

Der ARM-Architektur kann ein Wert nach links oder rechts bis zu 255 Bits verschoben werden vor Beginn der das Muster wiederholt werden soll. X86- und X64 Architekturen wird das Muster auf jedes Vielfache von 32 wiederholt, es sei denn, die Quelle des Musters eine 64-Bit-Variable ist; In diesem Fall wird das Muster wiederholt, auf jedem Vielfaches von 64 auf x 64 "und" jedes Vielfache von 256 auf X86, in denen eine Implementierung von Software beschäftigt ist. Z. B. für eine 32-Bit-Variable mit einem Wert von 1, die verschoben, um 32 Positionen nach links, auf ARM ist das Ergebnis 0 auf X86 lautet das Ergebnis 1 und unter X64 ist das Ergebnis auch 1. Allerdings ist die Quelle des Werts einer 64-Bit-Variablen, ist das Ergebnis auf allen drei Plattformen 4294967296, und der Wert nicht "umbrochen werden", bis er 64 Positionen auf X64 oder 256 Positionen auf ARM und X86 verschoben hat.

Da das Ergebnis eines schiebevorgangs, die die Anzahl der Bits in den Quelltyp überschreitet nicht definiert ist, wird der Compiler ist nicht erforderlich, um konsistentes Verhalten in allen Situationen zu erhalten. Beispielsweise wenn beide Operanden in einer Schicht zum Zeitpunkt der Kompilierung bekannt sind, kann der Compiler das Programm mithilfe von einer internen Routine auf das Ergebnis der Verschiebung im Voraus berechnen aus, und Ersetzen Sie dann das Ergebnis anstelle der Verschiebungsvorgang optimieren. Wenn die Verschiebung zu groß ist oder negativ ist, das Ergebnis der Routine, interne weicht möglicherweise das Ergebnis das gleiche verschiebungsausdrucks Wert wie von der CPU ausgeführt.

### <a name="variable-arguments-varargs-behavior"></a>Verhalten mit Variablen Argumenten (Varargs)

Auf der ARM-Architektur und unterliegen Ausrichtung Parameter aus der Argumentliste variabler, die auf dem Stapel übergeben werden. Beispielsweise wird ein 64-Bit-Parameter auf einer 64-Bit-Grenze ausgerichtet. Auf X86- und X64 werden Argumente, die auf dem Stapel übergeben sind nicht Ausrichtung und Pack eng. Dieser Unterschied kann dazu führen, dass eine Variadic-Funktion wie `printf` Speicheradressen zu lesen, die eigentlich mit Leerstellen aufgefüllt, auf die ARM, wenn der Argumentliste variabler als Layout erwartete nicht genau, zugeordnet ist, obwohl es für eine Teilmenge der einige Werte für die X86 funktioniert möglicherweise oder X64 Architekturen. Betrachten Sie das folgende Beispiel:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

In diesem Fall kann der Fehler behoben werden, indem Sie sicherstellen, dass die richtige Formatangabe verwendet wird, damit an, dass die Ausrichtung des Arguments berücksichtigt wird. Dieser Code ist korrekt:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Auswertungsreihenfolge des Arguments

Da ARM, x 86 "und" X64 Prozessoren so unterschiedlich sind, können sie verschiedene Anforderungen für die compilerimplementierungen und auch andere Möglichkeiten für Optimierungen stellen. Aus diesem Grund kann zusammen mit anderer Faktoren wie der Aufrufkonvention und Optimierung von Einstellungen, ein Compiler auswerten, Argumente der Funktion in einer anderen Reihenfolge auf verschiedenen Architekturen oder wenn die andere Faktoren geändert werden. Dadurch kann das Verhalten einer App, die abhängig von einer bestimmten Auswertungsreihenfolge unerwartet geändert.

Diese Art von Fehler kann auftreten, wenn Argumente für eine Funktion Nebeneffekte haben, die andere Argumente der Funktion im selben Aufruf auswirken. In der Regel dieser Art von Abhängigkeit ist leicht zu vermeiden, aber manchmal verdeckt werden können, die die Abhängigkeiten, die nur schwer zu erkennen oder Überladen von Operatoren. Beachten Sie in diesem Codebeispiel wird ein:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Dies scheint klar definierte, jedoch möglich, wenn `->` und `*` überladene Operatoren werden, und klicken Sie dann diesen Code in etwas übersetzt wird die folgende angezeigt:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Und es eine Abhängigkeit zwischen `operator->(memory_handle)` und `operator*(p)`, der Code kann mit einer bestimmten Auswertungsreihenfolge abhängig, auch wenn der ursprüngliche Code aussieht besteht keine Abhängigkeit möglich.

### <a name="volatile-keyword-default-behavior"></a>Schlüsselwort "volatile" Standardverhalten

Der MSVC-Compiler unterstützt zwei verschiedene Interpretationen der der `volatile` Storage-Qualifizierer, die Sie angeben können, indem Sie mithilfe von Compilerschaltern. Die [angegebenem](reference/volatile-volatile-keyword-interpretation.md) Switch wählt Microsoft erweitert der traditionelle Fall für X86 und X64 aufgrund das strenge Speichermodell für diese Architekturen wurde volatile-Semantik, die starke Reihenfolge garantiert. Die [/volatile:iso](reference/volatile-volatile-keyword-interpretation.md) Switch wählt die strikte C++ standard flüchtige Semantik, die starke Sortierung garantiert nicht.

Auf der ARM-Architektur und der Standardwert ist **/volatile:iso** da ARM-Prozessoren mit wöchentlichem haben sortiert Memory-Modell und ARM-Software mit eine älteren von der vertrauenden Seite, auf die erweiterten Semantik der keine **angegebenem**  und nicht in der Regel für die Kommunikation mit Software, die ausführt. Allerdings es ist trotzdem manchmal sogar erforderlich zum Kompilieren eines Programms ARM, um die erweiterten Semantik verwendet wird. Z. B. möglicherweise zu kostspielig So portieren Sie ein Programm, um die ISO C++-Semantik verwendet wird, oder Treibersoftware möglicherweise zu der herkömmlichen Semantik zum ordnungsgemäßen entsprechen. In diesen Fällen können Sie die **angegebenem** switch; jedoch um die herkömmlichen volatile-Semantik für ARM-Ziele neu zu erstellen, der Compiler muss einfügen Arbeitsspeicherbarrieren um jede Lese- oder Schreibvorgang für eine `volatile` Variable, um zu erzwingen starke Sortierung, die sich negativ auf die Leistung aufweisen kann.

Auf der X86- und X64-Architekturen, die der Standardwert ist **angegebenem** da ein Großteil der Software, die bereits für diese Architekturen erstellt wurde, indem mithilfe von MSVC darauf angewiesen ist. Wenn Sie X86- und X64 Programme kompilieren, können Sie angeben der **/volatile:iso** wechseln, um zu verhindern, dass unnötige Abhängigkeit von der herkömmlichen volatile-Semantik und Förderung der Portabilität.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Visual C++ für ARM-Prozessoren](configuring-programs-for-arm-processors-visual-cpp.md)
