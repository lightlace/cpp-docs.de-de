---
title: ARM-Ausnahmebehandlung
ms.date: 07/11/2018
ms.assetid: fe0e615f-c033-4ad5-97f4-ff96af45b201
ms.openlocfilehash: b2b6b9b3508dd7a4dd42a2e22ad1052851c7c0c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522270"
---
# <a name="arm-exception-handling"></a>ARM-Ausnahmebehandlung

Windows auf ARM verwendet denselben strukturierten Mechanismus für die Ausnahmebehandlung bei asynchronen – von der Hardware generierten – und synchronen – von der Software generierten – Ausnahmen. Sprachspezifische Ausnahmehandler werden auf von Windows strukturierter Ausnahmebehandlung mithilfe von Sprachhilfsfunktionen erstellt. Dieses Dokument beschreibt die Behandlung von Ausnahmen in Windows auf ARM und die sprachhilfen, die von Code, der von der Microsoft-ARM-Assembler- und Visual C++-Compiler generiert wird verwendet.

## <a name="arm-exception-handling"></a>ARM-Ausnahmebehandlung

Windows auf ARM verwendet *entladungscodes* zur Steuerung der stapelentladung während der [strukturierte Ausnahmebehandlung](https://msdn.microsoft.com/library/windows/desktop/ms680657) (SEH). Entladungscodes sind eine Folge von Bytes, die im „.xdata“-Abschnitt des ausführbaren Images gespeichert sind. Sie beschreiben den Betrieb von Funktionseinleitungs- und -epilogcode auf abstrakte Weise, sodass die Wirkung eines Funktionsprologs sich als Vorbereitung auf die Entladung des Stapelrahmens des Aufrufers rückgängig machen lässt.

Das ARM EABI (Embedded Application Binary Interface) legt ein Ausnahmeentladungsmodell fest, das Entladungscodes verwendet, aber für SEH-Entladung in Windows nicht ausreichend ist. Denn hier müssen asynchrone Fälle gehandhabt werden, in denen der Prozessor inmitten des Prologs oder Epilogs einer Funktion ist. Windows teilt außerdem die Entladungssteuerung in Entladung auf Funktionsebene und für den sprachspezifischen Bereich auf, was in der ARM EABI nicht definiert ist. Deshalb legt Windows auf ARM mehr Details für die Entladung von Daten und Verfahren fest.

### <a name="assumptions"></a>Annahmen

Ausführbare Images für Windows auf ARM verwenden das portierbare ausführbare Format (Portable Executable, PE). Weitere Informationen finden Sie unter [Microsoft PE- und COFF-Spezifikation](http://go.microsoft.com/fwlink/p/?linkid=84140). Ausnahmebehandlungsinformationen werden in den Abschnitten .pdata und .xdata des Bilds gespeichert.

Der Ausnahmebehandlungsmechanismus geht von bestimmten Annahmen über den Code aus, der ABI für Windows auf ARM folgt:

- Wenn eine Ausnahme im Funktionstext auftritt, ist es egal, ob die Vorgänge des Prologs rückgängig gemacht werden oder ob die Vorgänge des Epilogs auf eine nach vorn gerichtete Weise durchgeführt werden. Beides sollte zum gleichen Ergebnis führen.

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
|0|0-31|*Funktion RVA starten* ist die 32-Bit-RVA des Starts der Funktion. Wenn die Funktion Thumb-Code enthält, muss der niedrigste Bitwert dieser Adresse festgelegt werden.|
|1|0-1|*Flag* ist ein 2-Bit-Feld, wie Sie die verbleibenden 30 Bit des zweiten .pdata-Worts zu interpretieren angibt. Wenn *Flag* 0 ist, dann bilden die verbleibenden bits eine *Ausnahme Informationen RVA* (mit der die beiden niedrigsten Bitwerte implizit 0). Wenn *Flag* ungleich NULL ist, ist, dann bilden die verbleibenden bits eine *gepackte Entladedaten Daten* Struktur.|
|1|2-31|*Informationen zur Ausnahme RVA* oder *gepackte Entladedaten*.<br /><br /> *Ausnahme Informationen RVA* ist die Adresse der variabler Länge, die Struktur für Ausnahmeinformationen, im Abschnitt .xdata gespeichert. Diese Daten müssen 4-Bytes ausgerichtet sein.<br /><br /> *Gepackte Entladedaten Daten* ist eine komprimierte Beschreibung der Vorgänge zum Entladen von einer Funktion, wenn eine kanonische Form erforderlich. In diesem Fall ist kein .xdata-Datensatz erforderlich.|

### <a name="packed-unwind-data"></a>Gepackte Entladedaten

Bei Funktionen, deren Prolog und Epilog der unten beschriebenen kanonischen Form entsprechen, können gepackte Entladedaten verwendet werden. Damit wird kein .xdata-Datensatz benötigt und der erforderliche Platz für die Entladung der Daten deutlich reduziert. Die kanonischen Prologe und Epiloge wurden entwickelt, sodass sie den allgemeinen Anforderung einer einfachen Funktion entsprechen, die keinen Ausnahmehandler erfordert und ihre Setup- und Teardownvorgänge in der standardmäßigen Reihenfolge durchführt.

Diese Tabelle zeigt das Format eines .pdata-Datensatzes, der Entladedaten gepackt hat:

|Wortoffset|Bits|Zweck|
|-----------------|----------|-------------|
|0|0-31|*Funktion RVA starten* ist die 32-Bit-RVA des Starts der Funktion. Wenn die Funktion Thumb-Code enthält, muss der niedrigste Bitwert dieser Adresse festgelegt werden.|
|1|0-1|*Flag* ist ein 2-Bit-Feld, das folgende Bedeutungen hat:<br /><br />-00 = gepackte Entladedaten nicht verwendet. Verbleibende Bits zeigen auf .xdata-Datensatz.<br />– 01 = gepackte Entladedaten.<br />– 10 = gepackte Entladedaten, in dem die Funktion wird davon ausgegangen, dass keinen Prolog haben. Das ist nützlich beim Beschreiben von Funktionsfragmenten, die nicht mit dem Start der Funktion verbunden sind.<br />– 11 = reserviert.|
|1|2-12|*Länge-Funktion* ist ein 11-Bit-Feld, das die Länge der gesamten Funktion in Bytes geteilt durch 2 enthält. Wenn die Funktion größer als 4 KB ist, muss stattdessen ein voller .xdata-Datensatz verwendet werden.|
|1|13-14|*Ret* ist ein 2-Bit-Feld, der angibt, wie die Funktion zurückgibt:<br /><br />-00 = Rückgabe über Pop {pc} (die *L* flagbit muss in diesem Fall auf 1 festgelegt werden).<br />– 01 = gibt mithilfe einer 16-Bit-Verzweigung.<br />– 10 = gibt mithilfe einer 32-Bit-Verzweigung.<br />– 11 = Sie gar kein Epilog. Das ist nützlich, wenn ein nicht verbundenes Funktionsfragment beschrieben werden soll, das nur aus ein Prolog bestehen kann, aber dessen Epilog sich anderswo befindet.|
|1|15|*H* ist ein 1-Bit-Flag, das angibt, ob die Funktion "die herausgreift" (r0-r3) registriert, indem sie am Anfang der Funktion zu übertragen, und die 16 Bytes des Stapel vor der Rückgabe freigibt. (0 = greift die Register nicht heraus, 1 = Greift Register heraus.)|
|1|16-18|*Reg* ein 3-Bit-Feld, das der Index des letzten gibt nicht flüchtigen Register gespeichert. Wenn die *R* Bit 0, dann werden nur die Ganzzahlregister gespeichert werden, und wird angenommen, dass im Bereich r4-rn, wobei N gleich 4 ist + *Reg*. Wenn die *R* Bit 1 ist, dann werden nur die Gleitkommaregister gespeichert werden, und wird angenommen, dass im Bereich d8-dN befinden, wobei N gleich 8 + *Reg*. Die spezielle Kombination von *R* = 1 und *Reg* = 7 gibt an, dass keine Register gespeichert werden.|
|1|19|*R* ist ein 1-Bit-Flag, der angibt, ob die gespeicherten nicht flüchtigen Register Ganzzahlregister (0) oder Gleitkommaregister (1). Wenn *R* auf 1 festgelegt ist und die *Reg* Feld auf 7 festgelegt ist, wird keine nicht flüchtigen Register per Push abgelegt.|
|1|20|*L* ist ein 1-Bit-Flag, das angibt, ob die Funktion speichert und LR, zusammen mit anderen Registern Wiederherstellung der *Reg* Feld. (0 = speichert nicht/stellt nicht wieder her, 1 = speichert/stellt wieder her.)|
|1|21|*C* ist ein 1-Bit-Flag, das angibt, ob die Funktion zusätzliche Anweisungen zum Einrichten einer rahmenkette für schnelles Stack walking (1), oder nicht (0) enthält. Wen das Bit festgelegt wurde, wird r11 implizit in der Liste nicht flüchtiger Ganzzahlregister gespeichert. (Finden Sie unter Einschränkungen unten für den Fall der *C* Flag verwendet wird.)|
|1|22-31|*Passen Sie Stack* ist ein 10-Bit-Feld, das die Anzahl der Bytes vom Stapel gibt an, die für diese Funktion, geteilt durch 4 zugeordnet sind. Es lassen sich allerdings nur Werte zwischen 0x000 und 0x3F3 direkt codieren. Funktionen, die über 4044 Bytes an Stapel zuzuordnen, müssen einen vollständigen .xdata-Datensatz verwenden. Wenn die *Stack anpassen* Feld 0x3f4 oder größer ist, und klicken Sie dann die niedrigste 4 Bits eine besondere Bedeutung haben:<br /><br />-Bits 0-1-geben die Anzahl der Worte der stapelanpassung (1-4) minus 1.<br />-Bit-2 wird auf 1 festgelegt, wenn der Prolog diese Anpassung in seinen pushübertagungsvorgang kombiniert.<br />-Bit-3 wird auf 1 festgelegt, wenn der Epilog diese Anpassung in seinen popvorgang kombiniert.|

Wegen möglicher Redundanzen in den oben genannten Codierungen gelten folgende Einschränkungen:

- Wenn die *C* Flag auf 1 festgelegt ist:

   - Die *L* Flag muss ebenfalls auf 1 festgelegt werden, da rahmenverknüpfung sowohl r11 und LR erforderlich.

   - R11 darf nicht enthalten sein, in der Menge der Register beschriebenen *Reg*. Das heißt, wenn r4-r11 per Push übertragen werden, *Reg* sollte nur r4-r10 beschreiben, da die *C* Flag impliziert r11.

- Wenn die *Ret* Feld ist auf 0 (null) festgelegt die *L* Flag auf 1 festgelegt werden muss.

Werden diese Einschränkungen übergangen, kann dies eine nicht unterstützte Sequenz hervorrufen.

Für Rahmen die erläuterungen unten werden zwei pseudoflags von abgeleitet *Stack anpassen*:

- *PF* oder "Prologue folding" zeigt an, dass *Stack anpassen* 0x3f4 oder größer ist und Bit 2 festgelegt ist.

- *EF* oder "Epilogue folding" zeigt an, dass *Stack anpassen* 0x3f4 oder größer ist und Bit 3 festgelegt ist.

Prologe für nicht kanonische Funktionen können bis zu 5 Anweisungen haben (beachten Sie, dass 3a und 3b sich gegenseitig ausschließen):

|Anweisung|Es wird davon ausgegangen, dass Opcode vorhanden ist, wenn:|Größe|Opcode|Entladungscodes|
|-----------------|-----------------------------------|----------|------------|------------------|
|1|*H*== 1|16|`push {r0-r3}`|04|
|2|*C*== 1 oder *L*== 1 oder *R*== 0 oder PF == 1|16/32|`push {registers}`|80-BF/D0-DF/EC-ED|
|3a|*C*== 1 und (*L*== 0 und *R*== 1 und PF == 0)|16|`mov r11,sp`|C0-CF/FB|
|3b|*C*== 1 und (*L*== 1 oder *R*== 0 oder PF == 1)|32|`add r11,sp,#xx`|FC|
|4|*R*== 1 und *Reg* ! = 7|32|`vpush {d8-dE}`|E0-E7|
|5|*Anpassen von Stack* ! = 0 und PF == 0|16/32|`sub sp,sp,#xx`|00-7F/E8-EB|

Anweisung 1 wird immer angezeigt, wenn die *H* Bit auf 1 festgelegt ist.

Um die rahmenverknüpfung festzulegen, entweder Anweisung 3a oder 3 b vorhanden ist wenn die *C* Bit festgelegt ist. Es ist ein 16-Bit-`mov`, wenn kein Register außer r11 und LR per Push abgelegt wird; ansonsten ist es ein 32-Bit-`add`.

Wird eine nicht gefaltete Anpassung festgelegt, ist Anweisung die ausdrückliche Stapelanpassung.

Die Anweisungen 2 und 4 werden abhängig davon festgelegt, ob eine Pushübertagung erforderlich ist. Diese Tabelle wird zusammengefasst, welche Register basierend auf gespeichert wurden die *C*, *L*, *R*, und *PF* Felder. In allen Fällen *N* gleich *Reg* + 4, *E* gleich *Reg* + 8 und *S* ist gleich (~*Stack anpassen*) und 3.

|C|L|R|PF|Ganzzahlregister per Push abgelegt|VFP-Register per Push abgelegt|
|-------|-------|-------|--------|------------------------------|--------------------------|
|0|0|0|0|R4-R*N*|Keine|
|0|0|0|1|R*S*- R*N*|Keine|
|0|0|1|0|Keine|D8-d*E*|
|0|0|1|1|R*S*-r3|D8-d*E*|
|0|1|0|0|R4-R*N*, LR|Keine|
|0|1|0|1|R*S*- R*N*, LR|Keine|
|0|1|1|0|LR|D8-d*E*|
|0|1|1|1|R*S*-r3, LR|D8-d*E*|
|1|0|0|0|R4-R*N*, r11|Keine|
|1|0|0|1|R*S*- R*N*, r11|Keine|
|1|0|1|0|r11|D8-d*E*|
|1|0|1|1|R*S*-r3 r11|D8-d*E*|
|1|1|0|0|R4-R*N*, r11, LR|Keine|
|1|1|0|1|R*S*- R*N*, r11, LR|Keine|
|1|1|1|0|r11, LR|D8-d*E*|
|1|1|1|1|R*S*-r3, r11, LR|D8-d*E*|

Die Epiloge für kanonische Funktionen ermöglichen es, einer ähnlichen Form zu folgen, doch rückwärts und mit ein paar zusätzlichen Optionen. Der Epiloge kann bis zu 5 Anweisungen lang sein und seine Form wird streng durch das Format des Prologs diktiert.

|Anweisung|Es wird davon ausgegangen, dass Opcode vorhanden ist, wenn:|Größe|Opcode|
|-----------------|-----------------------------------|----------|------------|
|6|*Anpassen von Stack*! = 0 und *EF*== 0|16/32|`add   sp,sp,#xx`|
|7|*R*== 1 und *Reg*! = 7|32|`vpop  {d8-dE}`|
|8|*C*== 1 oder (*L*== 1 und *H*== 0) oder *R*== 0 oder *EF*== 1|16/32|`pop   {registers}`|
|9a|*H*== 1 und *L*== 0|16|`add   sp,sp,#0x10`|
|9b|*H*== 1 und *L*== 1|32|`ldr   pc,[sp],#0x14`|
|10a|*Ret*== 1|16|`bx    reg`|
|10b|*Ret*== 2|32|`b     address`|

Anweisung 6 ist die ausdrückliche Stapelanpassung, wenn eine nicht gefaltete Anpassung festgelegt wurde. Da *PF* ist unabhängig von *EF*, es ist möglich, dass Anweisung 5 ohne 6 vorhanden, oder umgekehrt.

Anweisungen 7 und 8 verwenden dieselbe Logik wie des Prologs um zu bestimmen, welche Register aus dem Stapel wiederhergestellt werden, jedoch mit diesen beiden folgenden Änderungen: Erstens *EF* dient anstelle von *PF*; Zweitens, wenn *Ret*  = 0, dann LR durch PC in der Registerliste ersetzt und der Epilog sofort endet.

Wenn *H* festgelegt ist, und klicken Sie dann entweder Anweisung 9a oder 9 b vorhanden ist. Anweisung 9a wird verwendet, wenn *L* ist 0, um anzugeben, dass sich LR nicht auf dem Stapel befindet. In diesem Fall wird der Stapel manuell angepasst und *Ret* muss 1 oder 2, um eine explizite Rückgabe festgelegt sein. Anweisung 9 b wird verwendet, wenn *L* ist 1, um ein frühes Ende des Epilogs anzuzeigen und um zurückzugeben, und passen Sie den Stapel zur gleichen Zeit.

Wenn der Epilog hat nicht bereits beendet wurde, dann ist entweder Anweisung 10a oder 10 b vorhanden ist, an einen 16-Bit- oder 32-Bit-Branch, basierend auf dem Wert des *Ret*.

### <a name="xdata-records"></a>.xdata-Datensätze

Wenn das gepackte Entladeformat nicht zur Beschreibung der Entladung einer Funktion ausreicht, muss ein .xdata-Datensatz mit variabler Länge erstellt werden. Die Adresse dieses Datensatzes wird im zweiten Wort des .pdata-Datensatzes gespeichert. Das Format von .xdata ist ein gepackter Satz an Worten mit variabler Länge, der vier Abschnitte hat:

1. Ein 1- oder 2-Wort-Header, der die Gesamtgröße der .xdata-Struktur beschreibt und wichtige Funktionsdaten enthält. Das zweite Worte ist nur vorhanden, wenn die *Epiloganzahl* und *Code Wörter* Felder sind beide auf 0 festgelegt. Die Felder sind in dieser Tabelle aufgeteilt:

   |Word|Bits|Zweck|
   |----------|----------|-------------|
   |0|0-17|*Länge-Funktion* ist ein 18-Bit-Feld, der die Gesamtlänge der Funktion in Bytes geteilt durch 2 angibt. Wenn eine Funktion größer als 512 KB ist, dann müssen mehrere .pdata- und .xdata-Datensätze verwendet werden, um die Funktion zu beschreiben. Weitere Informationen finden Sie im Abschnitt "Große Funktionen" in diesem Dokument.|
   |0|18-19|*Vers* ist ein 2-Bit-Feld, das die Version der verbleibenden Xdata beschreibt. Nur Version 0 ist derzeit definiert; die Werte 1-3 sind reserviert.|
   |0|20|*X* ist ein 1-Bit-Feld, das Vorhandensein (1) oder fehlen (0) von Ausnahmedaten angibt.|
   |0|21|*E* ist ein 1-Bit-Feld, der angibt, dass die Informationen, die ein einzelner Epilog in den Header (1) verpackt wird damit nicht muss der zusätzliche Bereich Wörter höher (0).|
   |0|22|*F* ist ein 1-Bit-Feld, der angibt, dass dieser Datensatz ein funktionsfragment (1) oder eine vollständige Funktion (0) beschreibt. Ein Fragment impliziert, dass es keinen Prolog gibt und dass sämtliche Prologverarbeitung ignoriert werden soll.|
   |0|23-27|*Epiloganzahl* ist ein 5-Bit-Feld mit zwei Bedeutungen, abhängig vom Zustand der *E* Bit:<br /><br /> -If *E* gleich 0 ist, ist dieses Feld die Anzahl der Gesamtzahl von ausnahmebereichen, die in Abschnitt 3 beschrieben. Wenn mehr als 31 Bereiche in der Funktion, und klicken Sie dann auf dieses Feld vorhanden sind und die *Code Wörter* Feld muss beide werden auf 0 festgelegt, um anzugeben, dass ein ausnahmewort erforderlich ist.<br />-If *E* 1, ist dieses Feld gibt den Index des ersten entladungscodes, die der nur den Epilog beschreibt.|
   |0|28-31|*Code Wörter* ist ein 4-Bit-Feld, der angibt, die Anzahl der 32-Bit-Wörter benötigt, damit alle entladungscodes in Abschnitt 4 enthalten. Wenn mehr als 15 Worte für mehr als 63 entladungscodebytes, dieses Feld erforderlich sind und die *Epiloganzahl* Feld muss beide werden auf 0 festgelegt, um anzugeben, dass ein ausnahmewort erforderlich ist.|
   |1|0-15|*Erweiterte Epiloganzahl* ist ein 16-Bit-Feld, das mehr Speicherplatz für das encoding bietet eine ungewöhnlich große Anzahl von epilogen. Das erweiterungswort, das enthält dieses Feld ist nur vorhanden, wenn die *Epiloganzahl* und *Code Wörter* Felder im ersten headerwort beide auf 0 festgelegt sind.|
   |1|16-23|*Erweiterte Code Wörter* ist eine 8-Bit-Feld, das mehr Speicherplatz für das encoding bietet eine ungewöhnlich große Anzahl von entladungscodeworten. Das erweiterungswort, das enthält dieses Feld ist nur vorhanden, wenn die *Epiloganzahl* und *Code Wörter* Felder im ersten headerwort beide auf 0 festgelegt sind.|
   |1|24-31|Reserviert|

1. Nach den Ausnahmedaten (wenn die *E* -Bit im Header auf 0 festgelegt wurde) wird eine Liste mit Informationen über epilogbereiche, die auf ein Wort gepackt und in der Reihenfolge zunehmender startoffsets gespeichert werden. Jeder Bereich enthält folgende Felder:

   |Bits|Zweck|
   |----------|-------------|
   |0-17|*Epilog starten Offset* ist ein 18-Bit-Feld, das den Offset des Epilogs in Bytes geteilt durch 2, relativ zum Start der Funktion beschreibt.|
   |18-19|*Res* ist ein 2-Bit-Feld, das für zukünftige Erweiterungen reserviert. Sein Wert muss 0 sein.|
   |20-23|*Bedingung* ist ein 4-Bit-Feld, das die Bedingung liefert, unter denen der Epilog ausgeführt wird. Für bedingungslose Epiloge muss es auf 0xE festgelegt sein, was "immer" bedeutet. (Ein Epilog muss vollständig beginnt oder bedingungslos sein und im Thumb-2-Modus beginnt der Epilog mit der ersten Anweisung nach dem IT-Opcode.)|
   |24-31|*StartIndex Epilog* ist eine 8-Bit-Feld, das den Byte-Index des ersten entladungscodes angibt, der diesen Epilog beschreibt.|

1. Nach der Liste von Epilogbereichen kommt ein Array von Bytes, das Entladungscodes enthält. Diese werden detailliert im Abschnitt Entladungscodes dieses Artikels beschrieben. Dieses Array ist am Ende aufgefüllt bis zur nächsten vollen Wortgrenze. Die Bytes werden in Little-Endian-Reihenfolge gespeichert, sodass sie im Little-Endian-Modus direkt abgerufen werden können.

1. Wenn die *X* -Feld im Header 1 ist, folgt den entladungscodebytes die ausnahmehandlerinformationen. Dies besteht aus einem *Ausnahme-Handler RVA* , enthält die Adresse des ausnahmehandlers, unmittelbar gefolgt von der (mit variabler Länge) Datenmenge, die vom Ausnahmehandler erforderlich.

Der Datensatz „.xdata“ ist so gestaltet, dass es möglich ist, die ersten 8 Bytes abzurufen und die volle Größe des Datensatzes zu berechnen, ausgenommen die Länge der folgenden Ausnahmedaten mit variabler Größe. Dieser Codeausschnitt berechnet die Datensatzgröße:

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

Obwohl der Prolog und jeder Epilog einen Index in den Entladungscodes besitzt, teilen sich die beiden die Tabelle. Es ist nicht ungewöhnlich, dass alle denselben Entladungscode teilen. Wir empfehlen, dass Compiler-Autoren für diesen Fall optimieren, denn der größte Index, der festgelegt werden kann, ist 255 und das begrenzt die Gesamtzahl der Entladungscodes, die für eine bestimmte Funktion mögliche sind.

### <a name="unwind-codes"></a>Entladungscodes

Das Array an Entladungscodes ist ein Pool von Anweisungsequenzen, der genau beschreibt, wie die Wirkungen des Prologs rückgängig gemacht werden und in welcher Reihenfolge. Die Entladungscodes sind ein Satz von Minianweisungen, die als eine Zeichenfolge von Bytes codiert wurden. Wenn die Ausführung abgeschlossen ist, befindet sich die Rückgabeadresse im LR-Register und alle nicht flüchtigen Register werden auf ihre Werte zu Beginn des Funktionsaufrufs zurückgesetzt.

Würden Ausnahmen garantiert immer nur innerhalb einer Funktion auftreten und niemals im Prolog oder Epilog, dann wäre nur eine Entladesequenz nötig. Doch das Windows-Entlademodell erfordert die Fähigkeit, von innerhalb eines teilweise ausgeführten Prologs oder Epilogs aus zu entladen. Damit dieser Anforderung Rechnung getragen wird, wurden die Entladungscodes sorgfältig so entwickelt, dass sie eine unzweifelhafte Eins-zu-Eins-Zuordnung zu jedem relevanten Opcode im Prolog und Epilog haben. Das hat eine Reihe von Auswirkungen:

- Es ist möglich, die Länge von Prolog und Epilog zu berechnen, indem man die Anzahl von Entladungscodes zählt. Das ist selbst mit Thumb-2-Anweisungen mit variabler Länge möglich, da es eine eindeutige Zuordnung für 16- und 32-Bit-Opcodes gibt.

- Durch Zählen der Anzahl von Anweisungen nach dem Start eines Epilogbereichs ist es möglich, die gleiche Anzahl von Entladungscodes zu überspringen und den Rest einer Sequenz auszuführen, um die teilweise ausgeführte Entladung abzuschließen, die der Epilog durchgeführt hat.

- Durch Zählen der Anzahl von Anweisungen vor dem Ende eines Prologs ist es möglich, die gleiche Anzahl von Entladungscodes zu überspringen und den Rest einer Sequenz auszuführen, sodass nur die Teile des Prologs rückgängig gemacht werden, die der Prolog durchgeführt hat.

Die folgende Tabelle zeigt die Zuordnung von Entladungscodes zu Opcodes. Die häufigsten Codes sind nur ein Byte, während weniger übliche zwei, drei oder sogar vier Bytes benötigen. Jeder Code wird vom signifikantesten bis zum am wenigsten signifikanten Byte gespeichert. Die Entladungscodestruktur unterscheidet sich von der Entladung, die in ARM EABI beschrieben ist, da diese Entladungscodes mit einer Eins-zu-Eins-Zuordnung zu den Opcodes in Prolog und Epilog entwickelt wurden, was die Entladung teilweise ausgeführter Prologe und Epiloge möglich macht.

|Byte 1|Byte 2|Byte 3|Byte 4|Opsize|Erklärung|
|------------|------------|------------|------------|------------|-----------------|
|00-7F||||16|`add   sp,sp,#X`<br /><br /> wobei X ist (Code & 0x7F) \* 4|
|80-BF|00-FF|||32|`pop   {r0-r12, lr}`<br /><br /> wobei LR per pop ausgelesen wird, wenn Code & 0x2000 und r0-r12 per pop ausgelesen werden, falls das korrespondierende Bit in Code & 0x1FFF festgelegt wurde|
|C0-CF||||16|`mov   sp,rX`<br /><br /> wobei X Code & 0x0F ist|
|D0-D7||||16|`pop   {r4-rX,lr}`<br /><br /> wobei X (Code & 0x03) + 4 ist und LR per pop ausgelesen wird, wenn Code & 0x04|
|D8-DF||||32|`pop   {r4-rX,lr}`<br /><br /> wobei X (Code & 0x03) + 8 ist und LR per pop ausgelesen wird, wenn Code & 0x04|
|E0-E7||||32|`vpop  {d8-dX}`<br /><br /> wobei X (Code & 0x07) + 8 ist|
|E8-EB|00-FF|||32|`addw  sp,sp,#X`<br /><br /> wobei X ist (Code & 0x03FF) \* 4|
|EC-ED|00-FF|||16|`pop   {r0-r7,lr}`<br /><br /> wobei LR per pop ausgelesen wird, wenn Code & 0x0100 und r0-r7 per pop ausgelesen werden, falls das korrespondierende Bit in Code & 0x00FF festgelegt wurde|
|EE|00-0F|||16|Microsoft-spezifisch|
|EE|10-FF|||16|Verfügbar|
|EF|00-0F|||32|`ldr   lr,[sp],#X`<br /><br /> wobei X ist (Code & 0x000F) \* 4|
|EF|10-FF|||32|Verfügbar|
|F0-F4||||-|Verfügbar|
|F5|00-FF|||32|`vpop  {dS-dE}`<br /><br /> wobei S (Code & 0x00F0) >> 4 und E Code & 0x000F ist|
|F6|00-FF|||32|`vpop  {dS-dE}`<br /><br /> wobei S ((Code & 0x00F0) >> 4) + 16 und E (Code & 0x000F) + 16 ist|
|F7|00-FF|00-FF||16|`add   sp,sp,#X`<br /><br /> wobei X ist (Code & 0x00FFFF) \* 4|
|F8|00-FF|00-FF|00-FF|16|`add   sp,sp,#X`<br /><br /> wobei X ist (Code & 0x00FFFFFF) \* 4|
|F9|00-FF|00-FF||32|`add   sp,sp,#X`<br /><br /> wobei X ist (Code & 0x00FFFF) \* 4|
|FA|00-FF|00-FF|00-FF|32|`add   sp,sp,#X`<br /><br /> wobei X ist (Code & 0x00FFFFFF) \* 4|
|FB||||16|nop (16-Bit)|
|FC||||32|nop (32-Bit)|
|FD||||16|end + 16-Bit nop im Epilog|
|FE||||32|end + 32-Bit nop im Epilog|
|FF||||-|end|

Dies zeigt einen Bereich hexadezimaler Werte für jedes Byte in einem entladungscode *Code*, zusammen mit der opcodegröße *Opsize* und die entsprechenden ursprünglichen anweisungsinterpretation. Leere Zellen weisen auf kürzere Entladungscodes hin. Die Anweisungen mit großen Werten umfassen mehrere Bytes, wobei die signifikanten zuerst gespeichert sind. Die *Opsize* Feld zeigt die implizite opcodegröße, die jedem Thumb-2-Vorgang zugeordnet. Die offensichtlichen Doppeleinträge in der Tabelle bei verschiedenen Codierungen werden verwendet, damit zwischen den verschiedenen Opcodegrößen unterschieden werden kann.

Die Entladungscodes wurden entwickelt, sodass das erste Byte des Codes sowohl die Gesamtgröße des Codes in Bytes als auch die Größe des entsprechenden Opcodes im Anweisungsstream verrät. Um die Größe von Prolog oder Epilog berechnen zu können, gehen Sie die Entladungscodes vom Beginn der Sequenz bis zum Ende durch und verwenden eine Nachschlagetabelle oder eine vergleichbare Methode, um zu bestimmen, wie lange der entsprechende Opcode ist.

Die Entladungscodes 0xFD und 0xFE sind gleich dem regulären Endcode 0xFF, machen aber einen zusätzlichen nop-Opcode im Epilogfall aus, entweder 16- oder 32-Bit. Bei Prologen sind die Codes 0xFD, 0xFE und 0xFF genau gleich. Das erklärt die gemeinsamen Epilogenden `bx lr` oder `b <tailcall-target>`, die keine gleichen Prologanweisungen haben. Das erhöht die Möglichkeit, Entladungssequenzen zwischen Prolog und Epilog zu teilen.

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

Neben jedem Opcode befindet sich der entsprechende Entladungscode, der diesen Vorgang beschreibt. Die Sequenz der Entladungscodes für den Prolog ist ein Spiegelbild derjenigen für den Epilog, abgesehen von der letzten Anweisung. Dieser Fall liegt häufig vor und der Grund, weshalb immer davon ausgegangen wird, dass die Entladungscodes für den Prolog in umgekehrter Reihenfolge zur ihrer Ausführung gespeichert werden. Damit erhalten wir einen gemeinsamen Satz von Entladungscodes:

```asm
0xc7, 0xdd, 0x04, 0xfd
```

Der Code 0xFD ist ein Spezialcode für das Ende der Sequenz und bedeutet, dass der Epilog eine 16-Bit-Anweisung länger als der Prolog ist. Damit ist es öfter möglich, Entladungscodes gemeinsam zu nutzen.

Im Beispiel beginnt die Entladung mit dem Epilogfall, wenn beim Ausführen des Funktionstextes zwischen Prolog und Epilog eine Ausnahme auftritt, und zwar bei Offset 0 im Epilogcode. Das entspricht dem Offset 0x140 im Beispiel. Der Entlader führt die volle Entladesequenz aus, da keine Bereinigung vorgenommen wurde. Wenn stattdessen die Ausnahme eine Anweisung nach dem Beginn des Epilogcodes auftritt, kann der Entlader erfolgreich entladen, indem er den ersten Entladungscode überspringt. Erhalten eine 1: 1-Zuordnung von Opcodes und entladungscodes, wenn die Entladung von Anweisung *n* im Epilog der Entlader die ersten überspringen soll *n* entladungscodes.

Die gleiche Logik gilt umgekehrt für den Prolog. Findet die Entladung von Offset 0 im Prolog statt, muss nichts ausgeführt werden. Findet die Entladung von einer Anweisung weiter innen statt, sollte die Entladungssequenz einen Entladungscode vom Ende starten, da Prolog-Entladungscodes in umgekehrter Reihenfolge gespeichert werden. Im Allgemeinen, wenn die Entladung von Anweisung *n* im Prolog entladen soll beginnen *n* entladungscodes vom Ende der Liste der Codes.

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

In ersterem Fall muss nur der Prolog beschrieben werden. Dies kann erfolgen im kompakten .pdata-Formats den Prolog normalerweise beschreiben, und geben eine *Ret* Wert 3, dass kein Epilog vorhanden. Im vollen .xdata-Format kann das erledigt werden, indem man wie üblich die Prologentladungscodes in Index 0 festlegt und eine Epiloganzahl von 0 angibt.

Der zweite Fall ist genauso wie eine normale Funktion. Wenn es nur einen Epilog im Fragment gibt und sich dieser am Ende des Fragments befindet, dann kann ein kompakter .pdata-Datensatz verwendet werden. Andernfalls muss ein vollständiger .xdata-Datensatzes eingesetzt werden. Beachten Sie, dass die für den Epilogstart festgelegten Offsets relativ zum Start des Fragments und nicht dem ursprünglichen Start der Funktion sind.

Der dritte und vierte Fall ist jeweils eine Variante des ersten und zweiten Falls, außer dass kein Prolog enthalten ist. In diesen Situationen wird davon ausgegangen, dass es Code vor dem Start des Epilogs gibt und er wird als Teil des Funktionstexts betrachtet, der normalerweise durch das Rückgängigmachen des Prologeffekts entladen wird. Diese Fälle müssen deshalb mit einem Pseudoprolog codiert werden, der beschreibt, wie im Text entladen wird, aber als 0-Länge bei der Bestimmung behandelt wird, ob beim Start des Fragments eine teilweise Entladung durchgeführt wird. Alternativ lässt sich dieser Pseudoprolog beschreiben, indem dieselben Entladungscodes wie beim Epilog verwendet werden, denn sie führen mutmaßlich gleiche Vorgänge durch.

In der dritten und vierten Fall wird das Vorhandensein eines pseudoprologs angegeben, entweder durch Festlegen der *Flag* Feld die .pdata-Datensatz auf 2 oder durch Festlegen der *F* Flag im .xdata-Header auf 1. In beiden Fällen wird die Überprüfung auf eine teilweise Prologentladung ignoriert und alle Nicht-Epilogentladungen werden als voll betrachtet.

#### <a name="large-functions"></a>Große Funktionen

Fragmente lassen sich für die Beschreibung von Funktionen einsetzen, die größer als das 512 KB-Limit sind, das von den Bit-Feldern im .xdata-Header vorgegeben wird. Um eine sehr große Funktion zu beschreiben, brechen Sie diese einfach in Fragmente herunter, die kleiner als 512 KB sind. Jedes Fragment sollte angepasst sein, sodass es einen Epilog nicht in mehrere Teile aufteilt.

Nur das erste Fragment der Funktion enthält einen Prolog; alle anderen sind mit einer Markierung versehen, wonach sie keinen Prolog enthalten. Je nach Anzahl der Epiloge kann jedes Fragment null oder mehr Epiloge enthalten. Beachten Sie, dass jeder Epilogbereich in einem Fragment dessen Startoffset relativ zum Start des Fragments und nicht dem Start der Funktion festlegt.

Wenn ein Fragment keinen Prolog und Epilog hat, erfordert er dennoch einen eigenen .pdata-Datensatz – möglicherweise auch einen .xdata-Datensatz – für die Beschreibung, wie die Entladung im Text der Funktion stattfindet.

#### <a name="shrink-wrapping"></a>Shrink-Wrapping

Ist ein komplexerer Spezialfall von funktionsfragmenten *Shrink*, eine Technik für das Verschieben von registerspeicherungen vom Start der Funktion, die weiter unten in der Funktion wird für einfache Fälle optimiert, die registerspeicherung nicht erforderlich. Das lässt sich als eine äußere Region beschreiben, die den Stapelspeicher zuweist, aber einen minimalen Registersatz speichert sowie einer inneren Region, die weitere Register speichert und wiederherstellt.

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

Bei Funktionen mit Shrink-Wrapping geht man typischerweise davon aus, dass der Platz für die zusätzlichen Registerspeicherungen im normalen Prolog im Voraus zugewiesen wird und die Registerspeicherungen dann mithilfe von `str` oder `stm` erfolgen statt mit `push`. Damit werden alle Aufruflistenzeigerbearbeitungen im ursprünglichen Prolog der Funktion gehalten.

Die Beispielfunktion mit Shrink-Wrapping muss in drei Regionen aufgeteilt werden, die in den Kommentaren mit A, B und C gekennzeichnet sind. Die erste Region A deckt den Start der Funktion bis zum Ende der zusätzlichen nicht flüchtigen Speicherungen ab. Es muss ein .pdata- oder .xdata-Datensatz konstruiert werden, der beschreibt, dass dieses Fragment einen Prolog und keine Epiloge hat.

Die mittlere B-Region hat einen eigenen .pdata- oder .xdata-Datensatz, der beschreibt, dass ein Fragment weder Prolog noch Epilog hat. Allerdings müssen die Entladungscodes für diese Region immer noch vorhanden sein, denn sie wird als Funktionstext betrachtet. Die Codes müssen einen zusammengesetzten Prolog beschreiben, der sowohl die ursprünglichen Register darstellt, die im Region-A-Prolog gespeichert sind, als auch die zusätzlichen Register, die vor Eintritt in Region B gespeichert wurden, als wären sie von einer Vorgangssequenz produziert worden.

Diese Registerspeicherung für Region B können nicht als "innerer Prolog" betrachtet werden, denn der für Region B beschriebene zusammengesetzte Prolog muss sowohl den Region-A-Prolog als auch die zusätzlichen, gespeicherten Register beschreiben. Würde man Fragment B so beschreiben, als hätte es einen Prolog, dann würden die Entladungscodes auch die Größe dieses Prologs implizieren und es gibt keine Möglichkeit, den zusammengesetzten Prolog so zu beschreiben, dass eine Eins-zu-Eins-Zuordnung mit den Opcodes möglich ist, die nur die zusätzlichen Register speichern.

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

Entscheidend ist hier, dass der Stapel bei jeder Anweisungsgrenze ganz mit den Entladungscodes für die Region übereinstimmt. Findet eine Entladung vor der inneren Pushübertagung in diesem Beispiel statt, wird sie als Teil von Region A betrachtet und nur der Region-A-Prolog wird entladen. Wenn die Entladung nach der inneren pushübertagung auftritt, wird davon ausgegangen, dass der Teil von Region B, die keinen Prolog, aber entladungscodes, die beschreiben, sowohl für die innere pushübertragung als auch für den ursprünglichen Prolog aus Region a ähnliche Logik ist für den inneren Pop enthält.

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

### <a name="example-1-leaf-function-no-locals"></a>Beispiel 1: Blattfunktion, kein lokal

```asm
Prologue:
  004535F8: B430      push        {r4-r5}
Epilogue:
  00453656: BC30      pop         {r4-r5}
  00453658: 4770      bx          lr
```

.pdata (fest, 2 Worte):

- Word 0

   - *Funktionsstarts RVA* = 0x000535F8 (= 0x004535F8-0 x 00400000)

- Word 1

   - *Flag* = 1 ist, der angibt, kanonische Prolog- und Epilog-Formate

   - *Länge-Funktion* 0x31 = (0 x 62/2 =)

   - *Ret* = 1, gibt einen 16-Bit-Branch zurück

   - *H* = 0 (null), der angibt, die Parameter nicht herausgegriffen wurden

   - *R*= 0 und *Reg* = 1 ist, der angibt, Push/Pop von r4-R5 an

   - *L* = 0, gibt kein LR gespeichert/wiederhergestellt

   - *C* = 0, gibt keine rahmenverknüpfung gibt

   - *Passen Sie Stack* = 0, gibt keine stapelanpassungen gibt

### <a name="example-2-nested-function-with-local-allocation"></a>Beispiel 2: Geschachtelte Funktion mit lokaler Zuteilung

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

   - *Funktionsstarts RVA* = 0x000533AC (= 0x004533AC-0 x 00400000)

- Word 1

   - *Flag* = 1 ist, der angibt, kanonische Prolog- und Epilog-Formate

   - *Länge-Funktion* = 0 x 35 (0x6A/2 =)

   - *Ret* = 0, gibt eine POP-{pc} return

   - *H* = 0 (null), der angibt, die Parameter nicht herausgegriffen wurden

   - *R*= 0 und *Reg* = 3, der angibt, Push/Pop von r4-R7 an

   - *L* = 1 ist, der angibt, LR gespeichert/wiederhergestellt wurde

   - *C* = 0, gibt keine rahmenverknüpfung gibt

   - *Anpassen von Stack* = 3 (0x0C/4 =)

### <a name="example-3-nested-variadic-function"></a>Beispiel 3: Geschachtelte Variadic-Funktion

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

   - *Funktionsstarts RVA* = 0x00053988 (= 0x00453988-0 x 00400000)

- Word 1

   - *Flag* = 1 ist, der angibt, kanonische Prolog- und Epilog-Formate

   - *Länge-Funktion* 0x2A = (0 x 54/2 =)

   - *Ret* = 0, gibt eine POP-{pc}-Stil zurückgegeben (in diesem Fall eine Ldr pc, [sp], #, 0 x 14 zurückgeben)

   - *H* = 1 ist, der angibt, die Parameter herausgegriffen wurden

   - *R*= 0 und *Reg* = 2, der angibt, Push/Pop von r4-R6 an

   - *L* = 1 ist, der angibt, LR gespeichert/wiederhergestellt wurde

   - *C* = 0, gibt keine rahmenverknüpfung gibt

   - *Passen Sie Stack* = 0, gibt keine stapelanpassungen gibt

### <a name="example-4-function-with-multiple-epilogues"></a>Beispiel 4: Funktionen mit mehreren epilogen

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

   - *Funktionsstarts RVA* = 0x000592F4 (= 0x004592F4-0 x 00400000)

- Word 1

   - *Flag* = 0 (null), die angibt, .xdata-Datensatz vorhanden (aufgrund mehrerer Epiloge erforderlich)

   - *.XData-Adresse* -0 x 00400000

.xdata (variabel, 6 Worte):

- Word 0

   - *Länge-Funktion* = 0x0001A3 (0x000346/2 =)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 0, gibt keine Ausnahmedaten vorhanden sind

   - *E* = 0, gibt eine Liste von epilogbereichen

   - *F* = 0, gibt eine volle funktionsbeschreibung einschließlich Prolog an

   - *Epiloganzahl* = 0 x 04, der angibt, die insgesamt 4 epilogbereiche

   - *Code Wörter* = 0 x 01, der angibt, eine 32-Bit-Wort mit entladungscodes

- Worte 1-4 beschreiben 4 Epilogbereiche an 4 Stellen. Jeder Bereich besitzt einen gemeinsamen Satz an Entladungscodes, der mit dem Prolog geteilt wird mit einem Offset 0x00; er ist bedingungslos, legt die Bedingung 0x0E (immer) fest.

- Entladungscodes, beginnend bei Wort 5: (gemeinsam von Prolog und Epilog genutzt)

   - Entladungscode 0 = 0x06: sp += (6 << 2)

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

   - *Funktionsstarts RVA* = 0x00085A20 (= 0x00485A20-0 x 00400000)

- Word 1

   - *Flag* = 0 (null), die angibt, .xdata-Datensatz vorhanden (aufgrund mehrerer Epiloge erforderlich)

   - *.XData-Adresse* -0 x 00400000

.xdata (variabel, 3 Worte):

- Word 0

   - *Länge-Funktion* = 0x0001A3 (0x000346/2 =)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 0, gibt keine Ausnahmedaten vorhanden sind

   - *E* = 0, gibt eine Liste von epilogbereichen

   - *F* = 0, gibt eine volle funktionsbeschreibung einschließlich Prolog an

   - *Epiloganzahl* = 0 x 001, der angibt, die insgesamt 1 epilogbereich

   - *Code Wörter* = 0 x 01, der angibt, eine 32-Bit-Wort mit entladungscodes

- Wort 1: Epilogbereich bei einem Offset von 0xC6 (= 0x18C/2), starten entladungscodeindex bei 0 x 00, und klicken Sie mit der Bedingung 0x0E (immer)

- Entladungscodes, beginnend bei Wort 2: (gemeinsam von Prolog und Epilog genutzt)

   - Entladungscode 0 = 0xC6: sp = r6

   - Entladungscode 1 = 0xDC: pop {r4-r8, lr}

   - Entladungscode 2 =0x04: sp += (4 << 2)

   - Entladungscode 3 = 0xFD: Ende, zählt als 16-Bit-Anweisung für Epilog

### <a name="example-6-function-with-exception-handler"></a>Beispiel 6: Funktion mit Ausnahmehandler

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

   - *Funktionsstarts RVA* = 0x00088C24 (= 0x00488C24-0 x 00400000)

- Word 1

   - *Flag* = 0 (null), die angibt, .xdata-Datensatz vorhanden (aufgrund mehrerer Epiloge erforderlich)

   - *.XData-Adresse* -0 x 00400000

.xdata (variabel, 5 Worte):

- Word 0

   - *Länge-Funktion* = 0x000027 (0x00004E/2 =)

   - *Vers* = 0, gibt die erste Version von XData an

   - *X* = 1 ist, der angibt, Ausnahmedaten vorhanden sind

   - *E* = 1, gibt einen einzelnen Epilog an

   - *F* = 0, gibt eine volle funktionsbeschreibung einschließlich Prolog an

   - *Epiloganzahl* = 0 x 00, der angibt, Epilog-entladungscodes beginnen bei Offset 0 x 00

   - *Code Wörter* = 0 x 02, der angibt, der zwei 32-Bit-Worte an entladungscodes

- Entladungscodes, beginnend bei Wort 1:

   - Entladungscode 0 = 0xC7: sp = r7

   - Entladungscode 1 = 0x05: sp += (5 << 2)

   - Entladungscode 2 = 0xED/0x90: pop {r4, r7, lr}

   - Entladungscode 4 = 0xFF: end

- Wort 3 legt einen Ausnahmehandler fest = 0x0019A7ED (= 0x0059A7ED – 0 x 00400000)

- Worte 4 und darüber hinaus sind inline gesetzte Ausnahmedaten

### <a name="example-7-funclet"></a>Beispiel 7: Funclet

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

   - *Funktionsstarts RVA* = 0x00088C72 (= 0x00488C72-0 x 00400000)

- Word 1

   - *Flag* = 1 ist, der angibt, kanonische Prolog- und Epilog-Formate

   - *Länge-Funktion* 0x0B = (0 x 16/2 =)

   - *Ret* = 0, gibt eine POP-{pc} return

   - *H* = 0 (null), der angibt, die Parameter nicht herausgegriffen wurden

   - *R*= 0 und *Reg* = 7, der angibt, der keine Register gespeichert/wiederhergestellt wurden

   - *L* = 1 ist, der angibt, LR gespeichert/wiederhergestellt wurde

   - *C* = 0, gibt keine rahmenverknüpfung gibt

   - *Passen Sie Stack* = 1, gibt eine 1 × 4-Byte-stapelanpassung

## <a name="see-also"></a>Siehe auch

[Übersicht über ARM-ABI-Konventionen](../build/overview-of-arm-abi-conventions.md)<br/>
[Häufig auftretende ARM-Migrationsprobleme bei Visual C++](../build/common-visual-cpp-arm-migration-issues.md)
