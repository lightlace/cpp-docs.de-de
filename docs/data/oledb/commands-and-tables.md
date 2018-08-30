---
title: Befehle und Tabellen | Microsoft-Dokumentation
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
ms.openlocfilehash: 2e9d9fc72791572d840b88f1d74eb736e3ad65c7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213709"
---
# <a name="commands-and-tables"></a>Befehle und Tabellen
Befehle und Tabellen können Sie auf Rowsets zugreifen; d. h. Rowsets öffnen, führen Sie Befehle und Binden von Spalten. Die [CCommand](../../data/oledb/ccommand-class.md) und [CTable](../../data/oledb/ctable-class.md) Klassen instanziieren der Befehls- und Tabellenobjekte. Diese Klassen werden aus [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) wie in der folgenden Abbildung dargestellt.  
  
 ![CCommand und CTable](../../data/oledb/media/vccommandstables.gif "Vccommandstables")  
Befehls- und Tabellenklassen  
  
 In der vorherigen Tabelle `TAccessor` Accessortyp kann aufgeführt [Zugriffsmethodentypen](../../data/oledb/accessors-and-rowsets.md). *TRowset* kann einen beliebigen Rowsettyp in aufgeführt werden [Rowsettypen](../../data/oledb/accessors-and-rowsets.md). *TMultiple* gibt den Ergebnistyp (eine einzelne oder mehrere Resultsets) an.  
  
 Die [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md) können Sie angeben, ob ein Befehl oder Table-Objekt werden soll.  
  
-   Für Datenquellen ohne Befehle können Sie die `CTable` Klasse. Sie verwenden sie in der Regel für einfache Rowsets, die keine weiteren Parameter angeben und nicht mehrere Ergebnisse benötigen. Diese einfache Klasse wird geöffnet, eine Tabelle in einer Datenquelle mit dem Namen einer Tabelle, den Sie angeben.  
  
-   Für Datenquellen, die Befehle unterstützen, können Sie die `CCommand` stattdessen. Um einen Befehl auszuführen, rufen [öffnen](../../data/oledb/ccommand-open.md) für diese Klasse. Als Alternative können Sie aufrufen können `Prepare` um einen Befehl vorzubereiten, die mehr als einmal ausgeführt werden soll.  
  
     `CCommand` verfügt über drei Argumente: ein Accessortyp, ein Rowset und einen Ergebnistyp (`CNoMultipleResults`, in der Standardeinstellung oder `CMultipleResults`). Bei Angabe von `CMultipleResults`, `CCommand` -Klasse unterstützt die `IMultipleResults` Schnittstelle und behandelt mehrere Rowsets. Die [DBVIEWER](https://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832) Beispiel wird veranschaulicht, die mehrere Ergebnisse zu behandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)