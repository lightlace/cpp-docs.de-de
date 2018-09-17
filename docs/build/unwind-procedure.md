---
title: Entladeprozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 82c5d0ca-70be-4d1a-a306-bfe01c29159f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 294353baf8c15818ba836bd3093226a78aa6e44c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700653"
---
# <a name="unwind-procedure"></a>Entladeprozedur

Das entladungscode-Array wird in absteigender Reihenfolge sortiert. Wenn eine Ausnahme auftritt, wird der vollständige Kontext vom Betriebssystem in einem Kontextdatensatz gespeichert. Die Dispatch-Exception-Logik wird dann aufgerufen, die wird wiederholt ausgeführt, die folgenden Schritte aus, um einen Ausnahmehandler zu finden.

1. Verwenden Sie die aktuelle RIP, die im Kontextdatensatz gespeichert, um Tabelleneintrag RUNTIME_FUNCTION gesucht, die die aktuelle Funktion (oder einen Teil der Funktion, im Fall von verketteten UNWIND_INFO-Einträgen) beschreibt.

1. Wenn kein Funktionstabelleneintrag gefunden wird, ist es in einer untergeordneten Funktion aus, und RSP geht es um das Zurücksetzen von Zeiger direkt. Der Zurücksetzen von Zeiger auf [RSP] befindet sich im aktuellen Kontext, der simulierte RSP um 8 erhöht und Schritt 1 wiederholt wird.

1. Wenn ein Funktionstabelleneintrag gefunden wird, kann RIP liegen, in drei Regionen (a) in einem Epilog, (b) im Prolog oder (c) in Code, der von einem Ausnahmehandler behandelt werden kann.

   - Groß-/Kleinschreibung einer) wenn RIP befindet sich in einem Epilog, dann Steuerelement ist die Funktion wird beendet, es keinen Ausnahmehandler, der dieser Ausnahme für diese Funktion zugeordnet darf und Sie die Auswirkungen des Epilogs fortsetzen müssen, im Rahmen der aufrufenden Funktion berechnet. Um zu bestimmen, ob die RIP innerhalb eines Epilogs, der Codestream, aus der RIP auf werden untersucht. Wenn der Codestream mit den abschließenden Teil eines gültigen Epilogs abgeglichen werden kann und es in einem Epilog ist und im weiteren Verlauf des Epilogs wird simuliert, wird mit der Kontextdatensatz aktualisiert, während jede Anweisung verarbeitet. Danach wird der Schritt 1 wiederholt.

   - Fall b) Wenn der RIP im Prolog liegt, und klicken Sie dann die Kontrolle nicht der Fall ist die Funktion eingegeben, es darf keinen Ausnahmehandler, der dieser Ausnahme für diese Funktion zugeordnet, und die Auswirkungen der Prolog müssen rückgängig gemacht werden, um den Kontext der aufrufenden Funktion zu berechnen. RIP befindet sich im Prolog, wenn der Abstand zwischen dem Start der Funktion und die RIP kleiner als oder gleich der Prolog-Größe, die in den Entladeinformationen codiert ist. Die Auswirkungen der Prolog werden entladen, indem Sie über das Array für den ersten Eintrag mit einem Offset kleiner oder gleich dem Offset des RIP Funktionsstarts Entladung vorwärtsspulen und anschließend rückgängig machen die Auswirkungen aller verbleibenden Elemente in das entladungscode-Array. Schritt 1 wird wiederholt.

   - Groß-/Kleinschreibung c) ist die RIP nicht innerhalb eines Prologs oder Epilogs und die Funktion wurde einen Ausnahmehandler (UNW_FLAG_EHANDLER festgelegt ist), und dann die sprachspezifischer Handler wird aufgerufen. Der Handler überprüft die Daten und Filterfunktionen für Aufrufe nach Bedarf. Die sprachspezifischer Handler kann zurückgeben, oder, dass die Ausnahme behandelt wurde, dass bei der Suche wird fortgesetzt werden. Sie können auch direkt eine Entladung initiieren.

1. Wenn die sprachspezifischer Handler behandelten Status zurück, die Ausführung wird fortgesetzt, mit dem ursprünglichen Kontextdatensatz.

1. Wenn keine sprachspezifischer Handler vorhanden ist, oder der Handler für den Status "Suche fortsetzen" zurück, muss der Kontextdatensatz entladen in den Zustand des Aufrufers sein. Dies erfolgt durch die Verarbeitung aller Entladung Codeelemente des Arrays, die Auswirkungen der einzelnen rückgängig. Schritt 1 wird wiederholt.

Wenn verkettete entladen beteiligt, weiterhin diese grundlegenden Schritte befolgt werden. Der einzige Unterschied ist, dass beim durchlaufen, um einen Prolog der Effekte, entladen, erreichen das Ende des Arrays des entladungscode-Arrays, klicken Sie dann mit den übergeordneten Entladeinformationen verknüpft und das gesamte entladungscode-Array gefunden. es wird. Diese Verknüpfung wird fortgesetzt, bis ein Entladeinformationen ohne das Flag UNW_CHAINED_INFO eintreffen und das Durchlaufen der entladungscode-Array.

Die kleinste Menge der Entladung der Daten ist 8 Byte. Dies würde eine Funktion dar, die nur 128 Byte des Stapels oder weniger zugeordnet, möglicherweise einen nicht flüchtiges Register. Dies ist auch die Größe einer verketteten Informationsstruktur für eine Zeichenfolge der Länge Null Prolog mit keine entladungscodes entladen.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)