---
title: "Hardwareausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fehler [C++], Hardware"
  - "Fehler [C++], Auf niedriger Ebene"
  - "Ausnahmen, Hardware"
  - "Hardwareausnahmen"
  - "Fehler auf niedriger Ebene"
ms.assetid: 06ac6f01-a8cf-4426-bb12-1688315ae1cd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Hardwareausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten Standardausnahmen, die vom Betriebssystem erkannt werden, sind Hardware\-definierte Ausnahmen.  Windows erkennt einige Softwareausnahmen auf niedriger Ebene, doch diese werden normalerweise am besten vom Betriebssystem selbst behandelt.  
  
 Windows ordnet die Hardwarefehler der verschiedenen Prozessoren den Ausnahmecodes in diesem Abschnitt zu.  In manchen Fällen generiert ein Prozessor möglicherweise nur eine Teilmenge dieser Ausnahmen.  Windows verarbeitet Informationen zur Ausnahme vor und gibt den entsprechenden Ausnahmecode aus.  
  
 Die Hardwareausnahmen, die von Windows erkannt werden, werden in der folgenden Tabelle zusammengefasst:  
  
|Ausnahmecode|Ursache der Ausnahme|  
|------------------|--------------------------|  
|**STATUS\_ACCESS\_VIOLATION**|Lesen oder Schreiben in einer Speicheradresse, auf die nicht zugegriffen werden kann.|  
|**STATUS\_BREAKPOINT**|Auftreten eines Hardware\-definierten Haltepunkts. Nur von Debuggern verwendet.|  
|**STATUS\_DATATYPE\_MISALIGNMENT**|Lesen oder Schreiben in Daten unter einer Adresse, die nicht ordnungsgemäß ausgerichtet ist. Beispielsweise müssen 16\-Bit\-Entitäten auf 2\-Byte\-Begrenzungen ausgerichtet sein. \(Nicht anwendbar auf Intel 80*x*86\-Prozessoren.\)|  
|**STATUS\_FLOAT\_DIVIDE\_BY\_ZERO**|Teilen des Gleitkommatyps durch 0,0.|  
|**STATUS\_FLOAT\_OVERFLOW**|Überschreiten des maximalen positiven Exponenten eines Gleitkommatyps.|  
|**STATUS\_FLOAT\_UNDERFLOW**|Überschreiten der Größe des niedrigsten negativen Exponenten eines Gleitkommatyps.|  
|**STATUS\_FLOATING\_RESEVERED\_OPERAND**|Verwenden eines reservierten Gleitkommaformats \(ungültige Verwendung von Format\).|  
|**STATUS\_ILLEGAL\_INSTRUCTION**|Versuch, einen Anweisungscode auszuführen, der nicht vom Prozessor definiert ist.|  
|**STATUS\_PRIVILEGED\_INSTRUCTION**|Ausführen einer Anweisung, die nicht im aktuellen Computermodus zulässig ist.|  
|**STATUS\_INTEGER\_DIVIDE\_BY\_ZERO**|Teilen eines ganzzahligen Typs durch 0.|  
|**STATUS\_INTEGER\_OVERFLOW**|Versuch, einen Vorgang auszuführen, der den Ganzzahlbereich übersteigt.|  
|**STATUS\_SINGLE\_STEP**|Ausführen einer Anweisung im einschrittigen Modus. Nur von Debuggern verwendet.|  
  
 Viele der Ausnahmen, die in der vorherigen Tabelle aufgelistet sind, sollen von Debuggern, dem Betriebssystem oder einem anderen Code auf niedriger Ebene behandelt werden.  Mit Ausnahme von Ganzzahl\- und Gleitkommafehlern sollte der Code diese Fehler nicht verarbeiten.  Daher sollten Sie normalerweise den Ausnahmebehandlungsfilter verwenden, um Ausnahmen zu ignorieren \(ergibt 0\).  Andernfalls hindern Sie Mechanismen auf niedrigerer Ebene möglicherweise daran, entsprechend zu reagieren.  Sie können jedoch geeignete Vorkehrungen gegen die möglichen Auswirkungen dieser Fehler auf niedriger Ebene treffen, indem Sie [Beendigungshandler schreiben](../cpp/writing-a-termination-handler.md).  
  
## Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)