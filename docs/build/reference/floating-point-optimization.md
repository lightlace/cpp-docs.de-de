---
title: Microsoft Visual C++ Gleitkommawert Optimierung | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35c9263fa6252469124eefb0dfd575ef5bd2ac34
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2018
ms.locfileid: "34422733"
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C++-Gleitkomma-Optimierung

Rufen Sie ein Handle auf die mithilfe der Microsoft C++-Compiler Methode zur Verwaltung von Gleitkomma Semantik gleitkommacode optimieren. Erstellen Sie schnell Programme, und gleichzeitig sicherstellen, dass nur sichere Optimierungen für gleitkommacode ausgeführt werden.

## <a name="optimization-of-floating-point-code-in-c"></a>Optimierung von gleitkommacode in C++

Eine C++-Optimierungscompiler übersetzt Quellcode nicht nur in Computercode, es ordnet die maschinenanweisungen in so, dass die Effizienz verbessern und/oder verkleinern. Leider sind viele allgemeine Optimierungen nicht unbedingt sicher, wenn auf gleitkommaberechnungen angewendet. Ein gutes Beispiel hierfür betrachtet werden kann, wobei die folgende Summierung-Algorithmus, David Goldberg, "Was jeder Computer Scientist sollten wissen über Gleitkommaarithmetik", entnommen *Computing Umfragen*, März 1991, Pg. 203:

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

Diese Funktion fügt n **"float"** Werte im Vektor Array `A`. Innerhalb der Schleife berechnet der Algorithmus einen ""-Korrekturwert, der dann mit dem nächsten Schritt der Summierung angewendet wird. Diese Methode wird die kumulierte Rundungsfehler im Vergleich zu einer einfachen Summierung, Beibehaltung der vorhandenen O(n) Zeitkomplexität erheblich reduziert.

Gleitkommazahlen algebraischen dieselben Regeln wie für reelle Zahl arithmetische folgt möglicherweise ein C++-Compiler Naïve angenommen. Solchen Compiler kann dann fälschlicherweise dazu aufgefordert, die beenden

> C = T - Sum - Y == > (Sum + Y) - Sum - Y == > 0;

D. h., dass die wahrgenommene Wert C immer eine Konstante 0 (null) ist. Wenn dieser Konstante Wert dann in nachfolgenden Ausdrücke weitergegeben wird, wird die Schleife auf eine einfache Summe reduziert. Um genau zu sein,

> Y = [i] - C == > Y = [i]<br/>T = Sum + Y == > T = Sum + A [i]<br/>SUM = T == > Sum = Sum + A [i]

Daher an den Naïve-Compiler, eine logische Umwandlung der `KahanSum` Funktion wäre:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Obwohl der transformierte Algorithmus schneller, ist *es ist gar nicht um eine genaue Darstellung des Programmierers Absicht*. Die sorgfältig ausgearbeitete Fehlerkorrektur vollständig entfernt wurde, und wir mit einem einfachen, direkte Summierung Algorithmus mit den dazugehörigen Fehler übrig.

Natürlich würde ein anspruchsvoller C++-Compiler, algebraische wissen Regeln von Real arithmetische Operationen im Allgemeinen gelten nicht für Gleitkommazahlen. Ein anspruchsvoller C++-Compiler kann jedoch immer noch nicht ordnungsgemäß des Programmierers Absicht interpretieren.

Erwägen Sie eine allgemeine Optimierung, die versucht, so viele Werte wie möglich (namens "Ablaufanalyse" einen Wert) in Registern zu speichern. In der `KahanSum` beispielsweise diese Optimierung versucht möglicherweise, registrieren kann die Variablen `C`, `Y` und `T` , da sie nur innerhalb der Schleife verwendet werden. Wenn die Register-Genauigkeit (double) 52bits statt 23bits (einfach) ist, diese Optimierung effektiv Typ stuft `C`, `Y` und `T` eingeben **doppelte**. Wenn die Sum-Variable nicht entsprechend registriert ist, verbleibt er in einfache Genauigkeit codiert. Dies wandelt die Semantik der `KahanSum` , der dem folgenden

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

Obwohl `Y`, `T` und `C` werden jetzt berechnet auf eine höhere Genauigkeit dieser neue Codierung ein weniger genau Ergebnis je nach den Werten in erzeugen `A[]`. Auch scheinbar können harmlose Optimierungen negative Auswirkungen haben.

Derartige Probleme bei der Optimierung nicht auf "einfach" gleitkommacode beschränkt. Einfache Gleitkomma-Algorithmen können fehlschlagen, wenn falsch optimiert. Betrachten Sie einen einfachen direkten Summierung Algorithmus:

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Da einige gleitkommaeinheiten kann mehrere Vorgänge gleichzeitig ausgeführt werden, kann ein Compiler anbieten, eine skalare Reduzierung Optimierung in Verbindung setzen. Diese Optimierung transformiert effektiv die einfachen Sum-Funktion von oben in der folgenden:

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

Die Funktion verwaltet nun vier separate Quarter-, die bei jedem Schritt gleichzeitig verarbeitet werden können. Zwar die optimierte Funktion nun viel schneller, können die optimierte Ergebnisse aus den Ergebnissen nicht optimierten unterschiedlich sein. In diese Änderung wird davon ausgegangen, dass der Compiler assoziativen gleitkommaaddition; d. h., dass diese zwei Ausdrücke gleichwertig sind: `(a + b) + c == a + (b + c)`. Allerdings errichtet Assoziativität immer "true" für Gleitkommazahlen keine. Anstatt die Summierung als Computervorgänge

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

die transformierte-Funktion berechnet jetzt das Ergebnis als

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

Für einige Werte der `A[]`, diese unterschiedliche Reihenfolge der Operationen Addition kann zu unerwarteten Ergebnissen führen. Um weitere wichtige Aspekte zu erschweren, können einige Programmierer erwarten diese Optimierungen und diese entsprechend kompensieren. In diesem Fall kann ein Programm erstellen Arrays `A` in einer anderen Reihenfolge, damit die optimierte Summe der erwarteten Ergebnisse liefert. Darüber hinaus kann in vielen Fällen die Genauigkeit des Ergebnisses optimierte "nah genug" sein. Dies gilt insbesondere, wenn die Optimierung überzeugende Geschwindigkeit Vorteile bietet. Video-Spiele erfordern z. B. auf, wie viel wie möglich zu beschleunigen, aber nicht häufig äußerst genaue gleitkommaberechnungen erfordern. Compilerfehler Entscheidungsträger müssen daher einen Mechanismus für Programmierer, die häufig unterschiedliche Ziele der Geschwindigkeit und Genauigkeit zu steuern bereitzustellen.

Bei einigen Compilern beheben den Kompromiss zwischen Geschwindigkeit und Genauigkeit durch die Bereitstellung eines separaten Switches für jeden Typ der Optimierung. Dadurch können Entwickler, um Optimierungen zu deaktivieren, die Änderungen zu Gleitkomma Genauigkeit für ihre bestimmte Anwendung verursacht werden. Während diese Lösung ein hohes Maß an Kontrolle über den Compiler hilfreich sein kann, führt es mehrere zusätzliche Probleme verursachen:

- Es ist oft unklar wechselt, die zum Aktivieren oder deaktivieren.
- Deaktivieren alle einzelnen Optimierung kann die Leistung nicht gleitkommacode beeinträchtigen.
- Jeder zusätzliche Switch verursacht viele neue Switch Kombinationen; die Anzahl der Kombinationen wird schnell unhandlich werden.

Daher beim Bereitstellen von separaten Switches für jede Optimierung ansprechend besonders intuitiv erscheinen, kann mit solchen Compilern umständlich und unzuverlässig sein.

Viele C++-Compiler bieten eine *Konsistenz* Gleitkommamodell, (über eine **op** oder **/fltconsistency** wechseln) mit dessen Hilfe Entwickler zum Erstellen von Programmen kompatibel mit strengen Gleitkomma-Semantik. Wenn involviert ist, verhindert, dass dieses Modell den Compiler die meisten Optimierungen auf gleitkommaberechnungen verwenden, während gleichzeitig die Optimierungen für nicht Gleitkomma-Code. Konsistenzmodell, hat jedoch eine dunklen-Seite. Um vorhersagbare Ergebnisse auf verschiedene FPU-Architekturen, fast alle Implementierungen von zurückzugeben **op** round zwischenausdrücke für den Benutzer angegebene Genauigkeit; betrachten Sie beispielsweise den folgenden Ausdruck:

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

Um eine konsistente und wiederholbare Ergebnissen unter **op**, diesen Ausdruck ausgewertet, als ob er wie folgt implementiert wurden:

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

Das Endergebnis jetzt noch dadurch erschwert mit einfacher Genauigkeit Rundungsfehler *bei jedem Schritt in der Auswertung des Ausdrucks*. Obwohl diese Interpretation unbedingt alle Regeln der C++-Semantik unterbrechen nicht, ist es fast nie die beste Möglichkeit, Gleitkomma-Ausdrücke ausgewertet werden. Es ist im Allgemeinen sinnvoller, um die Zwischendateien hoher Genauigkeit als durchführbar ist, führt zu berechnen. Beispielsweise wäre es besser, beim Berechnen des Ausdrucks `a = b * c + d * e` in einer höheren Genauigkeit als in

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

oder besser noch

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

Bei der Berechnung der Zwischenergebnisse in eine höhere Genauigkeit, ist das Endergebnis erheblich genauer. Ironischerweise wird durch die Übernahme eines Modells Konsistenz, die Wahrscheinlichkeit des Fehlers erhöht genau, wenn der Benutzer versucht, Fehler zu verringern, indem Sie die Deaktivierung von unsicheren Optimierungen. Daher kann Konsistenzmodell ernsthaft Effizienz reduzieren und gleichzeitig bietet keine Garantie für erhöhte Genauigkeit. Schwerwiegende numerische Programmierern angezeigt wird dies wie eine sehr gute Kompromiss scheint nicht und ist der wichtigste Grund, dass das Modell in der Regel nicht gut empfangen wird.

Ab Version 8.0 (Visual C++® 2005), Microsoft C++ enthält Compiler eine viel bessere Alternative darstellt. Es kann Programmierer das Auswählen eines drei allgemeine Gleitkomma-Modi: fp: präzise, FP und fp: strict.

- Unter fp: präzise, nur sichere Optimierungen sind gleitkommacode auch ausgeführt, im Gegensatz zu **op**, intermediate Berechnungen an die höchste praktische Genauigkeit konsistent durchgeführt werden.
- FP Modus lockert die Gleitkomma Regeln, die bei dem aggressiver Optimierung zu Lasten der Genauigkeit.
- fp: strict-Modus stellt die allgemeine Richtigkeit fp: präzise beim Aktivieren von fp-Ausnahme-Semantik und verhindert, dass ungültige Transformationen Wiederherstellungsprobleme FPU anwendungsumgebung ändert (z. B. Änderungen an die Register-Genauigkeit, Rundung Richtung usw.).

Gleitkommaausnahme Semantik kann unabhängig von einer Befehlszeilenoption oder ein Pragma Compiler gesteuert werden; Gleitkommaausnahmen Semantik sind standardmäßig unter fp deaktiviert: präzise und aktivierten unter fp: strict. Der Compiler bietet auch FPU Umgebung Empfindlichkeit und bestimmte Gleitkomma bestimmten Optimierungen, wie z. B. Kontraktionen steuern. Dieses Modell selbsterklärend bietet Entwicklern viel Kontrolle über die Kompilierung von gleitkommacode ohne den Aufwand zu viele Compilerschaltern oder die Aussicht unerwünschte Nebeneffekte.

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Das fp: präzise Modus für Gleitkomma-Semantik

Der Standardmodus für das Gleitkomma-Semantik ist fp: präzise. Wenn dieser Modus ausgewählt ist, verwendet der Compiler beim Optimieren von Gleitkommaoperationen streng auf einen Satz von Sicherheitsregeln. Diese Regeln erlauben den Compiler effiziente Computercode generiert und gleichzeitig die Genauigkeit von gleitkommaberechnungen an. Programme zur Erleichterung der Produktions Fast die fp: präzise Modell deaktiviert Gleitkommaausnahme-Semantik (obwohl sie explizit aktiviert werden können). Microsoft hat fp ausgewählt: präzise wie der Gleitkomma-Standardmodus, weil eine schnelle und genaue Programme erstellt.

Für das fp explizit anfordern: präzise Modus mithilfe der Befehlszeilencompiler, verwenden die [/fp: präzise](fp-specify-floating-point-behavior.md) wechseln:

> CL/fp: präzise source.cpp

Dies weist den Compiler an fp verwenden: genaue Semantik, die beim Generieren von Code für die source.cpp-Datei. Das fp: präzise Modell kann auch aufgerufen werden, für einen Basis Funktion, indem Sie mithilfe der [Float_control-Compiler-Pragma](#the-float-control-pragma).

Unter dem fp: präzise Modus führt der Compiler keine Optimierungen, die die Genauigkeit von gleitkommaberechnungen perturb. Der Compiler wird am Zuweisungen immer korrekt gerundet, typenumwandlungen und Funktionsaufrufe und fortgeschrittene Rundung konsistent erfolgt auf die gleiche Genauigkeit wie die FPU registriert. Sichere Optimierungen, wie z. B. Kontraktionen, sind standardmäßig aktiviert. Ausnahme Semantik und FPU Umgebung Empfindlichkeit sind standardmäßig deaktiviert.

|fp: genaue Semantik|Erklärung|
|-|-|
|Rundung Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe. Zwischenausdrücke werden an Register Genauigkeit ausgewertet.|
|Algebraische Transformationen|Strenge Einhaltung nicht assoziativ, nicht distributive Gleitkomma Algebra verglichen werden, es sei denn, eine Transformation immer garantiert wird erzeugen identische Ergebnisse.|
|Kontraktionen|Standardmäßig zulässig. Weitere Informationen finden Sie im Abschnitt [Fp_contract-Pragma](#the-fp-contract-pragma).|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler kann die Auswertung von Ausdrücken Gleitkomma neu anordnen, vorausgesetzt, dass die Endergebnisse nicht geändert werden.|
|FPU Umgebung Zugriff|Standardmäßig deaktiviert. Weitere Informationen finden Sie im Abschnitt [Fenv_access-Pragma](#the-fenv-access-pragma). Die standardgenauigkeit und Rundungsmodus wird angenommen.|
|Gleitkommaausnahmen-Semantik|Standardmäßig deaktiviert. Weitere Informationen finden Sie unter [/fp: außer](fp-specify-floating-point-behavior.md).|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Rundung Semantik für Gleitkommazahlen Ausdrücke unter fp: präzise

Das fp: präzise Modell führt immer intermediate Berechnungen auf der höchsten praktische Genauigkeit explizit nur an bestimmten Punkten in der ausdrucksauswertung Rundung. Rundung auf die vom Benutzer angegebene Genauigkeit immer erfolgt in vier Stellen: (a) bei eine Zuweisung, vorgenommen wird (b) Wenn Sie eine Typumwandlung ausgeführt wird, (c) Wenn ein Gleitkommawert wird als Argument übergeben an eine Funktion und (d) Wenn der Wert ein Gleitkommazahl aus zurückgegeben wird ein Funktion. Da intermediate Berechnungen immer am Register Genauigkeit ausgeführt werden, wird die Genauigkeit der Zwischenergebnisse Plattform abhängigen (obwohl Genauigkeit immer über mindestens so exakt wie der angegebene Benutzer werden Genauigkeit).

Betrachten Sie die Zuweisungsausdruck in den folgenden Code aus. Der Ausdruck auf der rechten Seite der Zuweisung Operator "=" wird am Register Genauigkeit berechnet, und dann explizit in den Typ der linken Seite der Zuweisung gerundet werden.

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

wird als berechnet.

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Stellen Sie eine Typumwandlung vor, um ein Zwischenergebnis explizit zu runden. Z. B. wenn der vorherige Code geändert wird, durch Hinzufügen einer expliziten umgewandelt, den intermediate-Ausdruck (c * d) in den Typ des Typumwandlung abgerundet wird.

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

wird als berechnet.

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Eine Auswirkung dieses Rundungsmethode ist, dass manche Transformationen scheinbar entsprechenden tatsächlich identische Semantik haben. Die folgende Transformationen teilt z. B. eine einzelne Zuweisungsausdruck in zwei Zuweisungsausdrücke.

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

Diese Codierungen müssen entsprechende Semantik keinen, da die zweite Codierungen jedes, die eine zusätzliche Zuweisungsvorgang eingeführt und daher zeigen eine zusätzliche Rundung.

Wenn eine Funktion einen Gleitkommawert zurückgibt, wird der Wert in den Typ der Funktion gerundet. Wenn ein Gleitkommawert als Parameter an eine Funktion übergeben wird, wird der Wert in den Typ des Parameters gerundet. Zum Beispiel:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

wird als berechnet.

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

wird als berechnet.

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>Architekturspezifischer Rundung unter fp: präzise

|Prozessor|Runden der Genauigkeit für zwischenausdrücke|
|-|-|
|x86|Zwischenausdrücke werden an die standardgenauigkeit von 53 Bit mit einem erweiterten Bereich einen 16-Bit-Exponenten gebotenen berechnet. Wenn diese Werte 53:16 "in den Arbeitsspeicher (wie bei einem Funktionsaufruf auftreten können) Aggregierung überlaufen sind", wird der erweiterte Exponent Bereich 11 Bits eingeschränkt werden. D. h. werden die übergelaufenen Werte in das Format standard mit doppelter Genauigkeit mit nur einem 11-Bit-Exponenten umgewandelt.<br/>Ein Benutzer möglicherweise wechseln Sie zur erweiterten 64-Bit-Genauigkeit für die intermediate Rundung durch Ändern der gleitkommasteuerelements Word mithilfe von `_controlfp` und durch das Aktivieren des Zugriffs der FPU-Umgebung (finden Sie unter [Fenv_access-Pragma](#the-fenv-access-pragma)). Bei der erweiterten Genauigkeit Registerwerte in den Arbeitsspeicher Aggregierung überlaufen sind, werden jedoch die Zwischenergebnisse weiterhin auf doppelte Genauigkeit gerundet.<br/>Diese bestimmte Semantik unterliegt.|
|amd64|FP-Semantik auf amd64 unterscheiden sich etwas von anderen Plattformen. Aus Gründen der Leistung werden intermediate Vorgänge an die längsten Genauigkeit einer der Operanden statt auf die umfassendsten Genauigkeit berechnet werden.  Um Berechnungen berechnet werden soll, verwenden eine größere Genauigkeit als Operanden zu erzwingen, müssen Benutzer ein Umwandlungsvorgangs auf mindestens einen Operanden in einem Unterausdruck einführen.<br/>Diese bestimmte Semantik unterliegt.|

### <a name="algebraic-transformations-under-fpprecise"></a>Algebraische Transformationen unter fp: präzise

Wenn das fp: präzise Modus aktiviert ist, der Compiler führt nie algebraische Transformationen *, wenn das endgültige Ergebnis nachweislich identisch ist*. Viele der vertrauten algebraischen Regeln für reelle Zahl arithmetische dauerhaft nicht immer für Gleitkommazahlen. Beispielsweise sind die folgenden Ausdrücke gleichwertig für versendeten, aber nicht notwendigerweise für float.

|Formular|Beschreibung|
|-|-|
|`(a+b)+c = a+(b+c)`|Assoziative Regel hinzufügen|
|`(a*b)*c = a*(b*c)`|Assoziative Regel für Multiplikation|
|`a*(b+c) = a*b + b*c`|Verteilung der Multiplikation erfolgt vor addition|
|`(a+b)(a-b) = a*a-b*b`|Algebraische Umgestalten|
|`a/b = a*(1/b)`|Division durch Kehrwert|
|`a*1.0 = a`|Multiplikative Identität|

Wie in der Einführung im Beispiel mit der Funktion dargestellt `KahanSum`, der Compiler möglicherweise verschiedene algebraische Transformationen ausführen, um Programme erheblich schneller zu erzeugen Versuchung sein. Obwohl solche algebraischen Transformationen abhängig Optimierungen fast immer falsch sind, stehen vorkommen, dass für die diese perfekt sicher sind. Beispielsweise ist es in einigen Fällen erwünscht, Division durch Ersetzen einer *konstant* bei der Multiplikation von die multiplikative Umkehrung der Konstante Wert:

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

Kann in transformiert werden

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

Dies ist eine sichere Transformation, da der Abfrageoptimierer, zum Zeitpunkt der Kompilierung X entscheiden kann / 4.0 == x*(1/4.0) für alle Gleitkommawerte von x, einschließlich unendlichen und NaN. Durch eine Division durch eine Multiplikation ersetzen, kann der Compiler mehrere Zyklen speichern – insbesondere bei FPUs, die nicht direkt Division implementieren, aber den Compiler generiert eine Kombination von Kehrwert Näherung und multiply add erfordern Anweisungen. Der Compiler kann solche Optimierung unter fp ausführen: präzise nur, wenn die Austausch Multiplikation die genaue erzeugt dasselbe Ergebnis wie der Division. Der Compiler möglicherweise auch nicht triviale Transformationen unter fp ausführen: präzise, vorausgesetzt, dass die Ergebnisse identisch. Dazu gehören:

|Formular|Beschreibung
|-|-|
|`(a+b) == (b+a)`|Kommutativ Regel hinzufügen|
|`(a*b) == (b*a)`|Kommutativ Regel für Multiplikation|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|Die Multiplikation mit 1.0|
|`x/1.0*y == x*y/1.0 == x*y`|Division durch 1.0|
|`2.0*x == x+x`|Die Multiplikation mit 2.0|

### <a name="contractions-under-fpprecise"></a>Kontraktionen unter fp: präzise

Eine architektonische Hauptfunktion von viele moderne gleitkommaeinheiten ist die Fähigkeit zum Ausführen einer Multiplikation, gefolgt von den Zusatz als einzelner Vorgang und kein intermediate runden Fehler. Intel Itanium-Architektur enthält z. B. Anweisungen, um diese ternäre Vorgänge zu kombinieren (eine*b + c), (eine*b + c) und (c-a * b), in einer einzelnen gleitkommaanweisung (Fma, Fms und fnma bzw.). Diese einzelnen Anweisungen sind schneller als separate Ausführung multiply "und" Hinzufügen von Anweisungen und genauer sind, da es ist keine intermediate Rundung des Produkts. Diese Optimierung kann erheblich beschleunigen von Funktionen mit mehreren multiply verzahnt und Vorgänge hinzufügen. Betrachten Sie beispielsweise den folgenden Algorithmus, der berechnet das Skalarprodukt zweier n-dimensionale Vektoren aus.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Diese Berechnung erfolgen kann eine Reihe von multiply add Anweisungen im Format p = p + X [i] * y [i].

Die Optimierung Kontraktion kann unabhängig gesteuert werden die `fp_contract` Compiler-Pragma. Standardmäßig wird das fp: präzise Modell ermöglicht Kontraktionen, da sie die Genauigkeit und Geschwindigkeit verbessern. Unter fp: präzise ist, wird der Compiler nie Vertrag die einen Ausdruck mit expliziten Rundung.
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

Optimierungen, die die Reihenfolge der Auswertung von Ausdrücken Gleitkomma beibehalten sind immer sicher und sind daher unter dem fp zulässig: präzise Modus. Betrachten Sie die folgende Funktion die berechnet das Skalarprodukt zweier n-dimensionale Vektoren in einfache Genauigkeit aus. Der erste Codeblock unten die ursprüngliche Funktion wie es durch einen Programmierer codiert werden kann die gleiche Funktion nach einer partiellen Schleife kein Bildlauf Optimierung folgt.

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

Der wichtigste Vorteil des diese Optimierung ist, die Anzahl der Schleife bedingte Verzweigung von mehr als 75 reduziert % an. Darüber hinaus kann der Compiler durch Erhöhen der Anzahl von Vorgängen innerhalb der Schleife, jetzt mehr Möglichkeiten, um weiter zu optimieren haben. Z. B. einige FPUs möglicherweise zum Ausführen der multiply add in p += X [i] * j [i] beim Abrufen eines gleichzeitig die Werte für x [i + 1] "und" y [i + 1] für die Verwendung im nächsten Schritt. Dieser Typ der Optimierung ist perfekt für gleitkommaberechnungen sicher, da die Reihenfolge der Vorgänge beibehalten.

Häufig ist es vorteilhaft sein, damit der Compiler gesamte Vorgänge neu anordnen, um Code schneller zu erzeugen. Betrachten Sie folgenden Code:

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

C++ semantische Regeln anzugeben, dass das Programm Ergebnisse erzeugt, als wäre es zuerst berechnet X, dann y und z auf schließlich. Nehmen Sie an, dass der Compiler nur vier verfügbaren Gleitkommaregister hat. Wenn der Compiler erzwungen wird, berechnet x-, y- und z in der Reihenfolge, empfiehlt sich zum Generieren von Code mit die folgende Semantik:

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

Es gibt mehrere klar redundante Vorgänge wird diese Codierung. Wenn der Compiler streng C++ semantische Regeln folgt, ist diese Reihenfolge erforderlich, da der FPU Umgebung dazwischen jede Zuordnung Zugriff auf das Programm möglicherweise. Allerdings die Standardeinstellungen für fp: präzise den Compiler an, zu optimieren, als wären die Umgebung, Zugriff auf das Programm nicht zulassen, sodass es diesen Ausdrücken neu anordnen. Es ist dann frei, um die Redundanzen zu entfernen, indem Sie berechnen die drei Werte in umgekehrter Reihenfolge, wie folgt:

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

Diese Codierung ist deutlich überlegen, müssen die Anzahl der fp-Anweisungen um fast 40 % verringert. Die Ergebnisse für X, y und z sind identisch, jedoch mit weniger Aufwand berechnet.

Unter fp: präzise, der Compiler kann auch *Interlaced* gemeinsame Teilausdrücke um Code schneller zu erzeugen. Code, um die Wurzeln einer Formel "quadratisch" zu berechnen könnte beispielsweise wie folgt geschrieben werden:

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

Obwohl diese Ausdrücke nur durch einen einzelnen Vorgang unterscheiden, der Programmierer möglicherweise ihn geschrieben haben auf diese Weise, um sicherzustellen, dass jede Stammwert in die praktische höchste Genauigkeit berechnet werden soll. Unter fp: präzise, der Compiler kann die Berechnung des root0 und root1 gemeinsame Teilausdrücke entfernen, ohne Genauigkeitsverlust Interlaced kann nach Belieben. Beispielsweise hat die folgenden mehrere redundanter Schritte entfernt immer genau dieselben Ergebnisse erzeugen.

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

Andere Optimierungen können versuchen, die Auswertung bestimmter unabhängigen Ausdrücke zu verschieben. Betrachten Sie den folgenden Algorithmus, der eine bedingte Verzweigung innerhalb einer Schleife enthält.

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

Der Compiler erkennt, die möglicherweise den Wert des Ausdrucks (abs(d) > 1) ist innerhalb der Schleife invariant. Dadurch kann der Compiler, "If auszudehnen" Anweisung außerhalb der Schleife den oben aufgeführten Code in der folgenden transformiert:

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

Nach der Transformation wird es nicht mehr eine bedingte Verzweigung entweder die Schleifenkörper, damit die allgemeine Leistung der Schleife erheblich zu verbessern. Dieser Typ der Optimierung ist vollkommen sicher da die Auswertung des Ausdrucks (abs(d) > 1.0) ist unabhängig von anderen Ausdrücken.

Wiederherstellungsprobleme FPU Umgebung Zugriff oder Gleitkommaausnahmen werden diese Formen der Optimierung contraindicated, da sie die semantische Fluss ändern. Diese Optimierungen sind nur verfügbar, unter dem fp: präzise Modus weil FPU Umgebung Zugriff und Gleitkommaausnahme Semantik standardmäßig deaktiviert sind. Diese Optimierungen können explizit mithilfe von Funktionen, die die FPU-Umgebung zuzugreifen Deaktivieren der `fenv_access` Compiler-Pragma. Ebenso sollten Funktionen mithilfe von Gleitkommaausnahmen verwenden die `float_control(except ... )` Compiler-Pragma (oder verwenden Sie die **/fp: außer** Befehlszeilenschalter).

Im Grunde das fp: präzise Modus ermöglicht, den Compiler an, die Auswertung von Ausdrücken Gleitkomma neu anordnen, unter der Voraussetzung, dass die Endergebnisse nicht geändert werden und dass Ergebnisse nicht abhängig, auf die FPU-Umgebung oder auf Gleitkommaausnahmen wurden.

### <a name="fpu-environment-access-under-fpprecise"></a>FPU Umgebung Zugriff unter fp: präzise

Wenn das fp: präzise Modus aktiviert ist, nimmt der Compiler an, dass ein Programm nicht zugreifen oder ändern die FPU-Umgebung. Wie bereits erwähnt, kann diese Annahme der Compiler neu anordnen oder Verschieben von Gleitkommaoperationen zur Verbesserung der Effizienz unter fp: präzise.

Einige Programme möglicherweise die Gleitkomma Rundung Richtung ändern, indem die `_controlfp` Funktion. Z. B. einige Programme oben berechnen, und niedrigere Fehlergrenzen auf arithmetische Operationen durch Ausführen der gleichen Berechnung zweimal, klicken Sie dann zuerst beim Runden in Richtung minus unendlich, während runden in Richtung plus unendlich. Da die FPU auf eine praktische Möglichkeit zur Kontrolle Rundung bereitstellt, können Programmierer Rundungsmodus zu ändern, indem Sie die FPU-Umgebung ändern. Der folgende Code berechnet, dass Fehler genauer ein Gleitkomma Multiplikation gebunden werden, durch Ändern der FPU-Umgebung.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Unter fp: präzise, nimmt der Compiler immer die standardumgebung FPU, damit der Optimierer frei, um die Aufrufe zu ignorieren ist `_controlfp` und zur Reduzierung der oben genannten Aufgaben cUpper = cLower = eine * b; Dies würde deutlich falsche Ergebnisse ergeben. Um diese Optimierungen zu verhindern, aktivieren Sie FPU Umgebung Zugriff mithilfe der `fenv_access` Compiler-Pragma.

Andere Programme können auf bestimmte Gleitkomma-Fehler zu erkennen, indem Sie überprüfen die FPU statuswort versuchen. Der folgende Code z. B. überprüft aufgrund einer Division durch Null und ungenau Bedingungen

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

Unter fp: präzise und Optimierungen, die Auswertung von Ausdrücken neu anordnen können sich ändern die Punkte, an dem bestimmte Fehler auftreten. Programme, die Zugriff auf das statuswort sollten FPU Umgebung Zugriff aktivieren, indem die `fenv_access` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Fenv_access-Pragma](#the-fenv-access-pragma).

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Gleitkommaausnahmen Semantik unter fp: präzise

Standardmäßig sind Gleitkommaausnahme Semantik unter fp deaktiviert: präzise. Die meisten C++-Programmierer bevorzugen, Gleitkomma Ausnahmebedingungen ohne Verwendung von System- oder C++-Ausnahmen zu behandeln. Darüber hinaus wie zuvor erwähnt, Flexibilität Deaktivieren von Gleitkommaausnahmen Semantik der Compiler größere beim Optimieren von Gleitkommaoperationen. Verwenden Sie entweder die **/fp: außer** wechseln oder die `float_control` Pragma Gleitkommaausnahme Semantik zu aktivieren, wenn mit dem fp: präzise Modell.

Weitere Informationen finden Sie im Abschnitt [Aktivierung von Gleitkommaausnahmen Semantik](#enabling-floating-point-exception-semantics).

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>Das FP-Modus für Gleitkomma-Semantik

Wenn das FP-Modus aktiviert ist, der Compiler lockert den Regeln, fp: präzise verwendet beim Optimieren von Gleitkommaoperationen. Dieser Modus ist, kann der Compiler gleitkommacode für Geschwindigkeit zu Lasten der Gleitkomma-Genauigkeit und Richtigkeit weiter zu optimieren. Programme, die nicht auf äußerst genaue gleitkommaberechnungen angewiesen sind treten möglicherweise eine erhebliche Geschwindigkeit Verbesserung von fp-Modus aktivieren.

Der Gleitkomma fp-Modus aktiviert ist, mit der [/fp: fast](fp-specify-floating-point-behavior.md) Befehlszeilencompiler Switch wie folgt:

> CL/fp: fast source.cpp

In diesem Beispiel weist den Compiler fp-Semantik verwendet beim Generieren von Code für die source.cpp-Datei. Das fp: fast-Modell kann auch aufgerufen werden, für einen Basis Funktion, indem Sie mithilfe der `float_control` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Float_control-Pragma](#the-float-control-pragma).

Im Modus für fp kann der Compiler Optimierungen ausführen, die die Genauigkeit von gleitkommaberechnungen zu ändern. Der Compiler möglicherweise nicht ordnungsgemäß am Zuweisungen runden, typenumwandlungen oder Funktionsaufrufe und fortgeschrittene Rundung wird nicht immer ausgeführt werden. Bestimmte gleitkommaoptimierungen, z. B. Kontraktionen, sind immer aktiviert. Gleitkommaausnahmen Semantik und FPU Umgebung Empfindlichkeit sind deaktiviert und nicht verfügbar.

|FP-Semantik|Erklärung
|-|-|
|Rundung Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe können ignoriert werden.<br/>Zwischenausdrücke möglicherweise am kleiner als die Genauigkeit gemäß leistungsanforderungen registrieren gerundet.|
|Algebraische Transformationen|Der Compiler möglicherweise Ausdrücke entsprechend reelle Zahl assoziativen, distributive Algebra Transformation. Diese Transformationen sind weder präzise noch richtig sein nicht garantiert.|
|Kontraktionen|Immer aktiviert. vom Pragma kann nicht deaktiviert werden `fp_contract`|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler kann die Auswertung von Gleitkomma Ausdrücken Neuanordnen von selbst, wenn Sie solche Änderungen die Endergebnisse ändern können.|
|FPU Umgebung Zugriff|Deaktiviert. Nicht verfügbar|
|Gleitkommaausnahmen-Semantik|Deaktiviert. Nicht verfügbar|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>Die Semantik für Gleitkommazahlen Ausdrücke unter fp Rundung

Im Gegensatz zu den fp: präzise Modell, das fp: fast-Modell führt zwischenberechnungen zum optimalen mit einfacher Genauigkeit. Typenumwandlungen Rundung am Zuweisungen und Funktionsaufrufe u. u. nicht immer erkannt. Beispielsweise führt die erste Funktion, die folgenden drei mit einfacher Genauigkeit Variablen (`C`, `Y` und `T`). Der Compiler möglicherweise registrieren kann diese Variablen faktisch von Typ Heraufstufen auswählen `C`, `Y` und `T` auf mit doppelter Genauigkeit.

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

In diesem Beispiel hat fp: fast den Zweck der ursprünglichen Funktion unterlaufen. Die endgültige optimiert Ergebnis, in der Variablen gespeicherten `sum`, möglicherweise ziemlich perturbed aus zum richtigen Ergebnis.

Unter fp versucht der Compiler in der Regel darin, dass mindestens die Genauigkeit, indem Sie den Quellcode einfügen. In einigen Fällen kann der Compiler jedoch auszuführenden zwischenausdrücke bei Auswählen einer *geringere Genauigkeit* als im Quellcode angegeben. Beispielsweise ruft der erste Codeblock unten eine Version mit doppelter Genauigkeit der Quadratwurzel Funktion. Fp: fast unter bestimmten Umständen, z. B. wenn das Ergebnis und die Operanden der Funktion explizit in die einfache Genauigkeit umgewandelt werden vom Compiler möglicherweise wählen Sie zum Ersetzen des Aufrufs der mit doppelter Genauigkeit `sqrt` durch einen Aufruf an eine einfache Genauigkeit `sqrtf`Funktion. Da Umwandlungen sicherzustellen, dass den Wert in `sqrt` und der Wert stammt auf einfache Genauigkeit gerundet werden, dies ändert nur die Stelle von Rundung. Wenn Sqrt eingeht ein Wert mit doppelter Genauigkeit wurde und der Compiler hat diese Transformation so viele wie die Hälfte der Genauigkeit Bits könnte falsch sein.

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

Obwohl weniger genau diese Optimierung möglicherweise besonders vorteilhaft Geschäftsgruppen mit Prozessoren, die einfache Genauigkeit, systeminterne Versionen von Funktionen, z. B. bereitstellen `sqrt`. Nur präzise Wenn der Compiler diese Optimierungen verwendet ist Plattform und Kontext abhängig.

Darüber hinaus besteht keine garantierte Konsistenz für die Genauigkeit der intermediate Berechnungen, die auf einer beliebigen Genauigkeit-Ebene für den Compiler verfügbar durchgeführt werden kann. Obwohl der Compiler versucht, die mindestens die Genauigkeit gemäß den Code zu gewährleisten, können fp den Optimierer Downcasting intermediate Berechnungen schneller oder kleineren Computercode zu erstellen. Beispielsweise kann der Compiler weiter den Code oben optimieren, einige der intermediate Multiplikationen auf einfache Genauigkeit gerundet.

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

Diese Art von zusätzlichen Rundung möglicherweise verwenden Sie eine niedrigere Genauigkeit Gleitkommaeinheit, z. B. SSE2, einige der intermediate Berechnungen ausführen. Die Genauigkeit der fp Rundung ist daher Plattform abhängig. Code, der auch für einen oder mehrere Prozessoren kompiliert funktioniert gut für einen anderen Prozessor möglicherweise nicht unbedingt. Es obliegt dem Benutzer zu bestimmen, ob die Geschwindigkeit Vorteile überwiegen im Vergleich zu Genauigkeit Probleme.

Wenn fp-Optimierung für eine bestimmte Funktion besonders problematisch ist, der Gleitkomma-Modus gewechselt werden, lokal zum fp: präzise mithilfe der `float_control` Compiler-Pragma.


### <a name="algebraic-transformations-under-fpfast"></a>Algebraische Transformationen unter fp

Das FP-Modus kann der Compiler auszuführenden bestimmte, unsichere algebraische Transformationen in Gleitkommazahlen zeigen Ausdrücke. Beispielsweise können die folgenden Optimierungen für unsicheren unter fp eingesetzt werden.

||||
|-|-|-|
|Ursprüngliche Code|Schritt #1|Schritt #2
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

In Schritt 1, berücksichtigt der Compiler, die `z = y – a – b` ist immer gleich null. Obwohl dies technisch gesehen eine ungültige Beobachtung ist, ist es unter fp zulässig. Der Compiler gibt dann den konstanten Wert 0 (null) für jede nachfolgende Verwendung von Variablen Z weiter. In Schritt 2, optimiert der Compiler Weitere durch genaues betrachten, die `x - 0 == x`, `x * 0 == 0`usw. Obwohl dieser Beobachtungen nicht unbedingt gültig sind, sind sie erneut unter fp zulässig. Der optimierte Code ist nun viel schneller, aber auch erheblich weniger genau oder sogar falsch sein.

Eine der folgenden (unsicheren) algebraischen Regeln kann durch den Optimierer verwendet werden, wenn das FP-Modus aktiviert ist:

|||
|-|-|
|Formular|Beschreibung|
|`(a + b) + c = a + (b + c)`|Assoziative Regel hinzufügen|
|`(a * b) * c = a * (b * c)`|Assoziative Regel für Multiplikation|
|`a * (b + c) = a * b + b * c`|Verteilung der Multiplikation erfolgt vor addition|
|`(a + b)(a - b) = a * a - b * b`|Algebraische Umgestalten|
|`a / b = a * (1 / b)`|Division durch Kehrwert|
|`a * 1.0 = a, a / 1.0 = a`|Multiplikative Identität|
|`a ± 0.0 = a, 0.0 - a = -a`|Additive Identität|
|`a / a = 1.0, a - a = 0.0`|Abbruch|

Wenn fp-Optimierung für eine bestimmte Funktion besonders problematisch ist, der Gleitkomma-Modus gewechselt werden, lokal zum fp: präzise mithilfe der `float_control` Compiler-Pragma.

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>Reihenfolge der Auswertung der Gleitkomma-Ausdruck unter fp

Im Gegensatz zu fp: präzise, FP kann der Compiler Neuanordnen von Gleitkommaoperationen um Code schneller zu erzeugen. Daher möglicherweise einige Optimierungen unter fp die gewünschte Reihenfolge der Ausdrücke nicht beibehalten. Betrachten Sie beispielsweise die folgende Funktion, die berechnet das Skalarprodukt zweier n-dimensionale Vektoren aus.

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

Unter fp, kann der Optimierer eine skalare Reduzierung der Ausführen der `dotProduct` Funktion transformieren effektiv die Funktion wie folgt:

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

In der optimierte Version der Funktion sind vier separaten Produkt Quarter-gleichzeitig ausgeführt werden und dann hinzugefügt zusammen. Diese Optimierung kann die Berechnung des beschleunigen der `dotProduct` durch so viel wie ein Faktor von vier je nach dem Zielprozessor, aber das endgültige Ergebnis sind möglicherweise ungenau daher hinsichtlich es unbrauchbar werden. Wenn diese Optimierungen für einzelne Funktion oder Übersetzungseinheit besonders problematisch sind, der Gleitkomma-Modus gewechselt werden, lokal zum fp: präzise mithilfe der `float_control` Compiler-Pragma.

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Das fp: strict-Modus für Gleitkomma-Semantik

Wenn das fp: strict-Modus aktiviert ist, der Compiler diese fp dieselben Regeln befolgt: präzise verwendet beim Optimieren von Gleitkommaoperationen. Dieser Modus ist auch Gleitkommaausnahme Semantik und Empfindlichkeit gegenüber der FPU-Umgebung aktiviert und deaktiviert bestimmte Optimierungen, wie z. B. Kontraktionen. Es ist die strengste Betriebsmodus.

Das fp: strict Gleitkomma-Modus aktiviert ist, mit der [/fp: strict](fp-specify-floating-point-behavior.md) Befehlszeilencompiler Switch wie folgt:

> CL/fp: strict source.cpp

In diesem Beispiel weist den Compiler verwenden fp: strict Semantik, die beim Generieren von Code für die source.cpp-Datei. Das fp: strict-Modell kann auch aufgerufen werden, für einen Basis Funktion, indem Sie mithilfe der `float_control` Compiler-Pragma.

Weitere Informationen finden Sie im Abschnitt [Float_control-Pragma](#the-float-control-pragma).

Unter dem fp: strict-Modus führt der Compiler keine Optimierungen, die die Genauigkeit von gleitkommaberechnungen perturb. Der Compiler wird am Zuweisungen immer korrekt gerundet, typenumwandlungen und Funktionsaufrufe und fortgeschrittene Rundung konsistent erfolgt auf die gleiche Genauigkeit wie die FPU registriert. Gleitkommaausnahmen Semantik und FPU Umgebung Empfindlichkeit sind standardmäßig aktiviert. Bestimmte Optimierungen, wie z. B. Kontraktionen, sind deaktiviert, da der Compiler nicht, in jedem Fall auf Richtigkeit garantieren kann.

|fp: strict Semantik|Erklärung|
|-|-|
|Rundung Semantik|Typenumwandlungen explizite Rundung am Zuweisungen und Funktionsaufrufe<br/>Zwischenausdrücke werden an Register Genauigkeit ausgewertet.<br/>Identisch mit fp: präzise|
|Algebraische Transformationen|Strenge Einhaltung nicht assoziativ, nicht distributive Gleitkomma Algebra verglichen werden, es sei denn, eine Transformation immer garantiert wird erzeugen identische Ergebnisse.<br/>Identisch mit fp: präzise|
|Kontraktionen|Immer deaktiviert|
|Reihenfolge der Auswertung von Gleitkommazahlen|Der Compiler wird nicht die Auswertung von Ausdrücken Gleitkomma neu anordnen.|
|FPU Umgebung Zugriff|Immer aktiviert.|
|Gleitkommaausnahmen-Semantik|Standardmäßig aktiviert.|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Gleitkommaausnahmen Semantik unter fp: strict

Standardmäßig Gleitkommaausnahme Semantik aktiviert sind, unter dem fp: strict-Modell. Um diese Semantik zu deaktivieren, verwenden Sie entweder die **/fp: außer-** wechseln, oder stellen Sie vor einem `float_control(except, off)` Pragma.

Weitere Informationen finden Sie in den Abschnitten [Aktivierung von Gleitkommaausnahmen Semantik](#enabling-floating-point-exception-semantics) und [Float_control-Pragma](#the-float-control-pragma).

## <a name="the-fenvaccess-pragma"></a>Fenv_access-pragma

Syntax:

```cpp
#pragma fenv_access( [ on  | off ] )
```

Die [Fenv_access](../../preprocessor/fenv-access.md) Pragma kann der Compiler bestimmte Optimierungen vornehmen möchten, die FPU flagtests und modusänderung FPU unterlaufen möglicherweise. Bei den Status der `fenv_access` deaktiviert ist, wird der Compiler kann davon ausgehen die standardmäßige FPU Modi gelten und, die FPU-Flags sind nicht getestet. Standardmäßig-Umgebung Zugriff ist deaktiviert, für die fp: präzise Modus, obwohl es explizit aktiviert werden kann mithilfe dieses Pragma. Unter fp: strict, `fenv_access` ist immer aktiviert und kann nicht deaktiviert werden. Unter fp `fenv_access` immer deaktiviert und kann nicht aktiviert werden.

Wie in der fp beschrieben: präzise Abschnitt einige Programmierer möglicherweise alter Gleitkomma Rundung Richtung mit der `_controlfp` Funktion. Beispielsweise führen zur Berechnung der oberen und unteren Fehlergrenzen auf arithmetische Operationen einige Programme zweimal dieselbe Berechnung zunächst beim Runden in Richtung minus unendlich aus, und klicken Sie dann beim Runden in Richtung plus unendlich. Da die FPU auf eine praktische Möglichkeit zur Kontrolle Rundung bereitstellt, können Programmierer Rundungsmodus zu ändern, indem Sie die FPU-Umgebung ändern. Der folgende Code berechnet, dass Fehler genauer ein Gleitkomma Multiplikation gebunden werden, durch Ändern der FPU-Umgebung.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Wenn deaktiviert, die `fenv_access` Pragma kann der Compiler die FPU standardumgebung wird davon ausgegangen, weshalb des Optimierers frei, um die Aufrufe von ignorieren `_controlfp` und zur Reduzierung der oben genannten Zuweisungen zu `cUpper = cLower = a*b`. Wenn aktiviert, jedoch `fenv_access` verhindert diese Optimierungen.

Programme können auch das statuswort FPU zum Erkennen bestimmter Gleitkommafehlern überprüfen. Der folgende Code z. B. überprüft aufgrund einer Division durch Null und ungenau Bedingungen

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

Wenn `fenv_access` ist deaktiviert, kann der Compiler die Ausführungsreihenfolge der Gleitkomma-Ausdrücke, daher möglicherweise Unterwandern die FPU Status überprüft ordnen. Aktivieren der `fenv_access` verhindert diese Optimierungen.

## <a name="the-fpcontract-pragma"></a>Fp_contract-pragma

Syntax:

```cpp
#pragma fp_contract( [ on | off ] )
```

Wie in der fp beschrieben: präzise Abschnitt Kontraktion ist eine wesentliche architektonische-Funktion für viele moderne gleitkommaeinheiten. Kontraktionen bieten die Möglichkeit zum Ausführen einer Multiplikation, gefolgt von den Zusatz als einzelner Vorgang und kein intermediate runden Fehler. Diese einzelnen Anweisungen sind schneller als separate Ausführung multiply "und" Hinzufügen von Anweisungen und genauer sind, da es ist keine intermediate Rundung des Produkts. Ein Vorgang vertraglich können berechnet den Wert des `(a*b+c)` wie, wenn beide Vorgänge mit unendlicher Genauigkeit berechnet wurden, und klicken Sie dann auf gerundet der am nächsten Gleitkommazahl. Diese Optimierung kann erheblich beschleunigen von Funktionen mit mehreren multiply verzahnt und Vorgänge hinzufügen. Betrachten Sie beispielsweise den folgenden Algorithmus, der berechnet das Skalarprodukt zweier n-dimensionale Vektoren aus.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Diese Berechnung erfolgen kann eine Reihe von multiply add Anweisungen der Form `p = p + x[i]*y[i]`.

Die [Fp_contract](../../preprocessor/fp-contract.md) Pragma gibt an, ob Gleitkomma Ausdrücke verkürzt werden können. Standardmäßig wird das fp: präzise Modus ermöglicht Kontraktionen, da sie die Genauigkeit und Geschwindigkeit verbessern. Kontraktionen sind für den Modus fp: fast immer aktiviert. Jedoch, da Kontraktionen die explizite Erkennung von fehlerbedingungen, unterlaufen können die `fp_contract` Pragma immer deaktiviert, unter dem fp: strict-Modus. Beispiele für Ausdrücke, die möglicherweise verkürzt, wenn die `fp_contract` Pragma aktiviert ist:

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

Die **/fp: präzise**, **/fp: fast**, **/fp: strict** und **/fp: außer** Switches steuern Gleitkomma-Semantik für eine Datei von Datei Basis. Die [Float_control](../../preprocessor/float-control.md) Pragma bietet diese Kontrolle auf Grundlage von Funktion.

Syntax:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

Die Pragmas `float_control(push)` und `float_control(pop)` bzw. push und pop von den aktuellen Status der Gleitkomma-Modus und die Ausnahme-Option auf einen Stapel. Beachten Sie, dass der Status der `fenv_access` und `fp_contract` Pragma sind nicht betroffen `pragma float_control(push/pop)`.

Das Pragma Aufrufen `float_control(precise, on)` wird aktiviert und `float_control(precise, off)` präzise-Modus-Semantik wird deaktiviert. Entsprechend dem Pragma `float_control(except, on)` wird aktiviert und `float_control(except, off)` Ausnahme-Semantik wird deaktiviert. Ausnahme Semantik kann nur aktiviert werden, wenn die genaue Semantik auch aktiviert werden. Wenn das optionale `push` Argument vorhanden ist, die Zustände der `float_control` Optionen werden vor der Änderung der Semantik abgelegt.

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>Durch Festlegen des Gleitkomma semantische Modus regelmäßig nach Funktion

Die Befehlszeilenoptionen werden in der Tat Kurzschreibweise zum Festlegen der vier verschiedene Gleitkommapragmas. Um einen bestimmten Gleitkomma semantische Modus auf Basis von Funktion explizit auszuwählen, wählen Sie jede der vier Gleitkommazahlen Option-Pragmas, wie in der folgenden Tabelle beschrieben:

||||||
|-|-|-|-|-|
||float_control(precise)|float_control(EXCEPT)|fp_contract|fenv_access|
|/ fp: strict|an|an|Ausschalten|an|
|/ fp: strict/fp: außer-|an|Ausschalten|Ausschalten|an|
|/ fp: präzise|an|Ausschalten|an|Ausschalten|
|/ fp: präzise/fp: außer|an|an|an|Ausschalten|
|/ fp: fast|Ausschalten|Ausschalten|an|Ausschalten|

Aktivieren Sie beispielsweise die folgenden explizit fp-Semantik.

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> Ausnahme Semantik muss vor einem ausschalten "präzise" Semantik durch ausgeschaltet werden.

## <a name="enabling-floating-point-exception-semantics"></a>Aktivieren der Gleitkommaausnahme-Semantik

Bestimmte Gleitkomma Ausnahmebedingungen, z. B. Division durch 0 (null), können dazu führen, dass die FPU um eine Hardwareausnahme zu signalisieren. Gleitkommaausnahmen sind standardmäßig deaktiviert. Gleitkommaausnahmen werden durch Ändern der FPU-Steuerwort mit aktiviert die `_controlfp` Funktion. Der folgende Code ermöglicht z. B. der Gleitkommaausnahme aufgrund einer Division durch Null:

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

Wenn die Ausnahme aufgrund einer Division durch Null aktiviert ist, wird jeder Divisionsvorgang mit einen Nenner gleich 0 (null) eine FPU-Ausnahme auf die Signalisierung ausgelöst.

Rufen Sie zum Wiederherstellen der FPU-Steuerwort in den Standardmodus `_controlfp(_CW_DEFAULT, ~0)`.

Aktivieren der Gleitkommaausnahme Semantik mit den **/fp: außer** Flag ist nicht identisch mit der Aktivierung von Gleitkommaausnahmen. Wenn Gleitkommaausnahme Semantik aktiviert sind, muss der Compiler die Möglichkeit berücksichtigen, dass alle Gleitkommaoperation möglicherweise eine Ausnahme auslöst. Da die FPU auf eine separate Prozessoreinheit ist, können Anweisungen ausführen, auf die FPU gleichzeitig mit anderen Einheiten Anweisungen ausgeführt werden.

Wenn eine Gleitkommaausnahme aktiviert ist, wird die FPU Anhalten der Ausführung der problematischen Anweisung und eine Ausnahmebedingung signalisiert werden durch Festlegen der FPU-statuswort. Wenn die CPU die nächste gleitkommaanweisung erreicht wird, überprüft die Tabelle zunächst für alle ausstehenden FPU Ausnahmen aus. Liegt eine ausstehende Ausnahme, fängt der Prozessor ihn durch Aufrufen von einem Ausnahmehandler, der vom Betriebssystem bereitgestellt. Dies bedeutet, dass bei eine Gleitkommaoperation eine Ausnahmebedingung trifft, die entsprechende Ausnahme nicht erkannt wird, bis der nächste Gleitkomma-Vorgang ausgeführt wird. Der folgende Code wird z. B. eine Ausnahme aufgrund einer Division durch Null aufgefangen:

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

Wenn eine Division-durch-Null-Bedingung im Ausdruck tritt auf, eine = b/c, FPU wird nicht Trap/auslösen die Ausnahme, bis die nächste Gleitkomma-Operation im Ausdruck 2.0 * b. Daraus ergibt sich die folgende Ausgabe:

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Die mit der ersten Zeile der Ausgabe entspricht Printf sollte nicht erreicht wurde; Es wurde erreicht, da der Gleitkommaausnahme verursacht durch den Ausdruck b/c ausgelöst wurde nicht, bis die Ausführung 2.0 erreicht * b. Zum Auslösen der Ausnahme unmittelbar nach dem Ausführen von b/c muss der Compiler eine Anweisung "Warten" einfügen:

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

Diese Anweisung "Warten" erzwingt, dass den Prozessor mit dem Status der FPU synchronisieren und alle ausstehenden Ausnahmen zu behandeln. Generiert der Compiler nur diese "Warten" Anweisungen bei der Gleitkomma-Semantik aktiviert sind. Wenn diese Semantik wie vorhanden, standardmäßig sind deaktiviert sind, dass Programme bei Gleitkommaausnahmen mit Synchronizität Fehler, wie oben, auftreten.

Wenn Gleitkomma Semantik aktiviert sind, der Compiler nicht nur "Warten" Anweisungen einführen, es wird auch verhindern, dass des Compilers illegal optimieren gleitkommacode Wiederherstellungsprobleme möglicher Ausnahmen. Dies schließt alle Transformationen, die die Punkte zu ändern, an denen Ausnahmen ausgelöst werden. Aufgrund dieser Faktoren kann die Effizienz der generierte Computercode daher beeinträchtigen die Leistung einer Anwendung beim Aktivieren der Gleitkomma-Semantik erheblich reduzieren.

Gleitkommaausnahmen Semantik sind standardmäßig aktiviert, unter dem fp: strict-Modus. So aktivieren Sie diese Semantik der fp: präzise Modus hinzufügen der **/fp: außer** an den Compiler, die Befehlszeile zu wechseln. Gleitkommaausnahmen Semantik kann auch aktiviert und deaktiviert Sie für einen Basis Funktion, indem Sie mithilfe der `float_control` Pragma.

### <a name="floating-point-exceptions-as-c-exceptions"></a>Gleitkommaausnahmen als C++-Ausnahmen

Wie bei allen Hardwareausnahmen, Gleitkommaausnahmen führen eine C++-Ausnahme nicht systemintern, sondern stattdessen eine strukturierte Ausnahme auslösen. Um C++-Ausnahmen strukturierte Gleitkommaausnahmen zuzuordnen, können Benutzer eine benutzerdefinierte SEH-Ausnahme-Konvertierer einführen. Stellen Sie zunächst eine C++-Ausnahme, die für jede Gleitkommaausnahme vor:

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

Führen Sie anschließend eine Übersetzungsfunktion, die eine Gleitkommazahl SEH-Ausnahme erkennt, und die entsprechenden C++-Ausnahme auslösen. Um diese Funktion verwenden zu können, legen Sie das Konvertierungsprogramm strukturierte Ausnahmehandler für den aktuellen Thread des Prozesses mit der [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) Funktion aus der Common Language Runtime-Bibliothek.

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

Nachdem diese Zuordnung initialisiert wird, verhält, als wären sie C++-Ausnahmen sind Gleitkommaausnahmen auf. Zum Beispiel:

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

[Jeder Computer Scientist zu Gleitkommazahlen Wissenswertes](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf) von David Stöber.

## <a name="see-also"></a>Siehe auch

[Codeoptimierung](optimizing-your-code.md)<br/>
