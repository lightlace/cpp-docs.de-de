---
title: OLE DB-Vorlagen, Attribute und andere Implementierungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ef9baf43ded1533eb7f4962db7344f9dc1def0ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>Vorlagen, Attribute und andere Implementierungen von OLE DB
## <a name="atl-ole-db-templates"></a>ATL-OLE DB-Vorlagen  
 Der OLE DB-Vorlagen, die ATL (Active Template Library) gehören, erleichtern die hohe Leistung OLE DB-datenbanktechnologie zu verwenden, indem Sie Klassen, die viele häufig verwendeten OLE DB-Schnittstellen implementieren. Zusammen mit dieser Vorlage wird die Bibliothek assistentenunterstützung zum Erstellen von OLE DB-startanwendungen.  
  
 Diese Vorlagenbibliothek besteht aus zwei Teilen:  
  
-   **OLE DB-Consumervorlagen** verwendet, um eine OLE DB-Clientanwendung (Consumer) zu implementieren.  
  
-   **OLE DB-Anbietervorlagen** verwendet, um eine OLE DB-Server (Provider)-Anwendung implementiert wird.  
  
 Sie sollten mit C++-Vorlagen, COM und den OLE DB-Schnittstellen vertraut sein, um OLE DB-Vorlagen verwenden zu können. Wenn Sie nicht mit OLE DB vertraut sind, finden Sie unter [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Weitere Informationen können Sie folgende Aktionen ausführen:  
  
-   Lesen Sie die Themen zu den [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) oder [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
-   Erstellen einer [OLE DB-Consumer](../../data/oledb/creating-an-ole-db-consumer.md) oder [OLE DB-Anbieter](../../data/oledb/creating-an-ole-db-provider.md).  
  
-   Die Liste der [OLE DB-Consumer-Klassen](../../data/oledb/ole-db-consumer-templates-reference.md) oder [OLE DB-Anbieterklassen](../../data/oledb/ole-db-provider-templates-reference.md).  
  
-   Die Liste der [OLE DB-Vorlagenbeispiele](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c).  
  
-   Finden Sie unter [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) (im Windows SDK).  
  
## <a name="ole-db-attributes"></a>OLE DB-Attribute  
 Die [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md) bieten eine einfache Möglichkeit, OLE DB-Consumer zu erstellen. Die OLE DB-Attribute fügen Code basierend auf den [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md) arbeiten OLE DB-Consumer und-Anbieter zu erstellen. Wenn Sie die Attribute nicht unterstützten Funktionen angeben müssen, können die OLE DB-Vorlagen in Verbindung mit den Attributen in Ihrem Code Sie.  
  
## <a name="mfc-ole-db-classes"></a>MFC-OLE DB-Klassen  
 Die MFC-Bibliothek enthält eine Klasse, [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), die Datenbankdatensätze in Steuerelementen anzeigt. Die Ansicht ist eine Formularansicht können Sie eine direkte Verbindung zum eine `CRowset` -Objekt und zeigt die Felder der `CRowset` Objekt in der Dialogfeldvorlage-Steuerelementen. Er liefert auch eine Standardimplementierung für das Verschieben von mit dem ersten nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des Datensatzes derzeit für die Sicht. Weitere Informationen finden Sie unter `COleDBRecordView`.  
  
## <a name="ole-db-sdk-interfaces"></a>OLE DB-SDK-Schnittstellen  
 In den Fällen, in denen die OLE DB-Vorlagen nicht mit OLE DB-Funktionalität unterstützen, müssen Sie den OLE DB-Schnittstellen verwenden. Weitere Informationen finden Sie unter [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)