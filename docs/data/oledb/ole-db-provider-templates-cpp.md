---
title: OLE DB-Anbietervorlagen (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: c88e03f509da3c97c270e308dc6dd44e3b44aeb7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413783"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB-Anbietervorlagen (C++)

OLE DB ist ein wichtiger Teil der Microsoft Universal Data Access-Strategie. Der OLE DB-Entwurf ermöglicht leistungsstarke Datenzugriff aus einer beliebigen Datenquelle an. Tabellendaten können durch OLE DB angezeigt werden, unabhängig davon, ob sie eine Datenbank stammen. Die Flexibilität bietet Ihnen eine enorme Menge Energie.

Siehe [OLE DB-Consumer und-Anbieter](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB-Consumer und-Anbieter verwendet. Der Consumer fordert Daten zurückgibt. der Anbieter gibt die Daten in einem tabellarischen Format an den Consumer zurück. Hinsichtlich der Programmierung besteht der wichtigste Aspekt dieses Modells, dass der Anbieter muss jeder Aufruf implementiert werden, die der Consumer vornehmen kann.

## <a name="what-is-a-provider"></a>Was ist ein Anbieter?

OLE DB-Anbieter ist ein Satz von COM-Objekte, die Aufrufe von einem Consumerobjekt, Interface fungieren übertragen von Daten in tabellarischer Form aus einer permanenten Datenquelle (einen Datenspeicher bezeichnet) an den Consumer.

Anbieter können einfach oder komplex sein. Der Anbieter kann eine minimale Menge an Funktionen erfüllen oder eine vollständige produktionsumgebung unterstützen, weitere Schnittstellen implementiert. Ein Anbieter kann geben eine Tabelle zurück, kann der Client das Format der Tabelle zu bestimmen und Vorgänge auf diesen Daten.

Jeder Anbieter implementiert einen standardmäßigen Satz von COM-Objekte zur Verarbeitung von Anforderungen vom Client mit einer standardmäßigen Bedeutung, alle OLE DB-Consumer Daten von einem Anbieter, unabhängig von der Sprache (z. B. C++ und grundlegende) zugreifen kann.

Jedes COM-Objekt enthält mehrere Schnittstellen, von denen einige erforderlich und von denen einige optional sind. Implementieren Sie die obligatorischen Schnittstellen, gewährleistet der Anbieter ein Mindestmaß an Funktionen (so genannte Kompatibilität), die einem beliebigen Client verwenden kann. Ein Anbieter kann es sich um optionale Schnittstellen um zusätzliche Funktionen bereitzustellen implementieren. Die [Anbieterarchitektur von OLE DB](../../data/oledb/ole-db-provider-template-architecture.md) werden diese Schnittstellen im Detail beschrieben. Rufen Sie der Client sollten immer `QueryInterface` zu bestimmen, ob ein Anbieter eine bestimmte Schnittstelle unterstützt.

## <a name="ole-db-specification-level-support"></a>Unterstützung von OLE DB-Spezifikation auf

Der OLE DB-Anbietervorlagen unterstützt die Spezifikation der OLE DB-Version 2.7. Verwenden den OLE DB-Anbietervorlagen, können Sie einen kompatiblen Ebene 0-Anbieter implementieren. Die `Provider` Beispiel verwendet beispielsweise die Vorlagen ein Servers Befehlsservers Befehl zu implementieren, die die DOS-Befehl DIR im Dateisystem Abfragen ausgeführt wird. Die `Provider` Beispiel gibt die Verzeichnisinformationen zurück, in einem Rowset, der standard OLE DB-Mechanismus zum Zurückgeben von tabellarischen Daten handelt.

Die einfachste Art des von der OLE DB-Vorlagen unterstützten Anbieter ist ein nur-Lese Anbieter keine Befehle. Anbieter mit den Befehlen werden ebenfalls unterstützt, wie das Hinzufügen von Lesezeichen und Lese-/Schreibzugriff sind. Sie können einen Lese-/Schreibzugriff-Anbieter implementieren, durch das Schreiben von zusätzlichem Code. Dynamische Rowsets und Transaktionen werden von der aktuellen Version nicht unterstützt, aber Sie können diese hinzufügen, wenn Sie möchten.

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>Wenn müssen Sie einen OLE DB-Anbieter zu erstellen?

Sie müssen nicht immer Ihren eigenen Anbieter erstellen. Microsoft bietet verschiedene vorgefertigte "," standard-Anbieter in der **Datenlinkeigenschaften** Dialogfeld in Visual C++. Der Hauptgrund für einen OLE DB-Anbieter erstellen, ist der Universal Data Access-Strategie nutzen. Einige der Vorteile dieser Vorgehensweise sind also:

- Der Datenzugriff mithilfe einer beliebigen Sprache wie C++, Basic und Visual Basic Scripting Edition. Sie können verschiedene Programmierer in Ihrer Organisation Zugriff auf die gleichen Daten auf die gleiche Weise, unabhängig davon, welche Sprache sie verwenden.

- Öffnen Sie Ihre Daten an andere Datenquellen wie SQL Server, Excel und Access. Dies kann nützlich sein, wenn Sie Daten zwischen unterschiedlichen Formaten übertragen möchten.

- Er in Operationen, Cross-Datenquelle (heterogenen). Dies kann eine effektive Möglichkeit des Datawarehousing sein. Mithilfe von OLE DB-Anbieter können Sie Daten im systemeigenen Format beibehalten und weiterhin können sie in einem einfachen Vorgang darauf zugreifen.

- Hinzufügen zusätzlicher Funktionen, um Ihre Daten, z. B. die abfrageverarbeitung.

- Erhöhen der Leistung beim Zugriff auf Daten, indem Sie steuern, wie es bearbeitet wird.

- Höhere Stabilität. Wenn Sie ein proprietäres Format haben, nur ein Programmierer zugreifen kann, die Sie gefährdet sind. Verwenden OLE DB-Anbieter, können Sie proprietäre Formate für alle Ihre Programmierer öffnen.

## <a name="read-only-and-updatable-providers"></a>Nur-Lese und aktualisierbare Anbieter

Anbieter können Komplexität und Funktionalität stark variieren. Es ist hilfreich, die Anbieter in nur-Lese und aktualisierbare Anbieter kategorisieren:

- Visual C++ 6.0 unterstützt nur nur-Lese Anbieter. [Erstellen einen OLE DB-Anbieter](../../data/oledb/creating-an-ole-db-provider.md) wird erläutert, wie einen nur-Lese Anbieter erstellt.
- Visual C++ unterstützt aktualisierbare Anbieter, die aktualisiert werden können (Schreiben) dem Datenspeicher. Weitere Informationen zu aktualisierbaren Anbietern finden Sie unter [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md); die [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) Beispiel ist ein Beispiel eines aktualisierbaren Anbieters.

Weitere Informationen finden Sie unter:

- [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)

- [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>Siehe auch

[Datenzugriff](../data-access-in-cpp.md)<br/>
[OLE DB-SDK-Dokumentation](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[OLE DB-Programmierreferenz](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
