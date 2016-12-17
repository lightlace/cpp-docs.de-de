---
title: "ATL-Datenbankklassen (OLE&#160;DB-Vorlagen)"
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
  - "Datenbankklassen [C++], ATL"
  - "Datenbankklassen [C++], OLE DB"
  - "OLE DB-Vorlagen [C++], ATL-Datenbankklassen"
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Datenbankklassen (OLE&#160;DB-Vorlagen)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft bietet verschiedene Implementierungen von OLE DB und eine Reihe von COM\-Schnittstellen für einen einheitlichen Zugriff auf Daten, die in unterschiedlichen Informationsquellen und Formaten vorliegen.  
  
 Bei den OLE DB\-Vorlagen handelt es sich um C\+\+\-Vorlagen in ATL. Sie erleichtern die Verwendung der leistungsfähigen OLE DB\-Datenbanktechnologie, indem sie Klassen bereitstellen, die viele der häufig verwendeten OLE DB\-Schnittstellen implementieren.  
  
 Diese Vorlagenbibliothek enthält zwei Teile:  
  
-   [OLE DB\-Consumervorlagen](../data/oledb/ole-db-consumer-templates-cpp.md) Werden zur Implementierung einer OLE DB\-Clientanwendung \(Consumeranwendung\) verwendet.  
  
-   [OLE DB\-Anbietervorlagen](../data/oledb/ole-db-provider-templates-cpp.md) Werden zur Implementierung einer OLE DB\-Serveranwendung \(Anbieteranwendung\) verwendet.  
  
 Zusätzlich stellen die [OLE DB\-Consumerattribute](../windows/ole-db-consumer-attributes.md) eine bequeme Möglichkeit zum Erstellen von OLE DB\-Consumern dar.  Die OLE DB\-Attribute fügen auf der Grundlage der OLE DB\-Consumervorlagen Code ein, um funktionierende OLE DB\-Consumer zu erstellen.  
  
 Beachten Sie, dass die MFC\-Bibliothek eine Klasse enthält \([COleDBRecordView](../mfc/reference/coledbrecordview-class.md)\), die Datenbankdatensätze in Steuerelementen anzeigt.  Bei der Ansicht handelt es sich um eine direkt mit einem `CRowset`\-Objekt verbundene Formularansicht, in der die Felder des `CRowset`\-Objekts in den Steuerelementen der Dialogfeldvorlage angezeigt werden.  
  
 Weitere Informationen finden Sie unter [OLE DB Programmierhandbuch](http://go.microsoft.com/fwlink/?LinkId=121548)[OLE DB\-Programmierung](../data/oledb/ole-db-programming.md).  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers](../data/oledb/creating-an-ole-db-consumer.md)   
 [Erstellen eines OLE DB\-Anbieters](../data/oledb/creating-an-ole-db-provider.md)   
 [Referenz der OLE DB\-Consumervorlagen](../data/oledb/ole-db-consumer-templates-reference.md)   
 [Referenz der OLE DB\-Anbietervorlagen](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Templates Samples](assetId:///08958863-0b5f-41ad-ae99-fca7440c553c)