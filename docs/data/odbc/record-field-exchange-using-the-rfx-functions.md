---
title: "Datensatzfeldaustausch: Verwenden der RFX-Funktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datentypen [C++], ODBC-Datensatzfeldaustausch"
  - "DoFieldExchange-Methode, Und RFX-Funktionen"
  - "Funktionsaufrufe, RFX-Funktionen"
  - "ODBC [C++], Datentypen"
  - "ODBC [C++], RFX"
  - "RFX (ODBC) [C++], Datentypen"
  - "RFX (ODBC) [C++], Funktionssyntax und -parameter"
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Datensatzfeldaustausch: Verwenden der RFX-Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie Sie die RFX\-Funktionsaufrufe verwenden, die das Kernstück der `DoFieldExchange`\-Überschreibung bilden.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von [CRecordset](../../mfc/reference/crecordset-class.md) abgeleitete Klassen, in denen der gesammelte Zeilenabruf nicht implementiert wurde.  Beim gesammelten Abrufen von Zeilen wird der Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) implementiert.  Der Bulk\-RFX ist mit RFX vergleichbar.  Unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) werden die Unterschiede erläutert.  
  
 Die globalen RFX\-Funktionen übertragen Daten zwischen Spalten der Datenquelle und Felddatenmembern des Recordsets.  Sie erstellen die RFX\-Funktionsaufrufe in der [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Memberfunktion des Recordsets.  In diesem Thema werden diese Funktionen kurz beschrieben und die Datentypen aufgeführt, für die RFX\-Funktionen zur Verfügung stehen.  Der [Technische Hinweis 43](../../mfc/tn043-rfx-routines.md) beschreibt, wie Sie für zusätzliche Datentypen eigene RFX\-Funktionen erstellen können.  
  
##  <a name="_core_rfx_function_syntax"></a> Syntax der RFX\-Funktionen  
 Jede RFX\-Funktion verfügt über drei Parameter \(manche haben zusätzlich einen optionalen vierten und fünften Parameter\):  
  
-   Einen Zeiger auf ein [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)\-Objekt.  Sie übergeben einfach den an `DoFieldExchange` übergebenen `pFX`\-Zeiger.  
  
-   Den Namen der Spalte, wie er in der Datenquelle angezeigt wird.  
  
-   Den Namen des zugehörigen Felddatenmembers oder Parameterdatenmembers in der Recordset\-Klasse.  
  
-   \(Optional\) In manchen Funktionen die Maximallänge der Zeichenfolge oder des Arrays, das übertragen wird.  Der Standardwert beträgt 255 Bytes, kann aber bei Bedarf geändert werden.  Die Maximalgröße leitet sich von der Maximalgröße eines `CString`\-Objekts ab \(**INT\_MAX** \(2.147.483.647 Bytes\)\), meist treten aber schon vor Erreichen dieser Grenze Einschränkungen des Treibers in Kraft;  
  
-   \(Optional\) In der Funktion `RFX_Text` legen Sie manchmal in einem fünften Parameter den Datentyp einer Spalte fest.  
  
 Weitere Informationen finden Sie in der Dokumentation der RFX\-Funktionen unter [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) \(nur auf Englisch verfügbar\) in der *Class Library Reference*.  Ein Beispiel für die spezielle Verwendung von Parametern finden Sie unter [Recordset: Abrufen von SUMs und anderen Aggregatergebnissen \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a> RFX\-Datentypen  
 Die Klassenbibliothek stellt RFX\-Funktionen für die Übertragung vieler verschiedener Datentypen zwischen der Datenquelle und den Recordsets zur Verfügung.  In der folgenden Liste sind die RFX\-Funktionen nach Datentyp zusammengefasst.  Falls Sie eigene RFX\-Funktionsaufrufe erstellen möchten, können Sie anhand des Datentyps in dieser Liste die richtige Funktion auswählen.  
  
|Funktion|Datentyp|  
|--------------|--------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  
 Weitere Informationen finden Sie in der Dokumentation der RFX\-Funktionen unter [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) \(nur auf Englisch verfügbar\) in der *Class Library Reference*.  Informationen über die Zuordnung von C\+\+\-Datentypen zu SQL\-Datentypen finden Sie in der Zuordnungstabelle zwischen C\+\+\-Datentypen und ANSI\-SQL\-Datentypen unter [SQL: SQL\- und C\+\+\-Datentypen \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## Siehe auch  
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)