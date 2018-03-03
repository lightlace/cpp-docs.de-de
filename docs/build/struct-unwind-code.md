---
title: Struktur UNWIND_CODE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76059ff24b46fd537db0c2670a30cf3f42ee2166
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="struct-unwindcode"></a>struct UNWIND_CODE
Das entladungscode-Array wird verwendet, um die Abfolge der Vorgänge im Prolog, die Einfluss auf die nicht flüchtigen Register und RSP aufzuzeichnen. Jedes Codeelement weist das folgende Format:  
  
|||  
|-|-|  
|UBYTE|Offset im prolog|  
|UBYTE: 4|Entladungscode Vorgang|  
|UBYTE: 4|Vorgang info|  
  
 Das Array wird in absteigender Reihenfolge des Offsets im Prolog sortiert.  
  
 **Offset im prolog**  
 Offset vom Anfang des Prologs vom Ende der Anweisung ausführt, die diesen Vorgang plus 1 (d. h. der Offset des Beginns der nächsten Anweisung).  
  
 **Entladungscode Vorgang**  
 Hinweis: Bestimmte Operationscodes erfordern einen Offset ohne Vorzeichen in einen Wert im lokalen Stapelrahmen. Dieser Offset ist ab dem Anfang (niedrigste Adresse) den festen stapelzuordnung. Wenn der Frame registrieren Feld UNWIND_INFO 0 (null) ist, ist dies ein Offset von RSP. Wenn das Feld Frame erfassen ungleich NULL ist, ist dies der Offset, in denen RSP gefunden wurde, wenn das FP Reg eingerichtet wurde. Dies entspricht das FP Reg minus dem FP Reg-Offset (16 * skalierten Rahmens registrieren Offset in UNWIND_INFO). Wenn ein FP Reg verwendet wird, muss alle entladungscode dauert einen Offset nur verwendet werden nach dem im Prolog FP Reg hergestellt wird.  
  
 Für alle Opcodes mit Ausnahme von UWOP_SAVE_XMM128 und UWOP_SAVE_XMM128_FAR wird der Offset immer ein Vielfaches von 8 sein, da alle Stack-Werte von Interesse an 8-Byte-Grenzen gespeichert werden (der Stapel selbst ist immer 16-Byte-ausgerichtet). Für Operationscodes mit einem kurzen Offset (weniger als 512 KB), enthält die endgültigen "ushort" in den Knoten für diesen Code den Offset, dividiert durch 8. Für Operationscodes mit langem Offset (512 KB < = < 4-GB-offset), die letzten beiden "ushort" Knoten für diesen Code, den Offset (im little-Endian-Format) zu belassen.  
  
 Für den Opcodes UWOP_SAVE_XMM128 und UWOP_SAVE_XMM128_FAR werden der Offset immer ein Vielfaches von 16 an, da alle 128-Bit-XMM-Vorgänge auf 16-Byte-ausgerichtete Speicher vorliegen müssen. Aus diesem Grund wird ein Skalierungsfaktor von 16 für UWOP_SAVE_XMM128 verwendet, die Offsets von weniger als 1 M verwendet.  
  
 Der Vorgang entladungscode ist eine der folgenden:  
  
 UWOP_PUSH_NONVOL (0) 1 Knoten  
  
 Bewirken Sie, dass ein nicht veränderliches Ganzzahlregister Dekrementieren RSP durch 8. Das Vorgang Info ist die Anzahl des Registers. Beachten Sie, dass aufgrund der Beschränkungen-epilogen UWOP_PUSH_NONVOL entladungscodes werden als erstes im Prolog und dementsprechend in das entladungscode-Array zuletzt werden müssen. Diese relative Reihenfolge gilt für alle anderen Entladecodes außer UWOP_PUSH_MACHFRAME.  
  
 UWOP_ALLOC_LARGE (1) 2 oder 3 Knoten  
  
 Zuweisen eines großen Bereichs auf dem Stapel. Es gibt zwei Formen. Info Vorgang 0, und klicken Sie dann auf die Größe der Zuweisung geteilt durch gleich wird 8 im nächsten Slot aufgezeichnet, sodass eine Zuweisung bis zu 512 KB - 8. Wenn die Vorgang-Infos gleich 1, der nicht skalierte Größe der speicherbelegung wird in den nächsten beiden Slots in little-Endian-Format, sodass Zuweisungen aufgezeichnet bis zu 4GB - 8.  
  
 UWOP_ALLOC_SMALL (2) 1 Knoten  
  
 Ordnen Sie einen kleinen Bereich auf dem Stapel an. Die Größe der Zuordnung ist der Vorgang Info-Feld * 8 + 8, sodass Zuweisungen von 8 bis 128 Byte.  
  
 Der entladungscode für eine stapelzuordnung sollten immer die kürzeste mögliche-Codierung verwenden:  
  
|||  
|-|-|  
|**Zuordnungsgröße**|**Entladungscode**|  
|8 bis 128 Byte|UWOP_ALLOC_SMALL|  
|136 auf 512 KB - 8-Byte|UWOP_ALLOC_LARGE Vorgang Info = 0|  
|512 KB und 4G - 8-Byte|UWOP_ALLOC_LARGE Vorgang Info = 1|  
  
 UWOP_SET_FPREG (3) 1 Knoten  
  
 Richten Sie das Framezeigerregister durch Festlegen der Register einen Offset vom aktuellen RSP angeben. Der Offset ist gleich der Frame registrieren Offset Feld (skaliert) in UNWIND_INFO * 16, sodass Offsets von 0 bis 240. Die Verwendung eines Offsets ermöglicht die Frame-Pointer, die auf die Mitte der festen stapelzuordnung helfen Code Dichte können weitere Zugriffe auf die kurze instruktionsformen verwenden verweist einrichten. Beachten Sie, dass der Vorgang Info-Feld reserviert ist und nicht verwendet werden sollte.  
  
 UWOP_SAVE_NONVOL (4) 2 Knoten  
  
 Ein nicht veränderliches Ganzzahlregister gespeichert, auf dem Stapel mit einem MOV anstelle eines PUSH. Dies wird hauptsächlich für die Komprimierung, verwendet, in dem ein nicht flüchtiges Register auf den Stapel an einer Position gespeichert ist, der zuvor zugewiesen wurde. Das Vorgang Info ist die Anzahl des Registers. Der Stapeloffset skaliert-by-8-wird aufgezeichnet, in der nächsten Vorgangscode Slot, entladen, wie zuvor beschrieben.  
  
 UWOP_SAVE_NONVOL_FAR (5) 3 Knoten  
  
 Ein nicht veränderliches Ganzzahlregister gespeichert, auf dem Stapel mit einem langen Offset, der mit einem MOV anstelle eines PUSH. Dies wird hauptsächlich für die Komprimierung, verwendet, in dem ein nicht flüchtiges Register auf den Stapel an einer Position gespeichert ist, der zuvor zugewiesen wurde. Das Vorgang Info ist die Anzahl des Registers. Der Stapeloffset nicht skalierten wird aufgezeichnet, in der nächsten zwei Vorgangscode Slots entladen, wie zuvor beschrieben.  
  
 UWOP_SAVE_XMM128 (8) 2 Knoten  
  
 Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel. Das Vorgang Info ist die Anzahl des Registers. Der Stapeloffset skaliert 16 wird im nächsten Slot aufgezeichnet.  
  
 UWOP_SAVE_XMM128_FAR (9) 3 Knoten  
  
 Speichern Sie alle 128 Bits von einem nichtflüchtigen XMM registrieren, auf dem Stapel mit einem langen Offset. Das Vorgang Info ist die Anzahl des Registers. Der Stapeloffset nicht skalierten wird in den nächsten beiden Slots aufgezeichnet.  
  
 UWOP_PUSH_MACHFRAME (10) 1 Knoten  
  
 Bewirken Sie, dass einen Computer Frame.  Dies wird verwendet, um die Auswirkung eines Hardware-Interrupt oder Ausnahme aufzuzeichnen. Es gibt zwei Formen. Wenn das Vorgang Info gleich 0 ist, hat die folgenden auf dem Stapel abgelegt wurden:  
  
|||  
|-|-|  
|RSP + 32|SS|  
|RSP + 24|Alte RSP|  
|RSP + 16|EFLAGS|  
|RSP + 8|CS|  
|RSP|RIP|  
  
 Die Vorgang-Infos 1, gleich, und klicken Sie dann die folgenden stattdessen verschoben wurden:  
  
|||  
|-|-|  
|RSP + 40|SS|  
|RSP + 32|Alte RSP|  
|RSP + 24|EFLAGS|  
|RSP + 16|CS|  
|RSP + 8|RIP|  
|RSP|Fehlercode|  
  
 Dieser Code entladen wird immer in eine dummy-Prolog angezeigt, die tatsächlich nie ausgeführt wird, jedoch stattdessen vor der tatsächlichen Einstiegspunkt eine Interrupt-Routine angezeigt wird, und dient nur dazu, um einen Ort zum Simulieren der Push eines Rahmens Computer verfügbar zu machen. UWOP_PUSH_MACHFRAME zeichnet diese Simulation gibt an, dass der Computer konzeptionell Folgendes ausgeführt wurde:  
  
 POP-RIP Rückgabeadresse vom Anfang des Stapels in *Temp*  
  
 Push-SS  
  
 Ablegen des alten RSP  
  
 Der EFLAGS  
  
 Push-CS  
  
 Mithilfe von Push übertragen *Temp*  
  
 Push-Fehlercode (falls Op Info 1 ist)  
  
 Das simulierte UWOP_PUSH_MACHFRAME Operation dekrementiert RSP um 40 (Op Info ist 0) oder 48 (Op Info ist 1).  
  
 **Vorgang info**  
 Die Bedeutung dieser 4 Bits richtet sich nach dem Vorgangscode. Um eine allgemeine (Integer) registrieren zu codieren, wird die folgende Zuordnung verwendet:  
  
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