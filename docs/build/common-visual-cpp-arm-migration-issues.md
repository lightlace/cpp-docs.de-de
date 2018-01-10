---
title: "Häufige Visual C++-ARM-Migrationsprobleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 39902d953702703a4367be24bf6c1cd011863289
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="common-visual-c-arm-migration-issues"></a>Häufig auftretende ARM-Migrationsprobleme bei Visual C++

Die gleiche Visual C++-Quellcode möglicherweise unterschiedliche Ergebnisse auf die ARM-Architektur erzeugen, als auf X86 oder X64 Architekturen funktioniert.  
  
## <a name="sources-of-migration-issues"></a>Quellen von Migrationsproblemen  

Viele Probleme, die auftreten können, wenn die Migration von Code aus der X86 oder X64 Architekturen ARM-Architektur beziehen sich auf Quellcode Konstrukte, die nicht definiert, die Implementierung definiertes oder nicht angegebene Verhalten aufrufen kann.  
  
*Nicht definiertes Verhalten*  
Verhalten, wird aufgrund eines Vorgangs, der keine angemessenen Ergebnis hat, die der C++-Standard definiert keine – beispielsweise einen Gleitkommawert in eine Ganzzahl ohne Vorzeichen zu konvertieren, oder Verschieben eines Werts von einer Anzahl von Positionen, die ist ein negativer Wert oder überschreitet die Anzahl der die Bits im sein höhergestufter Typ.  
  
*Die Implementierung definiertes Verhalten*  
Verhalten, die die C++-Standard der Compiler-Anbieter erfordert, um zu definieren und zu dokumentieren. Ein Programm kann problemlos auf die Implementierung definiertes Verhalten beruhen, obwohl dies daher nicht portabel sein kann. Beispiele für die Implementierung definiertes Verhalten sind die Größen der integrierten Datentypen und ihre ausrichtungsanforderungen. Ein Beispiel für einen Vorgang, der durch die Implementierung definiertes Verhalten betroffen sein könnten greift auf die Variable Argumentliste.  
  
*Nicht definiertes Verhalten*  
Verhalten, das der C++-Standard nicht deterministische absichtlich verlässt. Obwohl das Verhalten als nicht deterministisch angesehen wird, werden bestimmte Aufrufe von nicht definiertes Verhalten durch die Implementierung des Compilers bestimmt. Allerdings besteht keine Notwendigkeit für eine Compiler-Anbieter festlegen, das das Ergebnis Netzwerkkonto oder einheitliches Verhalten zwischen vergleichbare Aufrufe zu gewährleisten und besteht keine Notwendigkeit für die Dokumentation. Ein Beispiel für nicht definiertes Verhalten ist die Reihenfolge, in welcher Unterausdrücken – darunter Argumente an einen Funktionsaufruf – ausgewertet werden.  
  
Andere Probleme bei der Paketmigration können auf Hardwareunterschiede zwischen ARM und X86 oder X64, die mit dem C++-standard anders interagieren zurückverfolgt werden. Z. B. die starke Speichermodell der X86- und X64-Architektur bietet `volatile`-qualifiziert Variablen einige zusätzlichen Eigenschaften, die verwendet wurden, um bestimmte Arten von Kommunikation zwischen Threads in der Vergangenheit zu ermöglichen. Jedoch schwache Speichermodell für die ARM-Architektur unterstützt diese Verwendung nicht, und der C++-Standard erfordert es.  
  
> [!IMPORTANT]
>  Obwohl `volatile` Gewinne einige Eigenschaften, die verwendet werden können, um eingeschränkte Formen der Kommunikation zwischen Threads auf X86- und X64, diese zusätzlichen Eigenschaften zu implementieren nicht ausreichend sind, um implementieren thread prozessübergreifende Kommunikation im Allgemeinen. Der C++-Standard empfiehlt, dass solche Kommunikation mithilfe der entsprechenden Synchronisierungsprimitiven stattdessen implementiert werden.  
  
Da unterschiedliche Plattformen unterschiedlich diese Arten von Verhalten express können, kann zwischen Plattformen portieren, schwierig und fehleranfälliger, wenn sie das Verhalten einer bestimmten Plattform abhängig. Obwohl viele dieser Arten von Verhalten beobachtet werden können, und möglicherweise stabil angezeigt, der vertrauenden Seite auf diesen mindestens nicht portabel ist, und im Fall von Verhalten nicht definiert oder nicht angegeben, wird auch ein Fehler. Auch das Verhalten, das in diesem Dokument erwähnten ist sollte nicht genutzt werden, und kann in Zukunft ändern, Compiler oder CPU-Implementierungen.  
  
## <a name="example-migration-issues"></a>Beispiel-Migrationsprobleme  

Der Rest dieses Dokuments wird beschrieben, wie das unterschiedliche Verhalten dieser C++ Language-Elemente unterschiedliche Ergebnisse auf verschiedenen Plattformen erstellt werden kann.  
  
### <a name="conversion-of-floating-point-to-unsigned-integer"></a>Konvertierung von Gleitkommazahlen in Ganzzahl ohne Vorzeichen  

Auf der ARM-Architektur sättigt Konvertierung eines Gleitkommawerts in eine 32-Bit-Ganzzahl, auf den nächsten Wert, den die Ganzzahl darstellen kann, wenn der Gleitkommawert außerhalb des Bereichs liegt, die die ganze Zahl darstellen kann. Auf die Architekturen X86- und X64 umschließt die Konvertierung Wenn ganze Zahlen ohne Vorzeichen ist oder auf-2147483648 festgelegt ist, wenn die ganze Zahl signiert ist. Keines dieser Architekturen unterstützen direkt die Konvertierung von Gleitkommawerten in kleinere ganzzahlige Typen. stattdessen die Konvertierungen werden auf 32 Bits durchgeführt, und die Ergebnisse werden auf eine kleinere Größe abgeschnitten.  
  
Die ARM-Architektur, die Kombination von Sättigung und Abschneiden bedeutet, dass die Konvertierung in Typen ohne Vorzeichen ordnungsgemäß kleinere Typen ohne Vorzeichen sättigt sättigt eine 32-Bit-Ganzzahl, jedoch führt eine abgeschnittene Ergebnis für Werte, die größer sind als die kleineren Typ kann jedoch zu klein darstellen, auf die 32-Bit-Ganzzahl stark beanspruchen. Konvertierung auch sättigt ordnungsgemäß für 32-Bit-Ganzzahlen mit Vorzeichen, aber abgeschnitten wiederum überlastete, signierten Ganzzahlen-1 für positiv gesättigt Werte und 0 für die Werte negativ gesättigt führt. Die Konvertierung in eine kleinere Ganzzahl mit Vorzeichen erzeugt eine abgeschnittene Ergebnis, das die schlecht vorhersagbar ist.  
  
Für die X86- und X64-Architekturen die Kombination von umbrechende Verhalten für ganze Zahl ohne Vorzeichen Konvertierungen und explizite Bewertung für ganze Zahl mit Vorzeichen Konvertierungen, bei einem Überlauf zusammen mit abschneiden, werden die Ergebnisse für die meisten Verschiebungen unvorhersehbar, wenn sie sind zu groß.  
  
Diese Plattformen unterscheiden sich auch, wie sie die Konvertierung von NaN (Not a Number) in ganzzahlige Typen verarbeiten. Konvertiert auf ARM "" "NaN" auf 0 x 00000000; auf X86- und X64 konvertiert in 0 x 80000000.  
  
Gleitkommakonvertierung kann nur auf die zugegriffen werden, wenn Sie wissen, dass der Wert innerhalb des Bereichs des ganzzahligen Typs ist, die er konvertiert wird.  
  
### <a name="shift-operator---behavior"></a>Shift-Operator (<\< >>) Verhalten  

Auf der ARM-Architektur kann ein Wert nach links oder rechts bis zu 255 Bits verschoben wird, wie vor Beginn des Musters zu wiederholen. Auf X86- und X64 Architekturen ist das Muster an jedes Vielfache von 32 wiederholt, es sei denn, die Quelle des Musters ein 64-Bit-Variable ist; In diesem Fall werden das Muster zur jeder Vielfaches von 64 auf x 64 "und" jedes Vielfache von 256 auf X86,, in denen eine softwareimplementierung hervor wiederholt. Z. B. für eine 32-Bit-Variable mit dem Wert 1 verschoben, um 32 Positionen nach links, auf ARM ist das Ergebnis 0 auf X86 ist das Ergebnis 1 und auf X64 ist das Ergebnis auch 1. Allerdings ist die Quelle des Werts einer 64-Bit-Variablen, dann ist das Ergebnis auf allen drei Plattformen 4294967296 und der Wert nicht "umschließen", bis er auf X64 oder 256 Positionen auf ARM und X86 64 Positionen verschoben hat.  
  
Da das Ergebnis eines schiebevorgangs, die die Anzahl der Bits in den Quelltyp überschreitet nicht definiert ist, wird der Compiler keinen konsistentes Verhalten in allen Situationen aufweisen. Z. B. wenn beide Operanden aus einer Schicht zum Zeitpunkt der Kompilierung bekannt sind, kann der Compiler das Programm mithilfe von einer internen Routine auf das Ergebnis der Schicht im Voraus berechnen, und Ersetzen Sie dann das Ergebnis anstelle der UMSCHALT-Vorgang optimieren. Wenn Sie den Betrag der Verschiebung ist zu groß, oder negativ ist, das Ergebnis der internen Routine möglicherweise anders als das Ergebnis des gleichen UMSCHALT Ausdrucks wie von der CPU ausgeführt.  
  
### <a name="variable-arguments-varargs-behavior"></a>Variablen Argumenten (Varargs) Verhalten  

Auf der ARM-Architektur unterliegen Ausrichtung Parameter aus der Argumentliste variabler, die auf dem Stapel übergeben werden. Ein 64-Bit-Parameter ist z. B. auf einem 64-Bit-Grenze ausgerichtet. Auf X86- und X64 unterliegen Argumente, die auf dem Stapel übergeben sind nicht Ausrichtung und Pack eng. Dieser Unterschied kann dazu führen, dass eine Variadic-Funktion wie `printf` Speicheradressen zu lesen, die bestimmt wurden als Padding on ARM, wenn der Argumentliste variabler als Layout erwartete genau, keine Entsprechung gefunden, wird, obwohl es für eine Teilmenge der einige Werte in der X86 verwendet werden kann oder X64 Architekturen. Betrachten Sie das folgende Beispiel:  
  
```C  
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.  
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.  
// on ARM the calling convention will align the 64-bit value and the code will print a random value  
printf("%d\n", 1LL);     
```  
  
In diesem Fall kann der Fehler behoben werden, indem Sie sicherstellen, dass die richtige Formatangabe verwendet wird, damit, die die Ausrichtung des Arguments berücksichtigt wird. Dieser Code ist korrekt:  
  
```C  
// CORRECT: use %I64d for 64-bit integers  
printf("%I64d\n", 1LL);  
```  
  
### <a name="argument-evaluation-order"></a>Auswertungsreihenfolge des Arguments  

Da ARM "," x 86 "und" X64 Prozessoren so unterschiedlich sind, können sie unterschiedliche Anforderungen zu compilerimplementierungen sowie unterschiedliche Möglichkeiten für Optimierungen darstellen. Aus diesem Grund kann zusammen mit anderen Faktoren wie z. B. Einstellungen für die Aufrufkonvention und Optimierung, ein Compiler auswerten Funktionsargumenten in einer anderen Reihenfolge auf verschiedenen Architekturen oder wenn die andere Faktoren geändert werden. Dadurch kann das Verhalten einer App, die basiert auf einer bestimmten Auswertungsreihenfolge unerwartet geändert.  
  
Diese Art von Fehler kann auftreten, wenn Argumente für eine Funktion Nebeneffekte haben, die anderen Argumente an die Funktion im selben Aufruf auswirken. In der Regel ist diese Art der Abhängigkeit leicht zu vermeiden, aber manchmal verdeckt werden können, die schwer zu erkennen sind oder Operatoren überladen. Betrachten Sie dieses Codebeispiel:  
  
```cpp  
handle memory_handle;  
  
memory_handle->acquire(*p);  
```  
  
Klar definierten, erscheint jedoch möglich, wenn `->` und `*` sind überladene Operatoren, und klicken Sie dann diesen Code in etwas übersetzt wird, die Dies ähnelt:  
  
```cpp  
Handle::acquire(operator->(memory_handle), operator*(p));  
```  
  
Und es eine Abhängigkeit zwischen `operator->(memory_handle)` und `operator*(p)`, u. u. auch der Code auf eine bestimmte Evaluierungsreihenfolge benötigen, auch wenn der ursprüngliche Code aussieht keine möglichen Abhängigkeit vorhanden ist.  
  
### <a name="volatile-keyword-default-behavior"></a>volatile-Schlüsselwort von Standardverhalten  

Der Microsoft C++-Compiler unterstützt zwei verschiedene Interpretationen der der `volatile` Speicher-Qualifizierer, die Sie mithilfe von Compilerschalter angeben können. Die **/volatile:ms** Switch wählt erweiterte volatile Semantik, die starke Reihenfolge gewährleisten wie beim traditionellen Modell für X86- und X64 auf der Microsoft-Compiler aufgrund des Modells starken Arbeitsspeicher auf diesen wurde Microsoft Architekturen. Die **/volatile:iso** Switch wählt die strenge C++ volatile Standardsemantik, die starke Reihenfolge nicht garantiert.  
  
In der ARM-Architektur, die Standardeinstellung ist **/volatile:iso** Schreibberechtigung ARM-Prozessoren ein schwach Speichermodell sortiert, und da ARM Software hat eine Vorgängerversion von Vertrauensstellungen der vertrauenden Seite für die erweiterte Semantik der **/volatile:ms**  und muss nicht mehr in der Regel für die Kommunikation mit der Software, die ausführt. Es ist jedoch weiterhin manchmal praktisch oder sogar erforderlich zum Kompilieren eines Programms ARM erweiterte Semantik verwendet wird. Z. B. möglicherweise so portieren Sie ein Programm die Verwendung der ISO C++-Semantik zu teuer oder Treibersoftware möglicherweise die herkömmlichen Semantik zum ordnungsgemäßen entsprechen. In diesen Fällen können Sie die **/volatile:ms** switch; allerdings die herkömmlichen volatile-Semantik auf ARM-Ziele neu erstellen möchten, der Compiler muss einfügen Arbeitsspeicherbarrieren um jede Lese- oder Schreibvorgang für eine `volatile` Variable erzwingen starke Sortierung, die sich negativ auf die Leistung aufweisen kann.  
  
In der X86- und X64-Architekturen, die Standardeinstellung ist **/volatile:ms** daran, dass ein Großteil der Software, die bereits für diese Architekturen erstellt wurde, indem mithilfe des Microsoft C++-Compilers sie benötigt. Wenn Sie X86- und X64 Programme kompilieren, können Sie angeben der **/volatile:iso** Switch, um zu verhindern, dass unnötige Abhängigkeit von der herkömmlichen volatile Semantik und Portabilität höher stufen.  
  
## <a name="see-also"></a>Siehe auch  

[Konfigurieren von Visual C++ für ARM-Prozessoren](../build/configuring-programs-for-arm-processors-visual-cpp.md)