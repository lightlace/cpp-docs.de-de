---
title: "Entladeprozedur"
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
ms.assetid: 82c5d0ca-70be-4d1a-a306-bfe01c29159f
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Entladeprozedur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Entladecode\-Array wird in absteigender Reihenfolge sortiert.  Bei einer Ausnahme wird der vollständige Kontext vom Betriebssystem in einem Kontextdatensatz gespeichert.  Anschließend wird die Ausnahmeauslösung aufgerufen, die wiederholt die folgenden Schritte ausführt, um einen Ausnahmehandler zu finden.  
  
1.  Der aktuelle, im Kontextdatensatz gespeicherte RIP wird für die Suche nach einem RUNTIME\_FUNCTION\-Tabelleneintrag verwendet, der die aktuelle Funktion \(oder bei verketteten UNWIND\_INFO\-Einträgen einen Teil der Funktion\) beschreibt.  
  
2.  Wird kein Funktionstabelleneintrag gefunden, handelt es sich um eine Endfunktion, und RSP adressiert den Rückgabezeiger direkt.  Der Rückgabezeiger bei \[RSP\] ist im aktualisierten Kontext gespeichert, der simulierte RSP wird um 8 inkrementiert, und Schritt 1 wird wiederholt.  
  
3.  Wenn ein Funktionstabelleneintrag gefunden wird, kann RIP innerhalb von drei Bereichen liegen: a\) in einem Epilog, b\) im Prolog oder c\) in Code, der von einem Ausnahmehandler abgedeckt ist.  
  
    -   Fall a\): Wenn sich RIP innerhalb eines Epilogs befindet, dann gibt die Funktion die Steuerung ab: Der Ausnahme kann in dieser Funktion kein Ausnahmehandler zugeordnet sein, und die Auswirkungen des Epilogs müssen zur Berechnung des Kontexts der aufrufenden Funktion fortgesetzt werden.  Um zu bestimmen, ob RIP sich innerhalb eines Epilogs befindet, wird der Codestream ab RIP untersucht.  Wenn der Codestream mit dem abschließenden Teil eines gültigen Epilogs in Übereinstimmung gebracht werden kann, befindet er sich in einem Epilog. Der restliche Teil des Epilogs wird dann simuliert und der Kontextdatensatz bei der Verarbeitung der einzelnen Anweisungen jeweils aktualisiert.  Danach wird Schritt 1 wiederholt.  
  
    -   Fall b\): Wenn sich RIP innerhalb des Prologs befindet, wurde die Steuerung nicht an die Funktion übergeben: Der Ausnahme kann in dieser Funktion kein Ausnahmehandler zugeordnet werden, und die Auswirkungen des Prologs müssen zur Berechnung des Kontexts der aufrufenden Funktion rückgängig gemacht werden.  RIP befindet sich im Prolog, wenn der Abstand des Funktionsstarts zu RIP kleiner oder gleich der in den Entladeinformationen codierten Prologgröße ist.  Die Auswirkungen des Prologs werden entladen, indem das Entladecode\-Array vorwärts nach dem ersten Eintrag mit einem Offset durchsucht wird, der kleiner oder gleich dem Offset von RIP am Funktionsstart ist, und anschließend die Auswirkungen aller übrigen Elemente im Entladecode\-Array rückgängig gemacht werden.  Schritt 1 wird dann wiederholt.  
  
    -   Fall c\): Wenn RIP sich nicht in einem Prolog oder Epilog befindet und die Funktion einen Ausnahmehandler hat \(UNW\_FLAG\_EHANDLER ist festgelegt\), wird der sprachspezifische Handler aufgerufen.  Der Handler durchsucht seine Daten und ruft geeignete Filterfunktionenen auf.  Der sprachspezifische Handler kann zurückgeben, dass die Ausnahme verarbeitet wurde oder dass die Suche fortgesetzt wird.  Er kann auch direkt einen Entladevorgang initiieren.  
  
4.  Wenn der sprachspezifische Handler als Status eine Verarbeitung zurückgibt, wird die Ausführung unter Verwendung des ursprünglichen Kontextdatensatzes fortgesetzt.  
  
5.  Wenn kein sprachspezifischer Handler vorhanden ist oder der Handler den Status "Suche fortsetzen" zurückgibt, muss der Kontextdatensatz zum Status des Aufrufers entladen werden.  Dies geschieht durch eine Verarbeitung aller Entladecode\-Arrayelemente, bei der die Auswirkungen jedes einzelnen Elements rückgängig gemacht werden.  Schritt 1 wird dann wiederholt.  
  
 Auch wenn verkettete Entladeinformationen beteiligt sind, werden diese grundlegenden Schritte ausgeführt.  Der einzige Unterschied besteht darin, dass, beim Durchlaufen des Entladecode\-Arrays zum Entladen der Prologauswirkungen, bei Erreichen des Array\-Endes dieses mit den übergeordneten Entladeinformationen verknüpft und das gesamte dort vorhandene Entladecode\-Array durchlaufen wird.  Diese Verknüpfung wird so lange fortgesetzt, bis eine Entladeinformation ohne das UNW\_CHAINED\_INFO\-Flag erreicht und das Durchlaufen des Entladcode\-Arrays beendet wird.  
  
 Der kleinste Satz von Entladedaten hat eine Größe von 8 Byte.  Dies entspricht einer Funktion, die nur 128 Byte oder weniger auf dem Stapel reserviert und möglicherweise ein nicht veränderliches Register gespeichert hat.  Dies entspricht auch der Größe einer verketteten Entladeinformationstruktur für einen Prolog mit Nulllänge ohne Entladecodes.  
  
## Siehe auch  
 [Ausnahmebehandlung \(x64\)](../build/exception-handling-x64.md)