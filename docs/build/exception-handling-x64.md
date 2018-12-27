---
title: X64 Behandlung von Ausnahmen
ms.date: 12/17/2018
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: 33206dfb885239839c3a64436b6b540fc7d4e6e5
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627539"
---
# <a name="x64-exception-handling"></a>X64 Behandlung von Ausnahmen

Eine Übersicht über die strukturierte Ausnahmebehandlung und C++-Ausnahmebehandlung Programmierung Konventionen und Verhalten bei der X64. Allgemeine Informationen zur Behandlung von Ausnahmen, finden Sie unter [Ausnahmebehandlung in Visual C++](../cpp/exception-handling-in-visual-cpp.md).

## <a name="unwind-data-for-exception-handling-debugger-support"></a>Entladedaten Sie für die Ausnahmebehandlung, Debuggerunterstützung

Es sind verschiedene Datenstrukturen für Ausnahmebehandlung und debugging-Unterstützung erforderlich.

### <a name="struct-runtimefunction"></a>struct RUNTIME_FUNCTION

Tabellenbasierte Ausnahmebehandlung erfordert Tabelleneintrag für alle Funktionen, die Stapelspeicherplatz belegt werden, oder rufen Sie eine andere Funktion (z. B. Nichtblattelemente Funktionen). Funktion-Tabelleneinträge aufweisen Folgendes Format:

|||
|-|-|
|ULONG|Startadresse der Funktion|
|ULONG|Funktion-Endadresse|
|ULONG|Adresse der Entladeinformationen|

Die Struktur RUNTIME_FUNCTION muss DWORD im Arbeitsspeicher ausgerichtet sein. Alle Adressen sind relative-Image, d. h. 32-Bit-abweichungen von der die Startadresse des Bilds, das den Funktionstabelleneintrag enthält. Diese Einträge sind sortiert, und fügen Sie in den .pdata-Abschnitt eines Images PE32 +. Für dynamisch generierte Funktionen [JIT-Compiler] muss die Laufzeit zur Unterstützung dieser Funktionen entweder RtlInstallFunctionTableCallback oder RtlAddFunctionTable verwenden diese Informationen für das Betriebssystem bereitstellen. Bei unterlassen führt zu unzuverlässigen Behandlung von Ausnahmen und Debuggen von Prozessen.

### <a name="struct-unwindinfo"></a>struct UNWIND_INFO

Die Entladung-Info-Datenstruktur wird verwendet, um die Auswirkungen zu erfassen, die eine Funktion verfügt, auf den Stack-Pointer und, in dem die nicht flüchtigen Register auf dem Stapel gespeichert werden:

|||
|-|-|
|UBYTE: 3|Version|
|UBYTE: 5|Flags|
|UBYTE|Größe der prolog|
|UBYTE|Anzahl von entladungscodes|
|UBYTE: 4|Frame-Register|
|UBYTE: 4|Frame-Register-Offset (skaliert)|
|USHORT \* n|Entladen Sie Codes array|
|Variable|Entweder kann der Form (1) oder (2) im folgenden werden|

(1) Ausnahmehandler

|||
|-|-|
|ULONG|Adresse des ausnahmehandlers|
|-Variable|Sprachspezifischer Handlerdaten (optional)|

(2) verkettet Entladeinformationen

|||
|-|-|
|ULONG|Startadresse der Funktion|
|ULONG|Funktion-Endadresse|
|ULONG|Adresse der Entladeinformationen|

Die Struktur UNWIND_INFO muss DWORD im Arbeitsspeicher ausgerichtet sein. Hier ist, was bedeutet, dass jedes Feld:

- **Version**

   Die Versionsnummer der Entladedaten, derzeit 1.

- **Flags**

   Aktuell sind drei Flags definiert:

   |Flag|Beschreibung|
   |-|-|
   |`UNW_FLAG_EHANDLER`| Die Funktion weist einen Ausnahmehandler, der aufgerufen werden soll, beim Suchen nach Funktionen, die Ausnahmen zu analysieren.|
   |`UNW_FLAG_UHANDLER`| Die Funktion weist einen Beendigungshandler, der beim Entladen einer Ausnahme aufgerufen werden soll.|
   |`UNW_FLAG_CHAININFO`| Dies Entladeinformationen, dass die Struktur nicht das primäre Replikat für die Prozedur ist. Stattdessen Entladeinformationen die verketteten, dass Eintrag auf den Inhalt eines vorherigen RUNTIME_FUNCTION Eintrags ist. Weitere Informationen finden Sie unter [Verkettete Entladeinfostrukturen](#chained-unwind-info-structures). Wenn dieses Flag festgelegt ist, müssen die UNW_FLAG_EHANDLER und UNW_FLAG_UHANDLER Flags deaktiviert werden. Darüber hinaus müssen die Frame-registrieren und -Stack Allocation-Felder die gleichen Werte wie in der primären Informationen zu entladen.|

- **Größe der prolog**

   Die Länge des Funktionsprologs in Byte.

- **Anzahl von entladungscodes**

   Die Anzahl der Slots in das Array entladen werden soll. Einige entladungscodes, z. B. UWOP_SAVE_NONVOL, benötigen Sie mehr als einen Slot im Array.

- **Frame-register**

   Wert ungleich NULL ist, klicken Sie dann die Funktion verwendet einen Frame-Pointer (FP), und dieses Feld gibt an, der nicht flüchtigen Register als der Frame-Pointer verwenden die gleiche Codierung für das Feld des Vorgangs Informationen Framezeiger verwendet.

- **Frame erfassen Offset (skaliert)**

   Wenn das Feld "Register" des Frame ungleich NULL ist, wird dieses Feld ist die skalierte Offset von RSP, die auf ein FP registriert werden, wenn es eingerichtet wird. Das tatsächliche FP-Register nastaven NA hodnotu RSP + 16 \* diese Zahl, sodass die Offsets von 0 bis 240. Dieser Offset ermöglicht, zeigen das FP-Register, in die Mitte der lokalen stapelreservierung für dynamische Stapelrahmen, sodass eine höhere Dichte von Code mithilfe von kürzeren Anweisungen (Weitere Informationen können die signierten 8-Bit-Offset Formulars verwenden).

- **Entladen Sie Codes array**

   Ein Array von Elementen, die die Auswirkungen der Prolog auf die nicht flüchtigen Register und die RSP erläutert. Die Bedeutungen der einzelnen Elemente finden Sie im Abschnitt für UNWIND_CODE. Für die Ausrichtung die dieses Array weist immer eine gerade Anzahl von Einträgen aus, und der abschließende Eintrag wird möglicherweise nicht verwendet. In diesem Fall ist das Array eine länger als die Anzahl der Entladung Codes Feld angegeben.

- **Adresse des ausnahmehandlers**

   Ein Abbild relativ Zeiger auf der Funktion sprachspezifische Ausnahme oder Beendigungshandler, wenn das Flag UNW_FLAG_CHAININFO deaktivieren und zu den Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt ist.

- **Sprachspezifischer Handlerdaten**

   Der Funktion sprachspezifischer Handler Ausnahmedaten. Das Format dieser Daten ist nicht angegeben und vollständig vom Handler für bestimmte Ausnahmen verwendet bestimmt.

- **Verkettet Entladeinformationen**

   Wenn das UNW_FLAG_CHAININFO-Flag festgelegt ist, und klicken Sie dann die UNWIND_INFO-Struktur mit drei UWORDs endet.  Diese UWORDs stellen die RUNTIME_FUNCTION Informationen für die Funktion die verketteten Entladung dar.

### <a name="struct-unwindcode"></a>struct UNWIND_CODE

Das entladungscode-Array wird verwendet, die Reihenfolge der Vorgänge im Prolog, die die nicht flüchtigen Register und die RSP betreffen aufzeichnen. Jedes Codeelement weist dieses Format auf:

|||
|-|-|
|UBYTE|Der Offset im prolog|
|UBYTE: 4|Entladungscode Vorgang|
|UBYTE: 4|Vorgangsinformationen|

Das Array wird in absteigender Reihenfolge des Offsets im Prolog sortiert.

#### <a name="offset-in-prolog"></a>Der Offset im prolog

Offset vom Anfang des Prologs am Ende der Anweisung, die diesen Vorgang plus 1 (d. h. der Offset vom Anfang der nächsten Anweisung) ausführt.

#### <a name="unwind-operation-code"></a>Entladungscode Vorgang

Hinweis: Bestimmte Operationscodes erfordern einen Offset ohne Vorzeichen in einen Wert in der lokalen Stapelrahmen. Dieser Offset ist von Beginn, also die niedrigste Adresse von den festen stapelzuordnung. Das Registrieren der Frame-Feld in UNWIND_INFO ist 0 (null), diesen Offset von RSP. Wenn das Feld "Frame erfassen" ungleich NULL ist, ist dies der Offset, in denen RSP gefunden wurde, wenn der FP-Register eingerichtet wurde. Dies entspricht der FP-Register abzüglich des Offsets der FP-Register (16 \* skalierten Rahmens Offset in UNWIND_INFO registrieren). Wenn ein FP-Register verwendet wird, muss alle entladungscode dauert einen Offset nur verwendet werden, nachdem das FP-Register im Prolog hergestellt wird.

Für alle Opcodes außer `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`, der Offset ist immer ein Vielfaches von 8, da alle stack werden Werte von Interesse an 8-Byte-Grenzen (der Stapel selbst ist immer 16-Byte-Ausrichtung) gespeichert. Der letzte USHORT in den Knoten für diesen Code enthält Operationscodes mit einem kurzen Offset (weniger als 512 KB), den Offset, dividiert durch 8. Für die Operationscodes mit langem Offset (512 KB < = < 4GB offset), die letzten beiden "ushort"-Knoten für diesen Code enthält den Offset (im little-Endian-Format).

Bei den Opcodes `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`, der Offset ist immer ein Vielfaches von 16, da alle 128-Bit-XMM-Vorgänge auf 16-Byte-ausgerichteten Speicher erfolgen müssen. Aus diesem Grund wird für ein Skalierungsfaktor von 16 verwendet `UWOP_SAVE_XMM128`, Offsets von weniger als 1 Million zulassen.

Das entladungscode-Vorgang ist eine der folgenden Werte:

- `UWOP_PUSH_NONVOL` (0) 1 Knoten

  Übertragen Sie ein nicht flüchtigen Ganzzahlregister Dekrementieren RSP durch 8. Die Vorgangsinformationen ist die Anzahl der Register. Aufgrund der Einschränkungen für epilogen `UWOP_PUSH_NONVOL` entladungscodes müssen im Prolog zuerst angezeigt, und dementsprechend zuletzt in das entladungscode-Array. Diese relativen Reihenfolge gilt für alle anderen entladungscodes außer `UWOP_PUSH_MACHFRAME`.

- `UWOP_ALLOC_LARGE` (1) 2 oder 3 Knoten

  Zuweisen eines großen Bereichs auf dem Stapel. Es gibt zwei Arten. Die Vorgangsinformationen 0, und klicken Sie dann auf die Größe der speicherbelegung geteilt durch gleich ist 8 in den nächsten Slot aufgezeichnet, sodass eine Zuordnung bis zu 512 KB - 8. Wenn die Vorgangsinformationen gleich 1 ist, die nicht skalierte Größe der Zuordnung wird in den nächsten beiden Slots im little-Endian-Format, sodass Zuweisungen aufgezeichnet bis zu 4GB - 8.

- `UWOP_ALLOC_SMALL` (2) 1 Knoten

  Ordnen Sie einen kleinen Bereich auf dem Stapel. Die Größe der Zuordnung ist das Feld des Vorgangs Informationen \* 8 + 8, sodass Zuweisungen von 8 bis 128 Byte.

  Die entladungscode für eine stapelreservierung sollten immer die kürzeste mögliche-Codierung verwenden:

  |**Zuordnungsgröße**|**Entladungscode**|
  |-|-|
  |8 bis 128 bytes|`UWOP_ALLOC_SMALL`|
  |136 auf 512 KB - 8-Byte|`UWOP_ALLOC_LARGE`, Vorgangsinformationen = 0|
  |512 KB, 4G - 8-Byte|`UWOP_ALLOC_LARGE`, Vorgangsinformationen = 1|

- `UWOP_SET_FPREG` (3) 1 Knoten

  Richten Sie das Framezeigerregister durch Festlegen der Registrierung einen Offset vom aktuellen RSP angeben. Der Offset ist gleich dem Frame registrieren Offset (skaliert) Feld im UNWIND_INFO \* 16, sodass die Offsets von 0 bis 240. Die Verwendung eines Offsets ermöglicht die Einrichtung der Frame-Pointer, die auf die Mitte des festen Stack Zuweisung, Unterstützung von Code Dichte-Konfigurationsrichtlinien weitere Zugriffe auf kurze instruktionsformen verwenden verweist. Die Vorgang-Info-Feld ist reserviert und sollte nicht verwendet werden.

- `UWOP_SAVE_NONVOL` (4) 2 Knoten

  Ein nicht flüchtigen Ganzzahlregister gespeichert, auf dem Stapel, die einen PUSHVORGANG ein MOV statt. Dieser Code wird hauptsächlich für *Shrink*, in dem ein nicht flüchtiges Register an den Stapel in einer Position gespeichert ist, der zuvor zugewiesen wurde. Die Vorgangsinformationen ist die Anzahl der Register. Der Offset skaliert-von-8-Stack wird in den nächsten aufgezeichnet Vorgangscode Slot, entladen, wie im Hinweis oben beschrieben.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 Knoten

  Ein nicht flüchtigen Ganzzahlregister gespeichert, auf dem Stapel mit einem langen Offset, einen PUSHVORGANG ein MOV statt. Dieser Code wird hauptsächlich für *Shrink*, in dem ein nicht flüchtiges Register an den Stapel in einer Position gespeichert ist, der zuvor zugewiesen wurde. Die Vorgangsinformationen ist die Anzahl der Register. Der Stapeloffset wird aufgezeichnet, in den nächsten zwei Slots Vorgangscode entladen wird, wie im Hinweis oben beschrieben.

- `UWOP_SAVE_XMM128` (8) 2 Knoten

  Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel. Die Vorgangsinformationen ist die Anzahl der Register. Der Stapeloffset skaliert-von-16-wird im nächsten Slot aufgezeichnet.

- `UWOP_SAVE_XMM128_FAR` (9) 3 Knoten

  Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel mit einem langen Offset. Die Vorgangsinformationen ist die Anzahl der Register. Der Offset Stack wird in den nächsten beiden Slots aufgezeichnet.

- `UWOP_PUSH_MACHFRAME` (10) 1 Knoten

  Übertragen Sie einen Computer Frame.  Dies wird verwendet, um die Auswirkungen eines Hardware-Interrupt oder eine Ausnahme zu erfassen. Es gibt zwei Arten. Wenn die Vorgangsinformationen gleich 0 ist, wurde eines dieser Frames auf dem Stapel abgelegt:

  |||
  |-|-|
  |RSP + 32|SS|
  |RSP + 24|Alte RSP|
  |RSP + 16|EFLAGS|
  |RSP + 8|CS|
  |RSP|RIP|

  Wenn die Vorgangsinformationen 1 entspricht, wurde dann eine der folgenden Frames abgelegt:

  |||
  |-|-|
  |RSP + 40|SS|
  |RSP + 32|Alte RSP|
  |RSP + 24|EFLAGS|
  |RSP + 16|CS|
  |RSP + 8|RIP|
  |RSP|Fehlercode|

  Diese entladungscode wird immer in einen dummy-Prolog, die nie ausgeführt wird, jedoch stattdessen vor der tatsächlichen Einstiegspunkt einer Interruptroutine angezeigt wird, und vorhanden ist, nur um einen Ort zum Simulieren des Push eines Frames für Computer verfügbar zu machen. `UWOP_PUSH_MACHFRAME` Zeichnet die Simulation, die angibt, dass der Computer vom Konzept her dieser Vorgang ausgeführt wurde:

  1. POP-RIP-Absenderadresse vom Anfang des Stapels in *Temp*
  
  1. SS mithilfe von Push übertragen

  1. Alte RSP mithilfe von Push übertragen

  1. Der EFLAGS

  1. CS mithilfe von Push übertragen

  1. Mithilfe von Push übertragen *Temp*

  1. Übertragen von Fehlercode (falls Op Info 1 ist)

  Die simulierten `UWOP_PUSH_MACHFRAME` Vorgang dekrementiert RSP um 40 (Op Info ist 0) oder 48 (Op Info ist 1).

#### <a name="operation-info"></a>Vorgangsinformationen

Die Bedeutung der Bits Informationen Vorgang richtet sich nach dem Vorgangscode. Diese Zuordnung wird verwendet, um ein allgemeines (Integer) die Codierung:

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
|8 bis 15|R8 bis R15|

### <a name="chained-unwind-info-structures"></a>Verkettete Entladeinfostrukturen

Wenn die UNW_FLAG_CHAININFO-Flag festgelegt ist, klicken Sie dann eine Entladung Info-Struktur ist eine sekundäre und die freigegebenen Ausnahme-Handler/verkettet-Info-Adressfeld enthält die primären Entladeinformationen. Dieser Beispielcode ruft die primäre Entladeinformationen, vorausgesetzt, dass `unwindInfo` ist die Struktur, die das UNW_FLAG_CHAININFO flag so festgelegt sein.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Verkettete Informationen ist in zwei Situationen nützlich. Zunächst können sie für nicht zusammenhängende Codesegmente verwendet werden. Mit verketteten Informationen, können Sie die Größe des erforderlichen Entladeinformationen, reduzieren, da Sie nicht besitzen, das Array Entladung aus den primären Entladeinformationen zu duplizieren.

Sie können auch verketteten Informationen verwenden, um flüchtige registerspeicherungen zu gruppieren. Der Compiler kann eine Verzögerung von einigen volatile Register speichern, bis der Vorgang außerhalb des Funktionsprologs-Eintrag. Sie können dies durch die primäre Entladeinformationen für den Teil der Funktion vor dem gruppierten Code aufzeichnen und anschließendes Einrichten von Informationen mit einer nicht-NULL-Größe von Prolog, in dem die entladungscodes in den verketteten Informationen speichert, der nicht flüchtigen Register wiedergeben verkettet. In diesem Fall sind die entladungscodes alle Instanzen von UWOP_SAVE_NONVOL. Eine Gruppierung, die nicht flüchtige Register speichert, mithilfe einer CLIENTPUSHINSTALLATION oder ändert die RSP-Register mithilfe einer zusätzlichen festen stapelreservierung wird nicht unterstützt.

Bezeichnet ein UNWIND_INFO-Element, das UNW_FLAG_CHAININFO Satz kann einen Eintrag für die RUNTIME_FUNCTION enthalten, deren UNWIND_INFO-Element verfügt auch über UNW_FLAG_CHAININFO festgelegt ist, hat *mehrfache Komprimierung*. Die verketteten entladen schließlich Informationen, die Zeiger auf ein Element UNWIND_INFO eingehen, die UNW_FLAG_CHAININFO deaktiviert ist; Dies ist das primäre UNWIND_INFO-Element, das auf der tatsächlichen Prozedureinstiegspunkt verweist.

## <a name="unwind-procedure"></a>Entladeprozedur

Das entladungscode-Array wird in absteigender Reihenfolge sortiert. Wenn eine Ausnahme auftritt, wird der vollständige Kontext vom Betriebssystem in einem Kontextdatensatz gespeichert. Die Dispatch-Exception-Logik wird dann aufgerufen, die wird wiederholt ausgeführt, diese Schritte, um einen Ausnahmehandler gefunden wird:

1. Verwenden Sie die aktuelle RIP, die im Kontextdatensatz gespeichert, um Tabelleneintrag RUNTIME_FUNCTION gesucht, die die aktuelle Funktion (oder einen Teil der Funktion, für die verketteten UNWIND_INFO-Einträgen) beschreibt.

1. Wenn kein Funktionstabelleneintrag gefunden wird, ist es in einer untergeordneten Funktion aus, und RSP-Adressen direkt den Rückgabezeiger. Der Zurücksetzen von Zeiger auf [RSP] befindet sich im aktuellen Kontext, der simulierte RSP um 8 erhöht und Schritt 1 wiederholt wird.

1. Wenn ein Funktionstabelleneintrag gefunden wird, kann RIP innerhalb von drei Bereichen liegen: (a) in einem Epilog, (b) im Prolog oder (c) in Code, der von einem Ausnahmehandler behandelt werden kann.

   - Groß-/Kleinschreibung einer) wenn RIP befindet sich in einem Epilog, dann Steuerelement ist die Funktion wird beendet, es keinen Ausnahmehandler, der dieser Ausnahme für diese Funktion zugeordnet darf und Sie die Auswirkungen des Epilogs fortsetzen müssen, im Rahmen der aufrufenden Funktion berechnet. Um zu bestimmen, ob die RIP innerhalb eines Epilogs, der Codestream, aus der RIP auf werden untersucht. Wenn der Codestream mit den abschließenden Teil eines gültigen Epilogs abgeglichen werden kann und es in einem Epilog ist und im weiteren Verlauf des Epilogs wird simuliert, wird mit der Kontextdatensatz aktualisiert, während jede Anweisung verarbeitet. Danach wird der Schritt 1 wiederholt.

   - Fall b) Wenn der RIP im Prolog liegt, und klicken Sie dann die Kontrolle nicht der Fall ist die Funktion eingegeben, es darf keinen Ausnahmehandler, der dieser Ausnahme für diese Funktion zugeordnet, und die Auswirkungen der Prolog müssen rückgängig gemacht werden, um den Kontext der aufrufenden Funktion zu berechnen. RIP befindet sich im Prolog, wenn der Abstand zwischen dem Start der Funktion und die RIP kleiner als oder gleich der Prolog-Größe, die in den Entladeinformationen codiert ist. Die Auswirkungen der Prolog werden entladen, indem Sie über das Array für den ersten Eintrag mit einem Offset kleiner oder gleich dem Offset des RIP Funktionsstarts Entladung vorwärtsspulen und anschließend rückgängig machen die Auswirkungen aller verbleibenden Elemente in das entladungscode-Array. Schritt 1 wird wiederholt.

   - Groß-/Kleinschreibung c) ist die RIP nicht innerhalb eines Prologs oder Epilogs und die Funktion wurde einen Ausnahmehandler (UNW_FLAG_EHANDLER festgelegt ist), und dann die sprachspezifische-Handler wird aufgerufen. Der Handler überprüft die Daten und Filterfunktionen für Aufrufe nach Bedarf. Dass die Ausnahme behandelt wurde oder bei der Suche wird fortgesetzt werden, kann der Handler für die sprachspezifische zurückgeben. Sie können auch direkt eine Entladung initiieren.

1. Wenn der sprachspezifische-Handler behandelten Status zurück, die Ausführung wird fortgesetzt, mit dem ursprünglichen Kontextdatensatz.

1. Wenn kein sprachspezifischer Handler vorhanden ist, oder der Handler für den Status "Suche fortsetzen" zurück, muss der Kontextdatensatz entladen in den Zustand des Aufrufers sein. Dies erfolgt durch die Verarbeitung aller Entladung Codeelemente des Arrays, die Auswirkungen der einzelnen rückgängig. Schritt 1 wird wiederholt.

Wenn verkettete entladen beteiligt, weiterhin diese grundlegenden Schritte befolgt werden. Der einzige Unterschied ist, dass beim durchlaufen, um einen Prolog der Effekte, entladen, erreichen das Ende des Arrays des entladungscode-Arrays, klicken Sie dann mit den übergeordneten Entladeinformationen verknüpft und das gesamte entladungscode-Array gefunden. es wird. Diese Verknüpfung wird fortgesetzt, bis ein Entladeinformationen ohne das Flag UNW_CHAINED_INFO eintreffen, und klicken Sie dann es abgeschlossen ist, dessen entladungscode-Array durchlaufen.

Die kleinste Menge der Entladung der Daten ist 8 Byte. Dies würde eine Funktion dar, die nur 128 Byte des Stapels oder weniger zugeordnet, möglicherweise einen nicht flüchtiges Register. Dies ist auch die Größe einer verketteten Informationsstruktur für eine Zeichenfolge der Länge Null Prolog mit keine entladungscodes entladen.

## <a name="language-specific-handler"></a>Sprachspezifischer handler

Die relative Adresse des Handlers sprachspezifische ist in UNWIND_INFO vorhanden, wenn Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt sind. Wie im vorherigen Abschnitt beschrieben wird, wird der Handler für die sprachspezifische als Teil der Suche nach einem Ausnahmehandler oder als Teil des eine Entladung aufgerufen. Sie weist die folgenden Prototyp:

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** gibt einen Zeiger auf einen Ausnahmedatensatz, der die standard-Win64-Definition aufweist.

**EstablisherFrame** ist die Adresse der Basis der Zuordnung fester Stack für diese Funktion.

**ContextRecord** verweist auf den Ausnahmekontext auf die Zeit, die die Ausnahme (bei einer Ausnahme-Handler ausgelöst wurde) oder die aktuelle "abgewickelt" Kontext (im Fall Handler beenden).

**DispatcherContext** verweist auf die Dispatcher-Kontext für diese Funktion. Sie weist diese Definition auf:

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

**ControlPc** ist der Wert des RIP innerhalb dieser Funktion. Dieser Wert ist entweder eine Ausnahmeadresse oder die Adresse, an dem Steuerelement die Funktion verlassen. Die RIP wird verwendet, um zu bestimmen, ob das Steuerelement beispielsweise innerhalb eines überwachten Konstrukts innerhalb dieser Funktion ist eine `__try` blockieren `__try` / `__except` oder `__try` / `__finally`.

**ImageBase** ist die Anwendungsbasis (Ladeadresse) des Moduls mit dieser Funktion, die 32-Bit-Offsets, die in der Funktion-Eintrag verwendet hinzugefügt werden und Entladeinformationen um relative Adressen aufzuzeichnen.

**FunctionEntry** stellt einen Zeiger auf die RUNTIME_FUNCTION Funktionseinstieg, enthält die Funktion und entladen, Informationen zur Basis-Image relative Adressen für diese Funktion.

**EstablisherFrame** ist die Adresse der Basis der Zuordnung fester Stack für diese Funktion.

**TargetIp** liefert eine optionale Anweisungsadresse, die Fortsetzung Adresse die Entladung angibt. Diese Adresse wird ignoriert, wenn **EstablisherFrame** nicht angegeben ist.

**ContextRecord** verweist auf den Ausnahmekontext, für die Verwendung durch den Verteiler/entladen System Ausnahmecode.

**LanguageHandler** verweist auf die sprachspezifische Handlerroutine aufgerufen wird.

**HandlerData** zeigt auf die Handlerdaten sprachspezifischer für diese Funktion.

## <a name="unwind-helpers-for-masm"></a>Entladehilfen für MASM

Um das Schreiben, gibt es eine Reihe von Pseudo-Vorgänge, die parallel mit den tatsächlichen Assemblyanweisungen verwendet werden kann, um die entsprechenden .pdata und .xdata zu erstellen. Es gibt außerdem vereinfacht eine Reihe von Makros zur Verfügung, mit der Pseudo-Vorgänge für die häufigsten Verwendungszwecke.

### <a name="raw-pseudo-operations"></a>Unformatierte Pseudooperationen

|Pseudo-Vorgang|Beschreibung|
|-|-|
|PROC FRAME \[:*Ehandler*]|Bewirkt, dass MASM auf eine Funktion generieren Eintrag im .pdata-Datensatz der Tabelle und Entladeinformationen in .xdata für eine Funktion der strukturierten Ausnahmebehandlung entladen Verhalten.  Wenn *Ehandler* vorhanden ist, wird diese Prozedur im .xdata als sprachspezifischer Handler eingegeben.<br /><br /> Wenn der FRAME-Attribut verwendet wird, muss ihm durch ein. ENDPROLOG-Direktive.  Wenn die Funktion eine blattfunktion ist (gemäß [Funktionstypen](../build/stack-usage.md#function-types)) das FRAME-Attribut ist nicht erforderlich, die übrigen Pseudooperationen.|
|. PUSHREG *registrieren*|Generiert einen UWOP_PUSH_NONVOL Entladung-Code-Eintrag für die mit dem aktuellen offset im Prolog angegebenen Registernummer an.<br /><br /> Dies sollte nur mit permanenten Ganzzahlregister verwendet werden.  Für Push-Vorgänge von volatile Register, verwendet ein. ALLOCSTACK 8, stattdessen|
|. SETFRAME *registrieren*, *Offset*|Füllt das Registrieren Feld und den Offset in den Entladeinformationen unter Verwendung des angegebenen Register und Offset. Der Offset muss ein Vielfaches von 16 sein und kleiner als oder gleich 240. Diese Direktive generiert außerdem einen UWOP_SET_FPREG Entladung Code-Eintrag für die angegebene Register, die mit den aktuellen Prologoffset.|
|. ALLOCSTACK *Größe*|Generiert eine UWOP_ALLOC_SMALL oder einen UWOP_ALLOC_LARGE mit der angegebenen Größe für den aktuellen Offset im Prolog an.<br /><br /> Die *Größe* Operand muss ein Vielfaches von 8 sein.|
|. SAVEREG *registrieren*, *Offset*|Erzeugt entweder eine UWOP_SAVE_NONVOL oder einen UWOP_SAVE_NONVOL_FAR Entladung Code-Eintrag für das angegebene Register und den Offset den aktuelle Prologoffset verwenden. MASM wählt die effizienteste Codierung.<br /><br /> *Offset* muss positiv und ein Vielfaches von 8 sein. *Offset* ist relativ zum Basis der Prozedur bei der Frame, in der Regel in der RSP oder, wenn der Frame-Pointer, die-Frame-Pointer verwenden.|
|. SAVEXMM128 *registrieren*, *Offset*|Erzeugt entweder eine UWOP_SAVE_XMM128 oder einen UWOP_SAVE_XMM128_FAR Entladung Code-Eintrag für den angegebenen XMM-Register und der aktuelle Prologoffset mit Offset. MASM wählt die effizienteste Codierung.<br /><br /> *Offset* muss positiv und ein Vielfaches von 16 sein.  *Offset* ist relativ zum Basis der Prozedur bei der Frame, in der Regel in der RSP oder, wenn der Frame-Pointer, die-Frame-Pointer verwenden.|
|. PUSHFRAME \[ *Code*]|Generiert einen UWOP_PUSH_MACHFRAME Entladung Codeeintrag an. Wenn der optionale *Code* angegeben ist, wird der Eintrag der Entladung Code erhält einen Modifizierer von 1. Andernfalls ist der Modifizierer 0.|
|.ENDPROLOG|Signalisiert das Ende der Prologdeklarationen.  Muss in den ersten 255 Bytes der Funktion erfolgen.|

Hier ist eine Beispiel-Funktionsprologs mit richtiger Verwendung der meisten Opcodes:

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
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here’s the official epilog

    lea rsp, [rbp-020h]
    pop rbp
    ret
sample ENDP
```

### <a name="masm-macros"></a>MASM-Makros

Um die Verwendung von vereinfachen die [unformatierte Pseudooperationen](#raw-pseudo-operations), es gibt eine Reihe von Makros, definiert in ksamd64.inc, die verwendet werden kann, um typische Vorgehensweise Prologe und Epiloge zu erstellen.

|Makro|Beschreibung|
|-|-|
|alloc_stack(n)|Weist einen Stapelrahmen von n Bytes (mit `sub rsp, n`), und gibt die entsprechenden Entladeinformationen aus (.allocstack-n)|
|Save_reg *Reg*, *Loc*|Speichert ein nicht flüchtiges Register *Reg* im Stapel auf RSP offset *Loc*, und gibt die entsprechenden Entladeinformationen. (Reg .savereg, Loc)|
|Push_reg *Reg*|Legt ein nicht flüchtiges Register *Reg* auf dem Stapel und gibt die entsprechenden Entladeinformationen. (.pushreg Reg)|
|Rex_push_reg *Reg*|Ein nicht flüchtiges Register speichern, auf dem Stapel mit einem Push-2-Byte und gibt die entsprechenden Entladeinformationen (.pushreg Reg) dies verwendet werden, sollte Wenn der Push-Vorgang die erste Anweisung in der Funktion ist, um sicherzustellen, dass die Funktion "heiß"-patchfähigen ist.|
|save_xmm128 *Reg*, *Loc*|Speichert ein nicht flüchtiges XMM-Register *Reg* im Stapel auf RSP offset *Loc*, und gibt die entsprechenden Entladeinformationen aus (savexmm128 Reg, Loc)|
|Set_frame *Reg*, *Offset*|Legt das Frame-Register *Reg* sollen die RSP + *Offset* (mit einer `mov`, oder ein `lea`), und gibt die entsprechenden Entladeinformationen aus ("set_frame Reg", "Offset")|
|push_eflags|Verschiebt Eflags mit einem `pushfq` -Anweisung, und gibt die entsprechenden Entladeinformationen aus (. alloc_stack 8)|

Hier ist eine Beispiel-Funktionsprologs mit richtiger Verwendung der Makros:

```MASM
SkFrame struct
    Fill    dq ?; fill to 8 mod 16
    SavedRdi dq ?; saved register RDI
    SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
    Filldq?; fill to 8 mod 16
    SavedRdidq?; Saved Register RDI
    SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>Entladedaten Sie-Definitionen in C

Hier ist eine C-Beschreibung der Entladungsdaten:

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

[X64 Softwarekonventionen](../build/x64-software-conventions.md)