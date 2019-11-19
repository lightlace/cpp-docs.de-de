---
title: Übersicht über ARM64-ABI-Konventionen
ms.date: 03/27/2019
ms.openlocfilehash: 3a3df475b8f814fcecaf2e67a0a62c7267a0de30
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163218"
---
# <a name="overview-of-arm64-abi-conventions"></a>Übersicht über ARM64-ABI-Konventionen

Die grundlegende Anwendungs Binärdatei-Schnittstelle (ABI) für Windows, wenn Sie auf ARM-Prozessoren im 64-Bit-Modus (ARMv8 oder höher) kompiliert und ausgeführt wird, folgt größtenteils der Standard-AArch64 EABI von Arm. In diesem Artikel werden einige der wichtigsten Annahmen und Änderungen der in der EABI dokumentierten Informationen hervorgehoben. Weitere Informationen zur 32-Bit-ABI finden Sie unter [Übersicht über ARM-ABI-Konventionen](overview-of-arm-abi-conventions.md). Weitere Informationen zur Standard-ARM-EABI finden Sie unter [Application Binary Interface (ABI) für die ARM-Architektur](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html) (externer Link).

## <a name="definitions"></a>Definitionen

Mit der Einführung der 64-Bit-Unterstützung hat Arm mehrere Begriffe definiert:

- **AArch32** – die von Arm definierte ältere 32-Bit-Anweisungs Satz Architektur (ISA), einschließlich der Thumb-Modus-Ausführung.
- **AArch64** – die neue von Arm definierte 64-Bit-Anweisungs Satz Architektur (ISA).
- **ARMv7** – die Spezifikation der Arm-Hardware der 7. Generation, die nur die Unterstützung für AArch32 umfasst. Diese Version der Arm-Hardware ist die erste Version von Windows für Arm unterstützt.
- **ARMv8** – die Spezifikation der Arm-Hardware der "8. Generation", die Unterstützung für AArch32 und AArch64 umfasst.

Windows verwendet auch die folgenden Begriffe:

- **Arm** – bezieht sich auf die ARM-Architektur 32-Bit (AArch32), die manchmal auch als woa (Windows auf ARM) bezeichnet wird.
- **ARM32** – identisch mit Arm, oberhalb; wird aus Gründen der Übersichtlichkeit in diesem Dokument verwendet.
- **ARM64** – verweist auf die 64-Bit-ARM-Architektur (AArch64). Das ist nicht WoA64.

Schließlich wird beim Verweis auf Datentypen auf die folgenden Definitionen von Arm verwiesen:

- **Short-Vector** – ein Datentyp, der direkt in SIMD dargestellt werden kann, ein Vektor mit 8 Bytes oder einem Wert von 16 Bytes. Er ist auf seine Größe ausgerichtet, entweder 8 Bytes oder 16 Bytes, wobei jedes Element 1, 2, 4 oder 8 Bytes sein kann.
- **HFA (homogenes Gleit Komma Aggregat)** – ein Datentyp mit 2 bis 4 identischen Gleit Komma Membern, entweder float oder Double.
- **HVA (homogenes kurzes Vektor Aggregat)** – ein Datentyp mit 2 bis 4 identischen kurzvektor Membern.

## <a name="base-requirements"></a>Grundvoraussetzungen

Die ARM64-Version von Windows setzt voraus, dass Sie immer auf einer ARMv8-oder einer neueren Architektur ausgeführt wird. Die Unterstützung für Gleit Komma-und Neon-Unterstützung wird vermutlich in der Hardware vorhanden sein.

In der ARMv8-Spezifikation werden neue optionale Kryptografie-und CRC-hilfsopcodes für AArch32 und AArch64 beschrieben. Die Unterstützung für Sie ist zurzeit optional, wird jedoch empfohlen. Damit diese Opcodes genutzt werden können, sollten apps zunächst überprüfen, ob Sie vorhanden sind.

## <a name="endianness"></a>Endianness

Wie bei der ARM32-Version von Windows wird unter ARM64 Windows im Little-Endian-Modus ausgeführt. Das Umgestalten von Byte Reihenfolge ist ohne Kernel Modus-Unterstützung in AArch64 schwierig. Daher ist es einfacher, dies zu erzwingen.

## <a name="alignment"></a>Ausrichtung

Windows unter ARM64 ermöglicht der CPU-Hardware die transparente Verarbeitung von falsch ausgerichteten Zugriffen. In einer Verbesserung von AArch32 funktioniert diese Unterstützung jetzt auch für alle ganzzahligen Zugriffe (einschließlich der Zugriffe auf mehrere Wörter) und für Gleit Komma Zugriffe.

Allerdings muss der Zugriff auf den nicht zwischengespeicherten (Geräte-) Arbeitsspeicher immer noch ausgerichtet werden. Wenn Code möglicherweise falsch ausgerichtete Daten aus nicht zwischengespeicherten Arbeitsspeicher lesen oder schreiben könnte, muss sichergestellt werden, dass alle Zugriffe ausgerichtet werden.

Standardlayoutausrichtung für lokale Variablen:

| Größe in Bytes | Ausrichtung in Bytes |
| - | - |
| 1 | 1 |
| 2 | 2 |
| 3, 4 | 4 |
| > 4 | 8 |

Standardlayoutausrichtung für Globals und Statics:

| Größe in Bytes | Ausrichtung in Bytes |
| - | - |
| 1 | 1 |
| 2 - 7 | 4 |
| 8 - 63 | 8 |
| > = 64 | 16 |

## <a name="integer-registers"></a>Ganzzahlige Register

Die AArch64-Architektur unterstützt 32 ganzzahlige Register:

| Register | Volatil? | Rolle |
| - | - | - |
| X0 | Volatil | Parameter/Scratch-Register 1, Ergebnisregister |
| x1-x7 | Volatil | Parameter/Scratch-Register 2-8 |
| x8-X15 | Volatil | Register für Scratch |
| x16-x17 | Volatil | Intern aufzurufende Register |
| x18 | Nicht volatil | Platt Form Register: verweist im Kernel Modus auf "kpcr" für den aktuellen Prozessor. im Benutzermodus zeigt auf TEB. |
| x19-x28 | Nicht volatil | Register für Scratch |
| x29/FP | Nicht volatil | Frame-Pointer |
| x30/LR | Nicht volatil | Register verknüpfen |

Auf jedes Register kann als vollständiger 64-Bit-Wert (über X0-x30) oder als 32-Bit-Wert (über W0-W30) zugegriffen werden. 32-Bit-Vorgänge mit 0 (null) erweitern Sie Ihre Ergebnisse auf bis zu 64 Bits.

Ausführliche Informationen zur Verwendung der Parameter Register finden Sie im Abschnitt Parameter Übergabe.

Anders als bei AArch32 sind der Programm Counter (PC) und der Stapelzeiger (SP) keine indizierten Register. Sie sind darauf beschränkt, wie auf Sie zugegriffen werden kann. Beachten Sie auch, dass es keine x31 Register gibt. Diese Codierung wird für besondere Zwecke verwendet.

Der Frame Zeiger (x29) ist erforderlich, um die Kompatibilität mit der schnellen Stapel Wanderung von etw und anderen Diensten zu nutzen. Er muss auf das vorherige {x29, x30}-paar auf dem Stapel zeigen.

## <a name="floating-pointsimd-registers"></a>Gleit Komma-/SIMD-Register

Die AArch64-Architektur unterstützt auch 32-Gleit Komma-/SIMD-Register, die unten zusammengefasst sind:

| Register | Volatil? | Rolle |
| - | - | - |
| v0 | Volatil | Parameter/Scratch-Register 1, Ergebnisregister |
| v1-V7 | Volatil | Parameter/Scratch-Register 2-8 |
| V8-V15 | Nicht volatil | Register für Scratch (nur die unteren 64 Bits sind nicht flüchtig) |
| v16-v31 | Volatil | Register für Scratch |

Auf jedes Register kann als vollständiger 128-Bit-Wert (über "v0-v31" oder "q0-Q31") zugegriffen werden. Der Zugriff auf den Wert erfolgt möglicherweise als 64-Bit-Wert (über D0-D31), als 32-Bit-Wert (über S0-S31), als 16-Bit-Wert (über H0-H31) oder als 8-Bit-Wert (über B0-B31). Zugriffe, die kleiner als 128 Bits sind, greifen nur auf die unteren Bits des vollständigen 128-Bit-Registers zu. Die verbleibenden Bits bleiben unverändert, sofern nicht anders angegeben. (AArch64 unterscheidet sich von AArch32, wobei die kleineren Register zusätzlich zu den größeren Registern gepackt wurden.)

Für das Gleit Komma-Steuerelement Register (fpcr) gelten bestimmte Anforderungen an die verschiedenen Bitfeldern darin:

| Bits | Bedeutung | Volatil? | Rolle |
| - | - | - | - |
| 26 | AHP | Nicht flüchtig | Alternatives Steuerelement mit halber Genauigkeit. |
| 25 | DN | Nicht flüchtig | Standard-Nan-Modus-Steuerelement |
| 24 | FZ | Nicht volatil | Steuerelement für die Leerung im NULL-Modus. |
| 23-22 | RMode | Nicht volatil | Rundungs Modus-Steuerelement. |
| 15, 12-8 | IDE/IXE/usw. | Nicht flüchtig | Ausnahme Trap-enable Bits, muss immer 0 sein. |

## <a name="system-registers"></a>System Register

Wie AArch32 stellt die AArch64-Spezifikation drei vom System gesteuerte "Thread-ID"-Register bereit:

| Register | Rolle |
| - | - |
| TPIDR_EL0 | Reserviert. |
| TPIDRRO_EL0 | Enthält eine CPU-Nummer für den aktuellen Prozessor. |
| TPIDR_EL1 | Verweist auf die kpcr-Struktur für den aktuellen Prozessor. |

## <a name="floating-point-exceptions"></a>Gleit Komma Ausnahmen

Die Unterstützung für IEEE-Gleit Komma Ausnahmen ist in AArch64-Systemen optional. Bei Prozessor Varianten, die Hardware-Gleit Komma Ausnahmen aufweisen, fängt der Windows-Kernel die Ausnahmen im Hintergrund ab und deaktiviert sie implizit im fpcr-Register. Mit diesem Trap wird das normalisierte Verhalten über Prozessor Varianten hinweg sichergestellt. Andernfalls kann der Code, der auf einer Plattform ohne Ausnahme Unterstützung entwickelt wurde, bei der Ausführung auf einer Plattform mit Unterstützung unerwartete Ausnahmen finden.

## <a name="parameter-passing"></a>Parameterübergabe

Bei nicht-Variadic-Funktionen befolgt die Windows-ABI die Regeln, die von Arm für die Übergabe von Parametern angegeben werden. Diese Regeln werden direkt aus dem Prozedur aufrufsstandard für die AArch64-Architektur entnommen:

### <a name="stage-a--initialization"></a>Staging A – Initialization

Diese Phase wird genau einmal durchgeführt, bevor die Verarbeitung der Argumente beginnt.

1. Die nächste allgemeine Registrierungsnummer (ngrn) ist auf 0 (null) festgelegt.

1. Die nächste SIMD und die Gleit Komma Register Nummer (nsrn) werden auf 0 (null) festgelegt.

1. Die nächste gestapelte Argument Adresse (NSAA) wird auf den aktuellen Stapelzeiger Wert (SP) festgelegt.

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>Stufe B – vorab Auffüll Zeichen und Erweiterung von Argumenten

Für jedes Argument in der Liste wird die erste übereinstimmende Regel aus der folgenden Liste angewendet. Wenn keine Regel übereinstimmt, wird das Argument unverändert verwendet.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, dessen Größe nicht statisch vom Aufrufer und dem aufgerufenen bestimmt werden kann, wird das Argument in den Arbeitsspeicher kopiert, und das Argument wird durch einen Zeiger auf die Kopie ersetzt. (Es gibt keine derartigen Typen in CC++ /, aber Sie sind in anderen Sprachen oder in Spracherweiterungen vorhanden.)

1. Wenn der Argumenttyp ein HFA oder ein HVA ist, wird das Argument unverändert verwendet.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, der größer als 16 Bytes ist, wird das Argument in den vom Aufrufer zugeordneten Arbeitsspeicher kopiert, und das-Argument wird durch einen Zeiger auf die Kopie ersetzt.

1. Wenn der Argumenttyp ein zusammengesetzter Typ ist, wird die Größe des Arguments auf das nächste Vielfache von 8 Bytes aufgerundet.

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>Phase C – Zuweisung von Argumenten zu Registern und Stapel

Für jedes Argument in der Liste werden die folgenden Regeln nacheinander angewendet, bis das-Argument zugeordnet wurde. Wenn ein Argument einem Register zugewiesen ist, haben alle nicht verwendeten Bits im Register einen nicht angegebenen Wert. Wenn ein Argument einem Stapel Slot zugewiesen ist, haben nicht verwendete Auffüll Bytes einen nicht angegebenen Wert.

1. Wenn es sich bei dem Argument um einen Gleit Komma-oder kurzvektortyp der Hälfte-, Einzel-, Double-oder Quad-Genauigkeit handelt und der nsrn kleiner als 8 ist, wird das Argument den unwichtigsten Bits von Register v\[nsrn] zugeordnet. Der nsrn wird um eins erhöht. Das-Argument wurde nun zugeordnet.

1. Wenn es sich bei dem Argument um eine HFA oder eine HVA handelt und genügend nicht zugewiesene SIMD-und Gleit Komma Register vorhanden sind (nsrn + Anzahl der Member von 8), wird das Argument SIMD-und Gleit Komma Registern zugeordnet, ein Register pro Mitglied der HFA oder HVA. Der nsrn wird um die Anzahl der verwendeten Register erhöht. Das-Argument wurde nun zugeordnet.

1. Wenn das Argument ein HFA oder ein HVA ist, wird der nsrn auf 8 festgelegt, und die Größe des Arguments wird auf das nächste Vielfache von 8 Bytes aufgerundet.

1. Wenn das Argument ein HFA, ein HVA, ein Gleit Komma-oder kurzvektortyp mit vier Genauigkeit ist, wird das NSAA auf den größeren Wert von 8 oder die natürliche Ausrichtung des Argument Typs aufgerundet.

1. Wenn das Argument ein Gleit kommatyp mit halber oder einfacher Genauigkeit ist, wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt ist so, als ob das-Argument in die geringsten Bits eines 64-Bit-Registers kopiert wurde und die restlichen Bits mit nicht angegebenen Werten aufgefüllt wurden.

1. Wenn es sich bei dem Argument um einen HFA-, HVA-, ein-oder einen Gleit Komma-oder kurzvektortyp mit doppelter Genauigkeit handelt, wird das Argument beim angepassten NSAA in den Arbeitsspeicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das-Argument wurde nun zugeordnet.

1. Wenn das Argument ein ganzzahliger Typ oder ein Zeigertyp ist, ist die Größe des Arguments kleiner als oder gleich 8 Bytes, und der ngrn ist kleiner als 8. das Argument wird in x\[ngrn] auf die unwichtigsten Bits kopiert. Der ngrn wird um eins erhöht. Das-Argument wurde nun zugeordnet.

1. Wenn das Argument eine Ausrichtung von 16 hat, wird der ngrn auf die nächste gerade Zahl aufgerundet.

1. Wenn das Argument ein ganzzahliger Typ ist, ist die Größe des Arguments gleich 16, und der ngrn ist kleiner als 7. das Argument wird in x\[ngrn] und x\[ngrn + 1] kopiert. x\[ngrn] muss das untere doppelte Wort der Speicher Darstellung des Arguments enthalten. Der ngrn wird um zwei inkrementiert. Das-Argument wurde nun zugeordnet.

1. Wenn das Argument ein zusammengesetzter Typ ist und die Größe in doppelten Wörtern des Arguments nicht mehr als 8 minus ngrn beträgt, wird das Argument in aufeinander folgende allgemeine Register kopiert, beginnend bei x\[ngrn]. Das Argument wird so übermittelt, als ob es in die Register von einer Doppelwort ausgerichteten Adresse geladen worden wäre, mit einer entsprechenden Folge von LDR-Anweisungen, die aufeinanderfolgende Register aus dem Arbeitsspeicher laden. Der Inhalt aller nicht verwendeten Teile der Register wird von diesem Standard nicht angegeben. Der ngrn wird um die Anzahl der verwendeten Register erhöht. Das-Argument wurde nun zugeordnet.

1. Der ngrn ist auf 8 festgelegt.

1. Die NSAA wird auf die größere von 8 oder die natürliche Ausrichtung des Argument Typs aufgerundet.

1. Wenn das Argument ein zusammengesetzter Typ ist, wird das Argument beim angepassten NSAA in den Arbeitsspeicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das-Argument wurde nun zugeordnet.

1. Wenn die Größe des Arguments kleiner als 8 Bytes ist, wird die Größe des Arguments auf 8 Bytes festgelegt. Der Effekt ist so, als ob das-Argument in die geringsten Bits eines 64-Bit-Registers kopiert wurde und die restlichen Bits mit nicht angegebenen Werten aufgefüllt wurden.

1. Das-Argument wird im angepassten NSAA in den Arbeitsspeicher kopiert. Die NSAA wird um die Größe des Arguments inkrementiert. Das-Argument wurde nun zugeordnet.

### <a name="addendum-variadic-functions"></a>Nachtrag: Variadic-Funktionen

Funktionen, die eine Variable Anzahl von Argumenten akzeptieren, werden wie folgt anders behandelt:

1. Alle Verbund werden gleich behandelt. keine besondere Behandlung von hfas oder HVAS.

1. SIMD-und Gleit Komma Register werden nicht verwendet.

Tatsächlich ist sie identisch mit den folgenden Regeln c. 12 – C. 15, um Argumente einem imaginären Stapel zuzuweisen, wobei die ersten 64 Bytes des Stapels in X0-x7 geladen werden und alle verbleibenden Stapel Argumente normal abgelegt werden.

## <a name="return-values"></a>Rückgabewert

Ganzzahlige Werte werden in X0 zurückgegeben.

Gleit Komma Werte werden nach Bedarf in S0, D0 oder v0 zurückgegeben.

HFA-und HVA-Werte werden nach Bedarf in S0-S3, D0-D3 oder v0-V3 zurückgegeben.

Typen, die als Wert zurückgegeben werden, werden unterschiedlich behandelt, je nachdem, ob Sie bestimmte Eigenschaften aufweisen Typen, die über alle diese Eigenschaften verfügen,

- Sie werden durch die c++ 14-Standard Definition *aggregiert* , d. h., Sie haben keine vom Benutzer bereitgestellten Konstruktoren, keine privaten oder geschützten nicht statischen Datenmember, keine Basisklassen und keine virtuellen Funktionen.
- Sie verfügen über einen trivialen Kopier Zuweisungs Operator, und
- Sie verfügen über einen trivialen Dekonstruktor,

Verwenden Sie den folgenden Rückgabe Stil:

- Typen, die kleiner oder gleich 8 Bytes sind, werden in X0 zurückgegeben.
- Typen, die kleiner oder gleich 16 Bytes sind, werden in X0 und x1 zurückgegeben, wobei X0 die untere Ordnung von 8 Bytes enthält.
- Bei Typen, die größer als 16 Bytes sind, muss der Aufrufer einen Speicherblock mit ausreichender Größe und Ausrichtung reservieren, um das Ergebnis zu speichern. Die Adresse des Speicherblocks muss als zusätzliches Argument an die Funktion in x8 weitergegeben werden. Der aufgerufene kann den Ergebnisspeicher Block jederzeit während der Ausführung der Unterroutine ändern. Der aufgerufene muss den in x8 gespeicherten Wert nicht beibehalten.

Alle anderen Typen verwenden diese Konvention:

- Der Aufrufer muss einen Speicherblock mit ausreichender Größe und Ausrichtung reservieren, um das Ergebnis zu speichern. Die Adresse des Speicherblocks muss als zusätzliches Argument an die Funktion in X0 oder x1 weitergegeben werden, wenn $this in X0 weitergegeben wird. Der aufgerufene kann den Ergebnisspeicher Block jederzeit während der Ausführung der Unterroutine ändern. Der aufgerufene gibt die Adresse des Speicherblocks in X0 zurück.

## <a name="stack"></a>Stapel

Nach der von Arm gerichteten ABI muss der Stapel immer 16-Byte-ausgerichtet bleiben. AArch64 enthält eine Hardware Funktion, die Stapel Ausrichtungsfehler generiert, wenn der SP nicht 16-Byte-ausgerichtet ist und ein SP-relativer Lade-oder Speichervorgang durchgeführt wird. Windows wird mit dieser Funktion jederzeit aktiviert.

Funktionen, die einen oder mehr Stapel Stapel zuweisen, müssen sicherstellen, dass jede Seite vor der letzten Seite in der richtigen Reihenfolge berührt wird. Dadurch wird sichergestellt, dass kein Code über die Schutz Seiten "springen", die Windows zum Erweitern des Stapels verwendet. In der Regel erfolgt die Berührungen durch das `__chkstk`-Hilfsprogramm, das über eine benutzerdefinierte Aufruf Konvention verfügt, die die gesamte Stapel Belegung dividiert durch 16 in X15 hat.

## <a name="red-zone"></a>Rote Zone

Der 16-Byte-Bereich direkt unterhalb des aktuellen Stapel Zeigers ist für die Verwendung durch Analyse Szenarien und Szenarien für dynamisches Patchen reserviert. In diesem Bereich kann sorgfältig generierter Code eingefügt werden, der zwei Register bei [SP, #-16] speichert und diese temporär für beliebige Zwecke verwendet. Der Windows-Kernel stellt sicher, dass diese 16 Bytes nicht überschrieben werden, wenn eine Ausnahme oder ein Interrupt im Benutzer-und Kernel Modus ausgeführt wird.

## <a name="kernel-stack"></a>Kernel Stapel

Der standardkernelmodusstapel in Windows ist sechs Seiten (rund um die Uhr). Achten Sie besonders auf Funktionen mit großen Stapel Puffern im Kernel Modus. Ein Unterbrechungs gesteuerter interruptvorgang kann mit geringem Spielraum erfolgen und eine Stapel-Panik-Fehlerüberprüfung erstellen.

## <a name="stack-walking"></a>Stapel-Walking

Code in Windows wird mit aktivierten Frame Zeigern ([/Oy-](reference/oy-frame-pointer-omission.md)) kompiliert, um eine schnelle Stapel Suche zu ermöglichen. Im allgemeinen verweist x29 (FP) auf den nächsten Link in der Kette, bei dem es sich um ein {FP, LR}-Paar handelt, das den Zeiger auf den vorherigen Frame auf dem Stapel und die Rückgabeadresse angibt. Der Code von Drittanbietern wird auch zum Aktivieren von Frame Zeigern empfohlen, um eine verbesserte Profilerstellung und Ablauf Verfolgung zu ermöglichen.

## <a name="exception-unwinding"></a>Ausnahme Auflösung

Das Entladen während der Ausnahmebehandlung wird durch die Verwendung von Entladungs Codes unterstützt. Die Entladungs Codes sind eine Folge von Bytes, die im Abschnitt. XData der ausführbaren Datei gespeichert sind. Sie beschreiben den Vorgang des Prologs und des Epilogs auf abstrakte Weise, sodass die Auswirkungen des Prologs eines funktionsvorgangs rückgängig gemacht werden können, um die Sicherung auf den Stapel Rahmen des Aufrufers zu vorbereiten. Weitere Informationen zu den Entladungs Codes finden Sie unter [ARM64 Exception Handling](arm64-exception-handling.md).

Die ARM-EABI gibt auch ein Ausnahme Entladungs Modell an, das Entladungs Codes verwendet. Allerdings reicht die angegebene Spezifikation nicht für das lösen in Windows aus, da die Fälle behandelt werden müssen, in denen sich der PC in der Mitte eines Funktions Prologs oder Epilogs befindet.

Dynamisch generierter Code sollte mit dynamischen Funktionstabellen über `RtlAddFunctionTable` und zugehörige Funktionen beschrieben werden, damit der generierte Code an der Ausnahmebehandlung beteiligt sein kann.

## <a name="cycle-counter"></a>Cycle-Counter

Alle ARMv8-CPUs sind erforderlich, um ein Cycle Counter-Register zu unterstützen, ein 64-Bit-Register, das Windows so konfiguriert, dass es auf jeder beliebigen Ausnahme Ebene lesbar ist, einschließlich des Benutzermodus. Der Zugriff darauf erfolgt über das spezielle PMCCNTR_EL0 Register, über den MSR-Opcode im Assemblycode oder über die systeminterneC++ `_ReadStatusReg` in C/Code.

Bei dem hier aufgeführten Zyklen handelt es sich um einen echten Zyklen, nicht um eine Wand Uhr. Die Zähl Häufigkeit variiert je nach Prozessorfrequenz. Wenn Sie der Meinung sind, dass Sie die Häufigkeit des Cycle-Zählers kennen müssen, sollten Sie den-Cycle-Counter nicht verwenden. Stattdessen sollten Sie die Uhrzeit der Wand Messung Messen, für die Sie `QueryPerformanceCounter`verwenden möchten.

## <a name="see-also"></a>Siehe auch

[Häufig auftretende ARM-Migrationsprobleme bei Visual C++](common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64-Ausnahmebehandlung](arm64-exception-handling.md)
