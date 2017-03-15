---
title: "struct RUNTIME_FUNCTION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# struct RUNTIME_FUNCTION
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für tabellenbasierte Ausnahmebehandlung ist ein Tabelleneintrag für alle Funktionen erforderlich, durch die Stapelspeicher reserviert oder eine andere Funktion aufgerufen wird \(z. B. Funktionen, die keine Endfunktionen sind\).  Funktionstabelleneinträge haben das folgende Format:  
  
|||  
|-|-|  
|ULONG|Adresse des Funktionsanfangs|  
|ULONG|Adresse des Funktionsendes|  
|ULONG|Adresse der Entladeinformationen|  
  
 Die RUNTIME\_FUNCTION\-Struktur muss im Arbeitsspeicher auf DWORD\-Grenzen ausgerichtet sein.  Alle Adressen sind bildbezogen, d. h. es handelt sich um 32\-Bit\-Offsets aus der Startadresse des Bildes, das den Funktionstabelleneintrag enthält.  Diese Einträge werden sortiert und in den .pdata\-Abschnitt eines PE32\+\-Bildes eingefügt.  Damit dynamisch erzeugte Funktionen \[JIT\-Compiler\] unterstützt werden, muss von der Laufzeit RtlInstallFunctionTableCallback oder RtlAddFunctionTable verwendet werden, damit diese Informationen dem Betriebssystem bereitgestellt werden.  Andernfalls kann dies zu einer unzuverlässigen Ausnahmebehandlung und unzuverlässigem Debuggen von Prozessen führen.  
  
## Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)