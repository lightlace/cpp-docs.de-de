---
title: "&#220;bersicht &#252;ber die OLE&#160;DB-Programmierung | Microsoft Docs"
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
  - "OLE DB, Informationen über OLE DB"
  - "Universal Data Access"
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber die OLE&#160;DB-Programmierung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Was ist OLE DB, und was ist der Unterschied zu anderen Datenbanktechnologien?  Bei OLE DB handelt es sich um eine von Microsoft produzierte, hochleistungsfähige COM\-basierte Datenbanktechnologie.  OLE DB unterscheidet sich von anderen Microsoft\-Datenbanktechnologien in der Art der Bereitstellung des universellen Datenzugriffs \(Universal Data Access\).  
  
## Universal Data Access  
 Universal Data Access ermöglicht Ihnen einen einfachen Zugriff auf Daten, unabhängig von der Form, in der sie gespeichert sind.  In einer typischen Unternehmenssituation wird eine große Menge an Informationen außerhalb der Unternehmensdatenbanken gespeichert.  Diese Informationen befinden sich in Dateisystemen \(z. B. FAT oder NTFS\), indizierten sequenziellen Dateien, persönlichen Datenbanken \(z. B. in Access\), Arbeitsblättern \(z. B. in Excel\), Anwendungen zur Projektplanung \(z. B. Project\) sowie in E\-Mail\-Nachrichten \(z. B. in Outlook\).  
  
 Ein Zugriff auf diese Daten mithilfe der entsprechenden Anwendungen verzögert den Arbeitsablauf erheblich oder ist zumindest sehr aufwendig.  Die meisten Unternehmen befinden sich in solch einer Lage und behelfen sich dadurch, dass sie die Informationen in einem Datenbank\-Managementsystem \(DBMS\) zusammenfassen.  Dieser Schritt ist jedoch teuer, zeitaufwendig und in vielen Fällen nicht besonders praktisch.  
  
 Die Alternative liegt in der Entwicklung einer Universal Data Access\-Lösung.  OLE DB und ADO bieten Ihnen die entsprechenden Universal Data Access\-Funktionen.  OLE DB ist dabei leistungsfähiger und wird zur Verwendung mit Visual C\+\+\-Anwendungen empfohlen.  
  
 Universal Data Access beinhaltet zwei Funktionen: die erste ist die verteilte Abfrage oder der einheitliche Zugriff auf mehrere \(verteilte\) Datenquellen und die zweite ist die Fähigkeit, den Zugriff auf Datenquellen, die nicht Teil eines DBMS sind, durch Datenbankanwendungen zu ermöglichen.  
  
-   Verteilte Abfrage  
  
     Die Fähigkeit, auf Daten in mehreren \(d. h. in verteilten\) Datenquellen einheitlich zugreifen zu können.  Dabei kann es sich um gleichartige Datenquellen \(z. B. zwei Access\-Datenbanken\) oder um unterschiedliche Typen von Datenquellen handeln, z. B. eine SQL\-Serverdatenbank und eine Access\-Datenbank.  Einheitlich bedeutet in diesem Zusammenhang, dass es grundsätzlich möglich ist, die gleiche Abfrage in allen Datenquellen durchzuführen.  
  
-   Zugriff auf Nicht\-DBMS\-Daten  
  
     Die Fähigkeit, den Zugriff auf Datenquellen, die nicht in DBMS gespeichert sind, mithilfe von Datenbankanwendungen zu ermöglichen.  Beispiele für DBMS\-Datenquellen sind IMS, DB2, Oracle, SQL Server, Access und Paradox.  Zu den Beispielen von Nicht\-DBMS\-Datenquellen gehören Informationen in Dateisystemen, E\-Mail, Arbeitsblättern und Projektverwaltungstools.  
  
 Beispielszenario: Eine Verkaufsabteilung muss alle E\-Mail\-Nachrichten finden, die von Kunden aus einem bestimmten Gebiet in einem Zeitraum von einer Woche eingegangen sind.  Diese Abfrage könnte eine Suche in einer Mailboxdatei der E\-Mail\-Anwendung sowie eine Suche in einer Access\-Tabelle umfassen, um den Namen der jeweiligen Kunden zu ermitteln.  Bei Access handelt es sich um eine DBMS\-Anwendung, bei Outlook jedoch nicht.  
  
 OLE DB ermöglicht es Ihnen, Anwendungen zu entwickeln, mit denen Sie auf verschiedene DBMS\- und Nicht\-DBMS\-Datenquellen zugreifen können.  OLE DB ermöglicht den universellen Zugriff durch die Verwendung von COM\-Schnittstellen, die die entsprechenden DBMS\-Funktionen für die jeweilige Datenquelle unterstützen.  COM reduziert unnötige Verdoppelungen von Diensten und erhöht die Interoperabilität nicht nur zwischen Datenquellen, sondern auch zwischen anderen Anwendungen.  
  
## Vorteile von COM  
 Hier setzt COM an.  OLE DB stellt eine Gruppe von COM\-Schnittstellen dar.  Der Datenzugriff mithilfe einer einheitlichen Gruppe von Schnittstellen ermöglicht es Ihnen, eine Datenbank als Matrix kooperierender Komponenten zu organisieren.  
  
 OLE DB definiert auf der Grundlage der COM\-Spezifikation eine erweiterbare und verwaltbare Reihe von Schnittstellen, die konsistente und wiederverwendbare Teile der DBMS\-Funktionalität berücksichtigen und einschließen.  Diese Schnittstellen definieren die Grenzen der DBMS\-Komponenten, z. B. Zeilencontainer, Abfrageprozessoren und Transaktionskoordinatoren, die einen einheitlichen Transaktionszugriff auf verschiedene Informationsquellen ermöglichen.  
  
 OLE DB\-Anwendungen werden gewöhnlich als DLLs geschrieben. Aufgrund ihrer COM\-Implementierung werden jedoch die Nachteile der DLLs \(z. B. Namens\- und Versionsprobleme\) durch die Verwendung von Komponentencode umgangen.  Um in OLE DB Schnittstellen aufzurufen oder auf andere Komponenten zuzugreifen, verwenden Sie die entsprechenden GUIDs \(Globally Unique Identifiers\).  
  
 Darüber hinaus registriert COM durch das Zählen von Verweisen die Verwendung einzelner Komponenten.  Wenn Sie eine Methode auf einer Schnittstelle aufrufen, wird der Verweiszähler erhöht; wenn die Methode einen Rückgabewert liefert, wird der Verweiszähler heruntergesetzt.  Erreicht der Verweiszähler den Wert 0, wird die Komponente, zu der die Methode gehört, freigegeben.  
  
## Siehe auch  
 [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB\-Vorlagen](../../data/oledb/ole-db-templates.md)