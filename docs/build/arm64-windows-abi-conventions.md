---
title: Übersicht über die ARM64-ABI-Konventionen
ms.date: 07/11/2018
ms.openlocfilehash: 537f8cf5bb8db61854bea7f4624e3dd3176c6a59
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816541"
---
# <a name="overview-of-arm64-abi-conventions"></a>Übersicht über die ARM64-ABI-Konventionen

Die grundlegenden ABI für Windows bei der Kompilierung und Ausführung auf ARM-Prozessoren im 64-Bit-Modus (ARMv8 oder höher Architekturen) zum größten Teil, folgt die ARM EABI für standard AArch64. In diesem Artikel werden einige wichtige Annahmen und Änderungen aus, was in die EABI dokumentiert ist. Weitere Informationen zur 32-Bit-ABI, finden Sie unter [Übersicht der ARM-ABI-Konventionen](overview-of-arm-abi-conventions.md). Weitere Informationen über die standardmäßige ARM EABI finden Sie unter [Application Binary Interface (ABI) für die ARM-Architektur](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (externer Link).

## <a name="definitions"></a>Definitionen

ARM verfügt über mehrere Begriffe definiert, mit der Einführung von 64-Bit-Unterstützung können:

- **AArch32** – die ältere 32-Bit-Anweisung set-Architektur (ISA), der von ARM, einschließlich der Ausführung des Thumb-Steuerelement im definiert.
- **AArch64** – die neue 64-Bit-Anweisung set-Architektur (ISA), der von ARM definiert.
- **ARMv7** : die Angabe von "7. Generation" ARM-Hardware, die nur Unterstützung für AArch32 enthält. Dies ist die Version der ARM-Hardware, die die erste Version von Windows für ARM unterstützt.
- **ARMv8** : die Angabe von "8. Generation" ARM-Hardware, das sowohl für AArch32 AArch64 unterstützt.

Zusätzlich zu diesen Definitionen ist in Windows verwendet wir diese Begriffe:

- **ARM** – bezieht sich auf die 32-Bit-ARM-Architektur (AArch32). Dies wird manchmal als WoA (Windows auf ARM) bezeichnet.
- **ARM32** – identisch mit ARM, oben; wird in diesem Dokument aus Gründen der Übersichtlichkeit.
- **ARM64** – bezieht sich auf die 64-Bit-ARM-Architektur (AArch64). Es gibt keine als WoA64.

Schließlich werden in Bezug auf Datentypen, die folgenden Definitionen von ARM verwiesen:

- **Short-Vektor** – Dies ist ein Datentyp, der direkt in SIMD darstellbar ist, d. h. einen Vektor von 8 oder 16 Byte-Wert, der Elemente, die Größe (8 oder 16 Bytes), ausgerichtet sind, in dem jedes Element 1, 2, 4 oder 8 Byte sein kann
- **Zu HFA (homogen Floating-Point Aggregat)** – Dies ist ein Datentyp mit 2 bis 4 identische Gleitkomma Mitglieder (float oder Double-Werte)
- **HVA (homogen Short-Vektor-Aggregat)** – Dies ist ein Datentyp mit 2 bis 4 identische kurze-Vektor-Mitglieder

## <a name="base-requirements"></a>Grundanforderungen

Die ARM64-Version von Windows wird vorausgesetzt, dass dieser eine ARMv8 ausgeführt wird, oder höher Architektur zu jeder Zeit. Beide Gleitkomma- und werden als NEON-Unterstützung in der Hardware vorhanden sein.

Obwohl die ARMv8-Spezifikation für die vollständige Unterstützung von AArch32 Anwendungen gestattet, gibt es derzeit keine Pläne zur Unterstützung vorhandene ARM32-Anwendungen auf die ARM64-Version von Windows (d. h. keine Pläne für WOW64) ausgeführt. Dies ist abhängig von eine erneute Auswertung in der Zukunft, aber es ist die aktuelle arbeiten.

Die ARMv8-Spezifikation werden neue optional Verschlüsselung und CRC-Hilfsprogramm Opcodes für AArch32 und AArch64 beschreibt. Unterstützung für diese ist zurzeit optional, jedoch empfohlen. Code, der dieser Opcodes nutzen möchte, sollten für ihre Existenz Überprüfungen zur Laufzeit ausführen.

## <a name="endianness"></a>Endianness

Wie führt mit der ARM32 Version von Windows, auf ARM64 Windows im little-Endian-Modus. Der Wechsel Bytereihenfolge ist schwer zu erreichen, ohne die Kernel-Modus-Unterstützung in AArch64, daher ist es leichter durchgesetzt werden.

## <a name="alignment"></a>Ausrichtung

ARM64 unter Windows können die CPU-Hardware, falsch ausgerichtete Zugriffe transparent behandeln. In eine Verbesserung von AArch32 kann die diese Unterstützung jetzt auch für alle ganzzahlzugriffe (einschließlich mit mehreren Wörtern zugreift) sowie für Gleitkomma-Zugriff.

Zugriffe auf den Speicher für nicht-Cache (Gerät) müssen jedoch noch immer ausgerichtet werden. Dies bedeutet, dass es ist Code, der aufgerufen werden kann, um falsch ausgerichtete Daten aus dem nicht zwischengespeicherten Speicher, Schreib-/es muss spielen Dinge, die sicher und stellen Sie sicher, dass alle Zugriffe ausgerichtet sind.

## <a name="integer-registers"></a>Ganzzahlregister

Die Architektur der AArch64 unterstützt 32 Ganzzahlregister, die im folgenden zusammengefasst:

|Register|Volatil?|Rolle|
|-|-|-|
x0|Volatil|Parameter/neu registrieren, 1, Ergebnis registrieren
x1-x7|Volatil|Parameter/neu registrieren 2 bis 8
x8-x15|Volatil|Scratch-Register
x16-x17|Volatil|Intra-Procedure-Call/Scratch-Register
x18|Nicht volatil|Registrieren Sie Plattform: im Kernelmodus verweist auf KPCR für den aktuellen Prozessor; im Benutzermodus verweist auf TEB
x19-x28|Nicht volatil|Scratch-Register
x29/fp|Nicht volatil|Frame-Pointer
x30/lr|Nicht volatil|Link-Register

Jedes Register kann als 64-Bit-Wert (über X0-X30) oder als 32-Bit-Wert (über w0-w30) zugegriffen werden. 32-Bit-Betrieb erweitern 0 (null)-ihre Ergebnisse bis zu 64 Bits.

Sehen Sie die Parameter finden Sie Details für die Verwendung der Parameter Register übergeben.

Beachten Sie, dass im Gegensatz zu AArch32, den PC "und" SP keine indizierten registriert, und daher nur begrenzt wie auf sie zugegriffen werden können. Beachten Sie, dass es keine X31 auch registrieren möchten (die Codierung für besondere Zwecke verwendet wird).

Die Verwendung von den Frame-Pointer (x29) ist erforderlich, für die Kompatibilität mit schnelles Stack walking von ETW- und andere Dienste verwendet werden. Es muss auf den vorherigen {X29, x 30} zeigen Paar auf dem Stapel.

## <a name="floating-pointsimd-registers"></a>Gleitkomma-point/SIMD-Register

Die Architektur der AArch64 unterstützt auch 32 Gleitkomma-point/SIMD-Register, die im folgenden zusammengefasst:

Register|Volatil?|Rolle
|-|-|-|
v0|Volatil|Parameter/neu registrieren, 1, Ergebnis registrieren
v1-v7|Volatil|Parameter/neu registriert 2 bis 8
v8-v15|Nicht volatil|Scratch-Register (Beachten Sie, dass nur die unteren 64 Bits nicht flüchtigen)
v16-v31|Volatil|Scratch-Register

Jedes Register kann als ein vollständiger 128-Bit-Wert (per v0-v31 oder q0-F31) als 64-Bit-Wert (über d0-d31), als 32-Bit-Wert (über s0-s31), als ein 16-Bit-Wert (über h0-h31) oder als ein 8-Bit-Wert (über b0-b31) zugegriffen werden. Greift auf weniger als 128 Bits verwenden Sie nur die unteren Bits des Registers 128-Bit- und die verbleibenden Bits unverändert lassen, sofern nicht anders angegeben. (Beachten Sie, dass dies unterscheidet sich deutlich von AArch32, ist, in denen die kleinere Register auf größere Register gepackt wurden.)

Zusätzlich zu den datenregistern hat das gleitkommasteuerelements Register (FPCR) bestimmte Anforderungen, auf die verschiedenen Bitfelder darin:

Bits|Bedeutung|Volatil?|Rolle
|-|-|-|-|
26|AHP|Nicht flüchtigen|Alternative-Half-Precision-Steuerung
25|DN|Nicht flüchtigen|Standardmäßige NaN-Modussteuerung
24|FZ|Nicht volatil|Flush-to-Zero-Modussteuerung
23-22|RMode|Nicht volatil|Rounding-Modussteuerung
15,12-8|IDE/IXE/etc|Nicht flüchtigen|Ausnahme-Trap-Aktivierungsbits, muss immer 0 sein

## <a name="system-registers"></a>System-Register

Wie AArch32 bietet die AArch64 Spezifikation drei System kontrolliert "thread-ID" registriert sind, verwendet zugeordnet werden bzw. wie folgt:

Register|Rolle
|-|-|
TPIDR_EL0|Reserviert
TPIDRRO_EL0|Enthält die CPU-Anzahl für den aktuellen Prozessor
TPIDR_EL1|Zeigt auf KPCR-Struktur für den aktuellen Prozessor

## <a name="floating-point-exceptions"></a>Gleitkommaausnahmen

Unterstützung für IEEE-Gleitkommaausnahmen ist optional für AArch64 Systeme. Für prozessorvarianten, die Hardware-Gleitkommaausnahmen verfügen, der Windows-Kernel im Hintergrund fängt Ausnahmen ab und deaktiviert sie implizit in der Registrierung FPCR. Dadurch wird normalisiertes Verhalten zwischen prozessorvarianten sichergestellt (andernfalls entwickelter Code auf einer Plattform ohne ausnahmeunterstützung selbst unerwartete Ausnahmen erstellen, bei der Ausführung auf einer Plattform mit Unterstützung finden Sie unter Umständen).

## <a name="parameter-passing"></a>Parameterübergabe

Für nicht-Variadic-Funktionen folgt die Windows-ABI die Regeln von ARM für das Übergeben von Parametern. Diese Regeln sind direkt aus dem Prozeduraufruf-Standard für die Architektur der AArch64 Auszug:

### <a name="stage-a--initialization"></a>Stufe A – Initialisierung

Diese Phase wird genau einmal ausgeführt werden, bevor beginnt die Verarbeitung der Argumente.

1. Die nächste allgemeinen registrieren Anzahl (NGRN) wird auf 0 (null) festgelegt.

1. Die nächste SIMD und die Floating-Point registrieren Anzahl (NSRN) ist auf 0 (null) festgelegt.

1. Die Argumentadresse des nächste gestapelte (NSAA) wird mit dem aktuellen Stack-Pointer Wert (SP) festgelegt.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Stufe B – vorab-Padding und Erweiterung von Argumenten

Für jedes Argument in der Liste wird die erste übereinstimmende Regel aus der folgenden Liste angewendet. Wenn keine Regel entspricht das Argument verwendet wird, bleiben unverändert.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, dessen Größe nicht statisch vom Aufrufer und dem aufgerufenen bestimmt werden kann, ist das Argument in den Arbeitsspeicher kopiert, und das Argument durch einen Zeiger auf die Kopie ersetzt wird. (Es sind keine solche Typen in C/C++-, aber in anderen Sprachen oder in spracherweiterungen vorhanden).

1. Das Argument wird verwendet, wenn der Argumenttyp ist ein zu HFA oder einer HVA-unverändert.

1. Wenn der Argumenttyp ein zusammengesetzter Typ, die größer als 16 Bytes ist ist, wird das Argument auf vom Aufrufer zugeordneten Speicher kopiert, und das Argument durch einen Zeiger auf die Kopie ersetzt wird.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist wird die Größe des Arguments auf das nächste Vielfache von 8 Bytes aufgerundet.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Stufe C – Zuweisung von Argumenten zu Registern und zum stack

Für jedes Argument in der Liste werden wiederum die folgenden Regeln angewendet, bis das Argument zugeordnet wurde. Wenn ein Argument eines Registers zugewiesen wird kein Wert in der Registrierung nicht verwendeter Bits haben Wert angegeben. Wenn ein Argument an einen Slot Stack zugewiesen wird haben alle nicht verwendeten Auffüll-Bytes Wert nicht angegeben sind.

1. Das Argument ist ein halb-Single, Double oder Quad Gleitkommazahlen mit doppelter Genauigkeit oder kurzen Vektortyp und die NSRN, weniger als 8, und klicken Sie dann das Argument, die am niedrigstwertigen Bits von Register-V [NSRN] zugewiesen ist. Die NSRN wird um eins erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zu HFA oder einer HVA-ist, und es ausreichend verfügbaren SIMD und Gleitkommaregister (NSRN + Anzahl der Elemente im ≤ 8 gibt), wird das Argument zu SIMD Floating-Point registriert (mit einem registrieren pro Element der zu HFA oder HVA) zugeordnet. Die NSRN wird um die Anzahl der verwendeten Register inkrementiert. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zu HFA oder einer HVA-ist die NSRN auf 8 festgelegt ist, und die Größe des Arguments wird auf das nächste Vielfache von 8 Bytes aufgerundet.

1. Wenn das Argument ein zu HFA, ein HVA, ist ein Vektor Quad mit einfacher Genauigkeit, Gleitkomma oder kurz einen Typ die NSAA gerundet wird bis zu den größeren von 8 oder die natürliche Ausrichtung, der den Typ des Arguments.

1. Wenn das Argument ein Gleitkomma-halb - oder mit einfacher Genauigkeit ist, wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt wird als hätte das Argument in der unwichtigsten Bits von einem 64-Bit-Register und die verbleibenden Bits, die mit nicht angegebenen Werten gefüllt kopiert.

1. Wenn das Argument ein zu HFA ist, wird einer HVA-, halb-, Einzel-, Double-Wert - oder Quad Gleitkommazahlen mit doppelter Genauigkeit oder kurzen Vektortyp, und das Argument an der angepassten NSAA in den Speicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

1. Wenn das Argument einen Ganzzahl- oder Zeigertyp ist, ist die Größe des Arguments kleiner als oder gleich 8 Bytes und die NGRN kleiner als 8 ist das Argument in der unwichtigsten Bits x [NGRN] kopiert wird. Die NGRN wird um eins erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument eine Ausrichtung an 16 verfügt wird das NGRN klicken Sie dann auf die nächste gerade Zahl aufgerundet.

1. Wenn das Argument ein Integraltyp ist, der Größe des Arguments gleich 16 ist und dem NGRN weniger als 7 ist, ist das Argument x kopiert [NGRN]- und x [NGRN + 1]. X [NGRN] muss das untere bereits als Double-Wert-Wort für die Arbeitsspeicher-Darstellung des Arguments enthält. Die NGRN wird durch zwei erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zusammengesetzter Typ ist und die Größe in Doppelworte des Arguments nicht mehr als 8 minus NGRN, wird das Argument wird in aufeinander folgenden Allzweckregistern, kopiert x [NGRN] ab. Das Argument übergeben wird, als wären sie in die Register von einer Double Word-ausgerichtete Adresse mit der entsprechenden Reihenfolge von LDR-Anweisungen Laden von aufeinander folgenden Register aus dem Arbeitsspeicher geladen wurden (der Inhalt der alle nicht genutzten Bereichen der Register sind nicht angegeben von diesem Standard). Die NGRN wird um die Anzahl der verwendeten Register inkrementiert. Das Argument wurde nun zugeordnet.

1. Die NGRN ist auf 8 festgelegt.

1. Die NSAA wird aufgerundet auf die größere von 8 oder die natürliche Ausrichtung, der den Typ des Arguments...

1. Wenn das Argument ein zusammengesetzter Typ ist, wird das Argument in den Speicher an der angepassten NSAA kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

1. Die Größe des Arguments ist kleiner als 8 Bytes wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt ist, als ob das Argument in der unwichtigsten Bits von einem 64-Bit-Register und die verbleibenden Bits, die mit nicht angegebenen Werten gefüllt kopiert wurde.

1. Das Argument wird an der angepassten NSAA in den Speicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

### <a name="addendum-variadic-functions"></a>Nachtrag: Variadic-Funktionen

Funktionen, die eine Variable Anzahl von Argumenten akzeptieren werden anders als oben wie folgt behandelt:

1. Alle kombinierenden Zeichen ersetzt wurden, werden ähnlich behandelt; keine besondere Behandlung HFAs oder HVAs.

1. SIMD "und" Floating-Point registriert werden nicht verwendet.

Effektiv entspricht dies folgende Regeln C.12–C.15 zuweisen Argumente in einer imaginären Stack, in denen die ersten 64 Bytes des Stapels werden in den X0-X7 geladen, und alle übrigen Argumente für den Stapel normalerweise platziert werden.

## <a name="return-values"></a>Rückgabewert

Ganzzahlige Werte werden in X0 zurückgegeben. Gleitkommazahlen-Punktwerte werden in s0/d0/v0 entsprechend zurückgegeben.

Für die Rückgabe-von-Wert, der über Register übergeben werden kann, muss der Aufrufer einen Speicherblock von ausreichender Größe und Ausrichtung, um das Ergebnis aufzunehmen reservieren. Die Adresse des Speicherblocks sollte übergeben werden als zusätzliches Argument der Funktion in X8 für die POD-Typ oder in X0 (oder X1 Wenn $dies X0 übergeben wird) für nicht-POD-Typ. Der aufgerufene kann den Ergebnis-Speicherblock zu einem beliebigen Zeitpunkt während der Ausführung der Unterroutine ändern (es ist, dass keine Notwendigkeit für die aufgerufene Funktion zur Beibehaltung des Werts in X8 gespeichert, aber für nicht-POD, die Adresse dieses Puffers auch in X0 vom aufgerufenen zurückgegeben werden muss).

## <a name="stack"></a>Stapel

Nach der ABI, die vom ARM muss der Stapel bleiben, 16-Byte-ausgerichtet. AArch64 enthält eine Hardwarefunktion, die Ausrichtung der Stapel, die Fehler generiert, wenn eine Relative SP Lade- oder erfolgt und gespeicherten Prozedur nicht auf 16-Byte ist-ausgerichtet. Windows führt diese Funktion immer aktiviert.

Funktionen auf, die Zuordnen von 4 k oder mehr lohnt des Stapels müssen stellen Sie sicher, dass jede Seite vor der letzten Seite in der Reihenfolge verwendet wird, wodurch sichergestellt wird kein Code kann "leap über" die Schutzseiten, die Windows zur Erweiterung des Stacks verwendet. In der Regel erfolgt dies durch die `__chkstk` Hilfsmethode, die benutzerdefinierte Aufrufkonvention verfügt, die die gesamte stapelzuordnung geteilt durch 16 X8 übergibt.

## <a name="red-zone"></a>Rote zone

Der 16-Byte-Bereich unmittelbar unter dem aktuellen Stack-Pointer ist für die Verwendung von der Analyse reserviert und dynamische patching Szenarien. So kann sorgfältig generierter Code eingefügt werden soll dem 2 Register bei gespeichert [sp, #-16] und verwendet sie vorübergehend für beliebige Zwecke. Der Windows-Kernel wird sichergestellt, dass diese 16 Bytes nicht überschrieben wird, wenn eine Ausnahme oder ein Interrupt, sowohl Benutzer-als auch Kernel-Modus erstellt wird.

## <a name="kernel-stack"></a>Kernel-stack

Der Kernel-Modus-Standardstapel in Windows ist sechs Seiten (24 KB). Achten Sie zusätzliche Funktionen mit große Stack-Puffer im Kernel-Modus. Systemabschaltung Interrupt kann mit sehr geringem Spielraum stammen, und erstellen eine panic Stack-fehlerprüfung.

## <a name="stack-walking"></a>Durchlaufen von Stapeln

Code in Windows wird mit aktivierten Frame-Pointern kompiliert ([/Oy-](reference/oy-frame-pointer-omission.md)) zum schnellen Stackwalk zu ermöglichen. Das Fazit dieser lautet X29 (fp) im Allgemeinen auf den nächsten Link in der Kette, verweist ein {fp, Lr} handelt, der angibt, des Zeigers zum vorherigen Frame im Stack und die Rückgabeadresse Paar. Code von Drittanbietern wird empfohlen, auf Frame-Pointer auch aktivieren, um verbesserte profilerstellung und Ablaufverfolgung zu ermöglichen.

## <a name="exception-unwinding"></a>Ausnahmeentladung

Entladen während der Ausnahmebehandlung wird durch die Verwendung von entladungscodes unterstützt. Die entladungscodes sind eine Folge von Bytes, die im Abschnitt ".xdata" der ausführbaren Datei gespeichert, die den Vorgang der Prolog und Epilog auf abstrakte Weise beschreiben, die Effekte eines Funktionsprologs als Vorbereitung für die Sicherung rückgängig gemacht werden können, die Stapelrahmens des Aufrufers. Weitere Informationen zu den entladungscodes, finden Sie unter [ARM64-Ausnahmebehandlung](arm64-exception-handling.md).

Die ARM EABI gibt auch ein ausnahmeentladungsmodell, nutzt Codes entladen. Die Spezifikation angezeigte ist jedoch nicht ausreichend zum Entladen unter Windows, wobei Fälle behandelt werden müssen, in dem der Computer in der Mitte des Prologs oder Epilogs einer Funktion ist.

Code, der dynamisch generiert wird, sollte mit dynamischen Funktionstabellen über beschrieben werden `RtlAddFunctionTable` und die zugehörigen Funktionen, damit der generierte Code in der Ausnahmebehandlung teilnehmen kann.

## <a name="cycle-counter"></a>Zyklus-counter

Alle ARMv8 CPUs sind erforderlich, um einen Zyklus unterstützen Leistungsindikator registrieren. Dies ist ein 64-Bit-Register, die Windows konfiguriert wird, um auf jeder Ebene der Ausnahme (einschließlich Benutzermodus) gelesen werden. Darauf über die besondere PMCCNTR_EL0 zu registrieren, verwenden die MSR-Opcode in Assemblycode, oder die `_ReadStatusReg` inhärent für C/C++-Code.

Beachten Sie, dass der Zyklus-Counter hier ein wahrer Zyklus-Counter, keine Wall-Clock und daher die Zählung Frequenz variiert mit der Prozessorfrequenz. Wenn Sie, dass Sie die Häufigkeit des Zyklus-Counters wissen müssen glauben, sollten Sie nicht den Zyklus-Counter verwenden. Stattdessen soll die gesamtbetrachtungszeit, Sie für die verwenden `QueryPerformanceCounter`.

## <a name="see-also"></a>Siehe auch

[Häufig auftretende ARM-Migrationsprobleme bei Visual C++](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64-Ausnahmebehandlung](arm64-exception-handling.md)
