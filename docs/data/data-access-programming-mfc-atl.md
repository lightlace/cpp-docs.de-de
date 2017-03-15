---
title: "Datenzugriffsprogrammierung (MFC/ATL) | Microsoft Docs"
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
  - "Daten [C++], Datenzugriffstechnologien"
  - "Datenzugriff [C++], Klassenbibliotheken für Datenbanken"
  - "Datenbanken [C++], MFC"
  - "MFC [C++], Datenzugriffsanwendungen"
  - "OLE DB [C++], Datenzugriffstechnologien"
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Datenzugriffsprogrammierung (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ bietet verschiedene Methoden zum Arbeiten mit Datenbanken.  Die bevorzugte Zugriffsart besteht in der Verwendung einer der Klassenbibliotheken, z. B. ATL \(Active Template Class Library\) oder MFC \(Microsoft Foundation Class\), die die Arbeit mit Datenbank\-APIs vereinfachen.  
  
> [!NOTE]
>  In diesem Thema werden die älteren Technologien behandelt, die Sie zum Programmieren von Datenbanken in Visual C\+\+ verwenden können.  Informationen über die Datenzugriffsprogrammierung mit Visual C\+\+ und SQL Server 2005 finden Sie unter [Datenzugriff](../dotnet/data-access-using-adonet-cpp-cli.md), [Zugreifen auf Daten in Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md) und [Creating SQL Server 2005 Objects In Managed Code](assetId:///5358a825-e19b-49aa-8214-674ce5fed1da).  
  
 Die Bibliotheksklassen unterstützen die folgenden Arten des Datenzugriffs:  
  
-   ATL stellt OLE DB\-Vorlagen und Datenbankattribute bereit.  
  
-   MFC bietet Open Database Connectivity \(ODBC\) und einen ODBC\-Treiber.  
  
 Diese Bibliotheken stellen Abstraktionen bereit, die das Arbeiten mit Datenbanken erleichtern und mit der Geschwindigkeit, Leistungsfähigkeit und Flexibilität von C\+\+ kombinieren.  Sie integrieren Datenzugriffe mit dem Anwendungsframework der Bibliothek.  
  
 Sie können auch Datenbank\-API\-Funktionen direkt aus den COM\-, ODBC\- oder DAO\-Software Development Kits \(SDKs\) aufrufen.  Weitere Informationen über die direkte Programmierung mit den COM\-, DAO\- oder ODBC\-API\-Funktionen finden Sie in den SDKs für COM, DAO oder ODBC.  
  
 Wenn der Datenzugriff unabhängig von der Art der gespeicherten Daten erfolgen soll, verwenden Sie ATL\-OLE DB.  Verwenden Sie die ODBC\-Klassen von MFC, wenn Sie keine Microsoft Jet\-Datenbanken \(**.mdb**\) einsetzen und mit der ODBC\-API arbeiten möchten, um vollständige Datenquellenunabhängigkeit zu erzielen.  Verwenden Sie die DAO\-Klassen von MFC, wenn Sie Microsoft Jet\-Datenbanken \(.mdb\) \(oder externe Datenbanken, z. B. ODBC\-Datenquellen\) einsetzen möchten.  
  
> [!NOTE]
>  Microsoft empfiehlt für neue Projekte die Verwendung von OLE DB oder ODBC.  DAO sollte lediglich für die Verwaltung bereits vorhandener Anwendungen eingesetzt werden.  
  
 Neben der Entwicklung eigenständiger Datenbankanwendungen können Sie eine Datenbank auch in anderen Programmtypen oft als sehr effizientes Medium zum Speichern und Abrufen von Informationen verwenden.  
  
|Themenbereich|Siehe|  
|-------------------|-----------|  
|**Auswahl einer Datenbanktechnologie**||  
|ODBC im Vergleich zu  DAO|[Sollte DAO oder ODBC verwendet werden?](../data/should-i-use-dao-or-odbc-q.md)|  
|Verwenden der Microsoft Knowledge Base zum Suchen von zusätzlichen Artikeln zu Datenbankthemen, die von Produktsupportspezialisten verfasst wurden.|[Microsoft Knowledge Base](../data/where-can-i-find-microsoft-knowledge-base-articles-on-database-topics-q.md)|  
|**ATL\-Datenbankunterstützung \(OLE DB\)**||  
|OLE DB\-Programmierung \(konzeptionelle Themen\)|[Übersicht über die OLE DB\-Programmierung](../data/oledb/ole-db-programming-overview.md)|  
|Verwenden von OLE DB\-Consumervorlagen \(konzeptionelle Themen\)|[OLE DB\-Consumervorlagen](../data/oledb/ole-db-consumer-templates-cpp.md)|  
|OLE DB\-Consumerattribute|[OLE DB\-Consumerattribute](../windows/ole-db-consumer-attributes.md)|  
|Verwenden von OLE DB\-Anbietervorlagen \(konzeptionelle Themen\)|[OLE DB\-Anbietervorlagen](../data/oledb/ole-db-provider-templates-cpp.md)|  
|Hinzufügen eines OLE DB\-Consumers zu einem MFC\-Projekt|[Erstellen eines OLE DB\-Consumers](../data/oledb/creating-an-ole-db-consumer.md)|  
|**MFC\-Datenbankunterstützung \(ODBC und DAO\)**||  
|Was sind DAO und ODBC?|[Was sind DAO und ODBC?](../data/what-are-dao-and-odbc-q.md)|  
|Verwenden von MFC\-Datenbankklassen|[Wann sollten Datenbankklassen verwendet werden?](../data/when-should-i-use-the-database-classes-q.md)|  
|Informationen zum MFC\-Datenbankprogrammier\-Modell|[Wie ist das MFC\-Modell für die Datenbankprogrammierung aufgebaut?](../data/what-is-the-mfc-database-programming-model-q.md)|  
|Wählen zwischen den MFC\-DAO\-Klassen und den MFC\-ODBC\-Klassen|[Sollte DAO oder ODBC verwendet werden?](../data/should-i-use-dao-or-odbc-q.md)|  
|Datenquellen, auf die mit DAO und ODBC zugegriffen werden kann|[Auf welche Datenquellen kann mit DAO und ODBC zugegriffen werden?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)|  
|Open Database Connectivity \(ODBC\)|[ODBC und MFC](../data/odbc/odbc-and-mfc.md)|  
|Möglichkeit des direkten Aufrufens von DAO\-APIs oder ODBC\-APIs während der Verwendung der Klassen|[Kann DAO oder ODBC direkt aufgerufen werden?](../data/can-i-call-dao-or-odbc-directly-q.md)|  
|Zur Verfügung stehende ODBC\-Treiber|[Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)|  
|Zusammenwirken der Datenbankklassen mit der MFC\-Dokument\-\/\-Ansichtarchitektur|[MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md)|  
|Installieren der MFC\-Datenbankunterstützung; in Visual C\+\+ standardmäßig installierte ODBC\-Treiber; installierte ODBC SDK\- und DAO SDK\-Komponenten|[Installieren der MFC\-Datenbankunterstützung](../data/installing-mfc-database-support.md)|  
|**Datengebundene Steuerelemente \(ADO und RDO\)**||  
|Erstellen eines Programms, das datengebundene Steuerelemente verwendet|[Datengebundene Steuerelemente \(ADO und RDO\)](../data/ado-rdo/data-bound-controls-ado-and-rdo.md)|  
|Datenbindung mithilfe von ActiveX\-Steuerelementen|[MFC\-ActiveX\-Steuerelemente: Verwenden der Datenbindung in einem ActiveX\-Steuerelement](../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)|  
|Weitergabe von ActiveX\-Steuerelementen|[MFC\-ActiveX\-Steuerelemente: Weitergabe von ActiveX\-Steuerelementen](../mfc/mfc-activex-controls-distributing-activex-controls.md)|  
  
## Siehe auch  
 [Datenzugriff](../Topic/Data%20Access%20in%20Visual%20C++.md)