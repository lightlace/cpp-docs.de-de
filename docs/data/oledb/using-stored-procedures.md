---
title: "Verwenden von gespeicherten Prozeduren | Microsoft Docs"
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
  - "OLE DB-Anbietervorlagen, Gespeicherte Prozeduren"
  - "OLE DB, Gespeicherte Prozeduren"
  - "Gespeicherte Prozeduren, Informationen über gespeicherte Prozeduren"
  - "Gespeicherte Prozeduren, OLE DB"
  - "Gespeicherte Prozeduren, Visual C++"
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Verwenden von gespeicherten Prozeduren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei einer gespeicherten Prozedur handelt es sich um ein in einer Datenbank gespeichertes, ausführbares Objekt.  Der Aufruf einer gespeicherten Prozedur entspricht dem Aufrufen eines SQL\-Befehls.  Das Verwenden von gespeicherten Prozeduren für die Datenquelle \(anstelle der Ausführung oder der Vorbereitung einer Anweisung in der Clientanwendung\) kann u. a. folgende Vorteile bieten: höhere Leistung, reduzierte Netzwerkauslastung sowie verbesserte Konsistenz und Genauigkeit.  
  
 Eine gespeicherte Prozedur kann eine beliebige Anzahl von Eingabe\- oder Ausgabeparametern besitzen \(einschließlich 0\) und einen Rückgabewert übergeben.  Sie können die Parameterwerte entweder als spezifische Datenwerte fest kodieren oder eine Parametermarkierung \(ein Fragezeichen "?"\) verwenden.  
  
> [!NOTE]
>  Gespeicherte CLR\-Prozeduren für SQL Server, die mit Visual C\+\+ erstellt wurden, müssen mit der **\/clr:safe**\-Compileroption kompiliert werden.  
  
 Der OLE DB\-Anbieter für SQL Server \(SQLOLEDB\) unterstützt die folgenden, von gespeicherten Prozeduren zur Rückgabe von Daten verwendeten Mechanismen:  
  
-   Jede **SELECT**\-Anweisung in der Prozedur generiert ein Resultset.  
  
-   Die Prozedur kann Daten über Ausgabeparameter zurückgeben.  
  
-   Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.  
  
> [!NOTE]
>  Es ist nicht möglich, gespeicherte Prozeduren mit dem OLE DB\-Anbieter für Jet zu verwenden, denn dieser Anbieter unterstützt keine gespeicherten Prozeduren. In Abfragezeichenfolgen sind lediglich Konstanten zugelassen.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)