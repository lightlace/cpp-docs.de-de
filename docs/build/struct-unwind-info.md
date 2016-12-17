---
title: "struct UNWIND_INFO"
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
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# struct UNWIND_INFO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Entladedateninformationsstruktur wird zum Aufzeichnen der Auswirkungen einer Funktion auf den Stapelzeiger und des Speicherorts der nicht flüchtigen Register auf dem Stapel verwendet:  
  
|||  
|-|-|  
|UBYTE: 3|Version|  
|UBYTE: 5|Flags|  
|UBYTE|Größe des Prologs|  
|UBYTE|Anzahl der Entladecodes|  
|UBYTE: 4|Rahmenregister|  
|UBYTE: 4|Rahmenregisteroffset \(skaliert\)|  
|USHORT \* n|Entladecode\-Array|  
|variable|Kann die Form \(1\) oder \(2\) haben, wie unten angegeben|  
  
 \(1\) Ausnahmehandler  
  
|||  
|-|-|  
|ULONG|Adresse des Ausnahmehandlers|  
|variable|Sprachspezifische Handlerdaten \(optional\)|  
  
 \(2\) Entladungs\-Informationen verkettete  
  
|||  
|-|-|  
|ULONG|Adresse des Funktionsanfangs|  
|ULONG|Adresse des Funktionsendes|  
|ULONG|Adresse der Entladeinformationen|  
  
 Die UNWIND\_INFO\-Struktur muss im Arbeitsspeicher auf DWORD\-Grenzen ausgerichtet sein.  Die einzelnen Felder haben folgende Bedeutung:  
  
 **Version**  
 Versionsnummer der Entladedaten, gegenwärtig 1.  
  
 **Flags**  
 Drei Flags sind gegenwärtig definiert:  
  
 UNW\_FLAG\_EHANDLER die Funktion verfügt über einen Ausnahmehandler, der aufgerufen werden soll, wenn Sie nach Funktionen findet, die Ausnahmen überprüfen müssen.  
  
 UNW\_FLAG\_UHANDLER die Funktion verfügt über einen Beendigungshandler, der aufgerufen werden soll, wenn eine Ausnahme entlädt.  
  
 Entladungs\-Informationsstruktur UNW\_FLAG\_CHAININFO ist diese nicht das primäre für die Prozedur.  Vielmehr handelt es sich beim verketteten Entladeinformationseintrag um den Inhalt eines vorhergehenden RUNTIME\_FUNCTION\-Eintrags.  Eine Erklärung verketteter Entladeinformationsstrukturen finden Sie im folgenden Text.  Wenn dieses Flag festgelegt ist, müssen die Flags UNW\_FLAG\_EHANDLER und UNW\_FLAG\_UHANDLER gelöscht werden.  Außerdem müssen das Rahmenregisterfeld und das feste Stapelzuweisungsfeld dieselben Werte haben wie in den primären Entladeinformationen.  
  
 **Größe des Prologs**  
 Länge des Funktionsprologs in Byte.  
  
 **Anzahl der Entladecodes**  
 Dies ist die Anzahl der Slots im Entladecode\-Array.  Beachten Sie, dass einige Entladecodes \(z. B. UWOP\_SAVE\_NONVOL\) mehr als einen Slot im Array einnehmen.  
  
 **Rahmenregister**  
 Bei einem Wert ungleich 0 \(null\) verwendet die Funktion einen Framezeiger, und dieses Feld gibt die Anzahl der nicht flüchtigen Register an, die als Framezeiger verwendet werden. Dieselbe Codierung wird für das Operationsinfofeld der UNWIND\_CODE\-Knoten verwendet.  
  
 **Rahmenregisteroffset \(skaliert\)**  
 Wenn das Rahmenregisterfeld einen Wert ungleich 0 \(null\) hat, ist dieser Wert der skalierte Offset von RSP, der für FP reg übernommen wird, wenn es eingerichtet ist.  Der tatsächliche Wert von FP reg ist RSP \+ 16 \* diese Zahl, sodass Offsets von 0 bis 240 möglich sind.  Dadurch kann FP reg bei dynamischen Stapelrahmen auf die Mitte der lokalen Stapelzuweisung verweisen, um eine höhere Codedichte durch kürzere Anweisungen zu erzielen \(es können mehr Anweisungen den signierten 8\-Bit\-Offset verwenden\).  
  
 **Entladecode\-Array**  
 Dies ist ein Array von Elementen, das die Auswirkungen des Prologs auf die nicht flüchtigen Register und RSP angibt.  Informationen zu den Bedeutungen der einzelnen Elemente finden Sie im Abschnitt zu UNWIND\_CODE.  Aus Ausrichtungsgründen hat dieses Array stets eine gerade Anzahl von Einträgen, wobei der letzte Eintrag potenziell nicht verwendet wird \(in diesem Fall ist das Array um einen Eintrag länger als durch den Zähler im Entladecodefeld angegeben\).  
  
 **Adresse des Ausnahmehandlers**  
 Hierbei handelt es sich um einen bildbezogenen Zeiger auf die sprachspezifische Ausnahme oder den Beendigungshandler der Funktion \(wenn das Flag UNW\_FLAG\_CHAININFO nicht festgelegt und eines der Flags UNW\_FLAG\_EHANDLER oder UNW\_FLAG\_UHANDLER festgelegt ist\).  
  
 **Sprachspezifische Handlerdaten**  
 Dies sind die sprachspezifischen Ausnahmehandlerdaten der Funktion.  Das Format dieser Daten ist nicht festgelegt und wird vollständig durch den verwendeten sprachspezifischen Ausnahmehandler bestimmt.  
  
 **Verkettete Entladeinformationen**  
 Wenn das UNW\_FLAG\_CHAININFO\-Flag festgelegt ist, endet die UNWIND\_INFO\-Struktur mit drei UWORDs.  Diese UWORDs stellen die RUNTIME\_FUNCTION\-Informationen für die Funktion des verketteten Entladevorgangs dar.  
  
## Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)