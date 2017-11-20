---
title: "Funktionen der C-Laufzeitbibliothek zur Threadsteuerung | Microsoft Docs"
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
helpviewer_keywords: 
  - "_beginthread-Funktion"
  - "_beginthreadex-Funktion"
  - "_endthread-Funktion"
  - "_endthreadex-Funktion"
  - "Multithreading [C++], Steuern von Threads"
  - "Threading [C++], Steuern von Threads"
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Funktionen der C-Laufzeitbibliothek zur Threadsteuerung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alle Win32\-Programme weisen mindestens einen Thread auf.  Jeder Thread kann zusätzliche Threads generieren.  Ein Thread kann seine Aufgabe schnell abschließen oder während der gesamten Lebensdauer eines Programms aktiv bleiben.  
  
 In den C\-Laufzeitbibliotheken LIBCMT und MSVCRT stehen zwei Funktionen zur Threaderstellung und \-beendung zur Verfügung: [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) und [\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
 Mit der `_beginthread`\-Funktion und der `_beginthreadex`\-Funktion wird ein neuer Thread erstellt; wenn der Vorgang erfolgreich war, wird ein Threadbezeichner zurückgegeben.  Der Thread wird nach abgeschlossener Ausführung automatisch beendet. Er kann sich jedoch durch Aufruf von `_endthread` oder `_endthreadex` auch selbsttätig beenden.  
  
> [!NOTE]
>  Wenn Sie beabsichtigen, C\-Laufzeitroutinen von einem Programm aus aufzurufen, das mit Libcmt.lib erstellt wurde, müssen Sie die Threads über die `_beginthread`\-Funktion oder über die `_beginthreadex`\-Funktion starten.  Verwenden Sie nicht die Win32\-Funktionen `ExitThread` und `CreateThread`.  Bei der Verwendung von `SuspendThread` tritt möglicherweise ein Deadlock auf, wenn mehrere blockierte Threads darauf warten, dass der unterbrochene Thread den Zugriffsvorgang auf eine C\-Laufzeitdatenstruktur abschließt.  
  
##  <a name="_core_the__beginthread_function"></a> Die \_beginthread\-Funktion und die \_beginthreadex\-Funktion  
 Die `_beginthread`\-Funktion und die `_beginthreadex`\-Funktion erstellen einen neuen Thread.  Ein Thread nutzt den Code und die Datensegmente eines Prozesses gemeinsam mit anderen Threads in diesem Prozess, verfügt jedoch über eigene, eindeutige Registerwerte, Stapelspeicher und eine aktuelle Anweisungsadresse.  Das System weist jedem Thread seine bestimmte CPU\-Zeit zu, damit alle Threads in einem Prozess gleichzeitig ausgeführt werden können.  
  
 Die `_beginthread`\-Funktion und die `_beginthreadex`\-Funktion ähneln der [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)\-Funktion in der Win32\-API, weisen jedoch folgende Unterschiede auf:  
  
-   Sie initialisieren bestimmte Variablen der C\-Laufzeitbibliothek.  Dies ist nur von Bedeutung, wenn Sie die C\-Laufzeitbibliothek in Threads verwenden.  
  
-   Mit `CreateThread` können Sicherheitsattribute gesteuert werden.  Mit dieser Funktion können Sie einen Thread starten, der sich im angehaltenen Status befindet.  
  
 `_beginthread` und `_beginthreadex` geben ein Handle für den neuen Thread zurück, wenn der Vorgang erfolgreich war. Bei einem Fehler wird ein Fehlercode zurückgegeben.  
  
##  <a name="_core_the__endthread_function"></a> Die \_endthread\-Funktion und die \_endthreadex\-Funktion  
 Die [\_endthread](../c-runtime-library/reference/endthread-endthreadex.md)\-Funktion beendet einen von `_beginthread` erstellten Thread \(und analog beendet `_endthreadex` einen von `_beginthreadex` erstellten Thread\).  Threads werden automatisch beendet, wenn sie abgeschlossen sind.  `_endthread` und `_endthreadex` sind zum bedingten Beenden aus einem Thread heraus sinnvoll.  Ein für die Kommunikationsverarbeitung verantwortlicher Thread kann z. B. seine Aktivität einstellen, wenn die Steuerung des Kommunikationsanschlusses derzeit nicht möglich ist.  
  
## Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)