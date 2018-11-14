---
title: ATL-Datenbankklassen (OLE DB-Vorlagen)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 4304c350ce6a9303a7542809fa85fb0cd2560031
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522071"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL-Datenbankklassen (OLE DB-Vorlagen)

Microsoft bietet mehrere Implementierungen von OLE DB, einen Satz von COM-Schnittstellen, die einheitlichen Zugriff auf Daten in verschiedenen Datenquellen und Formaten bereitstellen.  OLE DB wird offiziell als veraltet markiert; Diese Dokumentation ist für Entwickler, die legacy-Code verwaltet werden. Neue Anwendungen sollten ODBC verwenden, für die Verbindung mit SQL-Datenquellen.

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