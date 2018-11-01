---
title: Vorlagen, Attribute und andere Implementierungen von OLE DB
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 97924110d6dd59e59eda9492713518dedf68af55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596598"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>Vorlagen, Attribute und andere Implementierungen von OLE DB

## <a name="atl-ole-db-templates"></a>ATL-OLE DB-Vorlagen

OLE DB-Vorlagen, die Teil der ATL (Active Template Library) sind, stellen die hohe Leistung OLE DB-datenbanktechnologie einfacher zu verwenden, indem Sie Klassen, die viele häufig verwendeten OLE DB-Schnittstellen implementieren. Zusammen mit dieser Vorlage wird die Bibliothek Unterstützung des Assistenten zum Erstellen von OLE DB-startanwendungen.

Diese Vorlagenbibliothek besteht aus zwei Teilen:

- **OLE DB-Consumervorlagen** verwendet, um eine OLE DB-Clientanwendung (Consumer) zu implementieren.

- **OLE DB-Anbietervorlagen** verwendet, um eine OLE DB-Server (Provider)-Anwendung zu implementieren.

Sie sollten mit C++-Vorlagen, COM und den OLE DB-Schnittstellen vertraut sein, um OLE DB-Vorlagen verwenden zu können. Wenn Sie nicht mit OLE DB vertraut sind, finden Sie unter [OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms713643).

Weitere Informationen können Sie folgende Aktionen ausführen:

- Lesen Sie die Themen zu den [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) oder [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).

- Erstellen Sie eine [OLE DB-Consumer](../../data/oledb/creating-an-ole-db-consumer.md) oder [OLE DB-Anbieter](../../data/oledb/creating-an-ole-db-provider.md).

- Die Liste der [OLE DB-Consumer-Klassen](../../data/oledb/ole-db-consumer-templates-reference.md) oder [OLE DB-Anbieterklassen](../../data/oledb/ole-db-provider-templates-reference.md).

- Die Liste der [OLE DB-Vorlagenbeispiele](https://github.com/Microsoft/VCSamples).

- Finden Sie unter [OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms713643) (in der Windows-SDK).

## <a name="ole-db-attributes"></a>OLE DB-Attribute

Die [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md) bieten eine einfache Möglichkeit zum Erstellen von OLE DB-Consumer. Die OLE DB-Attribute fügen Code auf Grundlage der [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md) arbeiten OLE DB-Consumer und-Anbieter zu erstellen. Bei Bedarf an Funktionen, die durch die Attribute nicht unterstützt, können Sie OLE DB-Vorlagen in Verbindung mit den Attributen in Ihrem Code verwenden.

## <a name="mfc-ole-db-classes"></a>MFC-OLE DB-Klassen

Die MFC-Bibliothek enthält eine Klasse, [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), die Datenbankdatensätze in Steuerelementen anzeigt. Die Ansicht ist eine Formularansicht können Sie direkt mit verbundenen eine `CRowset` -Objekts und zeigt die Felder der `CRowset` Objekt in der Dialogfeldvorlage-Steuerelementen. Außerdem gibt er eine Standardimplementierung für das Verschieben von mit dem ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren der aktuell angezeigten Datensatzes. Weitere Informationen finden Sie unter `COleDBRecordView`.

## <a name="ole-db-sdk-interfaces"></a>OLE DB-SDK-Schnittstellen

In den Fällen, in denen OLE DB-Vorlagen OLE DB-Funktionen unterstützen, müssen Sie den OLE DB-Schnittstellen verwenden. Weitere Informationen finden Sie unter [OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms713643) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)