---
title: Befehle und Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d63f0856b70761c6c6b4a31ddeedfa8921c3a304
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052811"
---
# <a name="commands-and-tables"></a>Befehle und Tabellen

Befehle und Tabellen können Sie auf Rowsets zugreifen; d. h. Rowsets öffnen, führen Sie Befehle und Binden von Spalten. Die [CCommand](../../data/oledb/ccommand-class.md) und [CTable](../../data/oledb/ctable-class.md) Klassen instanziieren der Befehls- und Tabellenobjekte. Diese Klassen werden aus [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) wie in der folgenden Abbildung dargestellt.

![CCommand und CTable](../../data/oledb/media/vccommandstables.gif "Vccommandstables")<br/>
Befehls- und Tabellenklassen

In der vorherigen Tabelle `TAccessor` Accessortyp kann aufgeführt [Zugriffsmethodentypen](../../data/oledb/accessors-and-rowsets.md). `TRowset` kann einen beliebigen Rowsettyp in aufgeführt werden [Rowsettypen](../../data/oledb/accessors-and-rowsets.md). `TMultiple` Gibt den Ergebnistyp (eine einzelne oder mehrere Resultsets) an.

Die [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md) können Sie angeben, ob ein Befehl oder Table-Objekt werden soll.

- Für Datenquellen ohne Befehle können Sie die `CTable` Klasse. Sie verwenden sie in der Regel für einfache Rowsets, die keine weiteren Parameter angeben und nicht mehrere Ergebnisse benötigen. Diese einfache Klasse wird geöffnet, eine Tabelle in einer Datenquelle mit dem Namen einer Tabelle, den Sie angeben.

- Für Datenquellen, die Befehle unterstützen, können Sie die `CCommand` stattdessen. Um einen Befehl auszuführen, rufen [öffnen](../../data/oledb/ccommand-open.md) für diese Klasse. Als Alternative können Sie aufrufen können `Prepare` um einen Befehl vorzubereiten, die mehr als einmal ausgeführt werden soll.

   `CCommand` verfügt über drei Argumente: ein Accessortyp, ein Rowset und einen Ergebnistyp (`CNoMultipleResults`, in der Standardeinstellung oder `CMultipleResults`). Bei Angabe von `CMultipleResults`, `CCommand` -Klasse unterstützt die `IMultipleResults` Schnittstelle und behandelt mehrere Rowsets. Die [DBVIEWER](https://github.com/Microsoft/VCSamples) Beispiel wird veranschaulicht, die mehrere Ergebnisse zu behandeln.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)