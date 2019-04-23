---
title: 'Datensatzfeldaustausch: Verwenden der RFX-Funktionen'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: dc717336a5279e7eda1b7c39b19a7c76f9055cd3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035983"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Datensatzfeldaustausch: Verwenden der RFX-Funktionen

In diesem Thema wird erläutert, wie mit RFX-Funktionsaufrufe, die den Text des machen Ihre `DoFieldExchange` außer Kraft setzen.

> [!NOTE]
>  Dieses Thema gilt für Klassen, die von [CRecordset](../../mfc/reference/crecordset-class.md) in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird die Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Die globalen RFX-Funktionen Austausch von Daten zwischen den Spalten für die Quelle und das Feld Daten Datenmember im Recordset. Sie schreiben den RFX-Funktionsaufrufe in des Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Member-Funktion. In diesem Thema werden die Funktionen kurz beschrieben und zeigt die Datentypen, die für die RFX-Funktionen zur Verfügung stehen. [Technischer Hinweis 43](../../mfc/tn043-rfx-routines.md) beschreibt, wie Sie Ihre eigenen RFX-Funktionen für zusätzliche Datentypen zu erstellen.

##  <a name="_core_rfx_function_syntax"></a> Die Syntax der RFX-Funktion

Jede RFX-Funktion akzeptiert drei Parameter (und einige akzeptieren eines optionalen vierten oder fünften Parameters):

- Ein Zeiger auf eine [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) Objekt. Sie übergeben einfach den `pFX` Zeiger übergeben wird, um `DoFieldExchange`.

- Der Name der Spalte, wie er wird in der Datenquelle angezeigt.

- Der Name des entsprechenden Datenmember für Feld oder Parameter-Datenmember in den Recordset-Klasse.

- (Optional) In einigen der Funktionen, die maximale Länge der Zeichenfolge oder Array übertragen werden. Dies ist standardmäßig auf 255 Bytes, aber Sie können es ändern möchten. Die maximale Größe basiert auf der maximalen Größe von einer `CString` Objekt – **INT_MAX** (2.147.483.647) Bytes – aber treten wahrscheinlich Treiber-Einschränkungen, bevor Sie diese Größe.

- (Optional) In der `RFX_Text` Funktion Sie manchmal verwenden, einen fünften Parameter um den Datentyp einer Spalte angeben.

Weitere Informationen finden Sie unter der RFX-Funktionen unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in die *Klassenbibliotheksreferenz*. Wenn Sie spezielle vornehmen können ein Beispiel für die Parameter, finden Sie unter [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).

##  <a name="_core_rfx_data_types"></a> RFX-Datentypen

Die Klassenbibliothek stellt RFX-Funktionen für die Übertragung von vielen verschiedenen Datentypen zwischen der Datenquelle und Ihre Recordsets. Die folgende Liste enthält die RFX-Funktionen durch-Datentyp. Wählen Sie in Fällen, in dem Sie Ihre eigenen RFX-Funktionsaufrufe schreiben müssen aus dieser Funktionen durch-Datentyp.

|Funktion|Datentyp|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|


Weitere Informationen finden Sie in der Dokumentation der RFX-Funktionen unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in die *Klassenbibliotheksreferenz*. Informationen zur Zuordnung von C++-Datentypen in SQL-Datentypen finden Sie in der Tabelle der ANSI SQL Data-Typen zugeordnet, C++-Datentypen in [SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

## <a name="see-also"></a>Siehe auch

[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange-Klasse](../../mfc/reference/cfieldexchange-class.md)