---
title: ATL-Datenbankklassen (OLE DB-Vorlagen)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: dc016a5e1e1d9652f6a69f73b5760f42dec5e889
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222559"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL-Datenbankklassen (OLE DB-Vorlagen)

Microsoft bietet mehrere Implementierungen von OLE DB, einen Satz von COM-Schnittstellen, die einheitlichen Zugriff auf Daten in verschiedenen Datenquellen und Formaten bereitstellen.

OLE DB-Vorlagen sind C++-Vorlagen in ATL-OLE DB-datenbanktechnologie einfacher zu verwenden, indem Sie Klassen, die viele häufig verwendeten OLE DB-Schnittstellen implementieren.

Diese Vorlagenbibliothek besteht aus zwei Teilen:

- [OLE DB-Consumervorlagen](../data/oledb/ole-db-consumer-templates-cpp.md) verwendet, um eine OLE DB-Clientanwendung (Consumer) zu implementieren.

- [OLE DB-Anbietervorlagen](../data/oledb/ole-db-provider-templates-cpp.md) verwendet, um eine OLE DB-Server (Provider)-Anwendung zu implementieren.

Darüber hinaus die [OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md) bieten eine einfache Möglichkeit zum Erstellen von OLE DB-Consumer. Die OLE DB-Attribute fügen Code basierend auf den OLE DB-Consumervorlagen arbeiten-OLE DB-Consumer zu erstellen.

Beachten Sie, dass die MFC-Bibliothek eine Klasse enthält [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), die Datenbankdatensätze in Steuerelementen anzeigt. Die Ansicht ist eine Formularansicht können Sie direkt mit verbundenen eine `CRowset` Objekt aus, und zeigt die Felder an die `CRowset` Objekt in der Dialogfeldvorlage-Steuerelementen.

Weitere Informationen finden Sie unter [OLE DB-Programmierung](../data/oledb/ole-db-programming.md) und [OLE DB Programmer's Guide](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[Erstellen eines OLE DB-Anbieters](../data/oledb/creating-an-ole-db-provider.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Referenz der OLE DB-Anbietervorlagen](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Beispiele für OLE DB-Vorlagen](https://github.com/Microsoft/VCSamples)
