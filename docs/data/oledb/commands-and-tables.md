---
title: Befehle und Tabellen
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
ms.openlocfilehash: b2cdf7a2b439af3a564f5801e015f6064fb141dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409088"
---
# <a name="commands-and-tables"></a>Befehle und Tabellen

Befehle und Tabellen können Sie auf Rowsets zugreifen; d. h. Rowsets öffnen, führen Sie Befehle und Binden von Spalten. Die [CCommand](../../data/oledb/ccommand-class.md) und [CTable](../../data/oledb/ctable-class.md) Klassen instanziieren der Befehls- und Tabellenobjekte. Diese Klassen werden aus [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) wie in der folgenden Abbildung dargestellt.

![CCommand und CTable](../../data/oledb/media/vccommandstables.gif "CCommand und CTable")<br/>
Befehls- und Tabellenklassen

In der vorherigen Tabelle `TAccessor` Accessortyp kann aufgeführt [Zugriffsmethodentypen](../../data/oledb/accessors-and-rowsets.md). `TRowset` kann einen beliebigen Rowsettyp in aufgeführt werden [Rowsettypen](../../data/oledb/accessors-and-rowsets.md). `TMultiple` Gibt den Ergebnistyp (eine einzelne oder mehrere Resultsets) an.

Die [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md) können Sie angeben, ob ein Befehl oder Table-Objekt werden soll.

- Für Datenquellen ohne Befehle können Sie die `CTable` Klasse. Sie verwenden sie in der Regel für einfache Rowsets, die keine weiteren Parameter angeben und nicht mehrere Ergebnisse benötigen. Diese einfache Klasse wird geöffnet, eine Tabelle in einer Datenquelle mit dem Namen einer Tabelle, den Sie angeben.

- Für Datenquellen, die Befehle unterstützen, können Sie die `CCommand` stattdessen. Um einen Befehl auszuführen, rufen [öffnen](../../data/oledb/ccommand-open.md) für diese Klasse. Als Alternative können Sie aufrufen können `Prepare` um einen Befehl vorzubereiten, die mehr als einmal ausgeführt werden soll.

   `CCommand` verfügt über drei Argumente: ein Accessortyp, ein Rowset und einen Ergebnistyp (`CNoMultipleResults`, in der Standardeinstellung oder `CMultipleResults`). Bei Angabe von `CMultipleResults`, `CCommand` -Klasse unterstützt die `IMultipleResults` Schnittstelle und behandelt mehrere Rowsets. Die [DBVIEWER](https://github.com/Microsoft/VCSamples) Beispiel wird veranschaulicht, die mehrere Ergebnisse zu behandeln.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)