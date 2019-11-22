---
title: Häufig auftretende ARM-Migrationsprobleme bei Visual C++
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 518b8872b301a8fcfc0f154cb3d5d0299efb0975
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303224"
---
# <a name="common-visual-c-arm-migration-issues"></a>Häufig auftretende ARM-Migrationsprobleme bei Visual C++

Wenn Sie den Microsoft C++ -Compiler (MSVC) verwenden, C++ kann der gleiche Quellcode in der ARM-Architektur andere Ergebnisse als bei x86-oder x64-Architekturen liefern.

## <a name="sources-of-migration-issues"></a>Quellen für Migrationsprobleme

Viele Probleme, die auftreten können, wenn Sie Code von der x86-oder x64-Architektur zur ARM-Architektur migrieren, beziehen sich auf quellcodekonstrukte, die möglicherweise nicht definiertes, Implementierungs definiertes oder nicht bestimmtes Verhalten aufrufen.

Nicht *definiertes Verhalten* ist das C++ Verhalten, das der Standard nicht definiert, und das durch einen Vorgang verursacht wird, der kein vernünftiges Ergebnis hat: z. b. das umrechnen eines Gleit Komma Werts in eine Ganzzahl ohne Vorzeichen oder das Verschieben eines Werts durch eine Anzahl von Punkten, die negativ oder größer als die Anzahl der Bits im höher gestuften Typ ist.

Durch die C++ *Implementierung definiertes Verhalten* ist das Verhalten, das der Compiler vom Compiler zum Definieren und dokumentieren benötigt. Ein Programm kann sich sicher auf Implementierungs definiertes Verhalten verlassen, obwohl dies möglicherweise nicht portabel ist. Beispiele für Implementierungs definiertes Verhalten sind u. a. die Größe der integrierten Datentypen und ihre Ausrichtungs Anforderungen. Ein Beispiel für einen Vorgang, der von Implementierungs definiertem Verhalten beeinflusst werden kann, ist der Zugriff auf die Liste der Variablen Argumente.

*Nicht spezifiziertes Verhalten* ist das Verhalten C++ , dass der Standard absichtlich nicht deterministisch bleibt. Obwohl das Verhalten als nicht deterministisch angesehen wird, werden bestimmte Aufrufe von nicht spezifiziertem Verhalten von der compilerimplementierung bestimmt. Es ist jedoch nicht erforderlich, dass ein Compilerhersteller das Ergebnis vorbestimmt oder ein konsistentes Verhalten zwischen vergleichbaren aufrufen gewährleistet, und es ist keine Dokumentation erforderlich. Ein Beispiel für ein nicht angegebenes Verhalten ist die Reihenfolge, in der unter Ausdrücke ausgewertet werden, die Argumente für einen Funktions aufrufenthalten.

Andere Migrationsprobleme können auf Hardware Unterschiede zwischen Arm-und x86-oder x64-Architekturen zurückzuführen sein C++ , die auf unterschiedliche Weise mit dem Standard interagieren. Beispielsweise bietet das starke Speichermodell der x86-und x64-Architektur `volatile`qualifizierten Variablen einige zusätzliche Eigenschaften, die verwendet wurden, um bestimmte Arten der Kommunikation zwischen Threads in der Vergangenheit zu vereinfachen. Das schwache Speichermodell der ARM-Architektur unterstützt diese Verwendung nicht, auch wenn C++ der Standard dies nicht erfordert.

> [!IMPORTANT]
>  Obwohl `volatile` einige Eigenschaften erhalten, die verwendet werden können, um eingeschränkte Formen der Thread übergreifenden Kommunikation auf x86 und x64 zu implementieren, reichen diese zusätzlichen Eigenschaften nicht aus, um die Kommunikation zwischen Threads im Allgemeinen zu implementieren. Der C++ Standard empfiehlt, dass eine solche Kommunikation implementiert wird, indem stattdessen die entsprechenden Synchronisierungs primitiven verwendet werden.

Da verschiedene Plattformen diese Verhaltensweisen anders ausdrücken könnten, kann das Portieren von Software zwischen Plattformen schwierig und fehleranfällig sein, wenn Sie vom Verhalten einer bestimmten Plattform abhängig ist. Obwohl viele dieser Arten von Verhalten beobachtet werden können und möglicherweise stabil erscheinen, ist die Verwendung von mindestens nicht portabel, und in Fällen von undefiniertem oder nicht spezifiziertem Verhalten ist auch ein Fehler. Auch das in diesem Dokument erwähnte Verhalten sollte sich nicht darauf verlassen und sich in zukünftigen Compilern oder CPU-Implementierungen ändern.

## <a name="example-migration-issues"></a>Beispiel für Migrationsprobleme

Im weiteren Verlauf dieses Dokuments wird beschrieben, wie das unterschiedliche C++ Verhalten dieser Sprachelemente auf verschiedenen Plattformen zu unterschiedlichen Ergebnissen führen kann.

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>Konvertierung einer Gleit Komma Zahl in eine ganze Zahl ohne Vorzeichen

Bei der ARM-Architektur wird die Konvertierung eines Gleit Komma Werts in eine 32-Bit-Ganzzahl in den nächstgelegenen Wert durchlaufen, den die ganze Zahl darstellen kann, wenn der Gleit Komma Wert außerhalb des Bereichs liegt, der von der Ganzzahl dargestellt werden kann. In den x86-und x64-Architekturen wird die Konvertierung umschlossen, wenn die Ganzzahl nicht signiert ist, oder auf-2147483648 festgelegt, wenn die Ganzzahl signiert ist. Keine dieser Architekturen unterstützt die Konvertierung von Gleit Komma Werten direkt in kleinere ganzzahlige Typen. Stattdessen werden die Konvertierungen in 32 Bits durchgeführt, und die Ergebnisse werden auf eine geringere Größe gekürzt.

Bei der ARM-Architektur bedeutet die Kombination aus Sättigung und Abschneiden, dass bei der Konvertierung in nicht signierte Typen kleinere nicht signierte Typen ordnungsgemäß gefüllt werden, wenn eine 32-Bit-Ganzzahl gefüllt wird, aber ein abgeschnittenes Ergebnis für Werte erzeugt wird, die größer sind als die ein kleinerer Typ kann, aber zu klein darstellen, um die vollständige ganzzahlige 32-Bit-Ganzzahl zu Die Konvertierung ist auch korrekt für 32-Bit-Ganzzahlen mit Vorzeichen, aber das Abschneiden von gesättigten Ganzzahlen mit Vorzeichen ergibt in-1 für positiv satte Werte und 0 für negative Werte. Die Konvertierung in eine kleinere Ganzzahl mit Vorzeichen erzeugt ein nicht vorhersagbares Ergebnis.

Bei den x86-und x64-Architekturen ist die Kombination aus Umschließungs Verhalten bei ganzzahligen Konvertierungen ohne Vorzeichen und der expliziten Bewertung für ganzzahlige Konvertierungen mit Vorzeichen bei Überlauf und beim Abschneiden die Ergebnisse für die meisten Verschiebungen unvorhersagbar, wenn Sie zu groß.

Diese Plattformen unterscheiden sich auch darin, wie Sie die Konvertierung von Nan (not-a-Number) in ganzzahlige Typen verarbeiten. Auf Arm wird NaN in 0x00000000; konvertiert. auf x86 und x64 wird in 0x80000000 konvertiert.

Die Gleit Komma Konvertierung ist nur möglich, wenn Sie wissen, dass sich der Wert innerhalb des Bereichs des ganzzahligen Typs befindet, in den er konvertiert wird.

### <a name="shift-operator---behavior"></a>Verhalten des Verschiebungs Operators (\<\< > >)

In der ARM-Architektur kann ein Wert nach links oder nach rechts bis zu 255 Bits verschoben werden, bevor das Muster wiederholt wird. In x86-und x64-Architekturen wird das Muster bei jedem Vielfachen von 32 wiederholt, es sei denn, die Quelle des Musters ist eine 64-Bit-Variable. in diesem Fall wiederholt sich das Muster bei jedem Vielfachen von 64 in x64 und jedes Vielfache von 256 auf x86, bei dem eine Software Implementierung verwendet wird. Wenn beispielsweise eine 32-Bit-Variable, die den Wert 1 hat, von 32 Positionen nach links verschoben wird, auf Arm ist das Ergebnis 0, auf x86 ist das Ergebnis 1, und auf x64 ist das Ergebnis ebenfalls 1. Wenn es sich bei der Quelle des Werts jedoch um eine 64-Bit-Variable handelt, ist das Ergebnis auf allen drei Plattformen 4294967296, und der Wert wird nicht "umbrochen", bis er 64 Positionen an x64 oder 256 Positionen auf Arm und x86 verschiebt.

Da das Ergebnis einer Verschiebungs Operation, die die Anzahl der Bits im Quelltyp überschreitet, nicht definiert ist, muss der Compiler nicht in allen Situationen über konsistentes Verhalten verfügen. Wenn z. b. beide Operanden einer Schicht zur Kompilierzeit bekannt sind, kann der Compiler das Programm mit einer internen Routine optimieren, um das Ergebnis der Verschiebung vorab zu berechnen und dann anstelle des Verschiebungs Vorgangs das Ergebnis zu ersetzen. Wenn die UMSCHALT Menge zu groß oder negativ ist, kann sich das Ergebnis der internen Routine von dem Ergebnis desselben Verschiebungs Ausdrucks unterscheiden, der von der CPU ausgeführt wird.

### <a name="variable-arguments-varargs-behavior"></a>Verhalten von Variablen Argumenten (VarArgs)

Bei der ARM-Architektur unterliegen Parameter aus der Liste der Variablen Argumente, die auf dem Stapel weitergegeben werden, der Ausrichtung. Beispielsweise wird ein 64-Bit-Parameter an einer 64-Bit-Grenze ausgerichtet. Bei x86 und x64 sind Argumente, die auf dem Stapel weitergegeben werden, nicht der Ausrichtung unterliegen und werden nicht eng verpackt. Dieser Unterschied kann dazu führen, dass eine Variadic-Funktion wie `printf` Speicheradressen liest, die als Auffüll Zeichen auf Arm vorgesehen waren, wenn das erwartete Layout der Variablen Argumentliste nicht genau übereinstimmt, auch wenn es für eine Teilmenge einiger Werte in den x86-oder x64-Architekturen funktionieren kann. Betrachten Sie das folgende Beispiel:

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will "parse" the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

In diesem Fall kann der Fehler behoben werden, indem sichergestellt wird, dass die richtige Format Angabe verwendet wird, damit die Ausrichtung des Arguments berücksichtigt wird. Dieser Code ist korrekt:

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>Reihenfolge der Argument Auswertung

Da Arm-, x86-und x64-Prozessoren so unterschiedlich sind, können Sie unterschiedliche Anforderungen an compilerimplementierungen und auch verschiedene Optimierungsmöglichkeiten bieten. Aus diesem Grund kann ein Compiler mit anderen Faktoren wie der Aufruf Konvention und den Optimierungs Einstellungen Funktionsargumente in einer anderen Reihenfolge auf verschiedenen Architekturen auswerten, oder wenn die anderen Faktoren geändert werden. Dies kann bewirken, dass sich das Verhalten einer APP, die von einer bestimmten Auswertungs Reihenfolge abhängt, unerwartet ändert.

Diese Art von Fehler kann auftreten, wenn Argumente für eine Funktion Nebeneffekte aufweisen, die sich im selben-Befehl auf andere Argumente der Funktion auswirken. Normalerweise ist diese Art der Abhängigkeit leicht zu vermeiden, Sie kann jedoch manchmal durch Abhängigkeiten verdeckt werden, die schwer zu erkennen sind, oder durch Operator Überladung. Sehen Sie sich dieses Codebeispiel an:

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

Dies ist klar definiert, aber wenn `->` und `*` überladene Operatoren sind, wird dieser Code in etwas übersetzt, das dem folgenden ähnelt:

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

Wenn eine Abhängigkeit zwischen `operator->(memory_handle)` und `operator*(p)`besteht, kann der Code auf eine bestimmte Auswertungs Reihenfolge zurückgreifen, auch wenn der ursprüngliche Code so aussieht, als ob keine mögliche Abhängigkeit vorhanden ist.

### <a name="volatile-keyword-default-behavior"></a>volatile-Schlüsselwort Standardverhalten

Der MSVC-Compiler unterstützt zwei unterschiedliche Interpretationen des `volatile` Speicher Qualifizierers, den Sie mithilfe von Compilerschaltern angeben können. Der Schalter [/volatile: ms](reference/volatile-volatile-keyword-interpretation.md) wählt die Microsoft Extended volatile-Semantik aus, die eine starke Reihenfolge garantiert, wie dies bei x86 und x64 der herkömmliche Fall war, weil das Modell für hohe Arbeitsspeicher auf diesen Architekturen hoch war. Der Schalter [/volatile: ISO](reference/volatile-volatile-keyword-interpretation.md) wählt die strikte C++ standardmäßige flüchtige Semantik aus, die keine starke Reihenfolge garantiert.

In der ARM-Architektur lautet der Standardwert **/volatile: ISO** , da ARM-Prozessoren ein schwach gestelltes Speichermodell aufweisen und die Arm-Software nicht über die erweiterte Semantik von **/volatile: ms** verfügt und in der Regel nicht mit der Software, die Sie verwendet, eine Schnittstelle hat. Dennoch ist es manchmal praktisch oder sogar erforderlich, ein Arm-Programm zu kompilieren, um die erweiterte Semantik zu verwenden. Beispielsweise ist es möglicherweise zu teuer, ein Programm für die Verwendung der ISO C++ -Semantik zu portieren, oder die Treibersoftware muss der herkömmlichen Semantik entsprechen, damit Sie ordnungsgemäß funktioniert. In diesen Fällen können Sie den Schalter **/volatile: ms** verwenden. zum erneuten Erstellen der herkömmlichen flüchtigen Semantik auf Arm-Zielen muss der Compiler jedoch alle Lese-oder Schreibvorgänge einer `volatile` Variablen in den Speicher sperren einfügen, um eine starke Reihenfolge zu erzwingen, was sich negativ auf die Leistung auswirken kann.

Auf den x86-und x64-Architekturen ist **/volatile: ms** der Standardwert, da ein Großteil der Software, die bereits für diese Architekturen erstellt wurde, mithilfe von MSVC darauf basiert. Wenn Sie x86-und x64-Programme kompilieren, können Sie den Schalter **/volatile: ISO** angeben, um unnötige Abhängigkeit von der herkömmlichen flüchtigen Semantik zu vermeiden und die Portabilität zu fördern.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Visual C++ für ARM-Prozessoren](configuring-programs-for-arm-processors-visual-cpp.md)
