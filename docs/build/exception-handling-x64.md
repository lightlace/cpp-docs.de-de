---
title: Ausnahmebehandlung bei x64-Systemen
ms.date: 10/14/2019
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: eff4f1a22512b597b5479dbcaabcc9d5fc93c940
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303200"
---
# <a name="x64-exception-handling"></a>Ausnahmebehandlung bei x64-Systemen

Eine Übersicht über die strukturierte Ausnahmebehandlung C++ und die Behandlung von Codierungs Konventionen und das Verhalten von Ausnahmen in x64. Allgemeine Informationen zur Ausnahmebehandlung finden Sie unter [Ausnahmebehandlung in Visual C++ ](../cpp/exception-handling-in-visual-cpp.md).

## <a name="unwind-data-for-exception-handling-debugger-support"></a>Entladen von Daten für die Ausnahmebehandlung, Debuggerunterstützung

Für die Unterstützung der Ausnahmebehandlung und des Debuggens sind mehrere Datenstrukturen erforderlich.

### <a name="struct-runtime_function"></a>struct RUNTIME_FUNCTION

Die Tabellen basierte Ausnahmebehandlung erfordert einen Tabelleneintrag für alle Funktionen, die Stapel Speicher zuordnen oder eine andere Funktion (z. b. nicht Blatt Funktionen) aufzurufen. Funktionstabellen Einträge haben das folgende Format:

|||
|-|-|
|ULONG|Startadresse der Funktion|
|ULONG|Endadresse der Funktion|
|ULONG|Infoadresse entladen|

Die RUNTIME_FUNCTION-Struktur muss DWORD aufweisen, das im Arbeitsspeicher ausgerichtet ist. Alle Adressen sind Bild relativ, d. h., Sie sind 32-Bit-Offsets von der Startadresse des Bilds, das den Funktionstabellen Eintrag enthält. Diese Einträge werden sortiert und im. pdata-Abschnitt eines das Format PE32 +-Bilds abgelegt. Bei dynamisch generierten Funktionen [JIT-Compiler] muss die Runtime zur Unterstützung dieser Funktionen entweder rtlinstallfunctiontablecallback oder RtlAddFunctionTable verwenden, um diese Informationen für das Betriebssystem bereitzustellen. Andernfalls führt dies zu einer unzuverlässigen Ausnahmebehandlung und zum Debuggen von Prozessen.

### <a name="struct-unwind_info"></a>struct UNWIND_INFO

Die Entladedaten-Informationsstruktur wird verwendet, um die Auswirkungen einer Funktion auf den Stapelzeiger aufzuzeichnen, und wo die nicht flüchtigen Register im Stapel gespeichert werden:

|||
|-|-|
|Ubyte: 3|Version|
|Ubyte: 5|Flags|
|Ubyte|Größe des Prologs|
|Ubyte|Anzahl von Entladungs Codes|
|Ubyte: 4|Frame Register|
|Ubyte: 4|Frame Register Offset (skaliert)|
|Ushort-\* n|Entladungs Code Array|
|variable|Kann entweder vom folgenden Format (1) oder (2) sein.|

(1) Ausnahme Handler

|||
|-|-|
|ULONG|Adresse des Ausnahme Handlers|
|variable|Sprachspezifische Handlerdaten (optional)|

(2) verkettete Entlade Informationen

|||
|-|-|
|ULONG|Startadresse der Funktion|
|ULONG|Endadresse der Funktion|
|ULONG|Infoadresse entladen|

Die UNWIND_INFO-Struktur muss DWORD aufweisen, das im Arbeitsspeicher ausgerichtet ist. Die einzelnen Felder bedeuten Folgendes:

- **Version**

   Versionsnummer der Entladedaten, derzeit 1.

- **Flags**

   Derzeit sind drei Flags definiert:

   |Flag|Beschreibung|
   |-|-|
   |`UNW_FLAG_EHANDLER`| Die Funktion verfügt über einen Ausnahmehandler, der bei der Suche nach Funktionen aufgerufen werden muss, die Ausnahmen untersuchen müssen.|
   |`UNW_FLAG_UHANDLER`| Die Funktion verfügt über einen Beendigungs Handler, der beim Entwickeln einer Ausnahme aufgerufen werden sollte.|
   |`UNW_FLAG_CHAININFO`| Diese Entlade Informationsstruktur ist nicht der primäre Vorgang für die Prozedur. Stattdessen ist der Eintrag der verketteten Entlade Informationen der Inhalt eines vorherigen RUNTIME_FUNCTION Eintrags. Weitere Informationen finden Sie unter [verkettete Entlade Info Strukturen](#chained-unwind-info-structures). Wenn dieses Flag festgelegt ist, müssen die UNW_FLAG_EHANDLER-und UNW_FLAG_UHANDLER Flags gelöscht werden. Außerdem müssen die Felder "Frame Register" und "fester Stapel Zuordnung" die gleichen Werte wie in den primären Entlade Informationen aufweisen.|

- **Größe des Prologs**

   Länge des Funktions Prologs in Bytes.

- **Anzahl von Entladungs Codes**

   Die Anzahl der Slots im Array der Entlade Codes. Einige Entladungs Codes, z. b. UWOP_SAVE_NONVOL, erfordern mehr als einen Slot im Array.

- **Frame Register**

   Wenn ungleich 0 (null) ist, verwendet die Funktion einen Frame Zeiger (FP), und dieses Feld ist die Nummer des nicht flüchtigen Registers, das als Frame Zeiger verwendet wird. dabei wird die gleiche Codierung für das Vorgangs Info-Feld UNWIND_CODE-Knoten verwendet.

- **Frame Register Offset (skaliert)**

   Wenn das Rahmen Register Feld ungleich 0 (null) ist, ist dieses Feld der skalierte Offset von RSP, der bei seiner Einrichtung auf das FP-Register angewendet wird. Das tatsächliche FP-Register wird auf RSP + 16 \* diese Zahl festgelegt, sodass Offsets zwischen 0 und 240 zugelassen werden. Dieser Offset ermöglicht das verweisen auf das FP-Register in der Mitte der lokalen Stapel Zuordnung für dynamische Stapel Rahmen und ermöglicht so eine bessere Code Dichte durch kürzere Anweisungen. (Das heißt, weitere Anweisungen können das 8-Bit-Offset-Formular mit Vorzeichen verwenden.)

- **Entladungs Code Array**

   Ein Array von-Elementen, das die Auswirkung des Prologs auf die nicht flüchtigen Register und RSP erläutert. Informationen zu den Bedeutungen einzelner Elemente finden Sie im Abschnitt UNWIND_CODE. Aus Gründen der Ausrichtung weist dieses Array immer eine gerade Anzahl von Einträgen auf, und der endgültige Eintrag wird möglicherweise nicht verwendet. In diesem Fall ist das Array ein länger als durch das Feld Anzahl der Entlade Codes angegeben.

- **Adresse des Ausnahme Handlers**

   Ein Bild relativer Zeiger auf den sprachspezifischen Ausnahme-oder Beendigungs Handler der Funktion, wenn Flag UNW_FLAG_CHAININFO klar und eines der Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt ist.

- **Sprachspezifische Handlerdaten**

   Die sprachspezifischen Ausnahmehandlerdaten der Funktion. Das Format dieser Daten ist nicht angegeben und wird vollständig durch den bestimmten verwendeten Ausnahmehandler bestimmt.

- **Verkettete Entlade Informationen**

   Wenn Flag UNW_FLAG_CHAININFO festgelegt ist, endet die UNWIND_INFO Struktur mit drei UWORDs.  Diese UWORDs stellen die RUNTIME_FUNCTION Informationen für die Funktion der verketteten Entladung dar.

### <a name="struct-unwind_code"></a>struct UNWIND_CODE

Das Entladungs Code Array wird verwendet, um die Abfolge von Vorgängen im Prolog aufzuzeichnen, die sich auf die nicht flüchtigen Register und RSP auswirken. Jedes Code Element weist das folgende Format auf:

|||
|-|-|
|Ubyte|Offset im Prolog|
|Ubyte: 4|Entladevorgangs Code|
|Ubyte: 4|Vorgangs Informationen|

Das Array wird im Prolog nach absteigender Reihenfolge sortiert.

#### <a name="offset-in-prolog"></a>Offset im Prolog

Offset (ab dem Anfang des Prologs) am Ende der Anweisung, die diesen Vorgang ausführt, plus 1 (d. h. der Offset des Starts der nächsten Anweisung).

#### <a name="unwind-operation-code"></a>Entladevorgangs Code

Hinweis: für bestimmte Vorgangs Codes ist ein Offset ohne Vorzeichen zu einem Wert im lokalen Stapel Rahmen erforderlich. Dieser Offset wird vom Start, d. h. von der niedrigsten Adresse der fixierten Stapel Zuordnung. Wenn das Rahmen Register Feld im UNWIND_INFO NULL ist, wird dieser Offset von RSP abgeleitet. Wenn das Rahmen Register Feld ungleich 0 (null) ist, wird dieser Offset von dem Ort, an dem sich RSP befand, als das FP-Register erstellt wurde. Es ist mit dem FP-Register abzüglich des FP-Register Offsets (16 \* dem skalierten Frame Register Offset im UNWIND_INFO) Gleichheits. Wenn ein FP-Register verwendet wird, muss jeder Entladungs Code, der einen Offset verwendet, erst verwendet werden, nachdem das FP-Register im Prolog erstellt wurde.

Für alle Opcodes mit Ausnahme von `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`ist der Offset immer ein Vielfaches von 8, da alle Stapel Werte, die von Interesse sind, in 8-Byte-Grenzen gespeichert werden (der Stapel selbst ist immer mit 16 Byte ausgerichtet). Bei Vorgangs Codes, die einen kurzen Offset (weniger als 512 KB) benötigen, enthält die abschließende ushort in den Knoten für diesen Code den Offset dividiert durch 8. Bei Vorgangs Codes mit einem langen Offset (512 KB < = Offset < 4 GB) enthalten die letzten beiden ushort-Knoten für diesen Code den Offset (im Little-Endian-Format).

Für die OpCodes `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`ist der Offset immer ein Vielfaches von 16, da alle 128-Bit-XMM-Vorgänge in einem 16-Byte-ausgerichteten Arbeitsspeicher ausgeführt werden müssen. Aus diesem Grund wird ein Skalierungsfaktor von 16 für `UWOP_SAVE_XMM128`verwendet, der Offsets von weniger als 1 Mio. zulässt.

Der Code für den Entladevorgang ist einer der folgenden Werte:

- `UWOP_PUSH_NONVOL` (0) 1 Knoten

  Überträgt ein nicht flüchtiges ganzzahliges Register und dekrementiert RSP um 8. Die Vorgangs Informationen sind die Nummer des Registers. Aufgrund der Einschränkungen für Epilogs müssen `UWOP_PUSH_NONVOL` Entladungs Codes zuerst im Prolog und entsprechend im Entladungs Code Array angezeigt werden. Diese relative Reihenfolge gilt für alle anderen Entladungs Codes außer `UWOP_PUSH_MACHFRAME`.

- `UWOP_ALLOC_LARGE` (1) 2 oder 3 Knoten

  Weisen Sie einen großen Bereich auf dem Stapel zu. Es gibt zwei Formen. Wenn die Vorgangs Informationen gleich 0 sind, wird die Größe der Zuordnung dividiert durch 8 im nächsten Slot aufgezeichnet und ermöglicht eine Zuordnung von bis zu 512 KB-8. Wenn die Vorgangs Informationen dem Wert 1 entsprechen, wird die nicht skalierte Größe der Zuordnung in den nächsten zwei Slots im Little-Endian-Format aufgezeichnet. Dies ermöglicht die Zuordnung von bis zu 4 GB-8.

- `UWOP_ALLOC_SMALL` (2) 1 Knoten

  Zuordnen eines Bereichs mit kleiner Größe auf dem Stapel. Die Größe der Zuordnung ist das Vorgangs Info Feld \* 8 + 8 und ermöglicht die Zuordnung von 8 zu 128 Bytes.

  Der Entlade Code für eine Stapel Zuordnung sollte immer die kürzeste mögliche Codierung verwenden:

  |**Zuordnungs Größe**|**Entladungs Code**|
  |-|-|
  |8 bis 128 Bytes|`UWOP_ALLOC_SMALL`|
  |136 bis 512 KB-8 Bytes|`UWOP_ALLOC_LARGE`, Vorgangs Info = 0|
  |512 KB bis 4G-8 Bytes|`UWOP_ALLOC_LARGE`, Vorgangs Info = 1|

- `UWOP_SET_FPREG` (3) 1 Knoten

  Richten Sie das Frame Zeiger Register ein, indem Sie das Register auf einen Offset des aktuellen RSP festlegen. Der Offset ist gleich dem Feld "Frame Register Offset (skaliert)" in der UNWIND_INFO \* 16 und ermöglicht Offsets zwischen 0 und 240. Durch die Verwendung eines Offsets kann ein Frame Zeiger festgelegt werden, der auf die Mitte der fixierten Stapel Zuordnung zeigt, wodurch die Code Dichte unterstützt wird, indem mehr Zugriffe auf kurze Anweisungs Formulare zugreifen können. Das Feld für den Vorgangs Info ist reserviert und sollte nicht verwendet werden.

- Knoten "`UWOP_SAVE_NONVOL` (4) 2"

  Speichern Sie ein nicht flüchtiges ganzzahliges Register im Stapel mithilfe eines MOV anstelle eines Pushvorgangs. Dieser Code wird hauptsächlich für die Verkleinerung verwendet, bei der ein nicht flüchtiges Register im Stapel an einer Position gespeichert *wird, die*zuvor zugeordnet wurde. Die Vorgangs Informationen sind die Nummer des Registers. Der Stapel Offset mit horizontaler Skalierung wird im nächsten Code Slot für den Entladevorgang aufgezeichnet, wie im obigen Hinweis beschrieben.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 Knoten

  Speichern Sie ein nicht flüchtiges ganzzahliges Register im Stapel mit einem langen Offset, und verwenden Sie dabei einen MOV anstelle eines Pushvorgangs. Dieser Code wird hauptsächlich für die Verkleinerung verwendet, bei der ein nicht flüchtiges Register im Stapel an einer Position gespeichert *wird, die*zuvor zugeordnet wurde. Die Vorgangs Informationen sind die Nummer des Registers. Der Offset des nicht skalierten Stapels wird in den nächsten zwei Code Slots des Entladevorgangs aufgezeichnet, wie im obigen Hinweis beschrieben.

- Knoten "`UWOP_SAVE_XMM128` (8) 2"

  Speichert alle 128 Bits eines nicht flüchtigen XMM-Registers auf dem Stapel. Die Vorgangs Informationen sind die Nummer des Registers. Der Stapel Offset mit horizontaler Skalierung wird im nächsten Slot aufgezeichnet.

- `UWOP_SAVE_XMM128_FAR` (9) 3 Knoten

  Speichern Sie alle 128 Bits eines nicht flüchtigen XMM-Registers auf dem Stapel mit einem langen Offset. Die Vorgangs Informationen sind die Nummer des Registers. Der Offset des nicht skalierten Stapels wird in den nächsten zwei Slots aufgezeichnet.

- `UWOP_PUSH_MACHFRAME` (10) 1 Knoten

  Verschieben eines Computer Rahmens  Dieser Entlade Code wird verwendet, um die Auswirkung eines Hardware Interrupts oder einer Ausnahme aufzuzeichnen. Es gibt zwei Formen. Wenn die Vorgangs Informationen 0 (null) sind, wird einer dieser Frames per Pushvorgang auf dem Stapel abgelegt:

  |||
  |-|-|
  |RSP + 32|SS|
  |RSP+24|Alte RSP|
  |RSP + 16|EFLAGS|
  |RSP+8|CS|
  |RSP|RIP|

  Wenn die Vorgangs Informationen 1 entsprechen, wird einer dieser Frames per Pushvorgang übermittelt:

  |||
  |-|-|
  |RSP + 40|SS|
  |RSP + 32|Alte RSP|
  |RSP+24|EFLAGS|
  |RSP + 16|CS|
  |RSP+8|RIP|
  |RSP|Fehlercode|

  Dieser Entladungs Code wird immer in einem Dummy-Prolog angezeigt, der nie tatsächlich ausgeführt wird, sondern vor dem echten Einstiegspunkt einer interruptaktion angezeigt wird und nur vorhanden ist, um den Push eines Computer Rahmens zu simulieren. `UWOP_PUSH_MACHFRAME` zeichnet diese Simulation auf, was darauf hinweist, dass der Computer diesen Vorgang konzeptionell ausgeführt hat:

  1. Pop-RIP-Rückgabeadresse von Anfang des Stapels in *Temp*
  
  1. Pushen

  1. Alte RSP pushen

  1. Push-EFLAGS

  1. Push-CS

  1. *Pushtemp*

  1. Pushfehlercode (wenn die OP-Informationen 1 entsprechen)

  Der simulierte `UWOP_PUSH_MACHFRAME` Vorgang Dekremente RSP um 40 (op-Informationen sind 0) oder 48 (op-Informationen sind 1).

#### <a name="operation-info"></a>Vorgangs Informationen

Die Bedeutung der Vorgangs Info Bits hängt vom Vorgangs Code ab. Diese Zuordnung wird verwendet, um ein allgemeines (ganzzahliges) Register zu codieren:

|||
|-|-|
|0|RAX|
|1|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSI|
|7|RDI|
|8 bis 15|R8 zu R15|

### <a name="chained-unwind-info-structures"></a>Verkettete Entlade Info Strukturen

Wenn das UNW_FLAG_CHAININFO-Flag festgelegt ist, ist eine Entlade Informationsstruktur eine sekundäre Struktur, und das Feld Shared Exception-Handler/verkettete info enthält die primären Entlade Informationen. Dieser Beispielcode ruft die primären Entlade Informationen ab, wobei angenommen wird, dass `unwindInfo` die Struktur ist, für die das UNW_FLAG_CHAININFO-Flag festgelegt ist.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Verkettete Informationen sind in zwei Situationen nützlich. Zuerst kann Sie für nicht zusammenhängende Code Segmente verwendet werden. Durch die Verwendung von verketteten Informationen können Sie die Größe der erforderlichen Entlade Informationen reduzieren, da Sie das Array von Entladungs Codes nicht aus den primären Entlade Informationen duplizieren müssen.

Sie können auch verkettete Informationen verwenden, um flüchtige Registrierungs Speicherungen zu gruppieren. Der Compiler kann die Speicherung einiger flüchtiger Register verzögern, bis er sich außerhalb des Funktions Eintrags Prologs befindet. Sie können diese Einträge aufzeichnen, indem Sie vor dem gruppierten Code primäre Entlade Informationen für den Teil der Funktion angeben und dann verkettete Informationen mit einer Größe von Prolog angeben, die nicht NULL ist, wobei die Entladungs Codes in den verketteten Informationen die Speicherung der nicht flüchtigen Register widerspiegeln. In diesem Fall sind die Entladungs Codes alle Instanzen von UWOP_SAVE_NONVOL. Eine Gruppierung, die nicht flüchtige Register mithilfe eines Push-Vorgangs speichert oder das RSP-Register mithilfe einer zusätzlichen, festgelegten Stapel Zuordnung ändert, wird nicht unterstützt.

Ein UNWIND_INFO Element, das über UNW_FLAG_CHAININFO Menge verfügt, kann einen RUNTIME_FUNCTION Eintrag enthalten, dessen UNWIND_INFO Element auch UNW_FLAG_CHAININFO festgelegt hat, manchmal auch als *mehrfache*Verkleinerung bezeichnet. Schließlich werden die verketteten Entlade Informations Zeiger bei einem UNWIND_INFO Element eintreffen, das UNW_FLAG_CHAININFO gelöscht wurde. Bei diesem Element handelt es sich um das primäre UNWIND_INFO Element, das auf den eigentlichen Prozedur Einstiegspunkt zeigt.

## <a name="unwind-procedure"></a>Entlade Prozedur

Das Entladungs Code Array wird in absteigender Reihenfolge sortiert. Wenn eine Ausnahme auftritt, wird der gesamte Kontext vom Betriebssystem in einem Kontext Daten Satz gespeichert. Anschließend wird die Ausnahme Dispatchlogik aufgerufen, die wiederholt diese Schritte ausführt, um einen Ausnahmehandler zu finden:

1. Verwenden Sie den aktuellen RIP, der im Kontext Daten Satz gespeichert ist, um nach einem RUNTIME_FUNCTION Tabelleneintrag zu suchen, der die aktuelle Funktion (oder den Funktionsteil für verkettete UNWIND_INFO Einträge) beschreibt.

1. Wenn kein Funktionstabellen Eintrag gefunden wird, befindet er sich in einer Blatt Funktion, und RSP adressiert direkt den Rückgabe Zeiger. Der Rückgabe Zeiger bei [RSP] wird im aktualisierten Kontext gespeichert. der simulierte RSP wird um 8 erhöht, und Schritt 1 wird wiederholt.

1. Wenn ein Funktionstabellen Eintrag gefunden wird, kann RIP innerhalb von drei Regionen liegen: a) in einem Epilog, b) im Prolog oder c) in Code, der möglicherweise von einem Ausnahmehandler abgedeckt wird.

   - Fall a) Wenn sich der RIP innerhalb eines Epilogcode befindet, verlässt das Steuerelement die Funktion, es kann für diese Funktion keinen Ausnahmehandler geben, der dieser Ausnahme zugeordnet ist, und die Auswirkungen des Epilogcode müssen fortgesetzt werden, um den Kontext der aufrufenden Funktion zu berechnen. Um zu ermitteln, ob sich der RIP in einem Epilog befindet, wird der Codestream von RIP weiter untersucht. Wenn dieser Codestream mit dem nachfolgenden Teil eines legitimen Epilogcode abgeglichen werden kann, befindet er sich in einem Epilogcode, und der verbleibende Teil des epiprotokolls wird simuliert, wobei der Kontext Daten Satz bei der Verarbeitung jeder Anweisung aktualisiert wird. Nach dieser Verarbeitung wird Schritt 1 wiederholt.

   - Fall b) Wenn das RIP innerhalb des Prologs liegt, hat das Steuerelement die Funktion nicht eingegeben, es kann für diese Funktion keinen Ausnahmehandler geben, der dieser Ausnahme zugeordnet ist, und die Auswirkungen des Prologs müssen rückgängig gemacht werden, um den Kontext der aufrufenden Funktion zu berechnen. Der RIP befindet sich innerhalb des Prologs, wenn der Abstand von der Funktion mit dem RIP-Wert kleiner oder gleich der in den Entlade Informationen codierten Prolog-Größe ist. Die Auswirkungen des Prologs werden durch das Durchsuchen des Entladungs Codes-Arrays für den ersten Eintrag mit einem Offset, der kleiner oder gleich dem Offset des RIP von der Funktions Start ist, und das Aufheben der Auswirkung aller verbleibenden Elemente im Entladungs Code Array. Schritt 1 wird dann wiederholt.

   - Fall c) Wenn sich der RIP nicht innerhalb eines Prologs oder Epilogs befindet und die Funktion über einen Ausnahmehandler verfügt (UNW_FLAG_EHANDLER festgelegt ist), wird der sprachspezifische Handler aufgerufen. Der Handler scannt seine Daten und ruft Filterfunktionen entsprechend auf. Der sprachspezifische Handler kann zurückgeben, dass die Ausnahme behandelt wurde oder dass die Suche fortgesetzt werden soll. Außerdem kann eine Entladung direkt initiiert werden.

1. Wenn der sprachspezifische Handler den Status "verarbeitet" zurückgibt, wird die Ausführung mit dem ursprünglichen Kontext Daten Satz fortgesetzt.

1. Wenn kein sprachspezifischer Handler vorhanden ist oder der Handler den Status "Fortsetzen der Suche" zurückgibt, muss der Kontext Daten Satz in den Zustand des Aufrufers entwickelt werden. Dies erfolgt durch die Verarbeitung aller Entladungs Code-Array Elemente, wobei die Auswirkung der einzelnen Elemente auf die einzelnen Elemente entlädt wird. Schritt 1 wird dann wiederholt.

Wenn verkettete Entlade Informationen beteiligt sind, werden diese grundlegenden Schritte trotzdem befolgt. Der einzige Unterschied besteht darin, dass beim Durchlaufen des Entladungs Code Arrays zum Entladen der Effekte eines Prologs, sobald das Ende des Arrays erreicht ist, das Ende des Arrays mit den übergeordneten Entlade Informationen verknüpft ist und das gesamte Entladungs Code Array, das Sie gefunden haben, durchlaufen wird. Diese Verknüpfung wird so lange fortgesetzt, bis eine Entlade Info ohne das UNW_CHAINED_INFO-Flag eingeht. Anschließend wird das Entladungs Code Array durchlaufen.

Der kleinste Satz von Entladungs Daten beträgt 8 Bytes. Dies stellt eine Funktion dar, die nur 128 Bytes des Stapels oder weniger zugeordnet hat und möglicherweise ein nicht flüchtiges Register gespeichert hat. Es ist auch die Größe einer verketteten Entlade Informationsstruktur für einen Prolog der Länge 0 (null) ohne Entladungs Codes.

## <a name="language-specific-handler"></a>Sprachspezifischer Handler

Die relative Adresse des sprachspezifischen Handlers ist in der UNWIND_INFO vorhanden, wenn Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt werden. Wie im vorherigen Abschnitt beschrieben, wird der sprachspezifische Handler als Teil der Suche nach einem Ausnahmehandler oder als Teil einer Entladung aufgerufen. Es verfügt über den folgenden Prototyp:

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** liefert einen Zeiger auf einen Ausnahme Daten Satz, der über die Win64-Standard Definition verfügt.

" **Framesherframe** " ist die Adresse der Basis der Stapel Zuordnung für diese Funktion.

**ContextRecord** verweist auf den Ausnahme Kontext zum Zeitpunkt, zu dem die Ausnahme ausgelöst wurde (im Fall eines Ausnahme Handlers), oder der aktuelle "Entlade Kontext" (im Fall eines Beendigungs Handlers).

**DispatcherContext verweist auf den dispatcherkontext** für diese Funktion. Sie verfügt über folgende Definition:

```cpp
typedef struct _DISPATCHER_CONTEXT {
    ULONG64 ControlPc;
    ULONG64 ImageBase;
    PRUNTIME_FUNCTION FunctionEntry;
    ULONG64 EstablisherFrame;
    ULONG64 TargetIp;
    PCONTEXT ContextRecord;
    PEXCEPTION_ROUTINE LanguageHandler;
    PVOID HandlerData;
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;
```

**ControlPc** ist der Wert von RIP innerhalb dieser Funktion. Dieser Wert ist entweder eine Ausnahme Adresse oder die Adresse, an der das Steuerelement die erstellende Funktion verlassen hat. Der RIP-Wert wird verwendet, um zu bestimmen, ob sich das Steuerelement innerhalb dieser Funktion innerhalb eines geschützten Konstrukts befindet, z. b. ein `__try` Block für `__try`/`__except` oder `__try`/`__finally`.

**Imagebase** ist die Abbild Basis (Lade Adresse) des Moduls, das diese Funktion enthält. es muss den im Funktions Eintrag verwendeten 32-Bit-Offsets und Entladungs Informationen zum Aufzeichnen relativer Adressen hinzugefügt werden.

**FunctionEntry** stellt einen Zeiger auf den RUNTIME_FUNCTION Funktions Eintrag bereit, der die Funktion enthält, und Entladungs Informationen Image-Base relative Adressen für diese Funktion.

" **Framesherframe** " ist die Adresse der Basis der Stapel Zuordnung für diese Funktion.

**TargetIp** Stellt eine optionale Anweisungs Adresse bereit, die die Fortsetzungs Adresse der Entladung angibt. Diese Adresse wird ignoriert, wenn " **framesherframe** " nicht angegeben wird.

**ContextRecord** verweist auf den Ausnahme Kontext, der von dem System Ausnahme-dispatchcode verwendet werden soll.

**LanguageHandler** verweist auf die sprachspezifische Sprachhandlerroutine, die aufgerufen wird.

**HandlerData** verweist auf die sprachspezifischen Handlerdaten für diese Funktion.

## <a name="unwind-helpers-for-masm"></a>Entladehilfen für MASM

Um ordnungsgemäße Assemblyroutinen zu schreiben, gibt es eine Reihe von Pseudo Operationen, die parallel mit den eigentlichen Assemblyanweisungen verwendet werden können, um die entsprechenden pData-und XData-Daten zu erstellen. Außerdem gibt es eine Reihe von Makros, die eine vereinfachte Verwendung der Pseudo Operationen für Ihre am häufigsten verwendeten Verwendungsmöglichkeiten bereitstellen.

### <a name="raw-pseudo-operations"></a>Unformatierte Pseudo Operationen

|Pseudo Vorgang|Beschreibung|
|-|-|
|PROC Frame \[:*ehandler*]|Bewirkt, dass MASM einen Funktionstabellen Eintrag in. pdata generiert und Informationen in. XData für das strukturierte Ausnahme Behandlungs Verhalten einer Funktion entlädt.  Wenn " *ehandler* " vorhanden ist, wird diese Prozedur in ". XData" als sprachspezifischer Handler eingegeben.<br /><br /> Wenn das Frame-Attribut verwendet wird, muss ihm ein gefolgt werden. ENDPROLOG-Direktive.  Wenn es sich bei der Funktion um eine Blatt Funktion handelt (wie in [Funktionstypen](../build/stack-usage.md#function-types)definiert), ist das Frame-Attribut unnötig, ebenso wie der Rest dieser Pseudo Vorgänge.|
|. Pushreg- *Register*|Generiert einen UWOP_PUSH_NONVOL Ladungs Code Eintrag für die angegebene Registernummer unter Verwendung des aktuellen Offsets im Prolog.<br /><br /> Verwenden Sie Sie nur mit nicht flüchtigen ganzzahligen Registern.  Verwenden Sie für Pushvorgänge flüchtiger Register eine. Stattdessen Zuordnung 8|
|. SetFrame- *Register*, *Offset*|Füllt das Rahmen Register Feld und den Offset in den Entlade Informationen mit dem angegebenen Register und Offset aus. Der Offset muss ein Vielfaches von 16 und kleiner oder gleich 240 sein. Diese Direktive generiert außerdem einen UWOP_SET_FPREG Entladungs Code Eintrag für das angegebene Register unter Verwendung des aktuellen prologoffsets.|
|. *Größe* des zugewiesenen Stapels|Generiert eine UWOP_ALLOC_SMALL oder eine UWOP_ALLOC_LARGE mit der angegebenen Größe für den aktuellen Offset im Prolog.<br /><br /> Der *Größen* Operand muss ein Vielfaches von 8 sein.|
|. SAVEREG- *Register*, *Offset*|Generiert entweder einen UWOP_SAVE_NONVOL oder einen UWOP_SAVE_NONVOL_FAR Entladungs Code Eintrag für das angegebene Register und den Offset unter Verwendung des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.<br /><br /> der *Offset* muss positiv und ein Vielfaches von 8 sein. der *Offset* ist relativ zur Basis des Frame-Rahmens der Prozedur, der sich in der Regel in RSP befindet, oder, wenn ein Frame Zeiger verwendet wird, der nicht skalierte Frame Zeiger.|
|. Savexmm128 *Register*, *Offset*|Generiert entweder einen UWOP_SAVE_XMM128 oder einen UWOP_SAVE_XMM128_FAR Entladungs Code Eintrag für das angegebene XMM-Register und den Offset mithilfe des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.<br /><br /> der *Offset* muss positiv und ein Vielfaches von 16 sein.  der *Offset* ist relativ zur Basis des Frame-Rahmens der Prozedur, der sich in der Regel in RSP befindet, oder, wenn ein Frame Zeiger verwendet wird, der nicht skalierte Frame Zeiger.|
|. \[*Code*für PushFrame]|Generiert einen UWOP_PUSH_MACHFRAME Entladungs Code Eintrag. Wenn der optionale *Code* angegeben wird, erhält der Entladungs Code Eintrag einen Modifizierer von 1. Andernfalls ist der-Modifizierer 0.|
|.ENDPROLOG|Signalisiert das Ende der Prolog-Deklarationen.  Muss in den ersten 255 Bytes der-Funktion auftreten.|

Im folgenden finden Sie einen Beispiel Funktions Prolog mit der richtigen Verwendung der meisten Opcodes:

```MASM
sample PROC FRAME
    db      048h; emit a REX prefix, to enable hot-patching
    push rbp
    .pushreg rbp
    sub rsp, 040h
    .allocstack 040h
    lea rbp, [rsp+020h]
    .setframe rbp, 020h
    movdqa [rbp], xmm7
    .savexmm128 xmm7, 020h ;the offset is from the base of the frame
                           ;not the scaled offset of the frame
    mov [rbp+018h], rsi
    .savereg rsi, 038h
    mov [rsp+010h], rdi
    .savereg rdi, 010h ; you can still use RSP as the base of the frame
                       ; or any other register you choose
    .endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn't have a frame pointer, this would be illegal
; if we didn't make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren't saved with a push
; this isn't part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here's the official epilog

    lea rsp, [rbp+020h] ; deallocate both fixed and dynamic portions of the frame
    pop rbp
    ret
sample ENDP
```

Weitere Informationen zum Epilogcode-Beispiel finden Sie unter [Epilogcode-Code](prolog-and-epilog.md#epilog-code) in [x64 Prolog und Epilogcode](prolog-and-epilog.md).

### <a name="masm-macros"></a>MASM-Makros

Um die Verwendung der [unformatierten Pseudo Vorgänge](#raw-pseudo-operations)zu vereinfachen, gibt es eine Reihe von Makros, die in ksamd64. Inc definiert sind. Diese können verwendet werden, um typische Prozedur Prologe und Epiloge zu erstellen.

|Makro|Beschreibung|
|-|-|
|alloc_stack(n)|Ordnet einen Stapel Rahmen von n Bytes (mit `sub rsp, n`) zu und gibt die entsprechenden Entlade Informationen (. zugcstack n) aus.|
|save_reg *reg*, *Loc*|Speichert eine nicht flüchtige Register- *reg* auf dem Stapel bei RSP Offset *Loc*und gibt die entsprechenden Entlade Informationen aus. (. SAVEREG reg, Loc)|
|push_reg *reg*|Überträgt eine nicht flüchtige Register- *reg* auf dem Stapel und gibt die entsprechenden Entlade Informationen aus. (. pushreg reg)|
|rex_push_reg *reg*|Speichert ein nicht flüchtiges Register im Stapel mithilfe eines 2-Byte-Pushvorgangs und gibt die entsprechenden Entlade Informationen (. pushreg reg) aus.  Verwenden Sie dieses Makro, wenn der Push die erste Anweisung in der Funktion ist, um sicherzustellen, dass die Funktion Hot-patchfähig ist.|
|save_xmm128 *reg*, *Loc*|Speichert ein nicht flüchtiges XMM-Registrierungs- *reg* auf dem Stapel bei RSP Offset *Loc*und gibt die entsprechenden Entlade Informationen aus (. savexmm128 reg, Loc).|
|set_frame *reg*, *Offset*|Legt die Rahmen Register- *reg* auf den RSP +- *Offset* (unter Verwendung eines `mov`oder eines `lea`) fest und gibt die entsprechenden Entlade Informationen aus (. set_frame reg, Offset).|
|push_eflags|Überträgt die EFLAGS mit einer `pushfq` Anweisung und gibt die entsprechenden Entlade Informationen aus (. alloc_stack 8)|

Hier ist ein Beispiel für einen Funktions Prolog mit ordnungsgemäßer Verwendung der Makros:

```MASM
sampleFrame struct
    Fill     dq ?; fill to 8 mod 16
    SavedRdi dq ?; Saved Register RDI
    SavedRsi dq ?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here's the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>Entladen von Daten Definitionen in C

Im folgenden finden Sie eine Beschreibung der Entladungs Daten:

```C
typedef enum _UNWIND_OP_CODES {
    UWOP_PUSH_NONVOL = 0, /* info == register number */
    UWOP_ALLOC_LARGE,     /* no info, alloc size in next 2 slots */
    UWOP_ALLOC_SMALL,     /* info == size of allocation / 8 - 1 */
    UWOP_SET_FPREG,       /* no info, FP = RSP + UNWIND_INFO.FPRegOffset*16 */
    UWOP_SAVE_NONVOL,     /* info == register number, offset in next slot */
    UWOP_SAVE_NONVOL_FAR, /* info == register number, offset in next 2 slots */
    UWOP_SAVE_XMM128 = 8, /* info == XMM reg number, offset in next slot */
    UWOP_SAVE_XMM128_FAR, /* info == XMM reg number, offset in next 2 slots */
    UWOP_PUSH_MACHFRAME   /* info == 0: no error-code, 1: error-code */
} UNWIND_CODE_OPS;

typedef union _UNWIND_CODE {
    struct {
        UBYTE CodeOffset;
        UBYTE UnwindOp : 4;
        UBYTE OpInfo   : 4;
    };
    USHORT FrameOffset;
} UNWIND_CODE, *PUNWIND_CODE;

#define UNW_FLAG_EHANDLER  0x01
#define UNW_FLAG_UHANDLER  0x02
#define UNW_FLAG_CHAININFO 0x04

typedef struct _UNWIND_INFO {
    UBYTE Version       : 3;
    UBYTE Flags         : 5;
    UBYTE SizeOfProlog;
    UBYTE CountOfCodes;
    UBYTE FrameRegister : 4;
    UBYTE FrameOffset   : 4;
    UNWIND_CODE UnwindCode[1];
/*  UNWIND_CODE MoreUnwindCode[((CountOfCodes + 1) & ~1) - 1];
*   union {
*       OPTIONAL ULONG ExceptionHandler;
*       OPTIONAL ULONG FunctionEntry;
*   };
*   OPTIONAL ULONG ExceptionData[]; */
} UNWIND_INFO, *PUNWIND_INFO;

typedef struct _RUNTIME_FUNCTION {
    ULONG BeginAddress;
    ULONG EndAddress;
    ULONG UnwindData;
} RUNTIME_FUNCTION, *PRUNTIME_FUNCTION;

#define GetUnwindCodeEntry(info, index) \
    ((info)->UnwindCode[index])

#define GetLanguageSpecificDataPtr(info) \
    ((PVOID)&GetUnwindCodeEntry((info),((info)->CountOfCodes + 1) & ~1))

#define GetExceptionHandler(base, info) \
    ((PEXCEPTION_HANDLER)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetChainedFunctionEntry(base, info) \
    ((PRUNTIME_FUNCTION)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetExceptionDataPtr(info) \
    ((PVOID)((PULONG)GetLanguageSpecificData(info) + 1)
```

## <a name="see-also"></a>Siehe auch

[Softwarekonventionen bei x64-Systemen](../build/x64-software-conventions.md)
