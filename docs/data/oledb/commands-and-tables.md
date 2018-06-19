---
title: Befehle und Tabellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 23d2739807a065b93b10a209a9ea68070b36970b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098679"
---
# <a name="commands-and-tables"></a>Befehle und Tabellen
Befehle und Tabellen können Sie auf Rowsets zugreifen; d. h. Öffnen Rowsets, Ausführen von Befehlen und Binden von Spalten. Die [CCommand](../../data/oledb/ccommand-class.md) und [CTable](../../data/oledb/ctable-class.md) Klassen instanziieren der Befehls- und Tabellenobjekte. Diese Klassen werden aus [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) wie in der folgenden Abbildung dargestellt.  
  
 ![CCommand und CTable](../../data/oledb/media/vccommandstables.gif "Vccommandstables")  
Befehls- und Tabellenklassen  
  
 In der vorherigen Tabelle `TAccessor` kann alle Accessortyp in aufgeführt [Accessortypen](../../data/oledb/accessors-and-rowsets.md). *TRowset* kann einen beliebigen Rowsettyp in aufgeführt [Rowsettypen](../../data/oledb/accessors-and-rowsets.md). *TMultiple* gibt den Ergebnistyp (einzelne oder mehrere Resultsets).  
  
 Die [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md) können Sie angeben, ob ein Befehl oder Table-Objekt verwendet werden soll.  
  
-   Bei Datenquellen ohne Befehle können Sie die `CTable` Klasse. Sie verwenden es im Allgemeinen für einfache Rowsets, die keine weiteren Parameter angeben und nicht mehrere Ergebnisse benötigen. Diese einfache Klasse öffnet eine Tabelle in einer Datenquelle mit dem Namen einer Tabelle, den Sie angeben.  
  
-   Für Datenquellen, die Befehle unterstützen, können Sie die `CCommand` stattdessen. Um einen Befehl auszuführen, rufen [öffnen](../../data/oledb/ccommand-open.md) für diese Klasse. Als Alternative können Sie erreichen `Prepare` um einen Befehl vorzubereiten, die mehr als einmal ausgeführt werden soll.  
  
     **CCommand** hat drei Argumente: ein Accessortyp, ein Rowsettyp und einen Ergebnistyp (`CNoMultipleResults`, standardmäßig oder `CMultipleResults`). Bei Angabe von `CMultipleResults`, `CCommand` -Klasse unterstützt die **IMultipleResults** Schnittstelle und behandelt mehrere Rowsets. Die [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) Beispiel veranschaulicht die Behandlung mehrerer Ergebnisse.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)