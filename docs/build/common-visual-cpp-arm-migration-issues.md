---
title: "H&#228;ufig auftretende ARM-Migrationsprobleme bei Visual C++"
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
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# H&#228;ufig auftretende ARM-Migrationsprobleme bei Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der gleiche Visual C\+\+\-Quellcode führt möglicherweise unterschiedliche Ergebnisse auf die ARMarchitektur, als er auf x86\- oder x64\-Architekturen ausführt.  
  
## Quellen von Migrationsproblemen  
 Viele Probleme, die beim, wenn Sie Code von x86 migrieren, oder x64\-Architekturen zur ARMarchitektur zu den Quellcodekonstrukten verknüpft werden, die möglicherweise nicht definiertes aufgerufen haben, haben Implementierung\-definiert oder nicht definiertes Verhalten.  
  
 Nicht definiertes Verhalten  
 Verhalten, das der C\+\+\-Standard nicht definiert und durch einen Vorgang verursacht wird, der nicht angemessenes Ergebnis\-für Beispiel verfügt, einen Gleitkommawert in eine ganze Zahl umgewandelt ohne Vorzeichen oder verschieben einen Wert von mehreren Positionen, der negativ ist oder die Anzahl der Bits in seinem gehöherstuften Typ überschreitet.  
  
 Implementierung\-definiertes Verhalten  
 Verhalten, dass der gemäß den Compileranbieter erfordert zu definieren und zu dokumentieren.  Ein Programm kann auf Implementierung\-definiertem Verhalten sicher beruhen, obwohl dies möglicherweise nicht portabel ist.  Beispiele für Implementierung\-definierten Verhalten die Größen von integrierten Datentypen und deren Ausrichtungsanforderungen.  Ein Beispiel eines Vorgangs, der möglicherweise von Implementierung\-definiertes Verhalten beeinflusst wird, greift auf die variable Argumentliste zu.  
  
 Nicht definiertes Verhalten  
 Verhalten, das der C\+\+\-Standard absichtlich nicht deterministisch verlässt.  Obwohl das Verhalten als nicht deterministisch betrachtet wird, werden bestimmte Aufrufe des nicht angegebenen Verhalten durch die Compilerimplementierung bestimmt.  jedoch, ist es nicht erforderlich, damit ein Compileranbieter das Ergebnis vorgegeben oder konsistentem Verhalten zwischen vergleichbaren Aufrufen gewährleistet, und es besteht keine Notwendigkeit für Dokumentation.  Ein Beispiel für die nicht angegebenen Verhaltens ist die Reihenfolge, in der, Sub\-Ausdruck\-die einschließen, Argumente an eine Funktion ausgewertet Aufruf\-werden.  
  
 Andere Migrationsprobleme können zugeschrieben werden den Hardwareunterschieden zwischen ARM und x86 oder x64\-Architekturen, die mit dem C\+\+\-Standard anders interagieren.  Beispielsweise gibt das Modell des starken des Arbeitsspeichers und der x64\-Architektur `volatile`\- qualifizierte Variablen einige zusätzliche Eigenschaften, die verwendet wurden, um bestimmte Arten der InterThreadkommunikation in der Vergangenheit zu erleichtern.  Das \- der ARMschwache Arbeitsspeichermodell Architektur nicht unterstützt diese Verwendung, noch benötigt der C\+\+\-Standard sie.  
  
> [!IMPORTANT]
>  Obwohl `volatile` einige Eigenschaften abrufen, die verwendet werden können, um bestimmte Formulare der InterThreadkommunikation auf x86 und x64 zu implementieren, sind diese zusätzlichen Eigenschaften nicht ausreichend, InterThreadkommunikation im Allgemeinen zu implementieren.  Im C\+\+\-Standard empfiehlt, dass solche Kommunikation implementiert wird, indem Sie stattdessen entsprechende Synchronisierungsprimitive verwendet.  
  
 Da verschiedene Plattformen können diese Arten des Verhaltens anders ausdrückten, Software zwischen Plattformen kann zu portieren und Fehler\-anfällig schwierig sein, wenn sie vom Verhalten einer bestimmten Plattform abhängt.  Obwohl viele dieser Arten des Verhaltens können beachtet werden und möglicherweise stabil aussähen, ist das Erstellen auf sie mindestens und in Fällen nicht definierten oder nicht angegebenen Verhaltens, ist auch ein Fehler nicht\-portabel.  Auch sollte Verhalten, das in diesem Dokument enthalten ist, nicht an gebaut werden und kann in zukünftigen Compilern oder im der CPU\-Implementierungen ändern.  
  
## Beispielsmigrationsprobleme  
 Der Rest des Dokuments wird beschrieben, wie das unterschiedliche Verhalten dieser C\+\+\-Sprachelemente auf unterschiedlichen Plattformen unterschiedliche Ergebnisse liefern kann.  
  
### Konvertierung des unverankert ganze Zahl ohne Vorzeichen  
 Klicken Sie auf der ARMarchitektur sättigt Konvertierung eines Gleitkommawerts in eine 32\-Bit\-Ganzzahl zum nächsten Wert, den die ganze Zahl darstellen kann, wenn der Gleitkommawert außerhalb des Bereichs befindet, den die ganze Zahl darstellen kann.  Auf den x86\- und x64\-Architekturen wird die Konvertierungsbauerntricks, wenn die ganze Zahl ohne Vorzeichen ist oder auf \-2147483648 festgelegt, wenn die ganze Zahl signiert wird.  Keine dieser Architekturen unterstützen direkt die Konvertierung von Gleitkommawerten werden kleineren ganzzahligen Typen; Stattdessen werden die Konvertierungen in 32 Bits ausgeführt, und die Ergebnisse werden in einen kleineren abgeschnitten.  
  
 Für die ARMarchitektur bedeutet die Kombination der Sättigung und des Abschneidens, dass die Konvertierung Typen den ohne Vorzeichen ordnungsgemäß kleinere Typen ohne Vorzeichen sättigt, wenn sie eine 32\-Bit\-Ganzzahl sättigt, ein abgeschnittenes Ergebnis für Werte, die größer sind, als der kleinere Typ darstellen kann, aber zu klein bereitstellt, um die vollständige 32\-Bit\-Ganzzahl zu sättigen.  Konvertierung sättigt auch ordnungsgemäß für 32\-Bit\-Ganzzahlen mit Vorzeichen, aber das Abschneiden von gesättigten, Zahlen mit Vorzeichen ergibt \-1 für positiv\-gesättigte Werte und 0 für negativ\-gesättigte Werte.  Konvertierung in einer kleineren Zahl mit Vorzeichen stellt ein abgeschnittenes Ergebnis, das unvorhersehbar ist.  
  
 Für die x86\- und x64\-Architekturen machen die Kombination des Umgriffsverhaltens für vorzeichenlose Konvertierungen Ganzzahl und der expliziten Bewertung für ganzzahlige Konvertierungen mit Vorzeichen auf Überlauf, zusammen mit Clipping, die Ergebnisse für die meisten Schichten unvorhersehbar, wenn sie zu groß sind.  
  
 Diese Plattformen unterscheiden sich auch in, wie diese Konvertierung von NaN \(NOT\-ein\-Zahl\) in ganzzahlige Typen behandeln.  Auf ARM Nan\-Bekehrte zu 0x00000000; auf x86 und x64 konvertiert es 0x80000000.  
  
 Gleitkommakonvertierung kann nur an gebaut werden, wenn Sie wissen, dass der Wert innerhalb des Bereichs des ganzzahligen Typs ist, dass er konvertiert wird.  
  
### Schiebeoperator\-\(\<\< \>\>\) Verhalten  
 Klicken Sie auf der ARMarchitektur kann ein \- Wert 255 Bits verschoben oder links bis zu sein, bevor das Muster beginnt, um zu überprüfen.  Auf x86 und x64\-Architekturen wird das Muster an jeder Vielfachen von 32 wiederholt, es sei denn, die Quelle des Musters eine 64\-Bit\-Variable ist; in diesem Fall, in den Musterwiederholungen an jeder Vielfachen von 64 auf x64 und an jeder Vielfachen von 256 auf x86, in dem eine Softwareimplementierung platziert wird.  Für eine 32\-Bit\-Variable, die einen Wert von 1 verschobenem links von 32 Positionen hat, auf ARM ist das Ergebnis 0, auf x86 ist das Ergebnis 1, und auf x64 ist das Ergebnis auch 1.  Wenn die Quelle des Werts eine 64\-Bit\-Variable handelt, ist die Auswirkungen auf alle drei Plattformen ist 4294967296, und der Wert jedoch nicht "Umbruch", bis er 64 Positionen auf x64 verschoben wurden oder 256 Positionen im ARM und x86.  
  
 Da das Ergebnis einer Schiebeoperation, die die Anzahl der Bits im Quelltyp überschreitet, nicht definiert ist, wird der Compiler nicht erforderlich, konsistentes Verhalten in allen Situationen verfügen.  Wenn beide Operanden einer Verschiebung zur Kompilierzeit bekannt ist, kann der Compiler optimiert das Programm, indem er eine interne Routine verwendet, um das Ergebnis der Verschiebung und dann das Ergebnis anstelle der Schiebeoperation vorauszuberechnen ersetzt.  Wenn der Verschiebungsbetrag zu groß ist, oder negativ, kann das Ergebnis der internen Routine anders als das Ergebnis denselben Schichtausdrucks wie durch die CPU ausgeführt.  
  
### Die Verhalten der Argument\-\(varargs\)  
 Klicken Sie auf der ARMarchitektur sind Parameter aus der Variablenargumentlisten, die auf dem Stapel übergeben werden, abhängig von Ausrichtung.  Beispielsweise ist ein 64\-Bit\-Parameter auf eine 64\-Bit\-Grenze ausgerichtet.  Auf x86 und x64 sind Argumente, die auf dem Stapel übergeben werden, nicht für Ausrichtung und packen eng.  Dieser Unterschied kann eine variadic Funktion wie `printf` bewirken, Speicheradressen zu lesen, die als Abstand auf ARM vorgesehen wurde, wenn das erwartete Layout der Variablenargumentlisten nicht genau vorliegt, auch wenn es sich für eine Teilmenge von einige Werte an den x86\- oder x64\-Architekturen funktioniert.  Betrachten Sie das folgende Beispiel:  
  
```  
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.  
// on x86 and x64 this may work for small values because %d will “parse” the low-32 bits of the argument.  
// on ARM the calling convention will align the 64-bit value and the code will print a random value  
printf("%d\n", 1LL);  
  
```  
  
 In diesem Fall kann der Fehler behoben werden, indem Sie sicherstellen, dass die richtige Formatangabe verwendet wird, für die die Ausrichtung des Arguments betrachtet wird.  Dieser Code richtig:  
  
```  
// CORRECT: use %I64d for 64-bit integers  
printf("%I64d\n", 1LL);  
  
```  
  
### Argumentauswertungsreihenfolge  
 Da ARM, x86 und x64\-Prozessoren so unterscheiden, können sie unterschiedliche Anforderungen zu den Compilerimplementierungen und auch verschiedene Möglichkeiten für Optimierungen darstellen.  Aufgrund dieser zusammen mit anderen Faktoren wie Sie Aufrufkonventions\- und Optimierungseinstellungen, lässt ein Compiler möglicherweise Funktionsargumente in einer anderen Reihenfolge auf verschiedenen Architekturen oder aus, wenn die anderen Faktoren geändert werden.  Dies kann das Verhalten einer Anwendung verursachen, die auf einer bestimmten Auswertungsreihenfolge, unerwartet ändern beruht.  
  
 Diese Art von Fehler kann auftreten, wenn Argumente an eine Funktion Nebeneffekte haben, die andere Argumente der Funktion im selben Aufruf auswirken.  Normalerweise ist diese Art der Abhängigkeit einfach zu vermeiden, sie kann jedoch durch Abhängigkeiten, schwer zu erkennen sind, oder durch Operatorüberladung manchmal verdeckt werden.  Betrachten Sie dieses Codebeispiel:  
  
```  
handle memory_handle;  
  
memory_handle->acquire(*p);  
  
```  
  
 Dies wird genau definiert, aber, wenn `->` und `*` überladene Operatoren sind, wird dieser Code übersetzt wird auf einige aus, das diesem ähnelt:  
  
```  
Handle::acquire(operator->(memory_handle), operator*(p));  
```  
  
 Und wenn es eine Abhängigkeit zwischen `operator->(memory_handle)` und `operator*(p)` beruhte gibt, kann der Code auf einer bestimmten Auswertungsreihenfolge, obwohl die ursprünglichen Codeaussehung wie keiner beliebige Abhängigkeit ist.  
  
### flüchtiges Schlüsselwort\-Standardverhalten  
 Der Microsoft C\+\+\-Compiler unterstützt zwei verschiedene Interpretationen des Qualifizierers für flüchtigen Speicher, den Sie angeben können, indem Sie Compilerschalter verwenden.  Der **\/volatile:ms** Schalter wählt die Microsoft erweiterte flüchtige Semantik, das starkem Reihenfolge sicherstellen, wie betraf das herkömmliche Argument für x86 und x64 auf dem Microsoft\-Compiler aufgrund des Modells des starken Speichers auf diesen Architekturen aus.  Der **\/volatile:iso** Schalter wählt die strikte flüchtige StandardSemantik C\+\+ aus, das nicht starkem Reihenfolge sicherstellen.  
  
 Klicken Sie auf der ARMarchitektur ist der Standardwert **\/volatile:iso**, da ARMprozessoren ein schwach bestelltes Arbeitsspeichermodell haben und da ARM\-Software keine Vorversion des Bauens auf die erweiterte Semantik von **\/volatile:ms** verfügt und nicht normalerweise an Software herstellen muss, die ausführt.  Allerdings ist es weiterhin manchmal nützlich oder sogar erforderlich, ein Rüstungsprogramm zu kompilieren, um die erweiterte Semantik zu verwenden.  Zum Beispiel kann er zu ressourcenintensiv, ein Programm zu portieren, um die Semantik ISO C\+\+ zu verwenden, oder Treiber\-Software muss möglicherweise die herkömmliche Semantik befolgen, um ordnungsgemäß zu funktionieren.  In diesen Fällen können Sie den \- Schalter verwenden, **\/volatile:ms** jedoch um die herkömmliche flüchtige Semantik auf ARMzielen neu zu erstellen, muss der Compiler Arbeitsspeicherbarrieren um jedes Lesen einfügen oder einer `volatile`\-Variable schreiben, um starke Reihenfolge zu erzwingen, die negativen Auswirkungen auf die Leistung haben kann.  
  
 Auf den x86\- und x64\-Architekturen ist der Standardwert **\/volatile:ms**, da viele der Software, die bereits für diese Architekturen erstellt wurde, indem der Microsoft C\+\+\-Compiler verwendete, darauf beruht.  Wenn Sie x86 und x64\-Programme kompilieren, können Sie den **\/volatile:iso** Schalter angeben, um zu helfen, unnötiges Vertrauen auf der herkömmlichen flüchtigen Semantik zu vermeiden, und Portabilität heraufzustufen.  
  
## Siehe auch  
 [Konfigurieren von Programmen für ARM\-Prozessoren](../build/configuring-programs-for-arm-processors-visual-cpp.md)