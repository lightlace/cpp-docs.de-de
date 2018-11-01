---
title: Datenquellen und Sitzungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a6cb4e27f8a248b0b90454acb782b3b8994abc4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056034"
---
# <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen

Die folgende Abbildung zeigt die Klassen, die eine Verbindung mit und Zugreifen auf eine Datenquelle zu unterstützen. Jede Klasse basiert auf eine Standardimplementierung der OLE DB-Komponente.

![Daten-Datenquelle und Sitzungsklassen](../../data/oledb/media/vcdatasourcesessionclasses.gif "Vcdatasourcesessionclasses") Datenquelle und Sitzungsklassen

Die Klassen sind:

- [CDataSource](../../data/oledb/cdatasource-class.md) diese Klasse instanziiert das Datenquellenobjekt, das erstellt und verwaltet eine Verbindung mit einer Datenquelle über einen OLE DB-Anbieter. Die Datenquelle hat Informationen wie z. B. die Adresse und Authentifizierungsinformationen Datenquelleninformationen in Form einer Verbindungszeichenfolge.

   Es ist auch Beachten Sie, dass die Hilfsklasse [CEnumerator](../../data/oledb/cenumerator-class.md) wird häufig verwendet werden, bevor eine Verbindung hergestellt wird, zum Abrufen einer Liste der verfügbaren Anbieter in einem System registriert. Dadurch können Sie zur Auswahl eines Anbieters als Datenquelle. Z. B. die **Datenlinkeigenschaften** Dialogfeld verwendet diese Klasse zum Auffüllen der Liste der Anbieter auf dem **Anbieter** Registerkarte. Es entspricht dem `SQLBrowseConnect` oder `SQLDriverConnect` Funktion.

- [CSession](../../data/oledb/csession-class.md) diese Klasse instanziiert das Sitzungsobjekt, das eine einzelnen Access-Sitzung mit der Datenquelle darstellt. Allerdings können Sie mehrere Sitzungen für eine Datenquelle erstellen. Für jede Sitzung können Sie Rowsets, Befehle und andere Objekte, zum Zugreifen auf Daten aus der Datenquelle erstellen. Die Sitzung verarbeitet Transaktionen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)