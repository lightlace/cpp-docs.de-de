---
title: "Fragen zum OLE&#160;DB-Architekturdesign"
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
  - "OLE DB, Überlegungen zum Anwendungsentwurf"
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Fragen zum OLE&#160;DB-Architekturdesign
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vor dem Starten Ihrer OLE DB\-Anwendung sollten Sie die folgenden Punkte beachten:  
  
 **Welche Programmierimplementierung verwenden Sie zum Schreiben Ihrer OLE DB\-Anwendung?**  
 Microsoft bietet hierfür verschiedene Bibliotheken an: eine OLE DB\-Vorlagenbibliothek, OLE DB\-Attribute und die unformatierten OLE DB\-Schnittstellen im OLE DB\-SDK.  Zusätzlich gibt es Assistenten, die Ihnen beim Schreiben Ihres Programms behilflich sind.  Diese Implementierungen werden in [Vorlagen, Attribute und andere Implementierungen von OLE DB](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md) beschrieben.  
  
 **Müssen Sie einen eigenen Anbieter schreiben?**  
 Die meisten Entwickler müssen keinen eigenen Anbieter schreiben.  Microsoft bietet verschiedene Anbieter an.  Jedes Mal, wenn Sie eine Datenverbindung erstellen, beispielsweise wenn Sie dem Projekt mithilfe des ATL OLE DB\-Consumer\-Assistenten einen Consumer hinzufügen, werden im Dialogfeld **Datenverknüpfungseigenschaften** alle auf dem System registrierten, zur Verfügung stehenden Anbieter aufgelistet.  Wenn einer dieser Anbieter den Anforderungen Ihrer Datenspeicher\- und Datenzugriffsanwendung entspricht, ist es das Einfachste, einen dieser Anbieter zu verwenden.  Entspricht jedoch der Datenspeicher keiner dieser Kategorien, müssen Sie einen eigenen Anbieter erstellen.  Weitere Informationen über das Erstellen von Anbietern finden Sie unter [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Welche Ebene der Unterstützung benötigen Sie für den Consumer?**  
 Einige Consumer können sehr einfach sein, andere wiederum sehr komplex.  Die Funktionalität von OLE DB\-Objekten wird durch Eigenschaften festgelegt.  Wenn Sie den ATL OLE DB\-Consumer\-Assistenten zum Erstellen eines Consumers oder den DB\-Anbieter\-Assistenten zum Erstellen eines Anbieters verwenden, legen diese die entsprechenden Objekteigenschaften fest, um Ihnen eine Reihe von Standardfunktionen zur Verfügung zu stellen.  Wenn die Unterstützung der mithilfe des Assistenten generierten Consumer\- oder Anbieterklassen nicht ausreicht, finden Sie in der [OLE DB\-Vorlagenbibliothek](../../data/oledb/ole-db-templates.md) weitere Informationen zu den Schnittstellen für diese Klassen.  Diese Schnittstellen umschließen die unformatierten OLE DB\-Schnittstellen und bieten zusätzliche Implementierungen für eine einfachere Verwendung.  
  
 Wenn Sie beispielsweise Daten in einem Rowset aktualisieren möchten, aber bei der Erstellung des Consumers mithilfe des Assistenten vergessen haben, dies anzugeben, können Sie diese Funktion nachträglich festlegen, indem Sie die **DBPROP\_IRowsetChange**\-Eigenschaft und die **DBPROP\_UPDATABILITY**\-Eigenschaft für das Befehlsobjekt festlegen.  Wenn der Rowset dann erstellt wird, verfügt er über die `IRowsetChange`\-Schnittstelle.  
  
 **Haben Sie älteren Code mit einer anderen Datenzugriffstechnologie? \(ADO, ODBC oder DAO\)?**  
 Mit Blick auf die möglichen Kombinationen verschiedener Technologien \(z. B. die Verwendung von ADO\-Komponenten mit OLE DB\-Komponenten und die Migration von ODBC\-Code nach OLE DB\) ist es nicht möglich, alle Situationen im Rahmen der Visual C\+\+\-Dokumentation zu behandeln.  In den folgenden Microsoft\-Websites finden Sie jedoch eine Vielzahl von Artikeln, die verschiedene Szenarien behandeln:  
  
-   [Microsoft Hilfe und Support](http://go.microsoft.com/fwlink/?LinkId=148218)  
  
-   [Microsoft\-Datenzugriffs\-technische Artikel\-Übersicht](http://go.microsoft.com/fwlink/?LinkId=148217)  
  
-   [Visual Besuchen](http://go.microsoft.com/fwlink/?LinkId=148215)  
  
-   [Suche Microsoft.com](http://search.microsoft.com/)  
  
 Geben Sie zum Starten einer Suche eine Kombination aus Stichworten ein, die auf das Szenario zutreffen; z. B.: Wenn Sie ADO\-Objekte mit einem OLE DB\-Anbieter verwendet haben, versuchen Sie es mit einer Booleschen Suche mit **ADO UND "OLE DB"**.  Wenn Sie DAO\-Code älteren ODBC\- migrieren möchten, wählen Sie "alle Wörter" aus und geben Sie Zeichenfolgen wie **migrating DAO** an.  
  
## Siehe auch  
 [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB\-Programmierung](../../data/oledb/ole-db-programming-overview.md)