---
title: Struktur UNWIND_CODE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5bccddd2ddd5c0f9dfbc828a7da3a66fa13339d
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861719"
---
# <a name="struct-unwindcode"></a>struct UNWIND_CODE

Das entladungscode-Array wird verwendet, die Reihenfolge der Vorgänge im Prolog, die die nicht flüchtigen Register und die RSP betreffen aufzeichnen. Jedes Codeelement weist das folgende Format:

|||
|-|-|
|UBYTE|Der Offset im prolog|
|UBYTE: 4|Entladungscode Vorgang|
|UBYTE: 4|Vorgangsinformationen|

Das Array wird in absteigender Reihenfolge des Offsets im Prolog sortiert.

## <a name="offset-in-prolog"></a>Der Offset im prolog

Offset vom Anfang des Prologs am Ende der Anweisung, die diesen Vorgang plus 1 (d. h. der Offset vom Anfang der nächsten Anweisung) ausführt.

## <a name="unwind-operation-code"></a>Entladungscode Vorgang

Hinweis: Bestimmte Operationscodes erfordern einen Offset ohne Vorzeichen in einen Wert in der lokalen Stapelrahmen. Dieser Offset ist ab dem Anfang (niedrigste Adresse) die festen stapelzuordnung. Das Registrieren der Frame-Feld in UNWIND_INFO ist 0 (null), diesen Offset von RSP. Wenn das Feld "Frame erfassen" ungleich NULL ist, ist dies der Offset, in denen RSP gefunden wurde, wenn das FP-Reg eingerichtet wurde. Dies entspricht FP Reg minus Offset Reg FP (16 \* skalierten Rahmens Offset in UNWIND_INFO registrieren). Wenn ein FP Reg verwendet wird, muss alle entladungscode dauert einen Offset nur verwendet werden nach dem im Prolog FP Reg hergestellt wird.

Für alle Opcodes außer `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`, der Offset wird immer ein Vielfaches von 8 sein, da alle stack werden Werte von Interesse an 8-Byte-Grenzen (der Stapel selbst ist immer 16-Byte-Ausrichtung) gespeichert. Der letzte USHORT in den Knoten für diesen Code enthält Operationscodes mit einem kurzen Offset (weniger als 512 KB), den Offset, dividiert durch 8. Für die Operationscodes mit langem Offset (512 KB < = < 4GB offset), die letzten beiden "ushort"-Knoten für diesen Code enthält den Offset (im little-Endian-Format).

Bei den Opcodes `UWOP_SAVE_XMM128` und `UWOP_SAVE_XMM128_FAR`, der Offset wird immer ein Vielfaches von 16, sein, da alle 128-Bit-XMM-Vorgänge auf 16-Byte-ausgerichteten Speicher erfolgen müssen. Aus diesem Grund wird für ein Skalierungsfaktor von 16 verwendet `UWOP_SAVE_XMM128`, Offsets von weniger als 1 Million zulassen.

Die entladungscodes für die Operation ist eines der folgenden:

`UWOP_PUSH_NONVOL` (0) 1 Knoten

Übertragen Sie ein nicht flüchtigen Ganzzahlregister Dekrementieren RSP durch 8. Die Vorgangsinformationen ist die Anzahl der Register. Beachten Sie, dass aufgrund der Einschränkungen für epilogen, `UWOP_PUSH_NONVOL` entladungscodes müssen im Prolog zuerst angezeigt, und dementsprechend zuletzt in das entladungscode-Array. Diese relativen Reihenfolge gilt für alle anderen entladungscodes außer `UWOP_PUSH_MACHFRAME`.

`UWOP_ALLOC_LARGE` (1) 2 oder 3 Knoten

Zuweisen eines großen Bereichs auf dem Stapel. Es gibt zwei Arten. Die Vorgangsinformationen 0, und klicken Sie dann auf die Größe der speicherbelegung geteilt durch gleich ist 8 in den nächsten Slot aufgezeichnet, sodass eine Zuordnung bis zu 512 KB - 8. Wenn die Vorgangsinformationen gleich 1 ist, die nicht skalierte Größe der Zuordnung wird in den nächsten beiden Slots im little-Endian-Format, sodass Zuweisungen aufgezeichnet bis zu 4GB - 8.

`UWOP_ALLOC_SMALL` (2) 1 Knoten

Ordnen Sie einen kleinen Bereich auf dem Stapel. Die Größe der Zuordnung ist das Feld des Vorgangs Informationen \* 8 + 8, sodass Zuweisungen von 8 bis 128 Byte.

Die entladungscode für eine stapelreservierung sollten immer die kürzeste mögliche-Codierung verwenden:

|**Zuordnungsgröße**|**Entladungscode**|
|-|-|
|8 bis 128 bytes|`UWOP_ALLOC_SMALL`|
|136 auf 512 KB - 8-Byte|`UWOP_ALLOC_LARGE`, Vorgangsinformationen = 0|
|512 KB, 4G - 8-Byte|`UWOP_ALLOC_LARGE`, Vorgangsinformationen = 1|

`UWOP_SET_FPREG` (3) 1 Knoten

Richten Sie das Framezeigerregister durch Festlegen der Registrierung einen Offset vom aktuellen RSP angeben. Der Offset ist gleich dem Frame registrieren Offset (skaliert) Feld im UNWIND_INFO \* 16, sodass die Offsets von 0 bis 240. Die Verwendung eines Offsets ermöglicht die Einrichtung der Frame-Pointer, die auf die Mitte des festen Stack Zuweisung, Unterstützung von Code Dichte-Konfigurationsrichtlinien weitere Zugriffe auf kurze instruktionsformen verwenden verweist. Beachten Sie, dass die Vorgang-Info-Feld reserviert ist und nicht verwendet werden sollte.

`UWOP_SAVE_NONVOL` (4) 2 Knoten

Ein nicht flüchtigen Ganzzahlregister gespeichert, auf dem Stapel, die einen PUSHVORGANG ein MOV statt. Dies ist in erster Linie für Shrink, verwendet, in dem ein nicht flüchtiges Register an den Stapel in einer Position gespeichert ist, der zuvor zugewiesen wurde. Die Vorgangsinformationen ist die Anzahl der Register. Der Offset skaliert-von-8-Stack wird in den nächsten aufgezeichnet Vorgangscode Slot, entladen, wie im Hinweis oben beschrieben.

`UWOP_SAVE_NONVOL_FAR` (5) 3 Knoten

Ein nicht flüchtigen Ganzzahlregister gespeichert, auf dem Stapel mit einem langen Offset, einen PUSHVORGANG ein MOV statt. Dies ist in erster Linie für Shrink, verwendet, in dem ein nicht flüchtiges Register an den Stapel in einer Position gespeichert ist, der zuvor zugewiesen wurde. Die Vorgangsinformationen ist die Anzahl der Register. Der Stapeloffset wird aufgezeichnet, in den nächsten zwei Slots Vorgangscode entladen wird, wie im Hinweis oben beschrieben.

`UWOP_SAVE_XMM128` (8) 2 Knoten

Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel. Die Vorgangsinformationen ist die Anzahl der Register. Der Stapeloffset skaliert-von-16-wird im nächsten Slot aufgezeichnet.

`UWOP_SAVE_XMM128_FAR` (9) 3 Knoten

Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel mit einem langen Offset. Die Vorgangsinformationen ist die Anzahl der Register. Der Offset Stack wird in den nächsten beiden Slots aufgezeichnet.

`UWOP_PUSH_MACHFRAME` (10) 1 Knoten

Übertragen Sie einen Computer Frame.  Dies wird verwendet, um die Auswirkungen eines Hardware-Interrupt oder eine Ausnahme zu erfassen. Es gibt zwei Arten. Wenn die Vorgangsinformationen gleich 0 ist, wurde die folgenden auf dem Stapel abgelegt:

|||
|-|-|
|RSP + 32|SS|
|RSP + 24|Alte RSP|
|RSP + 16|EFLAGS|
|RSP + 8|CS|
|RSP|RIP|

Wenn die Vorgangsinformationen 1 entspricht, und klicken Sie dann die folgenden stattdessen gepusht wurde:

|||
|-|-|
|RSP + 40|SS|
|RSP + 32|Alte RSP|
|RSP + 24|EFLAGS|
|RSP + 16|CS|
|RSP + 8|RIP|
|RSP|Fehlercode|

Diese entladungscode wird immer in ein dummy-Prolog angezeigt, die nie ausgeführt wird, jedoch stattdessen vor der tatsächlichen Einstiegspunkt einer Interruptroutine angezeigt wird, und vorhanden ist, nur um einen Ort zum Simulieren des Push eines Frames für Computer verfügbar zu machen. `UWOP_PUSH_MACHFRAME` Zeichnet die Simulation, die angibt, dass der Computer im Prinzip die folgenden Aufgaben ausgeführt hat:

1. POP-RIP-Absenderadresse vom Anfang des Stapels in *Temp*

1. SS mithilfe von Push übertragen

1. Alte RSP mithilfe von Push übertragen

1. Der EFLAGS

1. CS mithilfe von Push übertragen

1. Mithilfe von Push übertragen *Temp*

1. Übertragen von Fehlercode (falls Op Info 1 ist)

Die simulierten `UWOP_PUSH_MACHFRAME` Vorgang dekrementiert RSP um 40 (Op Info ist 0) oder 48 (Op Info ist 1).

## <a name="operation-info"></a>Vorgangsinformationen

Die Bedeutung dieser 4 Bits richtet sich nach dem Vorgangscode. Die folgende Zuordnung wird verwendet, um ein allgemeines (Integer) die Codierung:

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

## <a name="see-also"></a>Siehe auch

[Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)
