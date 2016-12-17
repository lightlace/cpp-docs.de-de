---
title: "ODBC-Klassen und Threads"
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
helpviewer_keywords: 
  - "ODBC-Klassen, Und Threads"
  - "ODBC, Multithreadanwendungen"
  - "Threading [MFC], ODBC-Unterstützung"
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC-Klassen und Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Seit MFC 4.2 ist Multithreadingunterstützung für MFC\-ODBC\-Klassen verfügbar.  Beachten Sie jedoch, dass MFC keine Multithreadingunterstützung für die DAO\-Klassen bereitstellt.  
  
 Für die Multithreadingunterstützung für die ODBC\-Klassen gelten gewisse Einschränkungen.  Da diese Klassen die ODBC\-API umschließen, beschränken sie sich auf die Multithreadingunterstützung der Komponenten, auf denen sie aufbauen.  Es gibt z. B. viele ODBC\-Treiber, die nicht threadsicher sind. Daher sind die MFC\-ODBC\-Klassen nicht threadsicher, wenn sie mit diesen Treibern verwendet werden.  Sie sollten überprüfen, ob ein spezieller Treiber threadsicher ist.  
  
 Beim Schreiben einer Multithreadinganwendung sollten Sie vorsichtig sein, wenn Sie mehrere Threads für die Veränderung desselben Objekts verwenden.  Wenn Sie in zwei Threads beispielsweise dasselbe `CRecordset`\-Objekt verwenden, kann dies beim Abrufen von Daten zu Problemen führen. Eine Abrufoperation in dem einen Thread könnte die Daten überschreiben, die in dem anderen Thread abgerufen wurden.  Ein häufigerer Verwendungszweck der MFC\-ODBC\-Klassen in verschiedenen Threads ist die gemeinsame Verwendung eines geöffneten `CDatabase`\-Objekts von verschiedenen Threads aus, um mit einem separaten `CRecordset`\-Objekt in jedem Thread von derselben ODBC\-Verbindung Gebrauch zu machen.  Beachten Sie, dass Sie kein ungeöffnetes `CDatabase`\-Objekt an ein `CRecordset`\-Objekt in einem anderen Thread übergeben sollten.  
  
> [!NOTE]
>  Wenn Sie mehrere Threads benötigen, die dasselbe Objekt ändern, sollten Sie einen geeigneten Synchronisierungsmechanismus implementieren, z. B. kritische Abschnitte.  Beachten Sie, dass bestimmte Operationen, z. B. **Open**, nicht geschützt sind.  Sie sollten sicherstellen, dass diese Operationen nicht von verschiedenen Threads aus gleichzeitig aufgerufen werden.  
  
 Weitere Informationen über das Erstellen von Multithread\-Anwendungen finden Sie unter [Multithreading\-Themen](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../../data/data-access-programming-mfc-atl.md)