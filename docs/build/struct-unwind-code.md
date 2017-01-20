---
title: "struct UNWIND_CODE"
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
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# struct UNWIND_CODE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Entladecode\-Array wird zum Aufzeichnen der Folge von Vorgängen im Prolog verwendet, die sich auf nicht veränderliche Register und RSP auswirken.  Jedes Codeelement hat das folgende Format:  
  
|||  
|-|-|  
|UBYTE|Offset im Prolog|  
|UBYTE: 4|Entladeoperationscode|  
|UBYTE: 4|Operationsinfo|  
  
 Das Array wird in absteigender Reihenfolge des Offsets im Prolog sortiert.  
  
 **Offset im Prolog**  
 Offset vom Anfang des Prologs vom Ende der Anweisung, die diese Operation ausführt, plus 1 \(d. h. der Offset des Starts der nächsten Anweisung\).  
  
 **Entladeoperationscode**  
 Hinweis: Bestimmte Operationscodes erfordern einen Offset ohne Vorzeichen für einen Wert im lokalen Stapelrahmen.  Dies ist ein Offset vom Anfang \(der niedrigsten Adresse\) der festen Stapelzuweisung.  Wenn das Frameregisterfeld in UNWIND\_INFO 0 \(null\) ist, ist dies ein Offset von RSP.  Wenn das Frameregisterfeld einen Wert ungleich 0 \(null\) hat, ist dies der Offset vom Speicherort von RSP zum Zeitpunkt der Einrichtung von FP reg.  Dies entspricht FP reg minus dem FP reg\-Offset \(16 \* der skalierte Frameregisteroffset in UNWIND\_INFO\).  Wenn ein FP reg verwendet wird, kann ein Entladecode mit einem Offset erst verwendet werden, nachdem im Prolog FP reg eingerichtet wurde.  
  
 Bei allen Opcodes mit Ausnahme von UWOP\_SAVE\_XMM128 und UWOP\_SAVE\_XMM128\_FAR ist der Offset immer ein Vielfaches von 8, da alle relevanten Stapelwerte auf 8\-Byte\-Grenzen gespeichert sind \(der Stapel selbst ist stets in 16 Byte ausgerichtet\).  Bei Operationscodes mit kurzem Offset \(weniger als 512 K\) enthält der letzte USHORT in den Knoten für diesen Code den Offset geteilt durch 8.  Bei Operationscodes mit langem Offset \(512 K \<\= Offset \< 4 GB\) enthalten die letzten beiden USHORT\-Knoten für diesen Code den Offset \(im Little\-Endian\-Format\).  
  
 Bei den Opcodes UWOP\_SAVE\_XMM128 und UWOP\_SAVE\_XMM128\_FAR ist der Offset immer ein Vielfaches von 16, da alle 128\-Bit\-XMM\-Operationen in einem in 16 Byte ausgerichteten Speicher erfolgen müssen.  Deshalb wird ein Skalierungsfaktor von 16 für UWOP\_SAVE\_XMM128 verwendet, der Offsets von weniger als 1 M erlaubt.  
  
 Für den Entladeoperationscode gibt es folgende Möglichkeiten:  
  
 UWOP\_PUSH\_NONVOL \(0\)1 Knoten  
  
 Ein nicht veränderliches Ganzzahlregister wird verschoben und RSP um 8 dekrementiert.  Die Operationsinfo ist die Anzahl der Register.  Beachten Sie, dass aufgrund der Beschränkungen für Epiloge UWOP\_PUSH\_NONVOL\-Entladecodes zuerst im Prolog und dementsprechend zuletzt im Entladecode\-Array auftreten müssen.  Diese relative Anordnung gilt mit Ausnahme von UWOP\_PUSH\_MACHFRAME für alle anderen Entladecodes.  
  
 UWOP\_ALLOC\_LARGE \(1\)2 oder 3 Knoten  
  
 Zuweisen eines großen Bereichs auf dem Stapel.  Dies kann in zwei Formen erfolgen.  Wenn die Operationsinfo gleich 0 \(null\) ist, wird die Größe der Zuweisung geteilt durch 8 im nächsten Slot aufgezeichnet, sodass eine Zuweisung bis zu 512 K – 8 möglich ist.  Wenn die Operationsinfo 1 ist, wird die unskalierte Größe der Zuweisung im Little\-Endian\-Format in den nächsten beiden Slots aufgezeichnet, sodass Zuweisungen bis zu 4 GB – 8 möglich sind.  
  
 UWOP\_ALLOC\_SMALL \(2\)1 Knoten  
  
 Zuweisen eines kleinen Bereichs auf dem Stapel.  Die Größe der Zuweisung ist das Operationsinfofeld \* 8 \+ 8, sodass Zuweisungen von 8 bis 128 Byte möglich sind.  
  
 Für den Entladecode für eine Stapelreservierung sollte immer eine so kurze Codierung wie möglich verwendet werden:  
  
|||  
|-|-|  
|**Zuweisungsgröße**|**Entladecode**|  
|8 bis 128 Byte|UWOP\_ALLOC\_SMALL|  
|136 bis 512 K \- 8\-Byte|UWOP\_ALLOC\_LARGE, Operationsinfo \= 0|  
|512 K bis 4 G \- 8 Byte|UWOP\_ALLOC\_LARGE, Operationsinfo \= 1|  
  
 UWOP\_SET\_FPREG \(3\)1 Knoten  
  
 Erstellen Sie das Framezeigerregister, indem Sie für das Register einen Offset vom aktuellen RSP angeben.  Der Offset entspricht dem Frameregisteroffset\-Feld \(skaliert\) in UNWIND\_INFO \* 16 mit möglichen Offsets von 0 bis 240.  Die Verwendung eines Offsets erlaubt die Erstellung eines Framezeigers, der auf die Mitte der festen Stapelzuweisung verweist. Dies unterstützt eine höhere Codedichte, da mehr Zugriffe für die Verwendung kurzer Anweisungsformen möglich sind.  Beachten Sie, dass das Operationsinfofeld reserviert ist und nicht verwendet werden sollte.  
  
 UWOP\_SAVE\_NONVOL \(4\)2 Knoten  
  
 Ein nicht veränderliches Ganzzahlregister wird auf dem Stapel mit einem MOV anstelle eines PUSH gespeichert.  Dies wird hauptsächlich zum platzsparenden Verpacken verwendet, bei dem ein nicht veränderliches Register auf dem Stapel in einer zuvor zugewiesenen Position gespeichert wird.  Die Operationsinfo ist die Anzahl der Register.  Der um 8 skalierte Stapeloffset wird im nächsten Entladeoperationscode\-Slot aufgezeichnet, wie im Hinweis oben beschrieben.  
  
 UWOP\_SAVE\_NONVOL\_FAR \(5\)3 Knoten  
  
 Ein nicht veränderliches Ganzzahlregister wird auf dem Stapel mit langem Offset gespeichert, wobei ein MOV anstelle eines PUSH verwendet wird.  Dies wird hauptsächlich zum platzsparenden Verpacken verwendet, bei dem ein nicht veränderliches Register auf dem Stapel in einer zuvor zugewiesenen Position gespeichert wird.  Die Operationsinfo ist die Anzahl der Register.  Der unskalierte Stapeloffset wird in den nächsten beiden Entladeoperationscode\-Slots aufgezeichnet, wie im Hinweis oben beschrieben.  
  
 UWOP\_SAVE\_XMM128 \(8\)2 Knoten  
  
 Die gesamten 128 Bits eines nicht veränderlichen XMM\-Registers werden auf dem Stapel gespeichert.  Die Operationsinfo ist die Anzahl der Register.  Der um 16 skalierte Stapeloffset wird im nächsten Slot aufgezeichnet.  
  
 UWOP\_SAVE\_XMM128\_FAR \(9\)3 Knoten  
  
 Die gesamten 128 Bits eines nicht veränderlichen XMM\-Registers werden auf dem Stapel mit einem langen Offset gespeichert.  Die Operationsinfo ist die Anzahl der Register.  Der unskalierte Stapeloffset wird in den nächsten beiden Slots aufgezeichnet.  
  
 UWOP\_PUSH\_MACHFRAME \(10\)1 Knoten  
  
 Verschieben eines Computerframes.  Dies wird verwendet, um die Auswirkungen eines Hardware\-Interrupts oder einer Ausnahme aufzuzeichnen.  Dies kann in zwei Formen erfolgen.  Wenn die Operationsinfo 0 \(null\) ist, wurde Folgendes auf dem Stapel abgelegt:  
  
|||  
|-|-|  
|RSP\+32|SS|  
|RSP\+24|Alter RSP|  
|RSP\+16|EFLAGS|  
|RSP\+8|CS|  
|RSP|RIP|  
  
 Ist die Operationsinfo 1, wurde stattdessen Folgendes abgelegt:  
  
|||  
|-|-|  
|RSP\+40|SS|  
|RSP\+32|Alter RSP|  
|RSP\+24|EFLAGS|  
|RSP\+16|CS|  
|RSP\+8|RIP|  
|RSP|Fehlercode|  
  
 Dieser Entladecode tritt stets in einem Platzhalter\-Prolog auf, der nie tatsächlich ausgeführt wird, sondern vor dem wirklichen Einstiegspunkt einer Interruptroutine als Platzhalter für die Simulation der Verschiebung eines Computerframes dient.  UWOP\_PUSH\_MACHFRAME zeichnet diese Simulation auf, die angibt, dass der Computer konzeptuell wie folgt vorgegangen ist:  
  
 Auslesen der RIP\-Rückgabeadresse oben im Stapel in *Temp*  
  
 Ablegen von SS  
  
 Ablegen des alten RSP  
  
 Ablegen der EFLAGS  
  
 Ablegen von CS  
  
 Ablegen von *Temp*  
  
 Ablegen des Fehlercodes \(wenn op info 1 ist\)  
  
 Die simulierte UWOP\_PUSH\_MACHFRAME\-Operation dekrementiert RSP um 40 \(op info ist 0\) oder um 48 \(op info ist 1\).  
  
 **Operationsinfo**  
 Die Bedeutung dieser 4 Bits ist abhängig vom Operationscode.  Für die Codierung eines Allzweckregisters \(ganzzahlig\) wird folgende Zuordnung verwendet:  
  
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
|8 bis 15|R8 to R15|  
  
## Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)