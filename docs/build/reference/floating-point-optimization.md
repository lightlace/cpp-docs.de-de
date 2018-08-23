---
title: Microsoft Visual C++ Gleitkommawert Optimierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 082cd3a7721f1bc72899130159b724b292e5e217
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595047"
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C++-Gleitkomma-Optimierung

Rufen Sie ein Handle zum mithilfe von Microsoft C++-Compiler die Methode zum Verwalten von Gleitkommasemantik gleitkommacode optimieren. Erstellen Sie schnell Programme, und gleichzeitig sicherstellen, dass nur sichere Optimierungen auf gleitkommacode ausgeführt werden.

## <a name="optimization-of-floating-point-code-in-c"></a>Optimierung der Gleitkomma-Code in C++

Eine C++-Optimierungscompiler wird nicht nur Quellcode in Computercode übersetzt, die er bereitet die computeranweisungen in so, dass die Effizienz verbessern bzw. Reduzieren der Größe. Leider sind viele allgemeine Optimierungen nicht unbedingt sicher, wenn auf gleitkommaberechnungen angewendet. Ein gutes Beispiel hierfür sehen Sie mit dem folgenden Summierung-Algorithmus, David Goldberg, "Was alle Computer Scientist sollte wissen über Gleitkommaarithmetik", entnommen *Computing "Surveys"*, März 1991, Pg. 203:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

Diese Funktion fügt n **"float"** Werte im Array Vektor `A`. Innerhalb der Schleife berechnet der Algorithmus einen ""-Korrekturwert, der dann mit dem nächsten Schritt der Summierung angewendet wird. Diese Methode verringert erheblich kumulative Rundungsfehler im Vergleich zu einer einfachen Summierung, Beibehaltung von O(n) Zeitkomplexität.

Ein naive-C++-Compiler könnten annehmen, dass der Gleitkommaarithmetik algebraischen dieselben Regeln wie für reelle Zahl arithmetische folgt. Solchen Compiler kann dann fälschlicherweise dazu aufgefordert, die daraus schließen

> C = T - Sum - Y == > (Summe + Y) - Sum - Y == > 0;

D. h., dass der wahrgenommene Wert des C immer eine Konstante 0 (null) ist. Wenn dieser Konstante Wert dann in nachfolgenden Ausdrücke weitergegeben wird, wird der Inhalt der Schleife auf eine einfache Summe reduziert. Um genau zu sein:

> Y = [i] - C == > Y = eine [i]<br/>T = Summe + Y == > T = Summe + eine [i]<br/>SUM = T == > Sum = Summe + eine [i]

Daher an den naive-Compiler, eine logische Transformation des der `KahanSum` Funktion wäre:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Obwohl die transformierten Algorithm schneller, ist *es ist überhaupt nicht um eine genaue Darstellung des Programmierers Absicht*. Die sorgfältig erstellte Fehlerkorrektur vollständig entfernt wurde, und wir sind Links, durch eine einfache, direkte Summierung-Algorithmus mit der alle damit zusammenhängenden Fehler.

Natürlich ein anspruchsvoller C++-Compiler würde sofort wissen, algebraischen Regeln von realen arithmetische Operationen im Allgemeinen gelten nicht für Gleitkommaoperatoren. Jedoch möglicherweise ein anspruchsvoller C++-Compiler immer noch falsch interpretiert werden der Programmierer beabsichtigt.

Erwägen Sie eine allgemeine Optimierung, die versucht, so viele Werte wie möglich (namens "Ablaufanalyse" einen Wert) in Registern zu speichern. In der `KahanSum` beispielsweise diese Optimierung versucht möglicherweise, registrieren die Variablen `C`, `Y` und `T` , da sie nur innerhalb der Schleife verwendet werden. Die Register-Genauigkeit (double) 52bits, anstatt 23bits (single) ist, diese Optimierung effektiv Typ höher gestuft `C`, `Y` und `T` eingeben **doppelte**. Wenn die Sum-Variable nicht entsprechend registriert ist, bleibt sie codiert mit einfacher Genauigkeit. Dies wandelt die Semantik der `KahanSum` folgt

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

Obwohl `Y`, `T` und `C` werden jetzt berechnet auf eine höhere Genauigkeit, diese neue Codierung ein weniger genaue Ergebnis abhängig von den Werten in erzeugt möglicherweise `A[]`. Daher auch scheinbar harmlose Optimierungen negative Auswirkungen einer möglicherweise.

Diese Arten von Optimierungsproblemen nicht auf "schwierig" gleitkommacode beschränkt. Selbst einfache Gleitkomma-Algorithmen können fehlschlagen, wenn falsch optimiert. Betrachten Sie einen einfachen, direkte-Summierung Algorithmus:

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Da einige gleitkommaeinheiten kann mehrere Vorgänge gleichzeitig auszuführen sind, kann auch ein Compiler eine skalare Reduzierung Optimierung erfassen. Diese Optimierung wandelt die einfache Sum-Funktion von oben effektiv in den folgenden:

```cpp
float Sum( const float A[], int n )
{
   int n4 = n-n%4; // or n4=n4&(~3)
   int i;
   float sum=0, sum1=0, sum2=0, sum3=0;
   for (i=0; i<n4; i+=4)
   {
      sum = sum + A[i];
      sum1 = sum1 + A[i+1];
      sum2 = sum2 + A[i+2];
      sum3 = sum3 + A[i+3];
   }
   sum = sum + sum1 + sum2 + sum3;
   for (; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Die Funktion führt nun vier separate Quarter-, die bei jedem Schritt gleichzeitig verarbeitet werden können. Obwohl die optimierte Funktion jetzt viel schneller ist, können die optimierte Ergebnisse sich maßgeblich von dem die Ergebnisse nicht optimierten sein. In dieser Änderung davon ausgegangen, dass der Compiler assoziativen gleitkommaaddition; d. h., dass diese zwei Ausdrücke gleichwertig sind: `(a + b) + c == a + (b + c)`. Allerdings ist Assoziativität nicht immer für Gleitkommazahlen möglich. Anstelle von berechnen die Summe als:

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

die transformierte-Funktion nun berechnet das Ergebnis als.

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

Für einige Werte von `A[]`, diese unterschiedliche Reihenfolge der hinzufügen-Vorgänge zu unerwarteten Ergebnissen führen kann. Um das ganze noch weiter zu verkomplizieren, könnten einige Programmierer erwarten solcher Optimierungen und entsprechende Lösungen gefunden werden entsprechend. In diesem Fall kann ein Programm erstellen Arrays `A` in einer anderen Reihenfolge, damit die optimierte Summe die erwarteten Ergebnisse erzeugt. Darüber hinaus kann in vielen Fällen die Genauigkeit des Ergebnisses optimierte "nah" sein. Dies gilt insbesondere, wenn die Optimierung überzeugende Geschwindigkeit Vorteile bietet. Videospiele, erfordern z. B. auf, wie viel wie möglich zu beschleunigen, jedoch nicht häufig äußerst präzise gleitkommaberechnungen erfordern. Compiler-Entwickler müssen daher einen Mechanismus für Programmierer, die zum Steuern der oftmals unterschiedlichen Ziele hinsichtlich Geschwindigkeit und Genauigkeit angeben.

Lösen den Kompromiss zwischen Geschwindigkeit und Genauigkeit einige Compiler durch die Bereitstellung eines separaten Switches für jeden Typ der Optimierung. Dadurch können Entwickler, um Optimierungen zu deaktivieren, die Änderungen zu einer Gleitkomma Genauigkeit für ihre spezifische Anwendung verursacht werden. Obwohl diese Lösung ein hohes Maß an Kontrolle über den Compiler angeboten werden, führt es mehrere zusätzliche Probleme verursachen:

- Häufig ist es unklar die wechselt zu aktivieren oder deaktivieren.
- Deaktivieren alle einzelnen Optimierung kann die Leistung nicht gleitkommacode beeinträchtigen.
- Jeder zusätzliche Schalter verursacht viele neue Schalter Kombinationen; die Anzahl der Kombinationen wird schnell unhandlich werden.

Also während der Bereitstellung von separaten Switches für die einzelnen Optimierung attraktiv erscheinen mag, kann mithilfe solcher Compiler mühsam und unzuverlässig sein.

Viele C++-Compiler bieten eine *Konsistenz* Gleitkommamodell, (über eine **die/op** oder **/fltconsistency** wechseln) mit dessen Hilfe Entwickler zum Erstellen von Programmen kompatibel mit strikte Gleitkommasemantik. Wenn involviert ist, verhindert, dass dieses Modell den Compiler über die meisten Optimierungen auf gleitkommaberechnungen gleichzeitig werden die Optimierungen für nicht-floating-Point-Code. Das Modell, verfügt jedoch über eine Dark-Seite. Um die vorhersagbaren Ergebnissen auf verschiedenen FPU-Architekturen, fast alle Implementierungen von **die/op** round zwischenausdrücke für den Benutzer angegebene Genauigkeit, betrachten Sie beispielsweise den folgenden Ausdruck:

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

Um eine konsistente und wiederholbare Ergebnissen unter **die/op**, diesen Ausdruck ausgewertet wird, als ob es wie folgt implementiert wurden:

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

Das endgültige Ergebnis weist jetzt mit einfacher Genauigkeit Rundungsfehler *bei jedem Schritt in der Auswertung des Ausdrucks*. Obwohl diese Interpretation unbedingt alle Regeln der C++-Semantik unterbrechen nicht, ist es fast nie die beste Möglichkeit, Gleitkomma-Ausdrücke ausgewertet werden. Es ist im Allgemeinen sinnvoller zum Berechnen der temporäre hoher Genauigkeit wie möglich zu führt. Beispielsweise wäre es besser, beim Berechnen des Ausdrucks `a = b * c + d * e` in eine höhere Genauigkeit:

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

oder noch besser

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

Wenn Sie die Zwischenergebnisse in eine höhere Genauigkeit zu berechnen, ist das Endergebnis deutlich genauer. Ironischerweise wird die Wahrscheinlichkeit, dass Fehler mit einem Konsistenzmodell, erhöht genau, wenn der Benutzer versucht, Fehler reduzieren, indem Sie die Deaktivierung von unsafe-Optimierungen. Daher kann das Konsistenzmodell ernst Effizienz reduzieren, dabei gleichzeitig keine Garantie für erhöhte Genauigkeit. Schwerwiegende numerische Programmierern angezeigt wird dies z. B. einen sehr guten Kompromiss scheint nicht und ist der wichtigste Grund, dass das Modell in der Regel nicht gut empfangen wird.

Ab Version 8.0 (Visual C++® 2005), die Microsoft C++-Compiler bietet eine viel bessere Alternative. Es kann Programmierer das auf einem von drei allgemeine Gleitkomma-Modi: fp: precise, fp: fast und fp: strict.

- Unter fp: precise, nur sichere Optimierungen durchgeführt gleitkommacode und im Gegensatz zu **die/op**, intermediate Berechnungen werden mit der höchsten praktische Genauigkeit durchgängig ausgeführt.
- fp: fast Modus lockert die Gleitkomma-Regeln aggressivere Optimierung zulasten der Genauigkeit ermöglicht.
- fp: strict-Modus stellt die allgemeinen Richtigkeit fp: präzise beim Aktivieren der fp-Ausnahme-Semantik und verhindern unzulässige Transformationen bei der FPU-umgebungsänderungen (z. B. Änderungen an die Register-Genauigkeit, Rundung Richtung usw.).

Gleitkomma-Ausnahmezustände Semantik kann durch eine Befehlszeilenoption oder ein Compiler-Pragma unabhängig voneinander kontrolliert werden. Standardmäßig werden die Gleitkomma-Ausnahmezustände Semantik unter fp deaktiviert: präzise und aktivierten unter fp: strict. Der Compiler bietet auch die Kontrolle über die Vertraulichkeit der FPU-Umgebung und bestimmte Gleitkomma bestimmten Optimierungen, wie z. B. Kontraktionen. Dieses Modell einfach bietet Entwicklern eine große Menge an Kontrolle über die Kompilierung von gleitkommacode ohne den Aufwand zu viele Compilerschaltern oder der Aussicht auf unerwünschte Nebeneffekte.

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Ein fp: precise-Modus für Gleitkommasemantik

Der Standardmodus für die Gleitkommasemantik ist fp: präzise. Wenn dieser Modus ausgewählt ist, entspricht der Compiler genau einen Satz von Sicherheitsregeln beim Optimieren von Gleitkommaoperationen. Diese Regeln ermöglichen den Compiler, effiziente Computercode und gleichzeitig die Genauigkeit von gleitkommaberechnungen zu generieren. Zur Erleichterung der Produktions von Fast-Programmen, die ein fp: präzise Modell deaktiviert Gleitkomma-Ausnahmezustände-Semantik (obwohl sie explizit aktiviert werden können). Microsoft hat fp ausgewählt: präzise wie der Gleitkomma-Standardmodus, da sowohl schnelle und präzise Programme erstellt.

Ein fp explizit anfordern: precise-Modus mithilfe des Befehlszeilencompilers, verwenden die [/fp: präzise](fp-specify-floating-point-behavior.md) wechseln:

> CL/fp: präzise source.cpp

Dies weist den Compiler an fp verwenden: genaue Semantik, die beim Generieren von Code für die source.cpp-Datei. Ein fp: präzise Modell kann auch aufgerufen werden, auf eine Funktion-von-Funktion mithilfe der [Compiler Float_control-Pragma](#the-float-control-pragma).

Unter der fp: precise-Modus, führt der Compiler keine Optimierungen, die die Genauigkeit von gleitkommaberechnungen zu stören. Der Compiler rundet immer ordnungsgemäß auf Zuweisungen, typenumwandlungen und Funktionsaufrufe und fortgeschrittene Rundung einheitlich erfolgt auf die gleiche Genauigkeit wie die FPU registriert. Sichere Optimierungen, wie beispielsweise Kontraktionen, sind standardmäßig aktiviert. Ausnahmesemantik und die vertraulichkeitsbezeichnung der FPU-Umgebung sind standardmäßig deaktiviert.

|fp: genaue Semantik|Erklärung|
|-|-|
|Runden der Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe. Intermediate Ausdrücke werden an Register Genauigkeit ausgewertet werden.|
|Algebraische Transformationen|Strenge Einhaltung nicht assoziativ, nicht distributiven Gleitkomma-Algebra, es sei denn, eine Transformation immer garantiert ist erzeugen identische Ergebnisse.|
|Kontraktionen|Standardmäßig zulässig. Weitere Informationen finden Sie im Abschnitt [das Fp_contract-Pragma](#the-fp-contract-pragma).|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler kann die Auswertung von Gleitkommaausdrücken neu anordnen, vorausgesetzt, dass die Endergebnisse nicht geändert werden.|
|Zugriff auf die FPU-Umgebung|Standardmäßig deaktiviert. Weitere Informationen finden Sie im Abschnitt [Fenv_access-Pragma](#the-fenv-access-pragma). Die standardgenauigkeit und Rundungsmodus des Gleitkommas wird angenommen.|
|Gleitkomma-Ausnahmezustände-Semantik|Standardmäßig deaktiviert. Weitere Informationen finden Sie unter [/fp: mit Ausnahme von](fp-specify-floating-point-behavior.md).|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Runden die Semantik für Gleitkommaausdrücken unter fp: präzise

Ein fp: präzise Modell immer intermediate Berechnungen mit der höchsten praktische Genauigkeit, Rundung explizit nur an bestimmten Punkten in der ausdrucksauswertung ausführt. Wird an vier Stellen gerundet, die vom Benutzer angegebene Genauigkeit immer,: (a) bei eine Zuweisung, vorgenommen wird (b) Wenn Sie eine Typumwandlung durchgeführt wird, (c) Wenn ein Gleitkommawert wird als Argument übergeben, die eine Funktion und (d) Wenn der Wert ein Gleitkommazahl aus zurückgegeben wird ein -Funktion. Da intermediate Berechnungen mit Register Genauigkeit immer ausgeführt werden, ist die Genauigkeit der Zwischenergebnisse Plattform abhängig (wenn Genauigkeit immer mindestens so genau wie der angegebene Benutzer kann mit einfacher Genauigkeit).

Erwägen Sie den Ausdruck für die Zuweisung in den folgenden Code aus. Der Ausdruck auf der rechten Seite der Zuweisung Operator "=" wird zur Registrierung mit einfacher Genauigkeit berechnet und dann explizit in den Typ der linken Seite der Zuweisung gerundet werden.

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

wird berechnet

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Stellen Sie eine Typumwandlung vor, um ein Zwischenergebnis explizit zu runden. Z. B. wenn der vorherige Code geändert wird, durch das Hinzufügen einer expliziten Typumwandlung, des intermediären Ausdrucks (c * d) wird in den Typ, der die Typumwandlung gerundet.

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

wird berechnet

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Eine Auswirkung dieser Rundungsmethode ist, dass einige scheinbar entsprechenden Transformationen tatsächlich identisch Semantik nicht an. Die folgende Transformation wird z. B. einen einzelnen Zuweisungsausdruck in zwei Zuweisungsausdrücke teilt.

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

ist nicht gleich

```cpp
float a, b, c, d;
// . . .
a = c+d;
a = b*a;
```

Ebenso:

```cpp
a = b*(c+d);
```

ist nicht gleich

```cpp
a = b*(a=c+d);
```

Diese Codierungen müssen nicht gleichbedeutender Semantik, da die zweite Codierungen jedes, eine zusätzliche Zuweisungsoperation eingeführt, und daher zeigen Sie eine zusätzliche Rundung.

Wenn eine Funktion einen Gleitkommawert zurückgibt, wird der Wert in den Typ der Funktion gerundet. Wenn Sie ein Gleitkommawert auf eine Funktion als Parameter übergeben wird, wird der Wert in den Typ des Parameters gerundet. Zum Beispiel:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

wird berechnet

```cpp
float sumsqr(float a, float b)
{
    register tmp3 = a*a;
    register tmp4 = b*b;
    register tmp5 = tmp3+tmp4;
    return (float) tmp5;
}
```

Ebenso:

```cpp
float w, x, y, z;
double c;
...
c = symsqr(w*x+y, z);
```

wird berechnet

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>Architekturspezifische Rundung unter fp: präzise

|Prozessor|Runden der Genauigkeit in zwischenausdrücke|
|-|-|
|x86|Zwischenausdrücke werden an die standardmäßige Genauigkeit von 53-Bit mit eine erweiterte Palette von einer 16-Bit-Exponenten bereitgestellten berechnet. Wenn diese Werte 53:16 "in den Speicher (wie bei einem Funktionsaufruf auftreten können) verschüttet sind", wird die erweiterte exponentenbereichs auf 11-Bit-eingeschränkt werden. D. h. werden die übergelaufenen Werte in das Format standard mit doppelter Genauigkeit mit nur einem 11-Bit-Exponenten umgewandelt.<br/>Ein Benutzer möglicherweise wechseln Sie zur erweiterten 64-Bit-Genauigkeit für die Zwischenergebnisse Rundung durch Ändern der gleitkommasteuerelements Word mithilfe von `_controlfp` und durch das Aktivieren der Zugriff auf die FPU-Umgebung (finden Sie unter [Fenv_access-Pragma](#the-fenv-access-pragma)). Bei der erweiterten Genauigkeit Register-Werte in den Speicher verschüttet sind, werden jedoch die Zwischenergebnisse immer noch auf doppelte Genauigkeit gerundet.<br/>Diese bestimmte Semantik sind vorbehalten.|
|amd64|FP-Semantik auf amd64 unterscheiden sich etwas von anderen Plattformen. Zur Verbesserung der Leistung sind die größtmögliche Genauigkeit von einer der Operanden statt auf die größtmögliche Genauigkeit intermediate-Vorgänge berechnet.  Um Berechnungen berechnet werden soll, verwenden eine größere Genauigkeit als den Operanden zu erzwingen, müssen Benutzer einen Cast-Vorgang für mindestens einen Operanden in einen Unterausdruck einführen.<br/>Diese bestimmte Semantik sind vorbehalten.|

### <a name="algebraic-transformations-under-fpprecise"></a>Algebraische Transformationen unter fp: präzise

Wenn der fp: precise-Modus aktiviert ist, wird der Compiler führt niemals algebraische Transformationen *, wenn das endgültige Ergebnis Cachelokalitäts-identisch ist*. Viele der vertrauten algebraischen Regeln für reelle Zahl, die arithmetische dauerhaft nicht immer Gleitkommazahlen. Die folgenden Ausdrücke sind beispielsweise Äquivalent für versendeten, aber nicht unbedingt für Gleitkommazahlen.

|Formular|Beschreibung|
|-|-|
|`(a+b)+c = a+(b+c)`|Assoziative Regel hinzufügen|
|`(a*b)*c = a*(b*c)`|Assoziative Regel für Multiplikation|
|`a*(b+c) = a*b + b*c`|Verteilung der Multiplikation erfolgt vor addition|
|`(a+b)(a-b) = a*a-b*b`|Algebraische Finanzierung|
|`a/b = a*(1/b)`|Division durch de Kehrwert|
|`a*1.0 = a`|Multiplikative Identität|

Wie im Beispiel Einführung in mit der Funktion dargestellt `KahanSum`, kann der Compiler Speisen werden, verschiedene algebraische Transformationen ausführen, um beträchtlich schneller Programme zu erzeugen. Obwohl Optimierungen, die abhängig von diese algebraischen Transformationen fast immer falsch sind, gibt es Situationen, in denen für die sie absolut sicher sind. Beispielsweise ist es manchmal wünschenswert, ersetzen Sie die Division durch eine *Konstanten* Multiplikation mit die multiplikative Umkehrung der Konstante Wert:

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

Unter Umständen in transformiert werden

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

Dies ist eine sichere Transformation, da der Abfrageoptimierer, zum Zeitpunkt der Kompilierung X entscheiden kann / 4.0 == x*(1/4.0) für alle Gleitkommawerte von x, einschließlich wurden unendliche und NaN bei Gleitkommawerten. Eine Division durch eine Multiplikation ersetzen, der Compiler mehrere Zyklen speichern kann – insbesondere bei FPUs, die nicht direkt Division implementieren, jedoch müssen den Compiler generiert eine Kombination von Kehrwert-Näherung und Multiplizieren addieren Anweisungen. Der Compiler kann eine Optimierung dieser Art unter fp ausführen: präzise nur, wenn die Ersetzung Multiplikation genau erzeugt dasselbe Ergebnis wie der Division. Der Compiler kann auch ausführen, einfache Transformationen unter fp: precise, vorausgesetzt, dass die Ergebnisse identisch sind. Dazu gehören:

|Formular|Beschreibung
|-|-|
|`(a+b) == (b+a)`|Kommutativ Regel hinzufügen|
|`(a*b) == (b*a)`|Kommutativ Regel für Multiplikation|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|Multiplikation mit 1,0|
|`x/1.0*y == x*y/1.0 == x*y`|Division durch 1.0|
|`2.0*x == x+x`|Multiplikation mit 2.0|

### <a name="contractions-under-fpprecise"></a>Kontraktionen unter fp: präzise

Ein Hauptfeature von vielen modernen gleitkommaeinheiten Architektur ist die Möglichkeit, eine Multiplikation, gefolgt von einer Addition als einzelner Vorgang und kein intermediate runden Fehler auszuführen. Enthält Anweisungen zum Kombinieren von einzelnen ternäre Vorgänge, beispielsweise von Intel Itanium-Architektur (eine*b + c), (eine*b + c) und (c-a * b), in eine einzelne Gleitkommazahl-Anweisung (Fma, Fms und fnma bzw.). Diese einzelnen Anweisungen sind schneller als das Ausführen von separaten multiplizieren, und fügen Sie Anweisungen und genauer sind, da es ist keine intermediate Rundung des Produkts. Diese Optimierung kann erheblich beschleunigen Sie Funktionen mit mehreren multiply überlappen und Hinzufügen von Vorgängen. Betrachten Sie beispielsweise den folgenden Algorithmus, der berechnet das Skalarprodukt von zwei n-dimensionale Vektoren aus.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Diese Berechnung erfolgen kann eine Reihe von multiply-add-Anweisungen der Form p = p + X [i] * y [i].

Die Widerspruch Optimierung kann unabhängig voneinander mit gesteuert werden die `fp_contract` Compiler-Pragma. Standardmäßig wird ein fp: präzise Modell ermöglicht Kontraktionen, da sie sowohl Genauigkeit und Geschwindigkeit verbessern. Unter fp: precise, der Compiler niemals Vertrag einen Ausdruck mit expliziten Rundung.
Beispiele

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add
etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

### <a name="order-of-floating-point-expression-evaluation-under-fpprecise"></a>Reihenfolge der Auswertung der Gleitkomma-Ausdruck unter fp: präzise

Optimierungen, die die Reihenfolge der Auswertung der Gleitkomma-Ausdruck beibehalten sind immer sicher und dürfen sich daher unter fp: precise-Modus. Erwägen Sie die folgende Funktion, die berechnet das Skalarprodukt von zwei n-dimensionale Vektoren in mit einfacher Genauigkeit. Der erste Codeblock nachstehenden die ursprüngliche Funktion, wie es durch einen Programmierer codiert werden kann die gleiche Funktion nach einer partiellen Loop unrolling Optimierung folgt.

```cpp
//original function
float dotProduct( float x[], float y[], int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}

//after a partial loop-unrolling
float dotProduct( float x[], float y[], int n )
{
   int n4= n/4*4; // or n4=n&(~3);
   float p=0;
   int i;

   for (i=0; i<n4; i+=4)
   {
      p+=x[i]*y[i];
      p+=x[i+1]*y[i+1];
      p+=x[i+2]*y[i+2];
      p+=x[i+3]*y[i+3];
   }

   // last n%4 elements
   for (; i<n; i++)
      p+=x[i]*y[i];

   return p;
}
```

Der Hauptvorteil dieser Optimierung ist, dass sie die Anzahl der Schleife bedingte Verzweigungen von mehr als 75 % verringert. Darüber hinaus kann der Compiler durch Erhöhen der Anzahl von Vorgängen innerhalb der Schleife, jetzt mehr Möglichkeiten zur weiteren Optimierung haben. Z. B. einige FPUs möglicherweise zum Ausführen der Multiplizieren addieren in p += X [i] * y [i] beim Abrufen von gleichzeitig die Werte für x [i + 1] "und" y [i + 1] für die Verwendung im nächsten Schritt. Diese Art von Optimierung ist perfekt für gleitkommaberechnungen sicher, da er die Reihenfolge der Vorgänge beibehält.

Häufig ist es vorteilhaft sein, für den Compiler für die gesamte Operationen so neu ordnen, um zu einem schnelleren Code zu erzeugen. Betrachten Sie folgenden Code:

```cpp
double a, b, c, d;
double x, y, z;
...
x = a*a*a + b*b*b + c*c*c;
...
y = a*a + b*b + c*c;
...
z = a + b + c;
```

C++ semantische Regeln anzugeben, dass die Anwendung Ergebnisse erzeugt, als ob er zuerst berechnet x und y und z auf schließlich. Nehmen wir an, dass der Compiler nur vier verfügbaren Gleitkommaregister verfügt. Der Compiler erzwungen wird, berechnet X, y und z in der Reihenfolge, es empfiehlt sich zum Generieren von Code mit der folgende Semantik:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute x
r0 = a;         // r1 = a*a*a
r1 = r0*r0;
r1 = r1*r0;
r0 = b;         // r2 = b*b*b
r2 = r0*r0;
r2 = r2*r0;
r0 = c;         // r3 = c*c*c
r3 = r0*r0;
r3 = r3*r0;
r0 = r1 + r2;
r0 = r0 + r3;
x = r0;         // x = r1+r2+r3
// . . .
// Compute y
r0 = a;         // r1 = a*a
r1 = r0*r0;
r0 = b;         // r2 = b*b
r2 = r0*r0;
r0 = c;         // r3 = c*c
r3 = r0*r0;
r0 = r1 + r2;
r0 = r0 + r3;
y = r0;         // y = r1+r2+r3
// . . .
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1 + r2;
r0 = r0 + r3;
z = r0;         // z = r1+r2+r3
```

Es gibt mehrere klar redundante Vorgänge wird diese Codierung. Wenn der Compiler genau C++ semantische Regeln folgt, ist diese Sortierung erforderlich, da der FPU-Umgebung, die zwischen jeder Zuordnung Zugriff auf das Programm kann. Jedoch die Standardeinstellungen für fp: präzise ermöglichen es dem Compiler zur Optimierung, als ob die Umgebung, Zugriff auf das Programm nicht, sodass sie diese Ausdrücke neu anordnen. Es ist kostenlos, um die Redundanzen zu entfernen, durch die Berechnung von drei Werten in umgekehrter Reihenfolge, wie folgt:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1+r2;
r0 = r0+r3;
z = r0;
...
// Compute y
r1 = r1*r1;
r2 = r2*r2;
r3 = r3*r3;
r0 = r1+r2;
r0 = r0+r3;
y = r0;
...
// Compute x
r0 = a;
r1 = r1*r0;
r0 = b;
r2 = r2*r0;
r0 = c;
r3 = r3*r0;
r0 = r1+r2;
r0 = r0+r3;
x = r0;
```

Diese Codierung ist deutlich überlegen, dass die Anzahl der fp-Anweisungen um fast 40 % reduziert. Die Ergebnisse für x-, y- und z entsprechen wie zuvor, jedoch mit weniger Aufwand berechnet.

Unter fp: precise, der Compiler kann außerdem *interlace-* gemeinsame Teilausdrücke um schnelleren Code zu erzeugen. Code, um den Stamm für eine quadratische Gleichung zu berechnen könnte beispielsweise wie folgt geschrieben werden:

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

Obwohl diese Ausdrücke nur durch einen einzelnen Vorgang unterscheiden, die Programmierer möglicherweise ihn geschrieben haben diese Möglichkeit sicherzustellen, dass jede Stammwert der höchsten praktische Genauigkeit berechnet wird. Unter fp: precise, der Compiler kann, die Berechnung der root0 und root1 gemeinsame Teilausdrücke entfernen, ohne Genauigkeitsverlust Interlaced. Beispielsweise hat die folgenden mehrere redundanter Schritte entfernt und erzeugt genaue dieselbe Antwort.

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

Weitere Optimierungen können versuchen, um die Auswertung von bestimmten unabhängigen Ausdrücke zu verschieben. Betrachten Sie den folgenden Algorithmus, der einen bedingten-Branch in einem Schleifentext enthält.

```cpp
vector<double> a(n);
double d, s;
// . . .
for (int i=0; i<n; i++)
{
   if (abs(d)>1.0)
      s = s+a[i]/d;
   else
      s = s+a[i]*d;
}
```

Der Compiler kann erkennen, die den Wert des Ausdrucks (abs(d) > 1) innerhalb der Schleife unveränderlich ist. Dadurch kann der Compiler um auszudehnen"If"-Anweisung außerhalb der Schleifenkörper Transformieren des obigen Codes in den folgenden:

```cpp
vector<double> a(n);
double d, s;
// . . .
if (abs(d)>1.0)
   for (int i=0; i<n; i++)
      s = s+a[i]/d;
else
   for (int i=0; i<n; i++)
      s = s+a[i]*d;
```

Nach der Transformation steht nicht mehr ein bedingter Zweig in einem der Schleife stellen somit die gesamtleistung der Schleife erheblich verbessern. Diese Art von Optimierung absolut sicher ist. da die Auswertung des Ausdrucks (abs(d) > 1.0) ist unabhängig von anderen Ausdrücken.

Bei Zugriff auf die FPU-Umgebung oder Gleitkommaausnahmen werden diese Arten von Optimierung contraindicated, da sie die semantische Flow ändern. Diese Optimierungen sind nur verfügbar unter fp: precise-Modus, da Zugriff auf die FPU-Umgebung und die Semantik der Gleitkomma-Ausnahmezustände standardmäßig deaktiviert sind. Solche Optimierungen können explizit mithilfe von Funktionen, die Zugriff auf die FPU-Umgebung Deaktivieren der `fenv_access` Compiler-Pragma. Ebenso sollten Funktionen mithilfe von Gleitkommaausnahmen verwenden die `float_control(except ... )` Compiler-Pragma (oder verwenden Sie die **/fp: mit Ausnahme von** Befehlszeilenschalter).

Zusammenfassung der fp: precise-Modus ermöglicht es den Compiler an, die Auswertung von Gleitkommaausdrücken neu anordnen, sofern die Endergebnisse nicht geändert werden und dass Ergebnisse nicht abhängig, die auf die FPU-Umgebung oder auf Gleitkommaausnahmen sind.

### <a name="fpu-environment-access-under-fpprecise"></a>Zugriff auf die FPU Umgebung unter fp: präzise

Wenn der fp: precise-Modus aktiviert ist, wird der Compiler geht davon aus, dass ein Programm nicht zugreifen oder alter die FPU-Umgebung. Wie bereits erwähnt, kann diese Annahme der Compiler neu anordnen oder Verschieben von Gleitkommaoperationen zur Verbesserung der Effizienz unter fp: präzise.

Einige Programme können die Gleitkomma Rundung Richtung ändern, indem die `_controlfp` Funktion. Z. B. einige Programme compute oben, und niedrigere Fehlergrenzen auf arithmetische Operationen durch, die die gleiche Berechnung ausführen, klicken Sie dann zunächst beim Runden in Richtung minus unendlich, während runden in Richtung plus unendlich. Da die FPU auf eine bequeme Möglichkeit zum Steuern der Rundung bereitstellt, können Programmierer Rundungsmodus des Gleitkommas zu ändern, indem Sie die FPU-Umgebung ändern. Der folgende Code berechnet, dass ein Fehler von einer Gleitkommazahl Multiplikation gebunden werden, durch Ändern der FPU-Umgebung.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Unter fp: precise, nimmt der Compiler immer die standardmäßigen FPU-Umgebung, damit der Optimierer ignoriert die Aufrufe von "free" ist `_controlfp` und reduzieren Sie die oben genannten Zuweisungen zu cUpper cLower = = eine * b; Dies würde offensichtlich falsche Ergebnisse ergeben. Um solche Optimierungen zu verhindern, aktivieren Sie auf den Zugriff auf die FPU-Umgebung, indem die `fenv_access` Compiler-Pragma.

Andere Programme versucht möglicherweise bestimmte Gleitkomma-Fehler zu erkennen, indem Sie überprüfen FPUs-statuswort. Beispielsweise überprüft der folgende Code, die aufgrund einer Division durch Null und ungenau Bedingungen

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = r;
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Unter fp: precise, Optimierungen, die Auswertung des Ausdrucks neu anordnen können sich ändern die Punkte, an dem bestimmte Fehler auftreten. Programme, die Zugriff auf das statuswort sollte Zugriff auf die FPU-Umgebung aktivieren, indem die `fenv_access` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Fenv_access-Pragma](#the-fenv-access-pragma).

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Gleitkomma-Ausnahmezustände Semantik unter fp: präzise

Standardmäßig werden die Gleitkomma-Ausnahmezustände Semantik unter fp deaktiviert: präzise. Die meisten C++-Programmierer bevorzugen, Gleitkomma Ausnahmebedingungen ohne Verwendung von System- oder C++-Ausnahmen zu behandeln. Darüber hinaus wie bereits erwähnt, Flexibilität deaktivieren die Gleitkomma-Ausnahmezustände Semantik der Compiler größere beim Optimieren von Gleitkommaoperationen. Verwenden Sie entweder die **/fp: mit Ausnahme von** wechseln oder die `float_control` Pragma, um die Gleitkomma-Ausnahmezustände-Semantik zu aktivieren, wenn der fp verwendet: präzise Modell.

Weitere Informationen finden Sie im Abschnitt [Aktivieren der Gleitkomma-Ausnahmezustände Semantik](#enabling-floating-point-exception-semantics).

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>Der fp-Modus für Gleitkommasemantik

Wenn der fp-Modus aktiviert ist, der Compiler lockert den Regeln, fp: präzise verwendet beim Optimieren von Gleitkommaoperationen. Dieser Modus ist, kann der Compiler gleitkommacode für Geschwindigkeit zu Lasten der Gleitkomma-Genauigkeit und Richtigkeit weiter zu optimieren. Programme, die nicht auf die äußerst präzise gleitkommaberechnungen angewiesen sind möglicherweise eine verbesserte erhebliche Geschwindigkeit durch Aktivieren des fp-Modus.

Der Gleitkomma fp: fast-Modus aktiviert ist, mit der [fast](fp-specify-floating-point-behavior.md) Befehlszeilencompiler Schalter wie folgt:

> CL fast source.cpp

In diesem Beispiel weist den Compiler fp: fast Semantik verwendet wird, beim Generieren von Code für die source.cpp-Datei. Das fp: fast-Modell kann auch aufgerufen werden, auf eine Funktion-von-Funktion mithilfe der `float_control` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Float_control-Pragma](#the-float-control-pragma).

Im Modus für fp: fast kann der Compiler Optimierungen ausführen, die die Genauigkeit von gleitkommaberechnungen zu ändern. Der Compiler möglicherweise nicht ordnungsgemäß auf Zuweisungen gerundet, typenumwandlungen oder Funktionsaufrufe und fortgeschrittene Rundung wird nicht immer ausgeführt werden. Bestimmte gleitkommaoptimierungen, z. B. Kontraktionen, sind immer aktiviert. Gleitkomma-Ausnahmezustände-Semantik und Vertraulichkeit der FPU-Umgebung sind deaktiviert und nicht verfügbar.

|fp: fast-Semantik|Erklärung
|-|-|
|Runden der Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe können ignoriert werden.<br/>Zwischenausdrücke können auf kleiner als die Genauigkeit entsprechend den leistungsanforderungen registrieren gerundet werden soll.|
|Algebraische Transformationen|Der Compiler kann die Ausdrücke, die entsprechend der reelle Zahl assoziativen, distributiven Algebra Transformation. Diese Transformationen sind nicht unbedingt entweder präzise oder korrekt sein.|
|Kontraktionen|Immer aktiviert. kann nicht von Pragma deaktiviert werden `fp_contract`|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler kann die Auswertung von Gleitkommaausdrücken, in neu anordnen, selbst wenn solche Änderungen die Endergebnisse ändern können.|
|Zugriff auf die FPU-Umgebung|Deaktiviert. Nicht verfügbar|
|Gleitkomma-Ausnahmezustände-Semantik|Deaktiviert. Nicht verfügbar|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>Runden die Semantik für Gleitkommaausdrücken unter fp: fast

Im Gegensatz zu den fp: präzise Modell, das fp: fast-Modell führt zwischenberechnungen zum optimalen mit einfacher Genauigkeit. Typenumwandlungen Rundung am Zuweisungen und Funktionsaufrufe möglicherweise nicht immer der Fall. Beispielsweise führt die erste Funktion, die folgenden drei mit einfacher Genauigkeit-Variablen (`C`, `Y` und `T`). Der Compiler kann auch registrieren diese Variablen in Kraft, der Typ heraufstufen `C`, `Y` und `T` zu mit doppelter Genauigkeit.

Ursprüngliche Funktion:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

Variablen registriert:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

In diesem Beispiel hat fp: fast der Zweck der ursprünglichen Funktion unterlaufen. Die endgültige optimiert, in der der Variablen Ergebnis `sum`, möglicherweise sehr perturbed über das richtige Ergebnis.

Unter fp: fast versucht der Compiler in der Regel darin, dass mindestens die Genauigkeit, indem Sie den Quellcode. In einigen Fällen kann der Compiler jedoch zum Ausführen von zwischenausdrücken unter Auswählen einer *niedrigere Genauigkeit* als im Quellcode angegeben. Der erste Codeblock nachstehenden ruft z. B. eine Version mit doppelter Genauigkeit der Quadratwurzel-Funktion. Unter bestimmten Umständen, z. B. wenn das Ergebnis und die Operanden der Funktion explizit in mit einfacher Genauigkeit, umgewandelt werden fp: fast der Compiler möglicherweise wählen Sie zum Ersetzen des Aufrufs der mit doppelter Genauigkeit `sqrt` mit einem Aufruf auf eine einfache Genauigkeit `sqrtf`Funktion. Da Umwandlungen sicherzustellen, dass den Wert in `sqrt` und der Wert, der ausgehend auf einfache Genauigkeit gerundet werden, dies ändert nur die Stelle der Rundung. Wenn der Wert in "SQRT" ein Wert mit doppelter Genauigkeit wurde und der Compiler diese Transformation hat, etwa die Hälfte der Bits Genauigkeit könnte falsch sein.

Ursprüngliche-Funktion

```cpp
double sqrt(double);
// . . .
double a, b, c;
float f1, f2;
// . . .
float length = (float)sqrt((float)(a*a + b*b + c*c));
float sum = (float) ((double)f1 + (double)f2);
```

Optimierte Funktion

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
double tmp0 = a*a + b*b + c*c;
float tmp1 = tmp0;    // round of parameter value
float length = sqrtf(tmp1); // rounded sqrt result
float sum = f1 + f2;
```

Obwohl weniger genau ist, diese Optimierung kann besonders vorteilhaft sein wenn Prozessoren verwendet, die mit einfacher Genauigkeit, systeminterne Versionen von Funktionen, z. B. bereitstellen `sqrt`. Genau nur wenn der Compiler solche Optimierungen verwendet, ist die Plattform- und Kontext abhängig.

Darüber hinaus besteht keine garantierte Konsistenz für die Genauigkeit aus intermediate Berechnungen, die für den Compiler verfügbar auf Genauigkeit durchgeführt werden kann. Obwohl der Compiler versucht, mindestens Genauigkeitsgrad gemäß den Code beizubehalten, kann fp: fast der Abfrageoptimierer Typumwandlung intermediate Berechnungen um schneller oder kleineren Computercode zu erzeugen. Beispielsweise kann der Compiler weiteren Optimierung des Codes von oben, einige der intermediate Multiplikation auf einfache Genauigkeit gerundet.

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
float tmp0 = a*a;     // round intermediate a*a to single-precision
float tmp1 = b*b;     // round intermediate b*b to single-precision
double tmp2 = c*c;    // do NOT round intermediate c*c to single-precision
float tmp3 = tmp0 + tmp1 + tmp2;
float length = sqrtf(tmp3);
float sum = f1 + f2;
```

Diese Art von zusätzlichen Rundung möglicherweise verwenden Sie eine niedrigere Genauigkeit Gleitkommaeinheit, z. B. SSE2, um einige der intermediate Berechnungen durchzuführen. Daher ist die Genauigkeit der Rundung der fp: fast Plattform abhängig; Code, der auch für einen Prozessor kompiliert, funktioniert möglicherweise nicht unbedingt gut für einen anderen Prozessor. Es wird dem Benutzer überlassen, um festzustellen, ob die Vorteile der Geschwindigkeit Genauigkeit Probleme überwiegen.

Wenn fp: fast-Optimierung für eine bestimmte Funktion besonders problematisch ist, der Gleitkomma-Modus umgestellt werden kann lokal fp: präzise mithilfe der `float_control` Compiler-Pragma.


### <a name="algebraic-transformations-under-fpfast"></a>Algebraische Transformationen unter fp: fast

Der fp-Modus kann der Compiler bestimmte, zeigen Sie unsichere algebraische Transformationen in Gleitkommatyp Ausdrücke. Beispielsweise können die folgenden Optimierungen für unsichere unter fp: fast eingesetzt werden.

||||
|-|-|-|
|Ursprünglicher Code|Schritt #1|Schritt #2
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

In Schritt 1 der Compiler beachtet, die `z = y – a – b` ist immer gleich 0 (null). Obwohl dies technisch gesehen eine ungültige Beobachtung ist, ist es unter fp: fast zulässig. Der Compiler gibt dann den konstanten Wert 0 (null) für jede nachfolgende Verwendung von Variablen Z weiter. In Schritt 2 der Compiler weiter optimiert werden, indem Sie prüfen, die `x - 0 == x`, `x * 0 == 0`usw. Obwohl diese Beobachtungen nicht unbedingt gültig sind, sind sie in diesem Fall unter fp: fast zulässig. Der optimierte Code ist nun sehr viel schneller, aber Sie können auch erheblich weniger genau oder sogar falsch sein.

Eine der folgenden (unsicheren) algebraischen Regeln möglicherweise durch den Optimierer verwendet werden, wenn der fp-Modus aktiviert ist:

|||
|-|-|
|Formular|Beschreibung|
|`(a + b) + c = a + (b + c)`|Assoziative Regel hinzufügen|
|`(a * b) * c = a * (b * c)`|Assoziative Regel für Multiplikation|
|`a * (b + c) = a * b + b * c`|Verteilung der Multiplikation erfolgt vor addition|
|`(a + b)(a - b) = a * a - b * b`|Algebraische Finanzierung|
|`a / b = a * (1 / b)`|Division durch de Kehrwert|
|`a * 1.0 = a, a / 1.0 = a`|Multiplikative Identität|
|`a ± 0.0 = a, 0.0 - a = -a`|Additive Identität|
|`a / a = 1.0, a - a = 0.0`|Abbruch|

Wenn fp: fast-Optimierung für eine bestimmte Funktion besonders problematisch ist, der Gleitkomma-Modus umgestellt werden kann lokal fp: präzise mithilfe der `float_control` Compiler-Pragma.

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>Reihenfolge der Auswertung der Gleitkomma-Ausdruck unter fp: fast

Im Gegensatz zu fp: precise, fp: fast können den Compiler an, um zu einem schnelleren Code erzeugen die Gleitkommaoperationen neu angeordnet. Daher möglicherweise einige Optimierungen unter fp: fast nicht die vorgegebenen Reihenfolge von Ausdrücken beibehalten. Betrachten Sie beispielsweise die folgende Funktion, die berechnet das Skalarprodukt von zwei n-dimensionale Vektoren aus.

```cpp
float dotProduct( float x[], float y[],
                  int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Unter fp: fast, kann der Optimierer eine skalare Reduzierung der Ausführen der `dotProduct` funktionieren, transformieren die Funktion tatsächlich wie folgt:

```cpp
float dotProduct( float x[], float y[],int n )
{
    int n4= n/4*4; // or n4=n&(~3);
    float p=0, p2=0, p3=0, p4=0;
    int i;

    for (i=0; i<n4; i+=4)
    {
        p+=x[i]*y[i];
        p2+=x[i+1]*y[i+1];
        p3+=x[i+2]*y[i+2];
        p4+=x[i+3]*y[i+3];
    }
    p+=p2+p3+p4;

    // last n%4 elements
    for (; i<n; i++)
    p+=x[i]*y[i];

    return p;
}
```

In der optimierten Version der Funktion sind vier separate Product-Quarter-gleichzeitig ausgeführt und anschließend addiert. Diese Optimierung kann die Berechnung des beschleunigen die `dotProduct` durch so viel wie ein Faktor von vier je nach dem Zielprozessor, aber das Endergebnis sind möglicherweise ungenau also, es unbrauchbar werden. Wenn solche Optimierungen besonders problematisch für einzelne Funktion oder Übersetzungseinheit sind, der Gleitkomma-Modus umgestellt werden kann lokal fp: präzise mithilfe der `float_control` Compiler-Pragma.

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Ein fp: strict-Modus für Gleitkommasemantik

Wenn der fp: strict-Modus aktiviert ist, wird der Compiler im Hinblick auf die gleichen Regeln, fp eingehalten: präzise verwendet beim Optimieren von Gleitkommaoperationen. Dieser Modus ermöglicht die Gleitkomma-Ausnahmezustände Semantik und Empfindlichkeit gegenüber der FPU-Umgebung auch und deaktiviert bestimmte Optimierungen, wie z. B. Kontraktionen. Es ist die strengste Betriebsmodus.

Fp: strict Gleitkomma-Modus aktiviert ist, mit der [/fp: strict](fp-specify-floating-point-behavior.md) Befehlszeilencompiler Schalter wie folgt:

> CL/fp: strict source.cpp

In diesem Beispiel weist den Compiler mit fp: strict Semantik, die beim Generieren von Code für die source.cpp-Datei. Ein fp: strict-Modell kann auch aufgerufen werden, auf eine Funktion-von-Funktion mithilfe der `float_control` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Float_control-Pragma](#the-float-control-pragma).

Unter der fp: strict-Modus führt der Compiler keine Optimierungen, die die Genauigkeit von gleitkommaberechnungen zu stören. Der Compiler rundet immer ordnungsgemäß auf Zuweisungen, typenumwandlungen und Funktionsaufrufe und fortgeschrittene Rundung einheitlich erfolgt auf die gleiche Genauigkeit wie die FPU registriert. Gleitkomma-Ausnahmezustände-Semantik und Vertraulichkeit der FPU-Umgebung sind standardmäßig aktiviert. Bestimmte Optimierungen, wie z. B. Kontraktionen, sind deaktiviert, da der Compiler nicht auf Richtigkeit in jedem Fall garantieren kann.

|fp: strict-Semantik|Erklärung|
|-|-|
|Runden der Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe<br/>Intermediate Ausdrücke werden an Register Genauigkeit ausgewertet werden.<br/>Identisch mit fp: präzise|
|Algebraische Transformationen|Strenge Einhaltung nicht assoziativ, nicht distributiven Gleitkomma-Algebra, es sei denn, eine Transformation immer garantiert ist erzeugen identische Ergebnisse.<br/>Identisch mit fp: präzise|
|Kontraktionen|Immer deaktiviert.|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler nicht die Auswertung von Gleitkommaausdrücken neu angeordnet|
|Zugriff auf die FPU-Umgebung|Immer aktiviert.|
|Gleitkomma-Ausnahmezustände-Semantik|Standardmäßig aktiviert.|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Gleitkomma-Ausnahmezustände Semantik unter fp: strict

In der Standardeinstellung Gleitkomma-Ausnahmezustände Semantik aktiviert sind, unter dem fp: strict-Modell. Um diese Semantik zu deaktivieren, verwenden Sie entweder die **/fp: mit Ausnahme von-** wechseln, oder stellen Sie vor einem `float_control(except, off)` Pragma.

Weitere Informationen finden Sie in Abschnitten [Aktivieren der Gleitkomma-Ausnahmezustände Semantik](#enabling-floating-point-exception-semantics) und [der Float_control-Pragma](#the-float-control-pragma).

## <a name="the-fenvaccess-pragma"></a>Fenv_access-pragma

Syntax:

```cpp
#pragma fenv_access( [ on  | off ] )
```

Die [Fenv_access](../../preprocessor/fenv-access.md) Pragma kann der Compiler bestimmte Optimierungen vornehmen, die FPU-flagtests und modusänderung FPU unterlaufen möglicherweise. Wenn der Status der `fenv_access` deaktiviert ist, kann der Compiler wird davon ausgegangen die Standard-FPU-Modi sind gültig und, die FPU-Flags sind nicht getestet. Standardmäßig Zugriff auf die Umgebung deaktiviert ist, für ein fp: precise-Modus, wenn es explizit aktiviert werden möglicherweise verwenden dieses Pragma. Unter fp: strict, `fenv_access` ist immer aktiviert und kann nicht deaktiviert werden. Unter fp: fast `fenv_access` ist immer deaktiviert, und kann nicht aktiviert werden.

Siehe fp: präzise Abschnitt einige Programmierer möglicherweise ändern, die Gleitkommazahl mit Rundung-Richtung das `_controlfp` Funktion. Beispielsweise führen Sie zur Berechnung der oberen und unteren Fehlergrenzen auf arithmetische Operationen einige Programme, die die gleiche Berechnung zunächst beim Runden in Richtung minus unendlich, und dann beim Runden in Richtung plus unendlich. Da die FPU auf eine bequeme Möglichkeit zum Steuern der Rundung bereitstellt, können Programmierer Rundungsmodus des Gleitkommas zu ändern, indem Sie die FPU-Umgebung ändern. Der folgende Code berechnet, dass ein Fehler von einer Gleitkommazahl Multiplikation gebunden werden, durch Ändern der FPU-Umgebung.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Wenn deaktiviert, die `fenv_access` Pragma ermöglicht dem Compiler, die Standard-FPU-Umgebung wird davon ausgegangen, weshalb des Optimierers frei, um die Aufrufe an ignorieren `_controlfp` und reduzieren Sie die oben genannten Zuweisungen zu `cUpper = cLower = a*b`. Wenn aktiviert, jedoch `fenv_access` wird verhindert, dass solche Optimierungen.

Programme können auch die FPU-statuswort, um bestimmte Gleitkomma-Fehler erkennen überprüfen. Beispielsweise überprüft der folgende Code, die aufgrund einer Division durch Null und ungenau Bedingungen

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Wenn `fenv_access` ist deaktiviert, kann der Compiler die Ausführungsreihenfolge Gleitkomma Ausdrücke aus, daher möglicherweise subverting die FPU-Status-Überprüfungen anordnen. Aktivieren der `fenv_access` wird verhindert, dass solche Optimierungen.

## <a name="the-fpcontract-pragma"></a>Das Fp_contract-pragma

Syntax:

```cpp
#pragma fp_contract( [ on | off ] )
```

Siehe fp: präzise Abschnitt Widerspruch ist eine grundlegende architektonische-Funktion für viele moderne gleitkommaeinheiten. Kontraktionen bieten die Möglichkeit, eine Multiplikation, gefolgt von einer Addition als einzelner Vorgang und kein intermediate runden Fehler auszuführen. Diese einzelnen Anweisungen sind schneller als das Ausführen von separaten multiplizieren, und fügen Sie Anweisungen und genauer sind, da es ist keine intermediate Rundung des Produkts. Ein zusammengezogen Vorgang können berechnet den Wert der `(a*b+c)` als ob beide Vorgänge mit unendlicher Genauigkeit berechnet wurden, und klicken Sie dann auf gerundet. die nächste Gleitkommazahl. Diese Optimierung kann erheblich beschleunigen Sie Funktionen mit mehreren multiply überlappen und Hinzufügen von Vorgängen. Betrachten Sie beispielsweise den folgenden Algorithmus, der berechnet das Skalarprodukt von zwei n-dimensionale Vektoren aus.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Diese Berechnung erfolgen kann eine Reihe von multiply-add-Anweisungen der Form `p = p + x[i]*y[i]`.

Die [Fp_contract](../../preprocessor/fp-contract.md) Pragma gibt an, ob Gleitkommaausdrücken verkürzt werden können. Standardmäßig wird ein fp: precise-Modus ermöglicht Kontraktionen, da sie sowohl Genauigkeit und Geschwindigkeit verbessern. Kontraktionen sind für den Modus fp: fast immer aktiviert. Jedoch, da Kontraktionen die explizite Erkennung von fehlerbedingungen unterlaufen können die `fp_contract` Pragma ist immer deaktiviert, unter dem fp: strict-Modus. Beispiele für Ausdrücke, die möglicherweise verkürzt, wenn die `fp_contract` Pragma aktiviert ist:

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

## <a name="the-floatcontrol-pragma"></a>Float_control-pragma

Die **/fp: präzise**, **fast**, **/fp: strict** und **/fp: mit Ausnahme von** Switches steuern Gleitkommasemantik auf eine Datei-für-Datei Grundlage. Die [Float_control](../../preprocessor/float-control.md) Pragma bietet eine Kontrolle auf Basis von Funktion.

Syntax:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

Die Pragmas `float_control(push)` und `float_control(pop)` bzw. push und pop den aktuellen Status der Gleitkomma-Modus und der Ausnahme-Option auf einen Stapel. Beachten Sie, dass der Status der der `fenv_access` und `fp_contract` Pragma sind nicht betroffen von `pragma float_control(push/pop)`.

Das Pragma Aufrufen `float_control(precise, on)` wird aktiviert und `float_control(precise, off)` precise-Modus Semantik deaktiviert. Ebenso das Pragma `float_control(except, on)` wird aktiviert und `float_control(except, off)` Ausnahmesemantik deaktiviert. Ausnahmesemantik kann nur aktiviert werden, wenn die genaue Semantik ebenfalls aktiviert werden. Wenn der optionale `push` Argument vorhanden ist, die Zustände des der `float_control` Optionen werden vor der Änderung der Semantik abgelegt.

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>Festlegen des Modus für Gleitkommazahlen semantische auf pro Funktion von

Die Befehlszeilenoptionen werden in der Tat Kurzschreibweise zum Festlegen der vier verschiedenen Gleitkommapragmas. Um einem bestimmten Modus der Gleitkommazahl semantische pro Funktion-von-Funktion explizit auswählen zu können, wählen Sie die vier Gleitkommazahlen Option Pragmas, wie in der folgenden Tabelle beschrieben:

||||||
|-|-|-|-|-|
||float_control(precise)|float_control(EXCEPT)|fp_contract|fenv_access|
|/ fp: strict|an|an|Ausschalten|an|
|/ fp: strict/fp: mit Ausnahme von:|an|Ausschalten|Ausschalten|an|
|/ fp: präzise|an|Ausschalten|an|Ausschalten|
|/ fp: precise/fp: mit Ausnahme|an|an|an|Ausschalten|
|fast|Ausschalten|Ausschalten|an|Ausschalten|

Beispielsweise kann die folgenden explizit fp: fast-Semantik.

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> Ausnahmesemantik muss vor dem Deaktivieren von "präzises" Semantik deaktiviert werden.

## <a name="enabling-floating-point-exception-semantics"></a>Aktivieren der Gleitkomma-Ausnahmezustände-Semantik

Bestimmte Gleitkomma Ausnahmebedingungen, z. B. Division durch 0 (null), können dazu führen, dass die FPU auf eine Hardwareausnahme zu signalisieren. Gleitkommaausnahmen sind standardmäßig deaktiviert. Gleitkommaausnahmen aktiviert sind, durch Ändern der FPU-Steuerwort, mit der `_controlfp` Funktion. Beispielsweise aktiviert der folgende Code die Division-durch-0-Gleitkomma-Ausnahmezustände:

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

Wenn die Ausnahme aufgrund einer Division durch Null aktiviert ist, wird Divisionsvorgang mit einen Nenner gleich 0 (null) eine FPU-Ausnahme zu signalisierende ausgelöst.

Rufen Sie zum Wiederherstellen der FPU-Steuerwort dem Standardmodus `_controlfp(_CW_DEFAULT, ~0)`.

Aktivieren der Gleitkomma-Ausnahmezustände-Semantik mit den **/fp: mit Ausnahme von** Flag ist nicht identisch mit der Aktivierung von Gleitkommaausnahmen. Wenn Gleitkomma-Ausnahmezustände Semantik aktiviert sind, muss der Compiler die Möglichkeit berücksichtigen, dass alle Gleitkommaoperation möglicherweise eine Ausnahme auslöst. Da die FPU auf eine separate Prozessoreinheit ist, können Anweisungen ausführen, auf die FPU gleichzeitig mit andere Zeiteinheiten Anweisungen ausgeführt werden.

Wenn ein Gleitkomma-Ausnahmezustände aktiviert ist, wird die FPU brechen Sie die Ausführung der problematischen Anweisung und eine außergewöhnliche Bedingung klicken Sie dann durch Festlegen der FPU-statuswort zu signalisieren. Wenn die CPU auf die nächste gleitkommaanweisung erreicht, wird zunächst überprüft für alle ausstehenden FPU-Ausnahmen. Wenn eine ausstehende Ausnahme vorhanden ist, fängt der Prozessor ihn durch Aufrufen von einem Ausnahmehandler, der vom Betriebssystem bereitgestellt. Dies bedeutet, dass bei eine Gleitkommaoperation eine Ausnahmebedingung auftritt, die entsprechende Ausnahme nicht erkannt wird, bis der nächste Gleitkomma-Vorgang ausgeführt wird. Der folgende Code erfasst z. B. eine Division durch Null-Ausnahme:

```cpp
double a, b, c;
// . . .
// ...unmasking of FPU exceptions omitted...
__try
{
   b/c; // assume c==0.0
   printf("This line shouldn't be reached when c==0.0\n");
   c = 2.0*b;
}
__except( EXCEPTION_EXECUTE_HANDLER )
{
   printf("SEH Exception Detected\n");
}
// . . .
```

Im Falle eine Division durch Null-Bedingung im Ausdruck einer = b/c, FPU wird nicht Trap/auslösen die Ausnahme, bis der nächste Gleitkomma-Vorgang im Ausdruck 2.0 * b. Dadurch wird die folgende Ausgabe:

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Die erste Zeile der Ausgabe für Printf sollte nicht erreicht wurden; Es wurde erreicht, da die Gleitkomma-Ausnahmezustände zurückzuführen, dass der Ausdruck b/c wurde nicht ausgelöst, bis Ausführung 2.0 erreicht * b. Zum Auslösen der Ausnahme unmittelbar nach dem Ausführen von b/c muss der Compiler eine Anweisung "Warten" eingeführt:

```cpp
// . . .
   __try
   {
      b/c; // assume this expression will cause a "divide-by-zero" exception
      __asm fwait;
      printf("This line shouldn't be reached when c==0.0\n");
      c = 2.0*b;
   }
// . . .
```

Diese Anweisung "Warten" erzwingt, dass den Prozessor mit dem Status der FPU synchronisieren und verarbeiten Sie alle ausstehenden Ausnahmen. Generiert der Compiler nur diese "Warten" Anweisungen Gleitkommasemantik aktiviert werden. Wenn diese Semantik wie es standardmäßig deaktiviert sind, können Programme Synchronismus, ähnlich der oben genannten Fehler bei Gleitkommaausnahmen verwenden.

Wenn Gleitkommasemantik aktiviert sind, wird der Compiler bietet nicht nur eine Einführung "Wait"-Anweisungen, es wird auch verhindern, dass des Compilers illegal optimieren gleitkommacode bei möglichen Ausnahmen. Dies schließt alle Transformationen, die die Punkte zu ändern, an denen Ausnahmen ausgelöst werden. Aufgrund dieser Faktoren kann die Effizienz der generierte Computercode daher beeinträchtigen die Leistung einer Anwendung beim Aktivieren der Gleitkommasemantik erheblich reduzieren.

Gleitkomma-Ausnahmezustände Semantik sind standardmäßig aktiviert, unter dem fp: strict-Modus. So aktivieren Sie diese Semantik in fp: precise-Modus, Hinzufügen der **/fp: mit Ausnahme von** an den Compiler, die Befehlszeile zu wechseln. Gleitkomma-Ausnahmezustände Semantik kann ebenfalls aktiviert und deaktiviert auf einem mit der jede Funktion von werden die `float_control` Pragma.

### <a name="floating-point-exceptions-as-c-exceptions"></a>Gleitkommaausnahmen als C++-Ausnahmen

Als mit der alle Hardwareausnahmen, die, Gleitkommaausnahmen führen eine C++-Ausnahme nicht systemintern, aber stattdessen eine strukturierte Ausnahme auslösen. Benutzer können einen benutzerdefinierten SEH-ausnahmeübersetzer einführen, zum Zuordnen von Gleitkomma-strukturierter Ausnahmen in C++-Ausnahmen. Stellen Sie zunächst eine C++-Ausnahme, die für jede Gleitkomma-Ausnahmezustände vor:

```cpp
class float_exception : public std::exception {};

class fe_denormal_operand : public float_exception {};
class fe_divide_by_zero : public float_exception {};
class fe_inexact_result : public float_exception {};
class fe_invalid_operation : public float_exception {};
class fe_overflow : public float_exception {};
class fe_stack_check : public float_exception {};
class fe_underflow : public float_exception {};
```

Führen Sie dann eine Übersetzungsfunktion, die eine Gleitkommazahl SEH-Ausnahme erkennt und die entsprechende C++-Ausnahme auslösen. Um diese Funktion verwenden zu können, legen Sie das Konvertierungsprogramm strukturierte Ausnahmehandler für den aktuellen Prozessthread mit der [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) Funktion aus der Common Language Runtime-Bibliothek.

```cpp
void se_fe_trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )
{
    switch (u)
    {
    case STATUS_FLOAT_DENORMAL_OPERAND:   throw fe_denormal_operand();
    case STATUS_FLOAT_DIVIDE_BY_ZERO:     throw fe_divide_by_zero();
   etc...
    };
}
// . . .
_set_se_translator(se_fe_trans_func);
```

Nachdem diese Zuordnung initialisiert wird, werden Gleitkommaausnahmen Verhalten, als wären sie C++-Ausnahmen sind. Zum Beispiel:

```cpp
try
{
   // floating-point code that might throw divide-by-zero
   // or other floating-point exception
}
catch(fe_divide_by_zero)
{
    cout << "fe_divide_by_zero exception detected" << endl;
}
catch(float_exception)
{
    cout << "float_exception exception detected" << endl;
}
```

## <a name="references"></a>Verweise

[Was jeder Computerwissenschaftler über Gleitkommaoperatoren wissen sollten](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf) von David Stöber.

## <a name="see-also"></a>Siehe auch

[Codeoptimierung](optimizing-your-code.md)<br/>
