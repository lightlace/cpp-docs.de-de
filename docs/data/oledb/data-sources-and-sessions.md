---
title: Datenquellen und Sitzungen
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 2c11230d106b50e8120dfa9f4e283e97700d2739
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175997"
---
# <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen

Die folgende Abbildung zeigt die Klassen, die eine Verbindung mit und Zugreifen auf eine Datenquelle zu unterstützen. Jede Klasse basiert auf eine Standardimplementierung der OLE DB-Komponente.

![Daten-Datenquelle und Sitzungsklassen](../../data/oledb/media/vcdatasourcesessionclasses.gif "Daten Datenquelle und Sitzungsklassen") <br/>
Datenquelle und Sitzungsklassen

Die Klassen sind:

- [CDataSource](../../data/oledb/cdatasource-class.md) diese Klasse instanziiert das Datenquellenobjekt, das erstellt und verwaltet eine Verbindung mit einer Datenquelle über einen OLE DB-Anbieter. Die Datenquelle hat Informationen wie z. B. die Adresse und Authentifizierungsinformationen Datenquelleninformationen in Form einer Verbindungszeichenfolge.

   Es ist auch Beachten Sie, dass die Hilfsklasse [CEnumerator](../../data/oledb/cenumerator-class.md) wird häufig verwendet werden, bevor eine Verbindung hergestellt wird, zum Abrufen einer Liste der verfügbaren Anbieter in einem System registriert. Dadurch können Sie zur Auswahl eines Anbieters als Datenquelle. Z. B. die **Datenlinkeigenschaften** Dialogfeld verwendet diese Klasse zum Auffüllen der Liste der Anbieter auf dem **Anbieter** Registerkarte. Es entspricht dem `SQLBrowseConnect` oder `SQLDriverConnect` Funktion.

- [CSession](../../data/oledb/csession-class.md) diese Klasse instanziiert das Sitzungsobjekt, das eine einzelnen Access-Sitzung mit der Datenquelle darstellt. Allerdings können Sie mehrere Sitzungen für eine Datenquelle erstellen. Für jede Sitzung können Sie Rowsets, Befehle und andere Objekte, zum Zugreifen auf Daten aus der Datenquelle erstellen. Die Sitzung verarbeitet Transaktionen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)