---
title: X64 Prolog und Epilog
ms.date: 12/17/2018
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
ms.openlocfilehash: be6a344b75fdc0cbc1876a250d0cc326bae43ccc
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418593"
---
# <a name="x64-prolog-and-epilog"></a>X64 Prolog und Epilog

Jede Funktion, die den Stapelspeicher zuweist, Aufrufen anderer Funktionen, nicht flüchtigen Register gespeichert oder mithilfe der Ausnahmebehandlung einen Prolog müssen, deren Adresse Grenzwerte im Zusammenhang mit der jeweiligen Funktionstabelleneintrag Entladedaten beschrieben werden. Weitere Informationen finden Sie unter [X64 Ausnahmebehandlung](../build/exception-handling-x64.md). Der Prolog speichert Argument Registern in der ihre privaten Adressen bei Bedarf legt nicht volatile Register auf den Stapel, ordnet die festen Bestandteil des Stapels für lokale Variablen und die temporären Dateien und optional richtet Frame-Pointer. Die zugeordnete Entladung der Daten muss die Aktion der Prolog beschreiben, und geben Sie müssen die erforderlichen Informationen für die Auswirkungen der Prologcode rückgängig zu machen.

Wenn die feste Zuordnung im Stapel mehr als eine Seite ist (d. h. größer als 4096 Bytes), ist es möglich, dass die Stack-gesamtzuordnung mehr als eine Seite des virtuellen Speichers umfassen kann und daher die Zuordnung muss überprüft werden, bevor es zugewiesen ist. Eine spezielle Routine, die von der Prolog ist und die nicht Zerstören eines Register Argument, wird für diesen Zweck bereitgestellt.

Die bevorzugte Methode zum Speichern von nicht volatile Register ist auf den Stapel vor dem festen stapelreservierung verschieben. Wenn die festen Stapelreservierungsgröße ausgeführt wird, bevor die nicht flüchtigen Register gespeichert werden, ist wahrscheinlich eine 32-Bit-Verschiebung erforderlich, um den gespeicherten Register-Bereich zu beheben. (Berichten nach, sind Pushbenachrichtigungen von Registern so schnell wie verschoben und in absehbarer trotz der implizite Abhängigkeit zwischen Pushvorgänge bleiben sollten.) Nicht volatile Register können in beliebiger Reihenfolge gespeichert werden. Allerdings muss die erste Verwendung von einem nicht flüchtigen Register im Prolog sein, um ihn zu speichern.

## <a name="prolog-code"></a>Prologcode

Der Code für einen typischen Prolog kann Folgendes sein:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    sub    RSP, fixed-allocation-size
    lea    R13, 128[RSP]
    ...
```

Dieser Prolog speichert das Argument Register RCX an ihrem privaten Speicherort, speichert permanenten Register R13-R15 reserviert den festen Teil des Stapelrahmens und richtet die Frame-Pointer, die von 128 Byte in den Bereich für feste Zuweisung verweist. Mit einem Offset kann mehrere Bereich feste Zuweisung mit 1-Byte-Offsets behandelt werden.

Ist die feste Zuordnungsgröße größer als oder gleich auf eine Seite des Arbeitsspeichers, muss eine Hilfsfunktion aufgerufen werden, bevor RSP geändert wird. Dieses Hilfsprogramm, `__chkstk`, Tests des Bereichs zu zuzuweisenden Stack, um sicherzustellen, dass der Stapel ordnungsgemäß erweitert wird. In diesem Fall würde das vorherige Beispiel für den Prolog stattdessen Folgendes stehen:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    mov    RAX,  fixed-allocation-size
    call   __chkstk
    sub    RSP, RAX
    lea    R13, 128[RSP]
    ...
```

Die `__chkstk` Hilfsprogramm ändert sich nicht auf anderen Register R10 R11 und die Bedingungscodes. Insbesondere wird RAX unverändert und lassen Sie alle nicht flüchtigen Register und Argumentübergabe Register bleiben unverändert.

## <a name="epilog-code"></a>Epilogcode

Epilogcode ist bei jeder Beendigung einer Funktion vorhanden. Während es normalerweise nur einen Prolog ist, können viele epilogen vorhanden sein. Epilogcode im Stapel auf die Größe der feste Zuweisung kürzt, (falls erforderlich), wird der feste stapelreservierung, wird Sie nicht flüchtigen Register wiederhergestellt, indem Sie die gespeicherten Werte aus dem Stapel entfernt und zurückgegeben.

Die Epilogcode muss einem strikter Regeln für die entladungscodes zuverlässig Entladung durch Ausnahmen und Interrupts einhalten. Diese Regeln Verringern der Anzahl der Entladung der Daten, die erforderlich sind, da keine zusätzlichen Daten zur Beschreibung der einzelnen Epiloge erforderlich ist. Stattdessen kann die entladungscodes, dass es sich bei einem Epilog ausgeführt wird, indem Sie über einen Codestream zum Identifizieren eines Epilogs vorwärtsspulen bestimmen.

Wenn keine Frame-Pointer, in verwendet wird die Funktion, und klicken Sie dann auf der Epilog muss zuerst die Zuweisung der festen Bestandteil des Stapels, die nicht flüchtigen Register per pop ausgelesen werden und wird die Steuerung an die aufrufende Funktion zurückgegeben. Ein auf ein Objekt angewendeter

```MASM
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

Wenn der Frame-Pointer in der Funktion verwendet wird, muss im Stapel auf seine feste Zuweisung vor der Ausführung des Epilogs entfernt werden. Diese Aktion ist genau genommen nicht Teil der Epilog. Beispielsweise könnte der folgende Epilog verwendet werden, den Prolog bislang rückgängig zu machen:

```MASM
    lea      RSP, -128[R13]
    ; epilogue proper starts here
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

In der Praxis Wenn Frame-Pointer verwendet wird, besteht kein guter Grund RSP in zwei Schritten anpassen, sodass stattdessen der folgende Epilog verwendet wird:

```MASM
    lea      RSP, fixed-allocation-size - 128[R13]
    pop      R13
    pop      R14
    pop      R15
    ret
```

Diese Formen werden nur eines Epilogs. Es muss entweder bestehen einer `add RSP,constant` oder `lea RSP,constant[FPReg]`, gefolgt von einer Reihe von NULL oder mehr 8-Byte-POP und `return` oder `jmp`. (Nur eine Teilmenge der `jmp` -Anweisungen sind im Epilog zulässig. Die Teilmenge wird ausschließlich für die Klasse der `jmp` ModRM Speicherverweise ModRM mod Feldwert, in denen 00 ist-Anweisungen. Die Verwendung von `jmp` Anweisungen in der Epilog mit ModRM mod Feldwert 01 oder 10 ist nicht zulässig. Finden Sie in Tabelle A-15 in der AMD X86-64-Architektur Programmer's manuelle Volume 3: Allgemeiner and System Instructions für Weitere Informationen zu den zulässigen ModRM-verweisen.) Es kann kein weiterer Code angezeigt. Insbesondere kann "nothing" in einem Epilog, einschließlich der beim Laden eines Rückgabewerts geplant werden.

Wenn der Frame-Pointer nicht verwendet wird, muss der Epilog verwenden `add RSP,constant` beim Aufheben der Zuordnung der festen Bestandteil des Stapels. Es können keine `lea RSP,constant[RSP]` stattdessen. Diese Einschränkung gilt, damit die entladungscodes weniger Muster zu erkennen, bei der Suche nach epilogen verfügt.

Befolgen diese Regeln kann die entladungscodes, um zu bestimmen, dass es sich bei einem Epilog derzeit ausgeführt wird und Ausführung von der Rest des Epilogs zu ermöglichen, den Kontext der aufrufenden Funktion neu zu simulieren.

## <a name="see-also"></a>Siehe auch

[Softwarekonventionen bei x64-Systemen](../build/x64-software-conventions.md)
