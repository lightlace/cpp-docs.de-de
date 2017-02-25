---
title: "Befehle und Tabellen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorRowset-Klasse, Befehls- und Tabellenklassen"
  - "CCommand-Klasse, OLE DB-Consumervorlagen"
  - "Befehle [C++], OLE DB-Consumervorlagen"
  - "CTable-Klasse"
  - "OLE DB-Consumervorlagen, Befehlsunterstützung"
  - "OLE DB-Consumervorlagen, Tabellenunterstützung"
  - "Rowsets, Aufrufen"
  - "Tabellen [C++], OLE DB-Consumervorlagen"
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Befehle und Tabellen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Befehlen und Tabellen können Sie auf Rowsets zugreifen, d. h., Sie können Rowsets öffnen, Befehle ausführen und Spalten binden.  Die [CCommand](../../data/oledb/ccommand-class.md)\-Klasse und die [CTable](../../data/oledb/ctable-class.md)\-Klasse instanziieren die entsprechenden Befehls\- und Tabellenobjekte.  Diese Klassen werden aus [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) abgeleitet, wie in der folgenden Abbildung gezeigt wird.  
  
 ![CCommand und CTable](../../data/oledb/media/vccommandstables.png "vcCommandsTables")  
Befehls\- und Tabellenklassen  
  
 In der oben stehenden Tabelle kann `TAccessor` jeder unter [Accessortypen](../../data/oledb/accessors-and-rowsets.md) aufgelistete Accessortyp sein.  *TRowset* kann jeder unter [Rowsettypen](../../data/oledb/accessors-and-rowsets.md) aufgelistete Rowsettyp sein.  *TMultiple* gibt den Ergebnistyp an \(ein einzelnes oder mehrere Resultsets\).  
  
 Der [ATL\-OLE DB\-Consumer\-Assistent](../../atl/reference/atl-ole-db-consumer-wizard.md) ermöglicht es Ihnen anzugeben, ob Sie ein Befehls\- oder ein Tabellenobjekt wünschen.  
  
-   Für Datenquellen ohne Befehle können Sie die `CTable`\-Klasse verwenden.  Sie wird gewöhnlich für einzelne Rowsets verwendet, die keine Parameter angeben und nicht mehrere Ergebnisse benötigen.  Diese einfache Klasse öffnet eine Tabelle in einer Datenquelle unter Verwendung eines von Ihnen festgelegten Tabellennamens.  
  
-   Für Datenquellen, die Befehle unterstützen, können Sie stattdessen die `CCommand`\-Klasse verwenden.  Um einen Befehl auszuführen, rufen Sie in dieser Klasse [Open](../../data/oledb/ccommand-open.md) auf.  Alternativ hierzu können Sie `Prepare` aufrufen, um einen Befehl vorzubereiten, den Sie mehr als einmal ausführen möchten.  
  
     `besitzt drei Vorlagenargumente: einen Accessortyp, einen Rowsettyp und einen Ergebnistyp (standardmäßig CNoMultipleResults oder CMultipleResults`\).  Wenn Sie `CMultipleResults` festlegen, unterstützt die `CCommand`\-Klasse die **IMultipleResults**\-Schnittstelle und behandelt mehrere Rowsets.  Im Beispiel [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832) wird die Behandlung mehrerer Ergebnisse gezeigt.  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)