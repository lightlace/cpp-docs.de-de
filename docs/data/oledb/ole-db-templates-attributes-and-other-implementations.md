---
title: "Vorlagen, Attribute und andere Implementierungen von OLE&#160;DB"
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
  - "OLE DB-Vorlagen"
  - "OLE DB-Vorlagen, Informationen über OLE DB-Vorlagen"
  - "OLE DB, Implementierungen"
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Vorlagen, Attribute und andere Implementierungen von OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## ATL\-OLE DB\-Vorlagen  
 Die OLE DB\-Vorlagen sind Teil der ATL \(Active Template Library\) und erleichtern die Verwendung der leistungsfähigen OLE DB\-Datenbanktechnologie, indem Sie Klassen bereitstellen, die viele der häufig verwendeten OLE DB\-Schnittstellen implementieren.  Neben dieser Vorlagenbibliothek steht auch eine Assistentenunterstützung zum Erstellen von OLE DB\-Startanwendungen zur Verfügung.  
  
 Diese Vorlagenbibliothek enthält zwei Teile:  
  
-   **OLE DB\-Consumervorlagen** Werden zur Implementierung einer OLE DB\-Clientanwendung \(Consumeranwendung\) verwendet.  
  
-   **OLE DB\-Anbietervorlagen** Werden zur Implementierung einer OLE DB\-Serveranwendung \(Anbieteranwendung\) verwendet.  
  
 Um die OLE DB\-Vorlagen zu verwenden, sollten Sie Erfahrungen im Umgang mit C\+\+\-Vorlagen, COM und den OLE DB\-Schnittstellen besitzen.  Wenn Sie noch keine Erfahrungen im Umgang mit OLE DB haben, informieren Sie sich in der [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Weitere Informationen erhalten Sie, wenn Sie:  
  
-   Die Themen über [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) oder [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md) lesen.  
  
-   Einen [OLE DB\-Consumer](../../data/oledb/creating-an-ole-db-consumer.md) oder einen [OLE DB\-Anbieter](../../data/oledb/creating-an-ole-db-provider.md) erstellen.  
  
-   Die Liste der [OLE DB\-Consumerklassen](../../data/oledb/ole-db-consumer-templates-reference.md) oder [OLE DB\-Anbieterklassen](../../data/oledb/ole-db-provider-templates-reference.md) durchgehen.  
  
-   Sich in der Liste der [Vorlagenbeispiele für OLE DB](assetId:///08958863-0b5f-41ad-ae99-fca7440c553c) informieren.  
  
-   Die Informationen in der [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) \(im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\) lesen.  
  
## OLE DB\-Attribute  
 Die [OLE DB\-Consumerattribute](../../windows/ole-db-consumer-attributes.md) stellen eine bequeme Möglichkeit zum Erstellen von OLE DB\-Consumern dar.  Die OLE DB\-Attribute fügen auf der Grundlage der [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md) Code ein, um funktionierende OLE DB\-Consumer und OLE DB\-Anbieter zu erstellen.  Wenn Sie Funktionen spezifizieren müssen, die von den Attributen nicht unterstützt werden, können Sie die OLE DB\-Vorlagen im Code zusammen mit Attributen verwenden.  
  
## MFC\-OLE DB\-Klassen  
 Die MFC\-Bibliothek enthält eine Klasse, [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), die Datenbankdatensätze in Steuerelementen anzeigt.  Bei der Ansicht handelt es sich um eine direkt mit einem `CRowset`\-Objekt verbundene Formularansicht, in der die Felder des `CRowset`\-Objekts in den Steuerelementen der Dialogfeldvorlage angezeigt werden.  Sie verfügt auch über eine standardmäßige Implementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz sowie über eine Schnittstelle zum Aktualisieren des aktuell angezeigten Datensatzes.  Weitere Informationen finden Sie unter `COleDBRecordView`.  
  
## OLE DB\-SDK\-Schnittstellen  
 In den Fällen, in denen die OLE DB\-Vorlagen OLE DB\-Funktionen nicht unterstützen, müssen Sie die OLE DB\-Schnittstellen verwenden.  Weitere Informationen finden Sie in der [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
## Siehe auch  
 [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB\-Programmierung](../../data/oledb/ole-db-programming-overview.md)