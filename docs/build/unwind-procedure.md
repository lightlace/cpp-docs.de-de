---
title: Entladeprozedur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 82c5d0ca-70be-4d1a-a306-bfe01c29159f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b8caa2be1528c26cf374637f3d0357847721de9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unwind-procedure"></a>Entladeprozedur
Das entladungscode-Array wird in absteigender Reihenfolge sortiert. Wenn eine Ausnahme auftritt, wird der vollständige Kontext vom Betriebssystem in einem Kontextdatensatz gespeichert. Die Ausnahme Dispatch-Logik wird dann aufgerufen, wird die wiederholt ausgeführt, die folgenden Schritte aus, um einen Ausnahmehandler gefunden.  
  
1.  Verwenden Sie die in den Kontextdatensatz gespeicherte RIP eines RUNTIME_FUNCTION-Tabelleneintrags gesucht, die die aktuelle Funktion (oder einen Teil der Funktion im Fall von verketteten UNWIND_INFO-Einträgen) beschreibt.  
  
2.  Wenn keine Funktion Tabelle-Eintrag gefunden wird, wird es wird eine Endfunktion und RSP geht es um das Zurücksetzen von Zeiger direkt. Das Zurücksetzen von Zeiger auf [RSP] ist im aktuellen Kontext gespeichert, der simulierte RSP 8 inkrementiert wird und Schritt 1 wird wiederholt.  
  
3.  Wenn eine Tabelle Funktionsstart gefunden wird, kann RIP liegen innerhalb von drei Bereichen a) in einem Epilog, b) im Prolog oder c) in Code, der von einem Ausnahmehandler abgedeckt werden kann.  
  
    -   Groß-/Kleinschreibung einer) wenn RIP innerhalb eines Epilogs dann Steuerelement ist die Funktion verlassen, kann kein Ausnahmehandler festgestellt, die dieser Ausnahme für diese Funktion zugeordnet ist und die Auswirkungen des Epilogs müssen im Rahmen der aufrufenden Funktion berechnet fortgesetzt werden. Um festzustellen, ob RIP innerhalb eines Epilogs, RIP-Codestream auf wird untersucht. Wenn dieser Codestream kann, um den abschließenden Teil eines gültigen Epilogs abgeglichen werden befindet sich im eines Epilogs und der verbleibende Teil des Epilogs simuliert wird, wird mit der Kontextdatensatz aktualisiert, da jede Anweisung verarbeitet. Danach wird Schritt 1 wiederholt.  
  
    -   Fall b) wenn RIP innerhalb der Prolog liegt, dann Steuerelement verfügt nicht über die Funktion eingegeben haben, treten möglicherweise keine Ausnahmehandler, die dieser Ausnahme für diese Funktion zugeordnet und die Auswirkungen der Prolog müssen rückgängig gemacht werden, um im Rahmen der aufrufenden Funktion zu berechnen. RIP befindet sich im Prolog, wenn der Abstand zwischen dem Start der Funktion und die RIP kleiner als oder gleich der Prolog-Größe, die in der Entladung Info codiert ist. Die Auswirkungen der Prolog sind Entladen von Scannen vorwärts durch die Entladung Codes Array für den ersten Eintrag mit einem Versatz kleiner als oder gleich dem Offset der Trennung vom Beginn Funktion, und klicken Sie dann rückgängig machen die Auswirkungen aller verbleibenden Elemente in das entladungscode-Array. Schritt 1 wird dann wiederholt.  
  
    -   Groß-/Kleinschreibung c) wenn RIP nicht innerhalb eines Prologs oder Epilogs und die Funktion befindet, verfügt über einen Ausnahmehandler (UNW_FLAG_EHANDLER festgelegt ist), und klicken Sie dann die sprachspezifischer Handler wird aufgerufen. Der Handler durchsucht seine Daten und Aufrufe Filterfunktionen nach Bedarf. Die Ausnahme behandelt wurde oder dass die Suche wird fortgesetzt werden, kann die sprachspezifischer Handler zurückgeben. Sie können auch direkt eine Entladung initiieren.  
  
4.  Wenn die sprachspezifischer Handler behandelten Status zurück, die Ausführung wird fortgesetzt, mit dem ursprünglichen Kontextdatensatz.  
  
5.  Wenn keine sprachspezifischer Handler vorhanden ist, oder der Handler den Status "Suche fortsetzen gibt", muss der Kontextdatensatz entladen in den Zustand des Aufrufers sein. Dies wird durch die Verarbeitung aller Entladung Array Codeelemente, die Auswirkungen der einzelnen Rückgängigmachen erreicht. Schritt 1 wird dann wiederholt.  
  
 Wenn verkettete entladen Info beteiligt ist, weiterhin diese grundlegenden Schritte befolgt werden. Der einzige Unterschied ist, dass während durchlaufen das entladungscode-Array um einen Prolog Effekte Entladung nach des Endes des Arrays erreichen an, klicken Sie dann mit ist des übergeordnete Entladung Infos verknüpft und das gesamte entladungscode-Array gefunden wird durchlaufen. Diese Verknüpfung wird fortgesetzt, bis die, die bei einer Entladung Info ohne das UNW_CHAINED_INFO-Flag und das durchlaufen seiner entladungscode-Array.  
  
 Die kleinste Menge der Entladedaten umfasst 8 Bytes. Dies würde eine Funktion dar, die nur 128 Byte des Stapels oder weniger zugewiesen und möglicherweise einen nicht flüchtiges Register gespeichert. Dies ist auch die Größe einer verketteten Info-Struktur für eine leere Prolog mit keine entladungscodes entladen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)