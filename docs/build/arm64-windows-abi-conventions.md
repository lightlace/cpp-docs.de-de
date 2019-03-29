---
title: Übersicht über die ARM64-ABI-Konventionen
ms.date: 03/27/2019
ms.openlocfilehash: 4c0f89f97529d4cd70e1449c90b131d25d30f9ee
ms.sourcegitcommit: ac5c04b347e817eeece6e2c98e60236fc0e307a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58639445"
---
# <a name="overview-of-arm64-abi-conventions"></a>Übersicht über die ARM64-ABI-Konventionen

Die grundlegende anwendungsbinärdateischnittstelle (ABI) für Windows, die bei der Kompilierung und Ausführung auf ARM-Prozessoren im 64-Bit-Modus (ARMv8 oder höher Architekturen) zum größten Teil, folgt die ARM EABI für standard AArch64. In diesem Artikel werden einige wichtige Annahmen und Änderungen aus, was in die EABI dokumentiert ist. Weitere Informationen zur 32-Bit-ABI, finden Sie unter [Übersicht der ARM-ABI-Konventionen](overview-of-arm-abi-conventions.md). Weitere Informationen über die standardmäßige ARM EABI finden Sie unter [Application Binary Interface (ABI) für die ARM-Architektur](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (externer Link).

## <a name="definitions"></a>Definitionen

ARM verfügt über mehrere Begriffe definiert, mit der Einführung von 64-Bit-Unterstützung können:

- **AArch32** – die ältere 32-Bit-Anweisung set-Architektur (ISA), der von ARM, einschließlich der Ausführung des Thumb-Steuerelement im definiert.
- **AArch64** – die neue 64-Bit-Anweisung set-Architektur (ISA), der von ARM definiert.
- **ARMv7** : die Angabe von "7. Generation" ARM-Hardware, die nur Unterstützung für AArch32 enthält. Diese Version der ARM-Hardware ist die erste Version von Windows für ARM unterstützt.
- **ARMv8** : die Angabe von "8. Generation" ARM-Hardware, das sowohl für AArch32 AArch64 unterstützt.

Windows werden auch diese Begriffe verwendet:

- **ARM** – bezieht sich auf die 32-Bit-ARM-Architektur (AArch32), auch als WoA (Windows auf ARM) bezeichnet.
- **ARM32** – identisch mit ARM, oben; wird in diesem Dokument aus Gründen der Übersichtlichkeit.
- **ARM64** – bezieht sich auf die 64-Bit-ARM-Architektur (AArch64). Es gibt keine als WoA64.

Schließlich werden in Bezug auf Datentypen, die folgenden Definitionen von ARM verwiesen:

- **Short-Vektor** – ein Datentyp, der direkt im SIMD, einen Vektor von 8 Byte oder 16 Bytes Menge von Elementen dargestellt werden kann. Es wird ausgerichtet, auf die Größe 8 Byte oder 16 Bytes ist, in dem jedes Element 1, 2, 4 oder 8 Byte sein kann.
- **Zu HFA (homogen Floating-Point Aggregat)** – ein Datentyp mit identischen Gleitkomma Membern 2 bis 4, floats oder verdoppelt.
- **HVA (homogen Short-Vektor-Aggregat)** – einem Datentyp mit 2 bis 4 identische kurze-Vektor-Mitglieder.

## <a name="base-requirements"></a>Grundanforderungen

Die ARM64-Version von Windows wird vorausgesetzt, dass dieser eine ARMv8 ausgeführt wird, oder höher Architektur zu jeder Zeit. Beide Gleitkomma- und werden als NEON-Unterstützung in der Hardware vorhanden sein.

Die ARMv8-Spezifikation ermöglicht die vollständige Unterstützung von AArch32 Anwendungen. Allerdings ist nicht die Unterstützung für vorhandene ARM32-Anwendungen für die ARM64-Version von Windows vorgesehen. (D. h. Es gibt keine Pläne für WOW64). Diese Unterstützung unterliegt erneute Auswertung in der Zukunft, aber es ist die aktuelle arbeiten.

Die ARMv8-Spezifikation werden neue optional Verschlüsselung und CRC-Hilfsprogramm Opcodes für AArch32 und AArch64 beschreibt. Unterstützung für sie ist derzeit optional, jedoch empfohlen. Um dieser Opcodes nutzen zu können, sollten apps zuerst laufzeitprüfungen für ihre Existenz machen.

## <a name="endianness"></a>Endianness

Wie führt mit der ARM32 Version von Windows, auf ARM64 Windows im little-Endian-Modus. Der Wechsel Bytereihenfolge ist schwer zu erreichen, ohne die Kernel-Modus-Unterstützung in AArch64, daher ist es leichter durchgesetzt werden.

## <a name="alignment"></a>Ausrichtung

ARM64 unter Windows können die CPU-Hardware, falsch ausgerichtete Zugriffe transparent behandeln. In eine Verbesserung von AArch32 kann die diese Unterstützung jetzt auch für alle ganzzahlzugriffe (einschließlich mit mehreren Wörtern zugreift) sowie für Gleitkomma-Zugriff.

Zugriffe auf den Speicher für nicht-Cache (Gerät) müssen jedoch noch immer ausgerichtet werden. Falls Code könnte möglicherweise lesen oder Schreiben falsch ausgerichtete Daten aus dem Arbeitsspeicher der nicht zwischengespeicherten, muss Sie sicher, dass alle Zugriffe ausgerichtet sein.

## <a name="integer-registers"></a>Ganzzahlregister

Die Architektur der AArch64 unterstützt 32 Ganzzahlregister:

| Register | Volatil? | Rolle |
| - | - | - |
| x0 | Volatil | Parameter/neu registrieren, 1, Ergebnis registrieren |
| x1-x7 | Volatil | Parameter/neu registrieren 2 bis 8 |
| x8-x15 | Volatil | Scratch-Register |
| x16-x17 | Volatil | Intra-Procedure-Call/Scratch-Register |
| x18 | Nicht volatil | Registrieren Sie Plattform: im Kernelmodus verweist auf KPCR für den aktuellen Prozessor; im Benutzermodus verweist auf TEB |
| x19-x28 | Nicht volatil | Scratch-Register |
| x29/fp | Nicht volatil | Frame-Pointer |
| x30/lr | Nicht volatil | Link-Register |

Jedes Register kann als 64-Bit-Wert (über X0-X30) oder als 32-Bit-Wert (über w0-w30) zugegriffen werden. 32-Bit-Betrieb erweitern 0 (null)-ihre Ergebnisse bis zu 64 Bits.

Sehen Sie die Parameter finden Sie Details für die Verwendung der Parameter Register übergeben.

Im Gegensatz zu AArch32 nicht der Programmzähler (PC) und der Stapelzeiger (SP) indizierten registriert. Sie sind beschränkt, in wie auf sie zugegriffen werden können. Beachten Sie, dass es keine X31 auch registrieren zu können. Diese Codierung ist für besondere Zwecke verwendet werden.

Die Frame-Pointer (x29) ist erforderlich, für die Kompatibilität mit schnellen Stackwalk von ETW- und andere Dienste verwendet werden. Es muss auf den vorherigen {X29, x 30} zeigen Paar auf dem Stapel.

## <a name="floating-pointsimd-registers"></a>Gleitkomma-point/SIMD-Register

Die Architektur der AArch64 unterstützt auch 32 Gleitkomma-point/SIMD-Register, die im folgenden zusammengefasst:

| Register | Volatil? | Rolle |
| - | - | - |
| v0 | Volatil | Parameter/neu registrieren, 1, Ergebnis registrieren |
| v1-v7 | Volatil | Parameter/neu registriert 2 bis 8 |
| v8-v15 | Nicht volatil | Scratch-Register (nur die unteren 64 Bits nicht flüchtigen sind) |
| v16-v31 | Volatil | Scratch-Register |

Jedes Register kann als 128-Bit-Wert (per v0-v31 oder q0-F31) zugegriffen werden. Es kann als 64-Bit-Wert (über d0-d31), als eine 32-Bit-Wert (über s0-s31), als ein 16-Bit-Wert (über h0-h31) oder als ein 8-Bit-Wert (über b0-b31) zugegriffen werden. Greift auf weniger als 128 Bit Zugriff auf nur die niederwertigen Bits von 128-Bit-Register. Sie lassen die verbleibenden Bits unverändert, sofern nicht anders angegeben. (AArch64 unterscheidet sich von AArch32, in denen die kleinere Register auf größere Register gepackt wurden.)

Das gleitkommasteuerelements Register (FPCR) hat bestimmte Anforderungen auf die verschiedenen Bitfelder darin:

| Bits | Bedeutung | Volatil? | Rolle |
| - | - | - | - |
| 26 | AHP | Nicht flüchtigen | Alternative halb-Precision-Steuerung. |
| 25 | DN | Nicht flüchtigen | Standardmäßige NaN-modussteuerung. |
| 24 | FZ | Nicht volatil | Flush-zu-Zero-modussteuerung. |
| 23-22 | RMode | Nicht volatil | Rounding-modussteuerung. |
| 15,12-8 | IDE/IXE/etc | Nicht flüchtigen | Ausnahme trap-aktivierungsbits, muss immer 0 sein. |

## <a name="system-registers"></a>System-Register

Wie AArch32 bietet die AArch64 Spezifikation drei System kontrolliert "thread-ID" registriert:

| Register | Rolle |
| - | - |
| TPIDR_EL0 | Reserviert. |
| TPIDRRO_EL0 | Enthält die CPU-Anzahl für den aktuellen Prozessor. |
| TPIDR_EL1 | Zeigt auf KPCR-Struktur für den aktuellen Prozessor. |

## <a name="floating-point-exceptions"></a>Gleitkommaausnahmen

Unterstützung für IEEE-Gleitkommaausnahmen ist optional für AArch64 Systeme. Für prozessorvarianten, die Hardware-Gleitkommaausnahmen verfügen, der Windows-Kernel im Hintergrund fängt Ausnahmen ab und deaktiviert sie implizit in der Registrierung FPCR. Das Trap wird ein normalisiertes Verhalten zwischen prozessorvarianten sichergestellt. Andernfalls möglicherweise auf einer Plattform ohne Unterstützung von Ausnahmen entwickelten Code selbst unerwartete Ausnahmen erstellen, bei der Ausführung auf einer Plattform mit Unterstützung.

## <a name="parameter-passing"></a>Parameterübergabe

Für nicht-Variadic-Funktionen folgt die Windows-ABI die Regeln von ARM für das Übergeben von Parametern. Diese Regeln sind direkt aus dem Prozeduraufruf-Standard für die Architektur der AArch64 Auszug:

### <a name="stage-a--initialization"></a>Stufe A – Initialisierung

Diese Phase erfolgt genau einmal vor Beginn der Verarbeitung der Argumente.

1. Die nächste allgemeinen registrieren Anzahl (NGRN) wird auf 0 (null) festgelegt.

1. Die nächste SIMD und die Floating-Point registrieren Anzahl (NSRN) ist auf 0 (null) festgelegt.

1. Die Argumentadresse des nächste gestapelte (NSAA) wird mit dem aktuellen Stack-Pointer Wert (SP) festgelegt.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Stufe B – vorab-Padding und Erweiterung von Argumenten

Für jedes Argument in der Liste wird die erste übereinstimmende Regel aus der folgenden Liste angewendet. Wenn keine Regel entspricht, das Argument wird verwendet, werden unmodified.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, dessen Größe nicht statisch vom Aufrufer und dem aufgerufenen bestimmt werden kann, ist das Argument in den Arbeitsspeicher kopiert, und das Argument durch einen Zeiger auf die Kopie ersetzt wird. (Es sind keine solche Typen in C/C++-, aber in anderen Sprachen oder in spracherweiterungen vorhanden).

1. Das Argument wird verwendet, wenn der Argumenttyp ist ein zu HFA oder einer HVA-unverändert.

1. Wenn der Argumenttyp ein zusammengesetzter Typ, der größer als 16 Bytes ist, klicken Sie dann das Argument auf vom Aufrufer zugeordneten Speicher kopiert wird und das Argument durch einen Zeiger auf die Kopie ersetzt wird.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, wird die Größe des Arguments auf das nächste Vielfache von 8 Bytes aufgerundet.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Stufe C – Zuweisung von Argumenten zu Registern und zum stack

Für jedes Argument in der Liste werden wiederum die folgenden Regeln angewendet, bis das Argument zugeordnet wurde. Wenn ein Argument eines Registers zugewiesen wird, müssen in der Registrierung nicht verwendeter Bits Wert nicht angegeben sind. Wenn ein Argument an einen Slot Stack zugewiesen ist, müssen alle nicht verwendeten Auffüll-Bytes Wert nicht angegeben sind.

1. Wenn das Argument eine halb ist-, Single, Double-Wert - oder Quad Gleitkommazahlen mit doppelter Genauigkeit oder kurzen Vektortyp und die NSRN kleiner als 8, wird das Argument ist die am niedrigstwertigen Bits Registers V zugeordnet\[NSRN]. Die NSRN wird um eins erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zu HFA oder einer HVA-ist und sind ausreichend verfügbaren SIMD und Gleitkommaregister (NSRN + Anzahl der Elemente im ≤ 8), wird das Argument zu SIMD Floating-Point registriert wurde, eine Registrierung pro Element der zu HFA oder HVA zugeordnet. Die NSRN wird um die Anzahl der verwendeten Register inkrementiert. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zu HFA oder einer HVA-ist, klicken Sie dann die NSRN auf 8 festgelegt ist, und die Größe des Arguments wird auf das nächste Vielfache von 8 Bytes aufgerundet.

1. Wenn das Argument ein zu HFA, einer HVA-, Vektortyp für eine Quad-Genauigkeit Gleitkomma oder kurz, wird die NSAA wird aufgerundet auf die größere von 8 oder die natürliche Ausrichtung, der den Typ des Arguments.

1. Wenn das Argument ein Gleitkomma-halb - oder mit einfacher Genauigkeit ist, wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt wird als hätte das Argument auf kopiert wurden, die am niedrigstwertigen Bits eines 64-Bit-Registers, und die verbleibenden Bits, die mit nicht angegebenen Werten gefüllt.

1. Wenn das Argument ein zu HFA ist, wird einer HVA-, halb-, Einzel-, Double-Wert-, oder Quad Gleitkommazahlen mit doppelter Genauigkeit oder kurzen Vektortyp, und das Argument an der angepassten NSAA in den Speicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein Ganzzahl- oder Zeigertyp aufweisen ist, die Größe des Arguments kleiner als oder gleich 8 Byte ist und die NGRN kleiner als 8 ist, wird das Argument in der unwichtigsten Bits X kopiert\[NGRN]. Die NGRN wird um eins erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument eine Ausrichtung an 16 verfügt, wird die NGRN klicken Sie dann auf die nächste gerade Zahl aufgerundet.

1. Wenn das Argument ein Integraltyp ist, der Größe des Arguments gleich 16 ist und dem NGRN weniger als 7 ist, ist das Argument x kopiert\[NGRN]- und x\[NGRN + 1]. X\[NGRN] muss das untere bereits als Double-Wert-Wort für die Arbeitsspeicher-Darstellung des Arguments enthält. Die NGRN wird durch zwei erhöht. Das Argument wurde nun zugeordnet.

1. Wenn das Argument ein zusammengesetzter Typ ist ist, und die Größe in Doppelworte des Arguments nicht mehr als 8 minus NGRN, wird das Argument wird in aufeinander folgenden Allzweckregistern, beginnend bei x kopiert\[NGRN]. Das-Argument wird übergeben, als wäre er in die Register aus einer Double Word-ausgerichtete Adresse, mit der entsprechenden Reihenfolge von LDR-Anweisungen geladen wurden, die aufeinander folgenden Register aus dem Arbeitsspeicher zu laden. Der Inhalt der alle nicht genutzten Bereichen der Register werden nicht von diesem Standard angegeben sind. Die NGRN wird um die Anzahl der verwendeten Register inkrementiert. Das Argument wurde nun zugeordnet.

1. Die NGRN ist auf 8 festgelegt.

1. Die NSAA wird aufgerundet auf die größere von 8 oder die natürliche Ausrichtung, der den Typ des Arguments.

1. Wenn das Argument ein zusammengesetzter Typ ist, wird das Argument in den Speicher an der angepassten NSAA kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

1. Wenn die Größe des Arguments auf weniger als 8 Bytes beträgt, wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt ist, als ob das Argument an die unwichtigsten Bits von einem 64-Bit-Register kopiert wurde, und die verbleibenden Bits mit nicht angegebenen Werten gefüllt wurden.

1. Das Argument wird an der angepassten NSAA in den Speicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das Argument wurde nun zugeordnet.

### <a name="addendum-variadic-functions"></a>Nachtrag: Variadic-Funktionen

Funktionen, die eine Variable Anzahl von Argumenten akzeptieren werden anders als oben wie folgt behandelt:

1. Alle kombinierenden Zeichen ersetzt wurden, werden ähnlich behandelt; keine besondere Behandlung HFAs oder HVAs.

1. SIMD "und" Floating-Point registriert werden, werden nicht verwendet.

Tatsächlich ist es identisch mit den folgenden Regeln C.12–C.15 zuweisen Argumente in einer imaginären Stack, in denen die ersten 64 Bytes des Stapels werden in den X0-X7 geladen, und alle übrigen Argumente für den Stapel normalerweise platziert werden.

## <a name="return-values"></a>Rückgabewert

Ganzzahlige Werte werden in X0 zurückgegeben.

Gleitkommazahlen-Punktwerte werden in s0/d0/v0 entsprechend zurückgegeben.

Typen, die als Wert zurückgegebene werden unterschiedlich gehandhabt, je nachdem, ob sie bestimmte Eigenschaften verfügen. Typen, die alle diese Eigenschaften haben,

- Sie sind *aggregieren* von der C ++ 14-Standarddefinition, d. h., sie haben keine von Benutzern bereitgestellten Konstruktoren, keine privaten oder geschützten nicht statischen Datenmember, ohne Basisklassen und ohne virtuellen Funktionen, und
- Sie haben einen trivialen Kopierzuweisungsoperator und
- Sie haben einen trivialen Destruktor,

Verwenden Sie das folgende Format für die Rückgabe an:

- Typen, die kleiner oder gleich 8 Bytes werden in X0 zurückgegeben werden.
- Typen, die kleiner oder gleich 16 Byte werden in X0 und X1, mit X0, enthält die niederwertigen 8 Bytes zurückgegeben.
- Für Typen, die mehr als 16 Bytes muss der Aufrufer einen Speicherblock von ausreichender Größe und Ausrichtung, um das Ergebnis aufzunehmen reservieren. Die Adresse des Speicherblocks muss als ein zusätzliches Argument der Funktion in X8 übergeben werden. Der aufgerufene kann den Ergebnis-Speicherblock zu einem beliebigen Zeitpunkt während der Ausführung der Unterroutine ändern. Der aufgerufene nicht erforderlich, den in X8 gespeicherten Wert beibehalten.

Alle anderen Typen verwenden diese Konvention:

- Der Aufrufer muss einen Speicherblock von ausreichender Größe und Ausrichtung, um das Ergebnis aufzunehmen, die reserviert werden. Die Adresse des Speicherblocks muss als ein zusätzliches Argument an die Funktion in X0 oder X1 übergeben werden, wenn $dies X0 übergeben wird. Der aufgerufene kann den Ergebnis-Speicherblock zu einem beliebigen Zeitpunkt während der Ausführung der Unterroutine ändern. Der aufgerufene gibt die Adresse des Speicherblocks in X0 zurück.

## <a name="stack"></a>Stapel

Nach der ABI, die vom ARM muss der Stapel bleiben, 16-Byte-ausgerichtet. AArch64 enthält eine Hardwarefunktion, die Stapel Ausrichtungsfehler generiert, wenn das SP nicht 16-Byte-ausgerichtet ist und eine Relative SP Lade- oder erfolgt. Windows führt diese Funktion immer aktiviert.

Funktionen, die 4-KB oder mehr lohnt des Stapels reservieren müssen stellen Sie sicher, dass jede Seite vor der letzten Seite in der Reihenfolge verwendet wird. Dadurch wird sichergestellt, ohne Code "über die Schutzseiten, die von Windows verwendet wird, um die Erweiterung des Stacks läuft". In der Regel die berühren erfolgt durch die `__chkstk` Hilfsmethode, die benutzerdefinierte Aufrufkonvention verfügt, die die gesamte stapelzuordnung geteilt durch 16 X15 übergibt.

## <a name="red-zone"></a>Rote zone

Die 16-Byte-Bereich unmittelbar unter dem aktuellen Stack-Pointer ist für die Verwendung von der Analyse reserviert und dynamische patching Szenarien. Dieser Bereich lässt sorgfältig generierten Code eingefügt werden soll, das speichert zwei Register bei [sp, #-16] und verwendet sie vorübergehend für beliebige Zwecke. Der Windows-Kernel wird sichergestellt, dass diese 16 Bytes nicht überschrieben, wenn eine Ausnahme oder ein Interrupt, sowohl Benutzer-als auch Kernel-Modus erstellt wird.

## <a name="kernel-stack"></a>Kernel-stack

Der Kernel-Modus-Standardstapel in Windows ist sechs Seiten (24 KB). Achten Sie zusätzliche Funktionen mit große Stack-Puffer im Kernel-Modus. Systemabschaltung Interrupt kann mit kleinen Spielraum stammen und erstellen Sie eine panic fehlerüberprüfung Stack.

## <a name="stack-walking"></a>Durchlaufen von Stapeln

Code in Windows wird mit aktivierten Frame-Pointern kompiliert ([/Oy-](reference/oy-frame-pointer-omission.md)) zum schnellen Stackwalk zu ermöglichen. Im Allgemeinen X29 (fp) verweist auf den nächsten Link in der Kette, die eine {fp, Lr} ist, der angibt, des Zeigers zum vorherigen Frame im Stack und die Rückgabeadresse-Paar. Code von Drittanbietern wird empfohlen, die Frame-Pointer aktiviert wird, um verbesserte profilerstellung und Ablaufverfolgung zu ermöglichen.

## <a name="exception-unwinding"></a>Ausnahmeentladung

Entladen während der Ausnahmebehandlung wird durch die Verwendung von entladungscodes unterstützt. Die entladungscodes sind eine Folge von Bytes, die im Abschnitt ".xdata" der ausführbaren Datei gespeichert. Sie beschreiben den Betrieb von Prolog und Epilog auf abstrakte Weise, aus, sodass die Effekte eines Funktionsprologs als Vorbereitung für die Sicherung Stapelrahmens des Aufrufers rückgängig gemacht werden können. Weitere Informationen zu den entladungscodes, finden Sie unter [ARM64-Ausnahmebehandlung](arm64-exception-handling.md).

Die ARM EABI gibt auch entladungscodes für ein ausnahmeentladungsmodell, die verwendet werden. Die Spezifikation dargestellt ist jedoch für die Entladung in Windows, wobei Fälle behandelt werden müssen, in dem der Computer in der Mitte funktionsprolog oder Epilog ist, jedoch nicht ausreichend.

Code, der dynamisch generiert wird, sollte mit dynamischen Funktionstabellen über beschrieben werden `RtlAddFunctionTable` und die zugehörigen Funktionen, damit der generierte Code in der Ausnahmebehandlung teilnehmen kann.

## <a name="cycle-counter"></a>Zyklus-counter

Alle ARMv8 CPUs sind erforderlich, um einen Zyklus-Counter unterstützen registrieren, ein 64-Bit-Register, die Windows konfiguriert wird, um auf jeder Ausnahme-Ebene, einschließlich User-Modus gelesen werden. Darauf über die besondere PMCCNTR_EL0 zu registrieren, verwenden die MSR-Opcode in Assemblycode, oder die `_ReadStatusReg` inhärent für C/C++-Code.

Der Zyklus-Counter hier ist ein wahrer Zyklus-Counter, keine tatsächliche Uhr. Die Zählung Frequenz variiert mit der Prozessorfrequenz. Wenn Sie, dass Sie die Häufigkeit des Zyklus-Counters wissen müssen glauben, verwenden Sie darf nicht den Zyklus-Counter. Stattdessen soll die gesamtbetrachtungszeit, Sie für die verwenden `QueryPerformanceCounter`.

## <a name="see-also"></a>Siehe auch

[Häufig auftretende ARM-Migrationsprobleme bei Visual C++](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64-Ausnahmebehandlung](arm64-exception-handling.md)
