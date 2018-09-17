---
title: Prolog und Epilog | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c2a1a9b1891af1c5616e78932cf4a530a300786
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718873"
---
# <a name="prolog-and-epilog"></a>Prolog und Epilog

Jede Funktion, die den Stapelspeicher zuweist, in Aufrufe an andere Funktionen, nicht flüchtigen Register gespeichert oder mithilfe der Ausnahmebehandlung müssen einen Prolog, deren Adresse Grenzwerte finden Sie unter den Tabelleneintrag für die jeweilige Funktion zugeordneten Entladedaten (finden Sie unter [Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)). Prolog Argument Registern in der ihre Privatadressen, legt nicht volatile Register auf dem Stapel gespeichert, ordnet die festen Bestandteil des Stapels für lokale Variablen und die temporären Dateien, die und stellt optional ein Frame-Pointer her. Die zugeordnete Entladung der Daten muss die Aktion der Prolog beschreiben, und geben Sie müssen die erforderlichen Informationen für die Auswirkungen der Prologcode rückgängig zu machen.

Wenn die feste Zuordnung im Stapel mehr als eine Seite ist (d. h. größer als 4096 Bytes), ist es möglich, dass die Stack-gesamtzuordnung mehr als eine Seite des virtuellen Speichers umfassen kann und daher die Zuordnung muss überprüft werden, bevor es tatsächlich zugeordnet ist. Eine spezielle Routine, die von der Prolog ist und der zerstört keine der Register Argument, wird für diesen Zweck bereitgestellt.

Die bevorzugte Methode zum Speichern von nicht volatile Register ist auf den Stapel vor dem festen stapelreservierung verschieben. Wenn die festen Stapelreservierungsgröße ausgeführt wurden, bevor die nicht flüchtigen Register gespeichert wurden, wahrscheinlich eine 32-Bit-Verschiebung wäre erforderlich, um die Adresse registrieren Sie die gespeicherten Bereich (Berichten nach, Push-Vorgänge von Registern sind nur so schnell wie verschoben und bleiben sollte für absehbare trotz der implizite Abhängigkeit zwischen Push-Vorgänge). Nicht volatile Register können in beliebiger Reihenfolge gespeichert werden. Allerdings muss die erste Verwendung von einem nicht flüchtigen Register im Prolog sein, um ihn zu speichern.

Der Code für einen typischen Prolog kann Folgendes sein:

```
mov       [RSP + 8], RCX
push   R15
push   R14
push   R13
sub      RSP, fixed-allocation-size
lea      R13, 128[RSP]
...
```

Dieser Prolog speichert das Argument Register RCX an ihrem privaten Speicherort, speichert permanenten Register R13-R15 reserviert den festen Teil des Stapelrahmens und richtet die Frame-Pointer, die von 128 Byte in den Bereich für feste Zuweisung verweist. Mit einem Offset kann mehrere Bereich feste Zuweisung mit 1-Byte-Offsets behandelt werden.

Ist die feste Zuordnungsgröße größer als oder gleich auf eine Seite des Arbeitsspeichers, muss eine Hilfsfunktion aufgerufen werden, bevor RSP geändert wird. Dieses Hilfsprogramm, __chkstk, ist verantwortlich für die Überprüfung des zu zuzuweisenden Stapelbereichs, um sicherzustellen, dass der Stapel ordnungsgemäß erweitert wird. In diesem Fall würde das vorherige Beispiel für den Prolog stattdessen Folgendes stehen:

```
mov       [RSP + 8], RCX
push   R15
push   R14
push   R13
mov      RAX,  fixed-allocation-size
call   __chkstk
sub      RSP, RAX
lea      R13, 128[RSP]
...
```

Das Hilfsprogramm __chkstk ändert sich nicht auf anderen Register R10 R11 und die Bedingungscodes aus. Insbesondere wird RAX unverändert und lassen Sie alle nicht flüchtigen Register und Argumentübergabe Register bleiben unverändert.

Epilogcode ist bei jeder Beendigung einer Funktion vorhanden. Während es normalerweise nur einen Prolog ist, können viele epilogen vorhanden sein. Epilogcode im Stapel auf die Größe der feste Zuweisung kürzt, (falls erforderlich), wird der feste stapelreservierung, wird Sie nicht flüchtigen Register wiederhergestellt, indem Sie die gespeicherten Werte aus dem Stapel entfernt und zurückgegeben.

Die Epilogcode muss einem strikter Regeln für die entladungscodes zuverlässig Entladung durch Ausnahmen und Interrupts einhalten. Dies reduziert die Menge der Entladung der Daten, die erforderlich sind, da keine zusätzlichen Daten zur Beschreibung der einzelnen Epiloge erforderlich ist. Stattdessen kann die entladungscodes, dass es sich bei einem Epilog ausgeführt wird, indem Sie über einen Codestream zum Identifizieren eines Epilogs vorwärtsspulen bestimmen.

Wenn keine Frame-Pointer, in verwendet wird die Funktion, und klicken Sie dann auf der Epilog muss zuerst die Zuweisung der festen Bestandteil des Stapels, die nicht flüchtigen Register per pop ausgelesen werden und wird die Steuerung an die aufrufende Funktion zurückgegeben. Ein auf ein Objekt angewendeter

```
add      RSP, fixed-allocation-size
pop      R13
pop      R14
pop      R15
ret
```

Wenn der Frame-Pointer in der Funktion verwendet wird, muss im Stapel auf seine feste Zuweisung vor der Ausführung des Epilogs entfernt werden. Dies ist genau genommen nicht Teil der Epilog. Beispielsweise könnte der folgende Epilog verwendet werden, den Prolog bislang rückgängig zu machen:

```
lea      RSP, -128[R13]
; epilogue proper starts here
add      RSP, fixed-allocation-size
pop      R13
pop      R14
pop      R15
ret
```

In der Praxis Wenn Frame-Pointer verwendet wird, besteht kein guter Grund RSP in zwei Schritten anpassen, sodass stattdessen der folgende Epilog verwendet wird:

```
lea      RSP, fixed-allocation-size - 128[R13]
pop      R13
pop      R14
pop      R15
ret
```

Dies sind die einzigen gültigen Formen eines Epilogs. Es muss entweder bestehen einer `add RSP,constant` oder `lea RSP,constant[FPReg]`, gefolgt von einer Reihe von NULL oder mehr 8-Byte- sowie einen Rückgabewert oder eine "jmp". (Nur eine Teilmenge der Anweisungen von "jmp" im Epilog zulässig sind. Dies sind ausschließlich der Klasse des Jmps mit ModRM Speicher verweisen, in denen ModRM mod Feldwert 00. Die Verwendung von Jmps im Epilog mit 01 oder 10 mod Feldwert ModRM ist nicht zulässig. Siehe Tabelle A-15 in der AMD X86-64-Architektur Programmer's Manual Volume 3: Allgemeine and System Instructions für Weitere Informationen zu den zulässigen ModRM-verweisen.). Es kann kein weiterer Code angezeigt. Insbesondere kann "nothing" in einem Epilog, einschließlich der beim Laden eines Rückgabewerts geplant werden.

Beachten Sie, dass, wenn der Frame-Pointer nicht verwendet wird, der Epilog `add RSP,constant` beim Aufheben der Zuordnung der festen Bestandteil des Stapels. Es können keine `lea RSP,constant[RSP]` stattdessen. Diese Einschränkung gilt, damit die entladungscodes weniger Muster zu erkennen, bei der Suche nach epilogen verfügt.

Befolgen diese Regeln kann die entladungscodes, um zu bestimmen, dass es sich bei einem Epilog derzeit ausgeführt wird und Ausführung von der Rest des Epilogs zu ermöglichen, den Kontext der aufrufenden Funktion neu zu simulieren.

## <a name="see-also"></a>Siehe auch

[x64-Softwarekonventionen](../build/x64-software-conventions.md)