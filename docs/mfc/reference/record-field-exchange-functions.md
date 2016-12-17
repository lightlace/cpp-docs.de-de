---
title: "Funktionen f&#252;r den Datensatzfeldaustausch"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Datenzugriffsobjekte), Datensatzfeldaustausch (DFX)"
  - "ODBC, Bulk-RFX-Datenaustauschfunktionen"
  - "RFX (Datensatzfeldaustausch), ODBC-Klassen"
  - "DFX (DAO-Datensatzfeldaustausch), Datenaustauschfunktionen"
  - "DFX-Funktionen"
  - "Sammel-RFX-Funktionen"
  - "DFX (DAO-Datensatzfeldaustausch)"
  - "RFX (Datensatzfeldaustausch), DAO-Klassen"
  - "ODBC, RFX"
  - "RFX (Datensatzfeldaustausch), Datenaustauschfunktionen"
  - "RFX (Datensatzfeldaustausch)"
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionen f&#252;r den Datensatzfeldaustausch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält die Datensatzfeldaustausch \([RFX](#_mfc_rfx_functions_.28.odbc.29), [Bulk\-RFX](#_mfc_bulk_rfx_functions_.28.odbc.29) und [DFX](#_mfc_dfx_functions_.28.dao.29)\)\-Funktionen, mit denen die Übertragung von Daten zwischen einem Recordset\-Objekt und den zugehörigen Datenquellen automatisiert und andere Datenvorgänge ausgeführt werden.  
  
 Wenn Sie die ODBC\-basierten Klassen verwenden und einen Massenzeilenabruf implementiert haben, müssen Sie die `DoBulkFieldExchange`\-Memberfunktion des `CRecordset` manuell überschreiben, indem Sie die Bulk\-RFX\-Funktionen für jedes Datenelement aufrufen, das einer Datenquellspalte entspricht.  
  
 Wenn Sie den Massenzeilenabruf in den ODBC\-basierten Klassen implementiert haben oder die DAO\-basierten Klassen verwenden, dann überschreibt der ClassWizard die `DoFieldExchange`\-Memberfunktion von `CRecordset` oder `CDaoRecordset` durch Aufrufen der RFX\-Funktionen \(für ODBC\-Klassen\) oder der DFX\-Funktionen \(für DAO\-Klassen\) für jedes Felddatenelement im Recordset.  
  
 Die Datensatzfeldaustausch\-Funktionen übertragen jedes Mal Daten, wenn das Framework `DoFieldExchange` oder `DoBulkFieldExchange` aufruft. Jede Funktion überträgt einen bestimmten Datentyp.  
  
 Weitere Informationen über die Verwendung dieser Funktionen finden Sie in den Artikeln [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Für Datenspalten, die Sie dynamisch binden, können Sie auch die RFX\- oder DFX\-Funktionen selbst aufrufen, wie in den Artikeln [Recordset: Dynamisches Binden von Spalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) beschrieben. Darüber hinaus können Sie Ihre eigenen benutzerdefinierten RFX\- oder DFX\-Routinen schreiben, wie im technischen Hinweis [43](../../mfc/tn043-rfx-routines.md) \(für ODBC\) und im technischen Hinweis [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) \(für DAO\) erläutert.  
  
 Ein Beispiel für RFX und Bulk\-RFX\-Funktionen wie in den `DoFieldExchange`\- und `DoBulkFieldExchange`\-Funktionen finden Sie unter [RFX\_Text](../Topic/RFX_Text.md) und [RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md). DFX\-Funktionen sind den RFX\-Funktionen sehr ähnlich.  
  
### RFX\-Funktionen \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary](../Topic/RFX_Binary.md)|Überträgt Byte\-Arrays vom Typ [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[RFX\_Bool](../Topic/RFX_Bool.md)|Überträgt boolesche Daten.|  
|[RFX\_Byte](../Topic/RFX_Byte.md)|Überträgt ein einzelnes Byte an Daten.|  
|[RFX\_Date](../Topic/RFX_Date.md)|Überträgt Uhrzeit\- und Datumsdaten mit [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double](../Topic/RFX_Double.md)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|  
|[RFX\_Int](../Topic/RFX_Int.md)|Überträgt Ganzzahldaten.|  
|[RFX\_Long](../Topic/RFX_Long.md)|Überträgt lange Ganzzahldaten.|  
|[RFX\_LongBinary](../Topic/RFX_LongBinary.md)|Überträgt BLOB\-Daten \(Binary Large Object\) mit einem Objekt der [CLongBinary](../../mfc/reference/clongbinary-class.md) Klasse.|  
|[RFX\_Single](../Topic/RFX_Single.md)|Überträgt Gleitkommadaten.|  
|[RFX\_Text](../Topic/RFX_Text.md)|Überträgt Zeichenfolgendaten.|  
  
### Bulk\-RFX\-Funktionen \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary\_Bulk](../Topic/RFX_Binary_Bulk.md)|Überträgt Arrays von Bytedaten.|  
|[RFX\_Bool\_Bulk](../Topic/RFX_Bool_Bulk.md)|Überträgt Arrays von booleschen Daten.|  
|[RFX\_Byte\_Bulk](../Topic/RFX_Byte_Bulk.md)|Überträgt Arrays von Einzelbytes.|  
|[RFX\_Date\_Bulk](../Topic/RFX_Date_Bulk.md)|Überträgt Arrays von Daten des Typs **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double\_Bulk](../Topic/RFX_Double_Bulk.md)|Überträgt Arrays von Gleitkommadaten mit doppelter Genauigkeit.|  
|[RFX\_Int\_Bulk](../Topic/RFX_Int_Bulk.md)|Überträgt Arrays von Ganzzahldaten.|  
|[RFX\_Long\_Bulk](../Topic/RFX_Long_Bulk.md)|Überträgt Arrays von langen Ganzzahldaten.|  
|[RFX\_Single\_Bulk](../Topic/RFX_Single_Bulk.md)|Überträgt Arrays von Gleitkommadaten.|  
|[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)|Überträgt Arrays von Daten des Typs **LPSTR**.|  
  
### DFX\-Funktionen \(DAO\)  
  
|||  
|-|-|  
|[DFX\_Binary](../Topic/DFX_Binary.md)|Überträgt Byte\-Arrays vom Typ [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[DFX\_Bool](../Topic/DFX_Bool.md)|Überträgt boolesche Daten.|  
|[DFX\_Byte](../Topic/DFX_Byte.md)|Überträgt ein einzelnes Byte an Daten.|  
|[DFX\_Currency](../Topic/DFX_Currency.md)|Überträgt Währungsdaten vom Typ [COleCurrency](../../mfc/reference/colecurrency-class.md).|  
|[DFX\_DateTime](../Topic/DFX_DateTime.md)|Überträgt Datums\- und Uhrzeitdaten vom Typ [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX\_Double](../Topic/DFX_Double.md)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|  
|[DFX\_Long](../Topic/DFX_Long.md)|Überträgt lange Ganzzahldaten.|  
|[DFX\_LongBinary](../Topic/DFX_LongBinary.md)|Überträgt BLOB\-Daten \(Binary Large Object\) mit einem Objekt der `CLongBinary`\-Klasse. Bei DAO wird empfohlen, dass Sie stattdessen [DFX\_Binary](../Topic/DFX_Binary.md) verwenden.|  
|[DFX\_Short](../Topic/DFX_Short.md)|Überträgt kurze Ganzzahldaten.|  
|[DFX\_Single](../Topic/DFX_Single.md)|Überträgt Gleitkommadaten.|  
|[DFX\_Text](../Topic/DFX_Text.md)|Überträgt Zeichenfolgendaten.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)   
 [CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)   
 [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)