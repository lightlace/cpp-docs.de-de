---
title: 'Datensatzfeldaustausch: Verwenden der RFX-Funktionen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a270b26fc0fd9be721ee0656f9f0d14ab579b477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Datensatzfeldaustausch: Verwenden der RFX-Funktionen
In diesem Thema wird erläutert, wie die RFX-Funktionsaufrufe verwenden, die den Text der Ihre `DoFieldExchange` außer Kraft setzen.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von abgeleiteten Klassen [CRecordset](../../mfc/reference/crecordset-class.md) in denen der gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird der Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Um die Unterschiede zu verstehen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Die globalen RFX-Funktionen Austausch von Daten zwischen den Spalten in der Datenquelle und Felddatenmembern im Recordset. Sie schreiben die RFX-Funktionsaufrufe in des Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Memberfunktion. In diesem Thema werden die Funktionen kurz beschrieben und zeigt die Datentypen für die RFX-Funktionen zur Verfügung stehen. [Technische Hinweis 43](../../mfc/tn043-rfx-routines.md) beschreibt, wie Sie Ihre eigenen RFX-Funktionen für zusätzliche Datentypen zu schreiben.  
  
##  <a name="_core_rfx_function_syntax"></a>Die Syntax der RFX-Funktion  
 Jede RFX-Funktion akzeptiert drei Parameter (und einige nehmen eines optionalen vierten oder fünften Parameters):  
  
-   Ein Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt. Sie übergeben einfach die `pFX` Zeiger übergeben wird, um `DoFieldExchange`.  
  
-   Der Name der Spalte, die für die Datenquelle wird angezeigt.  
  
-   Der Name des entsprechenden Felds-Datenmember oder Parameter-Datenmember in der Recordsetklasse.  
  
-   (Optional) In einige der Funktionen, die maximale Länge der Zeichenfolge oder des Arrays, die übertragen werden. Wird standardmäßig auf 255 Byte, aber möglicherweise möchten ihn zu ändern. Die maximale Größe basiert darauf, dass die maximale Größe einer `CString` Objekt – **INT_MAX** (2.147.483.647) Bytes – aber treten wahrscheinlich Grenzwerte Treiber, bevor diese Größe.  
  
-   (Optional) In der `RFX_Text` -Funktion, Sie manchmal mithilfe eines fünften Parameters den Datentyp einer Spalte angeben.  
  
 Weitere Informationen finden Sie unter der RFX-Funktionen unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in der *Klassenbibliotheksreferenz*. Wenn Sie spezielle treffen möglicherweise ein Beispiel für die Parameter, finden Sie unter [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a>RFX-Datentypen  
 Die Klassenbibliothek stellt RFX-Funktionen für die Übertragung vieler verschiedener Datentypen zwischen der Datenquelle und Ihre Recordsets. Die folgende Liste fasst die RFX-Funktionen durch-Datentyp. Wählen Sie in Fällen, in denen Sie eigene RFX-Funktionsaufrufe schreiben müssen aus dieser Funktionen durch-Datentyp.  
  
|Funktion|Datentyp|  
|--------------|---------------|  
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
  

 Weitere Informationen finden Sie in der Dokumentation der RFX-Funktionen unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in der *Klassenbibliotheksreferenz*. Informationen wie die C++-Datentypen in SQL-Datentypen zugeordnet werden, finden Sie in der Tabelle, die ANSI SQL Data Typen zugeordnet, um C++-Datentypen in [SQL: SQL- und C++-Daten-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange-Klasse](../../mfc/reference/cfieldexchange-class.md)