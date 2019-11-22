---
title: ARM-Ausnahmebehandlung
ms.date: 07/11/2018
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
ms.openlocfilehash: c55baf453c1879f1e0a857cc746bba7802d69f88
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303281"
---
# <a name="arm-exception-handling"></a>ARM-Ausnahmebehandlung

Windows auf ARM verwendet denselben strukturierten Mechanismus für die Ausnahmebehandlung bei asynchronen – von der Hardware generierten – und synchronen – von der Software generierten – Ausnahmen. Sprachspezifische Ausnahmehandler werden auf von Windows strukturierter Ausnahmebehandlung mithilfe von Sprachhilfsfunktionen erstellt. In diesem Dokument wird die Ausnahmebehandlung in Windows auf Arm und die sprach Hilfsprogramme beschrieben, die von Code verwendet werden, der vom Microsoft-Arm-Assembler und dem MSVC-Compiler generiert wird.

## <a name="arm-exception-handling"></a>ARM-Ausnahmebehandlung

Windows on Arm verwendet Entladungs *Codes* zum Steuern der Stapel Entladung während der [strukturierten Ausnahmebehandlung](/windows/win32/debug/structured-exception-handling) (SEH). Entladungscodes sind eine Folge von Bytes, die im „.xdata“-Abschnitt des ausführbaren Images gespeichert sind. Sie beschreiben den Betrieb von Funktions Prolog und Epilogcode auf abstrakte Weise, sodass die Auswirkungen des Prologs eines funktionsvorgangs rückgängig gemacht werden können, um den Stapel Rahmen des Aufrufers zu entwickeln.

Das ARM EABI (Embedded Application Binary Interface) legt ein Ausnahmeentladungsmodell fest, das Entladungscodes verwendet, aber für SEH-Entladung in Windows nicht ausreichend ist. Denn hier müssen asynchrone Fälle gehandhabt werden, in denen der Prozessor inmitten des Prologs oder Epilogs einer Funktion ist. Windows teilt außerdem die Entladungssteuerung in Entladung auf Funktionsebene und für den sprachspezifischen Bereich auf, was in der ARM EABI nicht definiert ist. Deshalb legt Windows auf ARM mehr Details für die Entladung von Daten und Verfahren fest.

### <a name="assumptions"></a>Annahmen

Ausführbare Dateien für Windows auf ARM verwenden das portierbare ausführbare Format (Portable Executable, PE). Weitere Informationen finden Sie in der [Microsoft PE-und COFF-Spezifikation](https://go.microsoft.com/fwlink/p/?linkid=84140). Ausnahmebehandlungsinformationen werden in den Abschnitten .pdata und .xdata des Bilds gespeichert.

Der Ausnahmebehandlungsmechanismus geht von bestimmten Annahmen über den Code aus, der ABI für Windows auf ARM folgt:

- Wenn eine Ausnahme innerhalb des Texts einer Funktion auftritt, spielt es keine Rolle, ob die Vorgänge des Prologs rückgängig gemacht werden oder die Vorgänge des Epilogs vorwärts ausgeführt werden. Beides sollte zum gleichen Ergebnis führen.

- Prologe und Epiloge entsprechen einander tendenziell. Das lässt sich nutzen, um die Größe der für die Beschreibung der Entladung nötigen Metadaten zu verringern.

- Funktionen sind eher relativ klein. Verschiedene Optimierungen stützen sich darauf im Hinblick auf das effiziente Packen von Daten.

- Wenn eine Bedingung in einen Epilog eingefügt wird, gilt sie gleichermaßen für jede Anweisung im Epilog.

- Wenn der Stapelzeiger (Stack Pointer, SP) in einem anderen Register im Prolog gespeichert wird, muss dieses in der ganzen Funktion unverändert bleiben, sodass der ursprüngliche SP jederzeit wiederhergestellt werden kann.

- Sämtliche Bearbeitungen des SP müssen strikt innerhalb von Prolog und Epilog erfolgen, außer wenn er in einem anderen Register gespeichert ist.

- Folgende Vorgänge sind nötig, damit ein Stapelrahmen entladen werden kann:

  - Anpassen von r13 (SP) in 4-Byte-Schritten.

  - Eines oder mehrere Ganzzahlregister per Pop entfernen.

  - Eines oder mehrere VFP-Register (Virtual Floating-Poin, Gleitkomma) per Pop entfernen.

  - Einen willkürlichen Registerwert nach r13 (SP) kopieren.

  - SP mithilfe eines kleinen Postdekrementvorgangs aus dem Stapel laden.

  - Einen Rahmentyp aus einigen klar definierten Rahmentypen analysieren.

### <a name="pdata-records"></a>.pdata-Datensätze

Die .pdata-Datensätze in einem PE-Format-Bild sind ein geordnetes Array von Elementen mit fester Länge, die jede Stapelbearbeitungsfunktion beschreiben. Blattfunktionen – das sind Funktionen, die keine andere Funktionen aufrufen – erfordern keine .pdata-Datensätze, wenn sie den Stapel nicht bearbeiten. (Das heißt, sie erfordern keinerlei lokales Speichern und müssen nicht flüchtige Register weder speichern noch wiederherstellen.). Datensätze für diese Funktionen können im .pdata-Bereich weggelassen werden, sodass Platz gespart wird. Ein Entladevorgang aus einer dieser Funktionen kann einfach die Rückgabeadresse aus dem Link Register (LR) an den Programmzähler (Program Counter, PC) kopieren, um nach oben zum Aufrufer zu bewegen.

Jeder .pdata-Datensatz für ARM ist 8 Byte lang. Das allgemeine Format für einen Datensatz platziert die relative virtuelle Adresse (RVA) des Funktionsstarts in das erste 32-Bit-Wort gefolgt von einem zweiten Wort, das entweder einen Zeiger zu einem .xdata-Block mit variabler Länge enthält oder ein gepacktes Wort, dass die Entladesequenz einer kanonischen Funktion beschreibt, wie in dieser Tabelle dargestellt:

|Wortoffset|Bits|Zweck|
|-----------------|----------|-------------|
|0|0-31|*RVA für Funktions Start* ist die 32-Bit-RVA des Starts der Funktion. Wenn die Funktion Thumb-Code enthält, muss der niedrigste Bitwert dieser Adresse festgelegt werden.|
|1|0-1|*Flag* ist ein 2-Bit-Feld, das angibt, wie die verbleibenden 30 Bits des zweiten. pdata-Worts interpretiert werden. Wenn *Flag* gleich 0 ist, bilden die übrigen Bits eine *RVA der Ausnahme Informationen* (mit den unteren zwei Bits implizit 0). Wenn das *Flag* ungleich 0 (null) ist, bilden die übrigen Bits eine *gepackte Entladedaten* Struktur.|
|1|2-31|*Ausnahme Informationen RVA* oder *gepackte Entladedaten*.<br /><br /> *Ausnahme Informationen RVA* ist die Adresse der Struktur der Ausnahme Informationen mit variabler Länge, die im Abschnitt. XData gespeichert ist. Diese Daten müssen 4-Bytes ausgerichtet sein.<br /><br /> *Gepackte Entladedaten* sind eine komprimierte Beschreibung der Vorgänge, die zum Entladen von einer Funktion erforderlich sind, vorausgesetzt, eine kanonische Form. In diesem Fall ist kein .xdata-Datensatz erforderlich.|

### <a name="packed-unwind-data"></a>Gepackte Entladedaten

Bei Funktionen, deren Prolog und Epilog der unten beschriebenen kanonischen Form entsprechen, können gepackte Entladedaten verwendet werden. Damit wird kein .xdata-Datensatz benötigt und der erforderliche Platz für die Entladung der Daten deutlich reduziert. Die kanonischen Prologe und Epiloge wurden entwickelt, sodass sie den allgemeinen Anforderung einer einfachen Funktion entsprechen, die keinen Ausnahmehandler erfordert und ihre Setup- und Teardownvorgänge in der standardmäßigen Reihenfolge durchführt.

Diese Tabelle zeigt das Format eines .pdata-Datensatzes, der Entladedaten gepackt hat:

|Wortoffset|Bits|Zweck|
|-----------------|----------|-------------|
|0|0-31|*RVA für Funktions Start* ist die 32-Bit-RVA des Starts der Funktion. Wenn die Funktion Thumb-Code enthält, muss der niedrigste Bitwert dieser Adresse festgelegt werden.|
|1|0-1|*Flag* ist ein 2-Bit-Feld, das die folgenden Bedeutungen hat:<br /><br />-00 = gepackte Entladedaten werden nicht verwendet. verbleibende Bits zeigen auf. XData-Datensatz.<br />-01 = entpackte Entladedaten.<br />-10 = gepackte Entladedaten, bei denen davon ausgegangen wird, dass die Funktion keinen Prolog hat. Das ist nützlich beim Beschreiben von Funktionsfragmenten, die nicht mit dem Start der Funktion verbunden sind.<br />-11 = reserviert.|
|1|2-12|Die *Funktions Länge* ist ein 11-Bit-Feld, das die Länge der gesamten Funktion in Bytes geteilt durch 2 bereitstellt. Wenn die Funktion größer als 4 KB ist, muss stattdessen ein voller .xdata-Datensatz verwendet werden.|
|1|13-14|*Ret* ist ein 2-Bit-Feld, das angibt, wie die Funktion zurückgibt:<br /><br />-00 = Return via Pop {PC} (das *L* -flagbit muss in diesem Fall auf 1 festgelegt werden).<br />-01 = Rückgabe mithilfe einer 16-Bit-Verzweigung.<br />-10 = Rückgabe mithilfe eines 32-Bit-Zweigs.<br />-11 = kein Epilog. Das ist nützlich, wenn ein nicht verbundenes Funktionsfragment beschrieben werden soll, das nur aus ein Prolog bestehen kann, aber dessen Epilog sich anderswo befindet.|
|1|15|*H* ist ein 1-Bit-Flag, das angibt, ob die Funktion den ganzzahligen Parameter registriert (r0-r3), indem Sie Sie an den Anfang der Funktion übertragen und die 16 Bytes des Stapels vor der Rückgabe aufheben. (0 = greift die Register nicht heraus, 1 = Greift Register heraus.)|
|1|16-18|*Reg* ist ein 3-Bit-Feld, das den Index des letzten gespeicherten nicht flüchtigen Registers angibt. Wenn das *R* -Bit 0 ist, werden nur ganzzahlige Register gespeichert, und es wird davon ausgegangen, dass Sie sich im Bereich von R4-RN befinden, wobei N gleich 4 + *reg*ist. Wenn das *R* -Bit 1 ist, werden nur Gleit Komma Register gespeichert, und es wird davon ausgegangen, dass Sie sich im Bereich von D8-DN befinden, wobei N gleich 8 + *reg*ist. Die besondere Kombination von *R* = 1 und *reg* = 7 gibt an, dass keine Register gespeichert werden.|
|1|19|*R* ist ein 1-Bit-Flag, das angibt, ob es sich bei den gespeicherten nicht flüchtigen Registern um ganzzahlige Register (0) oder Gleit Komma Register (1) handelt. Wenn *R* auf 1 festgelegt ist und das Feld *reg* auf 7 festgelegt ist, wurden keine nicht flüchtigen Register per pushübertragung übermittelt.|
|1|20|*L* ist ein 1-Bit-Flag, das angibt, ob die Funktion LR zusammen mit anderen Registern speichert/wiederherstellt, die durch das *reg* -Feld angegeben werden. (0 = speichert nicht/stellt nicht wieder her, 1 = speichert/stellt wieder her.)|
|1|21|*C* ist ein 1-Bit-Flag, das angibt, ob die Funktion zusätzliche Anweisungen zum Einrichten einer Frame Kette für schnelles Stapel laufen (1) oder nicht (0) enthält. Wen das Bit festgelegt wurde, wird r11 implizit in der Liste nicht flüchtiger Ganzzahlregister gespeichert. (Weitere Informationen finden Sie unter Einschränkungen, wenn das *C* -Flag verwendet wird.)|
|1|22-31|Die *Stapel Anpassung* ist ein 10-Bit-Feld, das die Anzahl der für diese Funktion zugeordneten Stapel Stapel angibt, dividiert durch 4. Es lassen sich allerdings nur Werte zwischen 0x000 und 0x3F3 direkt codieren. Funktionen, die über 4044 Bytes an Stapel zuzuordnen, müssen einen vollständigen .xdata-Datensatz verwenden. Wenn das Feld für die *Stapel Anpassung* 0x3f 4 oder größer ist, haben die unteren 4 Bits eine besondere Bedeutung:<br /><br />-Bits 0-1 zeigt die Anzahl der Wörter der Stapel Anpassung (1-4) minus 1 an.<br />-Bit 2 wird auf 1 festgelegt, wenn der Prolog diese Anpassung in seinen Pushvorgang kombiniert hat.<br />-Bit 3 wird auf 1 festgelegt, wenn der Epilog diese Anpassung in seinen Pop-Vorgang kombiniert hat.|

Wegen möglicher Redundanzen in den oben genannten Codierungen gelten folgende Einschränkungen:

- Wenn das *C* -Flag auf 1 festgelegt ist:

   - Das *L* -Flag muss auch auf 1 festgelegt werden, da für die Frame Verkettung sowohl die-als auch die-LR erforderlich sind

   - R11 dürfen nicht in den von *reg*beschriebenen Register Satz enthalten sein. Das heißt, wenn R4-R11 übermittelt werden, sollte *reg* nur R4-R10 beschreiben, da das *C* -Flag R11 impliziert.

- Wenn das Feld " *ret* " auf 0 festgelegt ist, muss das *L* -Flag auf 1 festgelegt werden.

Werden diese Einschränkungen übergangen, kann dies eine nicht unterstützte Sequenz hervorrufen.

In der nachfolgenden Diskussion werden zwei Pseudo-Flags von der *Stapel Anpassung*abgeleitet:

- *PF* oder "prologfold" gibt an, dass die *Stapel Anpassung* 0x3f 4 oder größer und Bit 2 festgelegt ist.

- *EF* oder "epilogfold" gibt an, dass die *Stapel Anpassung* 0x3f 4 oder größer und Bit 3 festgelegt ist.

Prologe für nicht kanonische Funktionen können bis zu 5 Anweisungen haben (beachten Sie, dass 3a und 3b sich gegenseitig ausschließen):

|Anweisung|Es wird davon ausgegangen, dass Opcode vorhanden ist, wenn:|Größe|Opcode|Entladungscodes|
|-----------------|-----------------------------------|----------|------------|------------------|
|1|*H*==1|16|`push {r0-r3}`|04|
|2|*C*= = 1 oder *L*= = 1 oder *R*= = 0 oder PF = = 1|16/32|`push {registers}`|80-BF/D0-DF/EC-ED|
|3a|*C*= = 1 und (*L*= = 0 und *R*= = 1 und PF = = 0)|16|`mov r11,sp`|C0-CF/FB|
|3b|*C*= = 1 und (*L*= = 1 oder *R*= = 0 oder PF = = 1)|32|`add r11,sp,#xx`|FC|
|4|*R*= = 1 und *reg* ! = 7|32|`vpush {d8-dE}`|E0-E7|
|5|*Stapel Anpassung* ! = 0 und PF = = 0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|

Anweisung 1 ist immer vorhanden, wenn das *H* -Bit auf 1 festgelegt ist.

Zum Einrichten der Frame Verkettung ist entweder die Anweisung 3a oder 3B vorhanden, wenn das *C* -Bit festgelegt ist. Es ist ein 16-Bit-`mov`, wenn kein Register außer r11 und LR per Push abgelegt wird; ansonsten ist es ein 32-Bit-`add`.

Wird eine nicht gefaltete Anpassung festgelegt, ist Anweisung die ausdrückliche Stapelanpassung.

Die Anweisungen 2 und 4 werden abhängig davon festgelegt, ob eine Pushübertagung erforderlich ist. In dieser Tabelle ist zusammengefasst, welche Register auf der Grundlage der *C*-, *L*-, *R*-und *PF* -Felder gespeichert werden. In allen Fällen ist *N* gleich *reg* + 4, *E* ist gleich *reg* + 8, und *S* ist gleich (~*Stapel Anpassung*) & 3.

|A|L|R|PF|Ganzzahlregister per Push abgelegt|VFP-Register per Push abgelegt|
|-------|-------|-------|--------|------------------------------|--------------------------|
|0|0|0|0|R4-r*N*|Keine|
|0|0|0|1|r*S*-r*N*|Keine|
|0|0|1|0|Keine|D8-d*E*|
|0|0|1|1|r*S*-R3|D8-d*E*|
|0|1|0|0|R4-r*N*, LR|Keine|
|0|1|0|1|r*S*-r*N*, LR|Keine|
|0|1|1|0|LR|D8-d*E*|
|0|1|1|1|r*S*-R3, LR|D8-d*E*|
|1|0|0|0|R4-r*N*, R11|Keine|
|1|0|0|1|r*S*-r*N*, R11|Keine|
|1|0|1|0|r11|D8-d*E*|
|1|0|1|1|r*S*-R3, R11|D8-d*E*|
|1|1|0|0|R4-r*N*, R11, LR|Keine|
|1|1|0|1|r*S*-r*N*, R11, LR|Keine|
|1|1|1|0|r11, LR|D8-d*E*|
|1|1|1|1|r*S*-R3, R11, LR|D8-d*E*|

Die Epiloge für kanonische Funktionen ermöglichen es, einer ähnlichen Form zu folgen, doch rückwärts und mit ein paar zusätzlichen Optionen. Der Epiloge kann bis zu 5 Anweisungen lang sein und seine Form wird streng durch das Format des Prologs diktiert.

|Anweisung|Es wird davon ausgegangen, dass Opcode vorhanden ist, wenn:|Größe|Opcode|
|-----------------|-----------------------------------|----------|------------|
|6|*Stapel Anpassung*! = 0 und *EF*= = 0|16/32|`add   sp,sp,#xx`|
|7|*R*= = 1 und *reg*! = 7|32|`vpop  {d8-dE}`|
|8|*C*= = 1 oder (*L*= = 1 und *H*= = 0) oder *R*= = 0 oder *EF*= = 1|16/32|`pop   {registers}`|
|9a|*H*= = 1 und *L*= = 0|16|`add   sp,sp,#0x10`|
|9b|*H*= = 1 und *L*= = 1|32|`ldr   pc,[sp],#0x14`|
|10a|*Ret*= = 1|16|`bx    reg`|
|10b|*Ret*= = 2|32|`b     address`|

Anweisung 6 ist die ausdrückliche Stapelanpassung, wenn eine nicht gefaltete Anpassung festgelegt wurde. Da *PF* unabhängig von *EF*ist, ist es möglich, dass Anweisung 5 ohne Anweisung 6 vorhanden ist, oder umgekehrt.

In den Anweisungen 7 und 8 wird die gleiche Logik wie der Prolog verwendet, um zu bestimmen, welche Register aus dem Stapel wieder hergestellt werden, jedoch mit diesen beiden Änderungen: zuerst wird *EF* anstelle von *PF*verwendet. Zweitens: Wenn *ret* = 0 ist, wird LR durch den PC in der Registerliste ersetzt, und der Epilog wird sofort beendet.

Wenn *H* festgelegt ist, ist entweder die Anweisung 9a oder 9B vorhanden. Anweisung 9a wird verwendet, wenn *L* 0 ist, um anzugeben, dass sich die LR nicht auf dem Stapel befindet. In diesem Fall wird der Stapel manuell angepasst und der *ret* muss 1 oder 2 sein, um eine explizite Rückgabe anzugeben. Anweisung 9B wird verwendet, wenn *L* 1 ist, um ein frühes Ende des Epilogs anzugeben und den Stapel gleichzeitig zurückzugeben und anzupassen.

Wenn der Epilog noch nicht beendet wurde, ist entweder die Anweisung 10A oder 10B vorhanden, um eine 16-Bit-oder 32-Bit-Verzweigung anzugeben, die auf dem Wert von *ret*basiert.

### <a name="xdata-records"></a>.xdata-Datensätze

Wenn das gepackte Entladeformat nicht zur Beschreibung der Entladung einer Funktion ausreicht, muss ein .xdata-Datensatz mit variabler Länge erstellt werden. Die Adresse dieses Datensatzes wird im zweiten Wort des .pdata-Datensatzes gespeichert. Das Format von .xdata ist ein gepackter Satz an Worten mit variabler Länge, der vier Abschnitte hat:

1. Ein 1- oder 2-Wort-Header, der die Gesamtgröße der .xdata-Struktur beschreibt und wichtige Funktionsdaten enthält. Das zweite Wort ist nur vorhanden, wenn die Felder *epilogcount* und *Code Words* beide auf 0 festgelegt sind. Die Felder sind in dieser Tabelle aufgeteilt:

   |Word|Bits|Zweck|
   |----------|----------|-------------|
   |0|0-17|Die *Funktions Länge* ist ein 18-Bit-Feld, das die Gesamtlänge der Funktion in Byte (dividiert durch 2) angibt. Wenn eine Funktion größer als 512 KB ist, dann müssen mehrere .pdata- und .xdata-Datensätze verwendet werden, um die Funktion zu beschreiben. Weitere Informationen finden Sie im Abschnitt "Große Funktionen" in diesem Dokument.|
   |0|18-19|*Vers* ist ein 2-Bit-Feld, das die Version der restlichen XData beschreibt. Nur Version 0 ist derzeit definiert; die Werte 1-3 sind reserviert.|
   |0|20|*X* ist ein 1-Bit-Feld, das das vorhanden sein (1) oder das Fehlen (0) von Ausnahme Daten angibt.|
   |0|21|*E* ist ein 1-Bit-Feld, das angibt, dass Informationen, die einen einzelnen Epilog beschreiben, in den Header (1) gepackt werden, anstatt zusätzliche Bereichs Wörter später (0) zu erfordern.|
   |0|22|*F* ist ein 1-Bit-Feld, das angibt, dass dieser Datensatz ein Funktions Fragment (1) oder eine vollständige Funktion (0) beschreibt. Ein Fragment impliziert, dass es keinen Prolog gibt und dass sämtliche Prologverarbeitung ignoriert werden soll.|
   |0|23-27|*Epilogcount* ist ein 5-Bit-Feld, das je nach Status des *E* -Bit zwei Bedeutungen hat:<br /><br /> -Wenn *E* 0 ist, ist dieses Feld die Anzahl der in Abschnitt 3 beschriebenen Ausnahme Bereiche. Wenn in der Funktion mehr als 31 Bereiche vorhanden sind, müssen dieses Feld und das Feld " *Code Wörter* " beide auf "0" festgelegt werden, um anzugeben, dass ein Erweiterungs Wort erforderlich ist.<br />Wenn *E* 1 ist, gibt dieses Feld den Index des ersten Entladungs Codes an, der den einzigen Epilog beschreibt.|
   |0|28-31|*Code Wörter* sind ein 4-Bit-Feld, das die Anzahl der 32-Bit-Wörter angibt, die erforderlich sind, um alle Entladungs Codes in Abschnitt 4 zu enthalten. Wenn mehr als 15 Wörter für mehr als 63 Entladungs Code Bytes erforderlich sind, müssen sowohl dieses Feld als auch das Feld *epilogcount* auf 0 festgelegt werden, um anzugeben, dass ein Erweiterungs Wort erforderlich ist.|
   |1|0-15|Die *Erweiterte epiloganzahl* ist ein 16-Bit-Feld, das mehr Platz für die Codierung einer ungewöhnlich großen Anzahl von epilogen bereitstellt. Das Erweiterungs Wort, das dieses Feld enthält, ist nur vorhanden, wenn die Felder *epilogcount* und *Code Words* des ersten Header Worts beide auf 0 festgelegt sind.|
   |1|16-23|*Erweiterte Codewörter* sind ein 8-Bit-Feld, das mehr Platz zum Codieren einer ungewöhnlich großen Anzahl von Entladungs Codewörtern bereitstellt. Das Erweiterungs Wort, das dieses Feld enthält, ist nur vorhanden, wenn die Felder *epilogcount* und *Code Words* des ersten Header Worts beide auf 0 festgelegt sind.|
   |1|24-31|Reserviert|

1. Nach den Ausnahme Daten (wenn das *E* -Bit in der Kopfzeile auf 0 festgelegt wurde) ist eine Liste mit Informationen zu epilogbereichen, die in ein Wort gepackt und in der Reihenfolge der Erhöhung des Start Offsets gespeichert werden. Jeder Bereich enthält folgende Felder:

   |Bits|Zweck|
   |----------|-------------|
   |0-17|Der *Epilog-Start Offset* ist ein 18-Bit-Feld, das den Offset des Epilogs in Byte dividiert durch 2 relativ zum Anfang der Funktion beschreibt.|
   |18-19|*Res* ist ein 2-Bit-Feld, das für zukünftige Erweiterungen reserviert ist. Sein Wert muss 0 sein.|
   |20-23|*Bedingung* ist ein 4-Bit-Feld, das die Bedingung für die Ausführung des Epilogs gibt. Für bedingungslose Epiloge muss es auf 0xE festgelegt sein, was "immer" bedeutet. (Ein Epilog muss vollständig beginnt oder bedingungslos sein und im Thumb-2-Modus beginnt der Epilog mit der ersten Anweisung nach dem IT-Opcode.)|
   |24-31|Der *Epilog-Start Index* ist ein 8-Bit-Feld, das den Byte Index des ersten Entladungs Codes angibt, der diesen Epilog beschreibt.|

1. Nach der Liste von Epilogbereichen kommt ein Array von Bytes, das Entladungscodes enthält. Diese werden detailliert im Abschnitt Entladungscodes dieses Artikels beschrieben. Dieses Array ist am Ende aufgefüllt bis zur nächsten vollen Wortgrenze. Die Bytes werden in Little-Endian-Reihenfolge gespeichert, sodass sie im Little-Endian-Modus direkt abgerufen werden können.

1. Wenn das *X* -Feld im Header 1 ist, folgen die Ausnahmehandler-Informationen den Entladungs Code bytes. Dies besteht aus einem *Ausnahmehandler-RVA* , der die Adresse des Ausnahme Handlers enthält, gefolgt von der (Variablen Länge) Menge der Daten, die vom Ausnahmehandler benötigt werden.

Der .xdata-Datensatz ist so gestaltet, dass es möglich ist, die ersten 8 Bytes abzurufen und die volle Größe des Datensatzes zu berechnen, ausgenommen die Länge der folgenden Ausnahmedaten mit variabler Größe. Dieser Codeausschnitt berechnet die Datensatzgröße:

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogueScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 23) != 0) {
        Size = 4;
        EpilogueScopes = (Xdata[0] >> 23) & 0x1f;
        UnwindWords = (Xdata[0] >> 28) & 0x0f;
    } else {
        Size = 8;
        EpilogueScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    if (!(Xdata[0] & (1 << 21))) {
        Size += 4 * EpilogueScopes;
    }
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;
    }
    return Size;
}
```

Obwohl der Prolog und jeder Epilog über einen Index für die Entladungs Codes verfügen, wird die Tabelle zwischen Ihnen gemeinsam genutzt. Es ist nicht ungewöhnlich, dass alle denselben Entladungscode teilen. Wir empfehlen, dass Compiler-Autoren für diesen Fall optimieren, denn der größte Index, der festgelegt werden kann, ist 255 und das begrenzt die Gesamtzahl der Entladungscodes, die für eine bestimmte Funktion mögliche sind.

### <a name="unwind-codes"></a>Entladungscodes

Das Array an Entladungscodes ist ein Pool von Anweisungsequenzen, der genau beschreibt, wie die Wirkungen des Prologs rückgängig gemacht werden und in welcher Reihenfolge. Die Entladungscodes sind ein Satz von Minianweisungen, die als eine Zeichenfolge von Bytes codiert wurden. Wenn die Ausführung abgeschlossen ist, befindet sich die Rückgabeadresse im LR-Register und alle nicht flüchtigen Register werden auf ihre Werte zu Beginn des Funktionsaufrufs zurückgesetzt.

Würden Ausnahmen garantiert immer nur innerhalb einer Funktion auftreten und niemals im Prolog oder Epilog, dann wäre nur eine Entladesequenz nötig. Doch das Windows-Entlademodell erfordert die Fähigkeit, von innerhalb eines teilweise ausgeführten Prologs oder Epilogs aus zu entladen. Damit dieser Anforderung Rechnung getragen wird, wurden die Entladungscodes sorgfältig so entwickelt, dass sie eine unzweifelhafte Eins-zu-Eins-Zuordnung zu jedem relevanten Opcode im Prolog und Epilog haben. Das hat eine Reihe von Auswirkungen:

- Es ist möglich, die Länge von Prolog und Epilog zu berechnen, indem man die Anzahl von Entladungscodes zählt. Das ist selbst mit Thumb-2-Anweisungen mit variabler Länge möglich, da es eine eindeutige Zuordnung für 16- und 32-Bit-Opcodes gibt.

- Durch Zählen der Anzahl von Anweisungen nach dem Start eines Epilogbereichs ist es möglich, die gleiche Anzahl von Entladungscodes zu überspringen und den Rest einer Sequenz auszuführen, um die teilweise ausgeführte Entladung abzuschließen, die der Epilog durchgeführt hat.

- Durch Zählen der Anzahl von Anweisungen vor dem Ende eines Prologs ist es möglich, die gleiche Anzahl von Entladungscodes zu überspringen und den Rest einer Sequenz auszuführen, sodass nur die Teile des Prologs rückgängig gemacht werden, die der Prolog durchgeführt hat.

Die folgende Tabelle zeigt die Zuordnung von Entladungscodes zu Opcodes. Die häufigsten Codes sind nur ein Byte, während weniger übliche zwei, drei oder sogar vier Bytes benötigen. Jeder Code wird vom signifikantesten bis zum am wenigsten signifikanten Byte gespeichert. Die Entladungscodestruktur unterscheidet sich von der Entladung, die in ARM EABI beschrieben ist, da diese Entladungscodes mit einer Eins-zu-Eins-Zuordnung zu den Opcodes in Prolog und Epilog entwickelt wurden, was die Entladung teilweise ausgeführter Prologe und Epiloge möglich macht.

|Byte 1|Byte 2|Byte 3|Byte 4|Opsize|Erklärung|
|------------|------------|------------|------------|------------|-----------------|
|00-7F||||16|`add   sp,sp,#X`<br /><br /> wobei X (Code & 0x7F) \* 4 ist.|
|80-BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> Wenn LR per pop ausgelesen wird, wenn der Code & 0x2000 und R0-R12 per pop ausgelesen werden, wenn das entsprechende Bit im Code & 0x1fff festgelegt ist.|
|C0-CF||||16|`mov   sp,rX`<br /><br /> wobei X Code & 0x0f ist.|
|D0-D7||||16|`pop   {r4-rX,lr}`<br /><br /> wobei X (Code & 0x03) + 4 ist und LR per Pop ausgeblendet wird, wenn Code & 0x04|
|D8-DF||||32|`pop   {r4-rX,lr}`<br /><br /> wobei X (Code & 0x03) + 8 und LR per Pop ausgeblendet wird, wenn Code & 0x04|
|E0-E7||||32|`vpop  {d8-dX}`<br /><br /> wobei X (Code & 0x07) + 8 ist.|
|E8-EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> wobei X (Code & 0x03ff) \* 4 ist.|
|EC-ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> Wenn LR per pop ausgelesen wird, wenn Code & 0x0100 und R0-R7 per pop ausgelesen werden, wenn das entsprechende Bit im Code & 0x00FF festgelegt ist.|
|EE|00-0F|||16|Microsoft-spezifisch|
|EE|10-FF|||16|Verfügbar|
|EF|00-0F|||32|`ldr   lr,[sp],#X`<br /><br /> wobei X (Code & 0x000f) \* 4 ist.|
|EF|10-FF|||32|Verfügbar|
|F0-F4||||-|Verfügbar|
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> wobei S (Code & 0x00f 0) > > 4 und E Code & 0x000f ist.|
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> Where S ist ((Code & 0x00f 0) > > 4) + 16 und E ist (Code & 0x000f) + 16|
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> wobei X (Code & 0x00ffff) \* 4 ist.|
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> wobei X (Code & 0x00ffffff) \* 4 ist.|
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> wobei X (Code & 0x00ffff) \* 4 ist.|
|FA|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> wobei X (Code & 0x00ffffff) \* 4 ist.|
|FB||||16|nop (16-Bit)|
|FC||||32|nop (32-Bit)|
|FD||||16|end + 16-Bit nop im Epilog|
|FE||||32|end + 32-Bit nop im Epilog|
|FF||||-|end|

Dadurch wird der Bereich der hexadezimalen Werte für jedes Byte in einem Entladungs Code *Code*zusammen mit der Opcode size *opsize* und der entsprechenden ursprünglichen Anweisungs Interpretation angezeigt. Leere Zellen weisen auf kürzere Entladungscodes hin. Die Anweisungen mit großen Werten umfassen mehrere Bytes, wobei die signifikanten zuerst gespeichert sind. Das Feld *opsize* zeigt die implizite opcodegröße an, die jedem Thumb-2-Vorgang zugeordnet ist. Die offensichtlichen Doppeleinträge in der Tabelle bei verschiedenen Codierungen werden verwendet, damit zwischen den verschiedenen Opcodegrößen unterschieden werden kann.

Die Entladungscodes wurden entwickelt, sodass das erste Byte des Codes sowohl die Gesamtgröße des Codes in Bytes als auch die Größe des entsprechenden Opcodes im Anweisungsstream verrät. Um die Größe von Prolog oder Epilog berechnen zu können, gehen Sie die Entladungscodes vom Beginn der Sequenz bis zum Ende durch und verwenden eine Nachschlagetabelle oder eine vergleichbare Methode, um zu bestimmen, wie lange der entsprechende Opcode ist.

Die Entladungscodes 0xFD und 0xFE sind gleich dem regulären Endcode 0xFF, machen aber einen zusätzlichen nop-Opcode im Epilogfall aus, entweder 16- oder 32-Bit. Bei Prologen sind die Codes 0xFD, 0xFE und 0xFF genau gleich. Dies berücksichtigt die allgemeinen epilogenden `bx lr` oder `b <tailcall-target>`, die keine entsprechende prologanweisung haben. Das erhöht die Möglichkeit, Entladungssequenzen zwischen Prolog und Epilog zu teilen.

In vielen Fällen sollte es möglich sein, denselben Satz an Entladungscodes für Prologe und Epiloge zu verwenden. Um jedoch die Entladung teilweise ausgeführter Prologe und Epiloge bewältigen zu können, benötigen Sie möglicherweise mehrere Entladungscodesequenzen, die sich hinsichtlich Sortierung oder Verhalten unterscheiden. Deshalb hat jeder Epilog seinen eigenen Index im Entladungsarray, sodass angezeigt wird, wo mit der Umsetzung zu beginnen ist.

### <a name="unwinding-partial-prologues-and-epilogues"></a>Entladen partieller Prologe und Epiloge

Der häufigste Entladungsfall ist eine Ausnahme, die im Text der Funktion auftritt, jenseits vom Prolog und allen Epilogen. In diesem Fall führt der Entlader die Codes im Entladungsarray aus, beginnend bei Index 0, und er fährt fort, bis ein Endopcode festgestellt wird.

Wenn während der Ausführung eines Prologs oder Epilogs eine Ausnahme auftritt, wird der Stapelrahmen nur teilweise konstruiert und der Entlader muss genau bestimmen, was vorgefallen ist, um dies korrekt rückgängig machen zu können.

Betrachten Sie beispielsweise diese Prolog-Epilog-Sequenz:

```asm
0000:   push  {r0-r3}         ; 0x04
0002:   push  {r4-r9, lr}     ; 0xdd
0006:   mov   r7, sp          ; 0xc7
...
0140:   mov   sp, r7          ; 0xc7
0142:   pop   {r4-r9, lr}     ; 0xdd
0146:   add   sp, sp, #16     ; 0x04
0148:   bx    lr
```

Neben jedem Opcode befindet sich der entsprechende Entladungscode, der diesen Vorgang beschreibt. Die Sequenz der Entladungscodes für den Prolog ist ein Spiegelbild derjenigen für den Epilog, abgesehen von der letzten Anweisung. Dieser Fall ist üblich, und der Grund dafür ist, dass die Entladungs Codes für den Prolog immer davon ausgegangen werden, dass Sie in umgekehrter Reihenfolge in der Ausführungsreihenfolge des Prologs gespeichert werden. Damit erhalten wir einen gemeinsamen Satz von Entladungscodes:

```asm
0xc7, 0xdd, 0x04, 0xfd
```

Der Code 0xFD ist ein Spezialcode für das Ende der Sequenz und bedeutet, dass der Epilog eine 16-Bit-Anweisung länger als der Prolog ist. Damit ist es öfter möglich, Entladungscodes gemeinsam zu nutzen.

Im Beispiel beginnt die Entladung mit dem Epilogfall, wenn beim Ausführen des Funktionstextes zwischen Prolog und Epilog eine Ausnahme auftritt, und zwar bei Offset 0 im Epilogcode. Das entspricht dem Offset 0x140 im Beispiel. Der Entlader führt die volle Entladesequenz aus, da keine Bereinigung vorgenommen wurde. Wenn stattdessen die Ausnahme eine Anweisung nach dem Beginn des Epilogcodes auftritt, kann der Entlader erfolgreich entladen, indem er den ersten Entladungscode überspringt. Ausgehend von einer Eins-zu-Eins-Zuordnung von Opcodes und Entladungscodes sollte der Entlader die ersten *n* Entladungscodes überspringen, wenn die Entladung von Anweisung *n* im Epilog stattfindet.

Die gleiche Logik gilt umgekehrt für den Prolog. Findet die Entladung von Offset 0 im Prolog statt, muss nichts ausgeführt werden. Findet die Entladung von einer Anweisung weiter innen statt, sollte die Entladungssequenz einen Entladungscode vom Ende starten, da Prolog-Entladungscodes in umgekehrter Reihenfolge gespeichert werden. Im allgemeinen Fall sollte die Entladung bei *n*-Entladungscodes vom Ende der Codeliste beginnen, wenn die Entladung von Anweisung *n* im Prolog erfolgt.

Prolog- und Epilog-Entladungscodes stimmen nicht immer genau überein. In diesem Fall muss das Entladungscode-Array eine Reihe von Codesequenzen enthalten. Verwenden Sie folgende Logik, um den Offset für den Beginn der Verarbeitungscodes zu bestimmen:

1. Wenn die Entladung im Funktionstext erfolgt, beginnen Sie mit der Ausführung der Entladungscodes bei Index 0 und fahren Sie fort, bis ein Endopcode erreicht wird.

2. Wenn die Entladung in einem Epilog erfolgt, verwenden Sie den epilogspezifischen Index, der vom Epilogbereich zur Verfügung gestellt wird. Kalkulieren Sie, wie viele Bytes sich der PC vom Beginn des Epilogs befindet. Springen Sie in den Entladungscodes vorwärts, bis alle bereits ausgeführten Anweisungen einbezogen sind. Der Start der Entladesequenz beginnt hier.

3. Erfolgt die Entladung im Prolog, beginnen Sie ab Index 0 in den Entladungscodes. Kalkulieren Sie die Länge des Prologcodes aus der Sequenz und dann, wie viele Bytes der PC sich vom Ende des Prologs befindet. Springen Sie in den Entladungscodes vorwärts, bis alle nicht ausgeführten Anweisungen einbezogen sind. Der Start der Entladesequenz beginnt hier.

Die Entladungscodes für den Prolog müssen immer zuerst im Array sein. Sie sind auch die Codes, die für die Entladung im Text verwendet werden. Jede epilogspezifische Codesequenz muss unmittelbar nach der Prologcodesequenz folgen.

### <a name="function-fragments"></a>Funktionsfragmente

Zur Codeoptimierung kann es hilfreich sein, eine Funktion in nicht verbundene Teile aufteilen. Wenn das geschieht, erfordert jedes Funktionsfragment einen eigenen .pdata-Datensatz – und möglicherweise einen .xdata-Datensatz.

Angenommen der Funktionsprolog befindet sich am Beginn der Funktion und kann nicht geteilt werden, dann gibt es vier Funktionsfragmentfälle:

- Nur Prolog; alle Epiloge in anderen Fragmenten.

- Prolog und einer oder mehr Epiloge; weitere Epiloge in anderen Fragmenten.

- Weder Prolog noch Epilog; Prolog und einer oder mehr Epiloge in anderen Fragmenten.

- Nur Epilog; Prolog und möglicherweise weitere Epiloge in anderen Fragmenten.

In ersterem Fall muss nur der Prolog beschrieben werden. Dies kann im Compact. pdata-Formular erfolgen, indem der Prolog normal beschrieben und ein *ret* -Wert von 3 angegeben wird, um einen Epilog anzugeben. Im vollen .xdata-Format kann das erledigt werden, indem man wie üblich die Prologentladungscodes in Index 0 festlegt und eine Epiloganzahl von 0 angibt.

Der zweite Fall ist genauso wie eine normale Funktion. Wenn nur ein Epilog im Fragment vorhanden ist und sich am Ende des Fragments befindet, kann ein Compact. pdata-Datensatz verwendet werden. Andernfalls muss ein vollständiger .xdata-Datensatzes eingesetzt werden. Beachten Sie, dass die für den Epilogstart festgelegten Offsets relativ zum Start des Fragments und nicht dem ursprünglichen Start der Funktion sind.

Der dritte und vierte Fall sind Varianten der ersten und zweiten Fälle, es sei denn, Sie enthalten keinen Prolog. In diesen Situationen wird davon ausgegangen, dass es Code vor dem Start des Epilogs gibt und er wird als Teil des Funktionstexts betrachtet, der normalerweise durch das Rückgängigmachen des Prologeffekts entladen wird. Diese Fälle müssen deshalb mit einem Pseudoprolog codiert werden, der beschreibt, wie im Text entladen wird, aber als 0-Länge bei der Bestimmung behandelt wird, ob beim Start des Fragments eine teilweise Entladung durchgeführt wird. Alternativ lässt sich dieser Pseudoprolog beschreiben, indem dieselben Entladungscodes wie beim Epilog verwendet werden, denn sie führen mutmaßlich gleiche Vorgänge durch.

Im dritten und vierten Fall wird das vorhanden sein eines Pseudo Prologs festgelegt, indem das *Flagfeld* des Compact. pdata-Datensatzes auf 2 festgelegt wird, oder indem das *F* -Flag im. XData-Header auf 1 festgelegt wird. In beiden Fällen wird die Überprüfung auf eine teilweise Prologentladung ignoriert und alle Nicht-Epilogentladungen werden als voll betrachtet.

#### <a name="large-functions"></a>Große Funktionen

Fragmente lassen sich für die Beschreibung von Funktionen einsetzen, die größer als das 512 KB-Limit sind, das von den Bit-Feldern im .xdata-Header vorgegeben wird. Um eine sehr große Funktion zu beschreiben, brechen Sie diese einfach in Fragmente herunter, die kleiner als 512 KB sind. Jedes Fragment sollte angepasst sein, sodass es einen Epilog nicht in mehrere Teile aufteilt.

Nur das erste Fragment der Funktion enthält einen Prolog; alle anderen sind mit einer Markierung versehen, wonach sie keinen Prolog enthalten. Je nach Anzahl der Epiloge kann jedes Fragment null oder mehr Epiloge enthalten. Beachten Sie, dass jeder Epilogbereich in einem Fragment dessen Startoffset relativ zum Start des Fragments und nicht dem Start der Funktion festlegt.

Wenn ein Fragment keinen Prolog und Epilog hat, erfordert er dennoch einen eigenen .pdata-Datensatz – möglicherweise auch einen .xdata-Datensatz – für die Beschreibung, wie die Entladung im Text der Funktion stattfindet.

#### <a name="shrink-wrapping"></a>Shrink-Wrapping

Ein komplexerer Sonderfall von Funktions Fragmenten ist Verkleinerungs Umbrüchen, eine Technik zum verzögern von *Register, die*vom Anfang der Funktion bis zu einem späteren Zeitpunkt in der Funktion gespeichert wird, um für einfache Fälle zu optimieren, für die keine Register Speicherung erforderlich ist. Das lässt sich als eine äußere Region beschreiben, die den Stapelspeicher zuweist, aber einen minimalen Registersatz speichert sowie einer inneren Region, die weitere Register speichert und wiederherstellt.

```asm
ShrinkWrappedFunction
    push   {r4, lr}          ; A: save minimal non-volatiles
    sub    sp, sp, #0x100    ; A: allocate all stack space up front
    ...                      ; A:
    add    r0, sp, #0xE4     ; A: prepare to do the inner save
    stm    r0, {r5-r11}      ; A: save remaining non-volatiles
    ...                      ; B:
    add    r0, sp, #0xE4     ; B: prepare to do the inner restore
    ldm    r0, {r5-r11}      ; B: restore remaining non-volatiles
    ...                      ; C:
    pop    {r4, pc}          ; C:
```

Bei Funktionen mit Shrink-Wrapping geht man typischerweise davon aus, dass der Platz für die zusätzlichen Registerspeicherungen im normalen Prolog im Voraus zugewiesen wird und die Registerspeicherungen dann mithilfe von `str` oder `stm` erfolgen statt mit `push`. Dadurch bleibt die gesamte Stapelzeiger Bearbeitung im ursprünglichen Prolog der Funktion.

Die Beispielfunktion mit Shrink-Wrapping muss in drei Regionen aufgeteilt werden, die in den Kommentaren mit A, B und C gekennzeichnet sind. Die erste Region A deckt den Start der Funktion bis zum Ende der zusätzlichen nicht flüchtigen Speicherungen ab. Es muss ein .pdata- oder .xdata-Datensatz konstruiert werden, der beschreibt, dass dieses Fragment einen Prolog und keine Epiloge hat.

Die mittlere B-Region hat einen eigenen .pdata- oder .xdata-Datensatz, der beschreibt, dass ein Fragment weder Prolog noch Epilog hat. Allerdings müssen die Entladungscodes für diese Region immer noch vorhanden sein, denn sie wird als Funktionstext betrachtet. Die Codes müssen einen zusammengesetzten Prolog beschreiben, der sowohl die ursprünglichen Register darstellt, die im Region-A-Prolog gespeichert sind, als auch die zusätzlichen Register, die vor Eintritt in Region B gespeichert wurden, als wären sie von einer Vorgangssequenz produziert worden.

Diese Registerspeicherung für Region B können nicht als "innerer Prolog" betrachtet werden, denn der für Region B beschriebene zusammengesetzte Prolog muss sowohl den Region-A-Prolog als auch die zusätzlichen, gespeicherten Register beschreiben. Würde man Fragment B so beschreiben, als hätte es einen Prolog, dann würden die Entladungscodes auch die Größe dieses Prologs implizieren, und es gibt keine Möglichkeit, den zusammengesetzten Prolog so zu beschreiben, dass eine Eins-zu-Eins-Zuordnung mit den Opcodes möglich ist, die nur die zusätzlichen Register speichern.

Die zusätzlichen Registerspeicherungen müssen als Teil von Region A betrachtet werden, denn ehe sie abgeschlossen sind, beschreibt der zusammengesetzte Prolog nicht genau den Zustand des Stapels.

Die letzte Region, C., erhält einen eigenen .pdata- oder .xdata-Datensatz, der ein Fragment beschreibt, das keinen Prolog, wohl aber einen Epilog hat.

Ein alternativer Ansatz kann ebenfalls funktionieren, wenn die Stapelbearbeitung vor Eintritt in Region B sich auf eine Anweisung reduzieren lässt:

```asm
ShrinkWrappedFunction
    push   {r4, lr}          ; A: save minimal non-volatile registers
    sub    sp, sp, #0xE0     ; A: allocate minimal stack space up front
    ...                      ; A:
    push   {r4-r9}           ; A: save remaining non-volatiles
    ...                      ; B:
    pop    {r4-r9}           ; B: restore remaining non-volatiles
    ...                      ; C:
    pop    {r4, pc}          ; C: restore non-volatile registers
```

Entscheidend ist hier, dass der Stapel bei jeder Anweisungsgrenze ganz mit den Entladungscodes für die Region übereinstimmt. Findet eine Entladung vor der inneren Pushübertagung in diesem Beispiel statt, wird sie als Teil von Region A betrachtet und nur der Region-A-Prolog wird entladen. Wenn die Entladung nach dem inneren Push erfolgt, wird Sie als Teil von Region B betrachtet, die keinen Prolog hat, aber Entladungs Codes enthält, die sowohl den inneren Push als auch den ursprünglichen Prolog aus Region A beschreiben. eine ähnliche Logik gilt für den inneren Pop.

### <a name="encoding-optimizations"></a>Optimierungen codieren

Da die Entladungscodes so umfangreich sind und kompakte und erweiterte Datenformen nutzen können, gibt es viele Gelegenheiten, die Codierung zu optimieren und so Platz zu sparen. Durch aggressiven Einsatz dieser Techniken lässt sich der Nettoaufwand zur Beschreibung von Funktionen und Fragmenten mithilfe von Entladungscodes recht stark minimieren.

Die wichtigste Optimierung besteht darin, sorgfältig darauf zu achten, die Prolog-/Epiloggrenzen für Entladungszwecke nicht mit ihren logischen Pendants aus Compilerperspektive zu verwechseln. Die Entladungsgrenzen lassen sich schrumpfen und verengen, was für mehr Effizienz sorgt. Ein Prolog kann beispielsweise Code für das Durchführen zusätzlicher Überprüfungen nach dem Stapelsetup enthalten. Doch nachdem die Stapelbearbeitung abgeschlossen ist, müssen keine weiteren Vorgänge mehr codiert werden und alles danach kann aus dem Entladungsprolog entfernt werden.

Die gleiche Regel gilt für Funktionslänge. Wenn es Daten gibt – zum Beispiel ein Literalpool –, der auf einen Epilog in einer Funktion folgt, dann sollte dieser nicht als Teil der Funktionslänge enthalten sein. Durch das Schrumpfen der Funktion auf lediglich den Code, der Teil der Funktion ist, sind die Chancen deutlich größer, dass der Epilog ganz am Ende und ein kompakter .pdata-Datensatz verwendet werden kann.

In einem Prolog ist es üblicherweise nicht nötig, weitere Opcodes aufzuzeichnen, nachdem der Stapelzeiger in ein anderes Register gespeichert wurde. Das erste, was zur Entladung der Funktion unternommen wird, ist das Wiederherstellen des SP aus dem gespeicherten Register. Weitere Vorgänge haben damit keine Auswirkung auf die Entladung.

Nur aus einer Anweisung bestehende Epiloge müssen überhaupt nicht codiert werden, weder als Bereiche noch als Entladungscodes. Findet eine Entladung statt, ehe diese Anweisung ausgeführt wurde, dann kann davon ausgegangen werden, dass sie aus dem Funktionstext stammt und es ist ausreichend, einfach nur die Prologentladungscodes auszuführen. Wenn die Entladung nach der einzelnen Anweisung ausgeführt wird, dann findet sie per Definition in einer anderen Region statt.

Epiloge mit mehreren Anweisungen müssen die erste Anweisung des Epilogs nicht codieren, aus demselben Grund wie im vorangehenden Punkt: Wenn die Entladung vor dem Ausführen der Anweisung stattfindet, ist eine vollständige Prologentladung ausreichend. Findet die Entladung nach dieser Anweisung statt, dann müssen nur die folgenden Vorgänge berücksichtigt werden.

Entladungscode sollte aggressiv wiederverwendet werden. Der von jedem Epilogbereich festgelegte Index zeigt auf einen willkürlichen Startpunkt im Array der Entladungscodes. Er muss nicht auf den Start einer vorangehenden Sequenz zeigen; er kann auch auf die Mitte zeigen. Der beste Ansatz hier besteht darin, die gewünschte Codesequenz zu generieren und dann nach einer exakten Byteübereinstimmung im bereits codierten Sequenzenpool zu suchen und irgendeine perfekte Übereinstimmung als Startpunkt für die Wiederverwendung zu nutzen.

Wenn nach dem Ignorieren von Epilogen mit nur einer Anweisung keine Epiloge verbleiben, dann sollten Sie den Einsatz eines kompakten .pdata-Formats in Betracht ziehen; das wird beim Fehlen eines Epilogs viel wahrscheinlicher.

## <a name="examples"></a>Beispiele

In diesen Beispielen ist die Abbildbasis bei 0x00400000.

### <a name="example-1-leaf-function-no-locals"></a>Beispiel 1: Blatt Funktion, keine lokalen

```asm
Prologue:
  004535F8: B430      push        {r4-r5}
Epilogue:
  00453656: BC30      pop         {r4-r5}
  00453658: 4770      bx          lr
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start RVA* = 0x000535f 8 (= 0x004535f 8-0x00400000)

- Word 1

   - *Flag* = 1, das kanonische Prolog-und epilogformate angibt

   - *Funktions Länge* = 0x31 (= 0x62/2)

   - *Ret* = 1, gibt eine 16-Bit-Verzweigungs Rückgabe an

   - *H* = 0, gibt an, dass die Parameter nicht in den vernetzt

   - *R*= 0 und *reg* = 1, gibt Push/Pop von R4-R5 an

   - *L* = 0, bedeutet, dass keine LR-Speicherung/-Wiederherstellung

   - *C* = 0, gibt an, dass keine Frame Verkettung

   - *Stapel* Anpassung = 0, gibt keine Stapel Anpassung an

### <a name="example-2-nested-function-with-local-allocation"></a>Beispiel 2: netsted-Funktion mit lokaler Zuordnung

```asm
Prologue:
  004533AC: B5F0      push        {r4-r7, lr}
  004533AE: B083      sub         sp, sp, #0xC
Epilogue:
  00453412: B003      add         sp, sp, #0xC
  00453414: BDF0      pop         {r4-r7, pc}
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start RVA* = 0x000533ac (= 0x004533ac-0x00400000)

- Word 1

   - *Flag* = 1, das kanonische Prolog-und epilogformate angibt

   - *Funktions Länge* = 0x35 (= 0x6a/2)

   - *Ret* = 0, gibt eine Pop-{PC}-Rückgabe an

   - *H* = 0, gibt an, dass die Parameter nicht in den vernetzt

   - *R*= 0 und *reg* = 3, angeben von Push/Pop von R4-R7

   - *L* = 1, gibt an, dass LR gespeichert/wieder hergestellt wurde

   - *C* = 0, gibt an, dass keine Frame Verkettung

   - *Stapel Anpassung* = 3 (= 0x0c/4)

### <a name="example-3-nested-variadic-function"></a>Beispiel 3: netsted Variadic-Funktion

```asm
Prologue:
  00453988: B40F      push        {r0-r3}
  0045398A: B570      push        {r4-r6, lr}
Epilogue:
  004539D4: E8BD 4070 pop         {r4-r6}
  004539D8: F85D FB14 ldr         pc, [sp], #0x14
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start-RVA* = 0x00053988 (= 0x00453988-0x00400000)

- Word 1

   - *Flag* = 1, das kanonische Prolog-und epilogformate angibt

   - *Funktions Länge* = 0x2A (= 0x54/2)

   - *Ret* = 0, gibt an, dass eine Pop {PC}-Rückgabe Rückgabe (in diesem Fall ein LDR-PC, [SP], #0x14 Return)

   - *H* = 1, gibt an, dass die Parameter in einem Heim angegeben wurden

   - *R*= 0 und *reg* = 2, gibt Push/Pop von R4-R6 an

   - *L* = 1, gibt an, dass LR gespeichert/wieder hergestellt wurde

   - *C* = 0, gibt an, dass keine Frame Verkettung

   - *Stapel* Anpassung = 0, gibt keine Stapel Anpassung an

### <a name="example-4-function-with-multiple-epilogues"></a>Beispiel 4: Funktion mit mehreren Epilogen

```asm
Prologue:
  004592F4: E92D 47F0 stmdb       sp!, {r4-r10, lr}
  004592F8: B086      sub         sp, sp, #0x18
Epilogues:
  00459316: B006      add         sp, sp, #0x18
  00459318: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  0045943E: B006      add         sp, sp, #0x18
  00459440: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  004595D4: B006      add         sp, sp, #0x18
  004595D6: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  00459606: B006      add         sp, sp, #0x18
  00459608: E8BD 87F0 ldm         sp!, {r4-r10, pc}
  ...
  00459636: F028 FF0F bl          KeBugCheckEx     ; end of function
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start RVA* = 0x000592f 4 (= 0x004592f 4-0x00400000)

- Word 1

   - *Flag* = 0, gibt an, dass ein. XData-Datensatz vorhanden ist (erforderlich aufgrund mehrerer Epiloge)

   - *. XData-Adresse* -0x00400000

.xdata (variabel, 6 Worte):

- Word 0

   - *Funktions Länge* = 0x0001a3 (= 0x000346/2)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 0, gibt keine Ausnahme Daten an

   - *E* = 0, gibt eine Liste von epilogbereichen an

   - *F* = 0, gibt eine vollständige Funktionsbeschreibung an, einschließlich Prolog

   - *Epilogcount* = 0x04, gibt die vier gesamten epilogbereiche an

   - *Code Wörter* = 0x01, was 1 32-Bit-Wort von Entladungs Codes angibt

- Worte 1-4 beschreiben 4 Epilogbereiche an 4 Stellen. Jeder Bereich besitzt einen gemeinsamen Satz an Entladungscodes, der mit dem Prolog geteilt wird mit einem Offset 0x00; er ist bedingungslos, legt die Bedingung 0x0E (immer) fest.

- Entladungs Codes, beginnend bei Wort 5: (Shared between Prolog/Epilog)

   - Entladungs Code 0 = 0x06: SP + = (6 < < 2)

   - Entladungscode 1 = 0xDE: pop {r4-r10, lr}

   - Entladungscode 2 = 0xFF: end

### <a name="example-5-function-with-dynamic-stack-and-inner-epilogue"></a>Beispiel 5: Funktion mit dynamischem Stapel und innerem Epilog

```asm
Prologue:
  00485A20: B40F      push        {r0-r3}
  00485A22: E92D 41F0 stmdb       sp!, {r4-r8, lr}
  00485A26: 466E      mov         r6, sp
  00485A28: 0934      lsrs        r4, r6, #4
  00485A2A: 0124      lsls        r4, r4, #4
  00485A2C: 46A5      mov         sp, r4
  00485A2E: F2AD 2D90 subw        sp, sp, #0x290
Epilogue:
  00485BAC: 46B5      mov         sp, r6
  00485BAE: E8BD 41F0 ldm         sp!, {r4-r8, lr}
  00485BB2: B004      add         sp, sp, #0x10
  00485BB4: 4770      bx          lr
  ...
  00485E2A: F7FF BE7D b           #0x485B28    ; end of function
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start RVA* = 0x00085a20 (= 0x00485a20-0x00400000)

- Word 1

   - *Flag* = 0, gibt an, dass ein. XData-Datensatz vorhanden ist (aufgrund mehrerer Epiloge erforderlich)

   - *. XData-Adresse* -0x00400000

.xdata (variabel, 3 Worte):

- Word 0

   - *Funktions Länge* = 0x0001a3 (= 0x000346/2)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 0, gibt keine Ausnahme Daten an

   - *E* = 0, gibt eine Liste von epilogbereichen an

   - *F* = 0, gibt eine vollständige Funktionsbeschreibung an, einschließlich Prolog

   - *Epilogcount* = 0x001, gibt den gesamten epilogbereich an.

   - *Code Wörter* = 0x01, was 1 32-Bit-Wort von Entladungs Codes angibt

- Word 1: epilogscope bei Offset 0xc6 (= 0x18c/2), Start des Entladungs Codes bei 0x00 und mit der Bedingung 0x0E (immer)

- Entladungs Codes, beginnend bei Wort 2: (Shared between Prolog/Epilog)

   - Entladungscode 0 = 0xC6: sp = r6

   - Entladungscode 1 = 0xDC: pop {r4-r8, lr}

   - Entladungs Code 2 = 0x04: SP + = (4 < < 2)

   - Entladungscode 3 = 0xFD: Ende, zählt als 16-Bit-Anweisung für Epilog

### <a name="example-6-function-with-exception-handler"></a>Beispiel 6: Funktion mit Ausnahme Handler

```asm
Prologue:
  00488C1C: 0059 A7ED dc.w  0x0059A7ED
  00488C20: 005A 8ED0 dc.w  0x005A8ED0
FunctionStart:
  00488C24: B590      push        {r4, r7, lr}
  00488C26: B085      sub         sp, sp, #0x14
  00488C28: 466F      mov         r7, sp
Epilogue:
  00488C6C: 46BD      mov         sp, r7
  00488C6E: B005      add         sp, sp, #0x14
  00488C70: BD90      pop         {r4, r7, pc}
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start RVA* = 0x00088c24 (= 0x00488c24-0x00400000)

- Word 1

   - *Flag* = 0, gibt an, dass ein. XData-Datensatz vorhanden ist (aufgrund mehrerer Epiloge erforderlich)

   - *. XData-Adresse* -0x00400000

.xdata (variabel, 5 Worte):

- Word 0

   - *Funktions Länge* = 0x000027 (= 0x00004e/2)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 1, gibt die vorhandenen Ausnahme Daten an

   - *E* = 1, gibt einen einzelnen Epilog an

   - *F* = 0, gibt eine vollständige Funktionsbeschreibung an, einschließlich Prolog

   - *Epilogcount* = 0x00, gibt an, dass Epilog-Entlade Codes bei Offset 0x00 beginnen.

   - *Code Wörter* = 0x02, das 2 32-Bit-Wörter der Entladungs Codes angibt

- Entladungscodes, beginnend bei Wort 1:

   - Entladungscode 0 = 0xC7: sp = r7

   - Entladungs Code 1 = 0x05: SP + = (5 < < 2)

   - Entladungscode 2 = 0xED/0x90: pop {r4, r7, lr}

   - Entladungscode 4 = 0xFF: end

- Word 3 gibt einen Ausnahmehandler an = 0x0019a7ed (= 0x0059a7ed-0x00400000).

- Worte 4 und darüber hinaus sind inline gesetzte Ausnahmedaten

### <a name="example-7-funclet"></a>Beispiel 7: funclet

```asm
Function:
  00488C72: B500      push        {lr}
  00488C74: B081      sub         sp, sp, #4
  00488C76: 3F20      subs        r7, #0x20
  00488C78: F117 0308 adds        r3, r7, #8
  00488C7C: 1D3A      adds        r2, r7, #4
  00488C7E: 1C39      adds        r1, r7, #0
  00488C80: F7FF FFAC bl          target
  00488C84: B001      add         sp, sp, #4
  00488C86: BD00      pop         {pc}
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktions Start-RVA* = 0x00088c72 (= 0x00488c72-0x00400000)

- Word 1

   - *Flag* = 1, das kanonische Prolog-und epilogformate angibt

   - *Funktions Länge* = 0x0B (= 0x16/2)

   - *Ret* = 0, gibt eine Pop-{PC}-Rückgabe an

   - *H* = 0, gibt an, dass die Parameter nicht in den vernetzt

   - *R*= 0 und *reg* = 7, gibt an, dass keine Register gespeichert/wieder hergestellt wurden

   - *L* = 1, gibt an, dass LR gespeichert/wieder hergestellt wurde

   - *C* = 0, gibt an, dass keine Frame Verkettung

   - *Stapel* Anpassung = 1, was eine 1 × 4-Byte-Stapel Anpassung angibt

## <a name="see-also"></a>Siehe auch

[Übersicht über ARM-ABI-Konventionen](overview-of-arm-abi-conventions.md)<br/>
[Häufig auftretende ARM-Migrationsprobleme bei Visual C++](common-visual-cpp-arm-migration-issues.md)
