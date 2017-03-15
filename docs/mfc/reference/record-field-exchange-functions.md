---
title: Aufzeichnen von-Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions
- DFX functions
- bulk RFX functions
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 87b658cab22ad1aa5db17a00d1d3817e55ff4fc7
ms.lasthandoff: 02/24/2017

---
# <a name="record-field-exchange-functions"></a>Funktionen für den Datensatzfeldaustausch
Dieses Thema enthält Informationen über den Datensatzfeldaustausch (RFX, Bulk-RFX und DFX) Funktionen, die die Übertragung von Daten zwischen einem Recordset-Objekt und die zugehörigen Daten zu automatisieren und andere Vorgänge auf die Daten verwendet.  
  
 Wenn Sie die ODBC-basierten Klassen verwenden und einen Massenzeilenabruf implementiert haben, müssen Sie die `DoBulkFieldExchange` -Memberfunktion des `CRecordset` manuell überschreiben, indem Sie die Bulk-RFX-Funktionen für jedes Datenelement aufrufen, das einer Datenquellspalte entspricht.  
  
 Wenn Sie den Massenzeilenabruf in den ODBC-basierten Klassen implementiert haben oder die DAO-basierten Klassen verwenden, dann überschreibt der ClassWizard die `DoFieldExchange` -Memberfunktion von `CRecordset` oder `CDaoRecordset` durch Aufrufen der RFX-Funktionen (für ODBC-Klassen) oder der DFX-Funktionen (für DAO-Klassen) für jedes Felddatenelement im Recordset.  
  
 Die Datensatzfeldaustausch-Funktionen übertragen jedes Mal Daten, wenn das Framework `DoFieldExchange` oder `DoBulkFieldExchange`aufruft. Jede Funktion überträgt einen bestimmten Datentyp.  
  
 Weitere Informationen über die Verwendung dieser Funktionen finden Sie in den Artikeln [Datensatzfeldaustausch: wie RFX Works (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Für Datenspalten, die Sie dynamisch zu binden, können Sie aufrufen, die RFX oder DFX-Funktionen, wie im Artikel erläutert [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Darüber hinaus können Sie Ihre eigenen benutzerdefinierten RFX oder DFX-Routinen schreiben, wie im technischen Hinweis erläutert [43](../../mfc/tn043-rfx-routines.md) (für ODBC) und technische Hinweis [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (für DAO).  
  
 Ein Beispiel für RFX und Sammel-RFX-Funktionen wie in der `DoFieldExchange` und `DoBulkFieldExchange` -Funktionen finden Sie unter [RFX_Text](#rfx_text) und [RFX_Text_Bulk] #Rfx_text_bulk). DFX-Funktionen sind den RFX-Funktionen sehr ähnlich.  
  
### <a name="rfx-functions-odbc"></a>RFX-Funktionen (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary](#rfx_binary)|Überträgt die Arrays von Bytes vom Typ [CByteArray](cbytearray-class.md).|  
|[RFX_Bool](#rfx_bool)|Überträgt boolesche Daten.|  
|[RFX](#rfx_byte)|Überträgt ein einzelnes Byte an Daten.|  
|[RFX_Date](#rfx_date)|Überträgt die Uhrzeit und Datum mit [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder **TIMESTAMP_STRUCT**.|  
|[RFX_Double](#rfx_double)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|  
|[RFX_Int](#rfx_int)|Überträgt Ganzzahldaten.|  
|[RFX](#rfx_long)|Überträgt lange Ganzzahldaten.|  
|[RFX_LongBinary](#rfx_longbinary)|Überträgt Daten von binary large Object (BLOB) durch ein Objekt mit dem [CLongBinary](clongbinary-class.md) Klasse.|  
|[RFX_Single](#rfx_single)|Überträgt Gleitkommadaten.|  
|[RFX_Text](#rfx_text)|Überträgt Zeichenfolgendaten.|  
  
### <a name="bulk-rfx-functions-odbc"></a>Bulk-RFX-Funktionen (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Überträgt Arrays von Bytedaten.|  
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Überträgt Arrays von booleschen Daten.|  
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Überträgt Arrays von Einzelbytes.|  
|[RFX_Date_Bulk](#rfx_date_bulk)|Überträgt Arrays von Daten des Typs **TIMESTAMP_STRUCT**.|  
|[RFX_Double_Bulk](#rfx_double_bulk)|Überträgt Arrays von Gleitkommadaten mit doppelter Genauigkeit.|  
|[RFX_Int_Bulk](#rfx_int_bulk)|Überträgt Arrays von Ganzzahldaten.|  
|[RFX_Long_Bulk](#rfx_long_bulk)|Überträgt Arrays von langen Ganzzahldaten.|  
|[RFX_Single_Bulk](#rfx_single_bulk)|Überträgt Arrays von Gleitkommadaten.|  
|[RFX_Text_Bulk](#rfx_text_bulk)|Überträgt Arrays von Daten des Typs **LPSTR**.|  
  
### <a name="dfx-functions-dao"></a>DFX-Funktionen (DAO)  
  
|||
|-|-|  
|[DFX_Binary](#dfx_binary)|Überträgt die Arrays von Bytes vom Typ [CByteArray](cbytearray-class.md).|  
|[DFX_Bool](#dfx_bool)|Überträgt boolesche Daten.|  
|[DFX](#dfx_byte)|Überträgt ein einzelnes Byte an Daten.|  
|[DFX_Currency](#dfx_currency)|Überträgt Daten vom Typ Currency [COleCurrency](colecurrency-class.md).|  
|[DFX_DateTime](#dfx_datetime)|Überträgt die Datums- und Uhrzeitdaten vom Typ [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX_Double](#dfx_double)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|  
|[DFX](#dfx_long)|Überträgt lange Ganzzahldaten.|  
|[DFX_LongBinary](#dfx_longbinary)|Überträgt BLOB-Daten (Binary Large Object) mit einem Objekt der `CLongBinary` -Klasse. DAO wird empfohlen, dass Sie verwenden [DFX_Binary](#dfx_binary) stattdessen.|  
|[DFX_Short](#dfx_short)|Überträgt kurze Ganzzahldaten.|  
|[DFX_Single](#dfx_single)|Überträgt Gleitkommadaten.|  
|[DFX_Text](#dfx_text)|Überträgt Zeichenfolgendaten.|  

 =============================================

## <a name="a-namerfxbinarya--rfxbinary"></a><a name="rfx_binary"></a>RFX_Binary
Arrays von Bytes zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_BINARY**, **SQL_VARBINARY**, oder **SQL_LONGVARBINARY**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Binary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CByteArray& value,  
   int nMaxLength = 255);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Zeichenfolge oder des Arrays, das übertragen. Der Standardwert von `nMaxLength` ist 255. Zulässige Werte sind 1 bis zu `INT_MAX`. Das Framework ordnet diese Menge an Speicherplatz für die Daten. Übergeben Sie den Wert, der groß genug für die größten Datenelement, das Sie erwarten, für eine optimale Leistung.  
  
### <a name="remarks"></a>Hinweise  
 Daten in der Datenquelle dieser Typen zugeordnet ist, und vom Typ `CByteArray` im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxboola--rfxbool"></a><a name="rfx_bool"></a>RFX_Bool
Boolesche Daten zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_BIT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Bool(  
   CFieldExchange* pFX,  
   const char* szName,  
   BOOL& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **BOOL**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxbytea--rfxbyte"></a><a name="rfx_byte"></a>RFX
Übertragungen einzelner Bytes zwischen den Felddatenmembern ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_TINYINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Byte(  
   CFieldExchange* pFX,  
   const char* szName,  
   BYTE& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **BYTE**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxdatea--rfxdate"></a><a name="rfx_date"></a>RFX_Date
Überträgt `CTime` oder **TIMESTAMP_STRUCT** Daten zwischen den Felddatenmembern ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_DATE**, **SQL_TIME**, oder **SQL_TIMESTAMP**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Date(  
   CFieldExchange* pFX,  
   const char* szName,  
   CTime& value);
  
void RFX_Date(  
   CFieldExchange* pFX,  
   const char* szName,  
   TIMESTAMP_STRUCT& value);
  
void RFX_Date(  
   CFieldExchange* pFX,  
   const char* szName,  
   COleDateTime& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert; der Wert übertragen werden. Die verschiedenen Versionen der Funktion werden verschiedene Datentypen für Wert:  
  
 Die erste Version der Funktion akzeptiert einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt. Für eine Übertragung vom Recordset die Datenquelle wird dieser Wert aus den angegebenen Datenmember verwendet. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 Die zweite Version der Funktion akzeptiert einen Verweis auf eine **TIMESTAMP_STRUCT** Struktur. Sie müssen diese Struktur selbst vor dem Aufruf einrichten. Weder Dialogdatenaustausch (DDX) unterstützt, noch Code-Assistenten-Unterstützung ist für diese Version verfügbar. Die dritte Version der Funktion arbeitet ähnlich wie die erste Version mit der Ausnahme, dauert es einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTime` Version der Funktion erzwingt den Aufwand für fortgeschrittene verarbeiten und hat einen Bereich eingeschränkten. Wenn Sie entweder diese Faktoren eingeschränkt finden, verwenden Sie die zweite Version der Funktion. Beachten Sie jedoch das Fehlen des Code-Assistenten und DDX-Unterstützung und die Anforderung, die Sie der Struktur selbst eingerichtet.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxdoublea--rfxdouble"></a><a name="rfx_double"></a>RFX_Double
Überträgt **double-Float** Daten zwischen den Felddatenmembern ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_DOUBLE**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Double(  
   CFieldExchange* pFX,  
   const char* szName,  
   double& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxinta--rfxint"></a><a name="RFX_Int"></a>RFX_Int
Ganzzahlige Daten zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs `int`, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxlonga--rfxlong"></a><a name="RFX_Long"></a>RFX
Lange ganze Zahl werden Daten zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle der ODBC-Datentyp **SQL_INTEGER**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Long(  
   CFieldExchange* pFX,  
   const char* szName,  
   LONG&   
value );  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **lang**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="a-namerfxlongbinarya--rfxlongbinary"></a><a name="RFX_LongBinary"></a>RFX_LongBinary
Übertragung von binary large Object (BLOB)-Daten, die mithilfe der Klasse [CLongBinary](clongbinary-class.md) zwischen den Felddatenmembern ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_LONGVARBINARY** oder **SQL_LONGVARCHAR**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_LongBinary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CLongBinary& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs `CLongBinary`, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxsinglea--rfxsingle"></a><a name="rfx_single"></a>RFX_Single
Gleitkommadaten zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_REAL**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Single(  
   CFieldExchange* pFX,  
   const char* szName,  
   float& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **Float**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  

## <a name="a-namerfxtexta--rfxtext"></a><a name="rfx_text"></a>RFX_Text
Überträgt `CString` Daten zwischen den Felddatenmembern ein `CRecordset` -Objekt und Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, oder **SQL_NUMERIC**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Text(  
   CFieldExchange* pFX,  
   const char* szName,  
   CString& value,  
   int nMaxLength = 255,  
   int nColumnType = SQL_VARCHAR,  
   short nScale = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse `CFieldExchange`. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs `CString`, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Zeichenfolge oder des Arrays, das übertragen. Der Standardwert von `nMaxLength` ist 255. Gültige Werte sind 1 bis `INT_MAX`). Das Framework ordnet diese Menge an Speicherplatz für die Daten. Übergeben Sie den Wert, der groß genug für die größten Datenelement, das Sie erwarten, für eine optimale Leistung.  
  
 *nColumnType*  
 In erster Linie für Parameter verwendet. Eine ganze Zahl, die den Datentyp des Parameters angibt. Der Typ ist ein ODBC-Datentyp des Formulars **SQL_XXX**.  
  
 `nScale`  
 Gibt den Maßstab für Werte vom Typ ODBC **SQL_DECIMAL** oder **SQL_NUMERIC**. `nScale`Dieser ist ist nur nützlich, wenn Sie Parameterwerte festlegen. Weitere Informationen finden Sie im Thema "Genauigkeit, Dezimalstellen, Länge und Größe" in Anhang D der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Daten in der Datenquelle, der alle diese Typen zugeordnet ist, und `CString` im Recordset.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe `RFX_Text`. Beachten Sie auch die beiden Aufrufe von `CFieldExchange::SetFieldType`. Für Parameter müssen Sie den Aufruf von schreiben `SetFieldType` und seinem RFX-Aufruf. Der Aufruf der Ausgabe-Spalte und seine zugehörigen RFX-Aufrufe werden normalerweise von einem Code-Assistenten geschrieben.  
  
```cpp  
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  


## <a name="a-namerfxbinarybulka--rfxbinarybulk"></a><a name="rfx_binary_Bulk"></a>RFX_Binary_Bulk
Übertragen Sie mehrere Zeilen vom Typ Byte aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Binary_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE** prgByteVals,  
   long** prgLengths,  
   int nMaxLength);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgByteVals`  
 Ein Zeiger auf ein Array von **BYTE** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgByteVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Werte im Array auf die gespeicherten `prgByteVals`. Um sicherzustellen, dass die Daten nicht abgeschnitten werden, übergeben Sie einen Wert für das größte Datenelement ausreicht, das Sie erwarten.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können einen ODBC-Typ **SQL_BINARY**, **SQL_VARBINARY**, oder **SQL_LONGVARBINARY**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **BYTE**.  
  
 Wenn Sie initialisieren `prgByteVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Um das Recordset aktualisierbar zu machen, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxboolbulka--rfxboolbulk"></a><a name="rfx_bool_Bulk"></a>RFX_Bool_Bulk
Überträgt die mehrere Zeilen mit boolesche Daten aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Bool_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL** prgBoolVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgBoolVals`  
 Ein Zeiger auf ein Array von **BOOL** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgBoolVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen Sie einen ODBC-Typ **SQL_BIT**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **BOOL**.  
  
 Wenn Sie initialisieren `prgBoolVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxbytebulka--rfxbytebulk"></a><a name="rfx_byte_Bulk"></a>RFX_Byte_Bulk
Überträgt die mehrere Zeilen mit einzelnen Bytes aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Byte_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE** prgByteVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgByteVals`  
 Ein Zeiger auf ein Array von **BYTE** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgByteVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen Sie einen ODBC-Typ **SQL_TINYINT**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **BYTE**.  
  
 Wenn Sie initialisieren `prgByteVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="a-namerfxdatebulka--rfxdatebulk"></a><a name="rfx_date_Bulk"></a>RFX_Date_Bulk
Übertragen Sie mehrere Zeilen in der **TIMESTAMP_STRUCT** Daten aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Date_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   TIMESTAMP_STRUCT** prgTSVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgTSVals`  
 Ein Zeiger auf ein Array von **TIMESTAMP_STRUCT** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden. Weitere Informationen zu den **TIMESTAMP_STRUCT** -Datentyp, finden Sie im Thema "C-Datentypen" in Anhang D der *ODBC SDK Programmer's Reference*.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgTSVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können einen ODBC-Typ **SQL_DATE**, **SQL_TIME**, oder **SQL_TIMESTAMP**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **TIMESTAMP_STRUCT**.  
  
 Wenn Sie initialisieren `prgTSVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxdoublebulka--rfxdoublebulk"></a><a name="rfx_double_Bulk"></a>RFX_Double_Bulk
Überträgt die mehrere Zeilen mit doppelter Genauigkeit, Gleitkomma-Daten aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Double_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   double** prgDblVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgDblVals`  
 Ein Zeiger auf ein Array von **doppelte** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgDblVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen Sie einen ODBC-Typ **SQL_DOUBLE**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **doppelte**.  
  
 Wenn Sie initialisieren `prgDblVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxintbulka--rfxintbulk"></a><a name="RFX_Int_Bulk"></a>RFX_Int_Bulk
Ganzzahlige Daten zwischen den Felddatenmembern übertragen ein `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs `int`, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxlongbulka--rfxlongbulk"></a><a name="RFX_Long_Bulk"></a>RFX_Long_Bulk
Übertragen Sie mehrere Datenzeilen mit long integer-Wert aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Long_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   long** prgLongVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgLongVals`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgLongVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen Sie einen ODBC-Typ **SQL_INTEGER**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **lang**.  
  
 Wenn Sie initialisieren `prgLongVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namerfxsinglebulka--rfxsinglebulk"></a><a name="rfx_single_Bulk"></a>RFX_Single_Bulk
Überträgt die mehrere Zeilen mit Gleitkommadaten aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Single_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   float** prgFltVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgFltVals`  
 Ein Zeiger auf ein Array von **Float** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgFltVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen Sie einen ODBC-Typ **SQL_REAL**. Das Recordset muss einen Felddatenmember des Typs Zeiger zu definieren **Float**.  
  
 Wenn Sie initialisieren `prgFltVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  

## <a name="a-namerfxtextbulka--rfxtextbulk"></a><a name="rfx_text_Bulk"></a>RFX_Text_Bulk
Überträgt die mehrere Zeilen mit Daten aus einer Spalte mit einer ODBC-Datenquelle in einem entsprechenden Array in ein `CRecordset`-abgeleitetes Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Text_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   LPSTR* prgStrVals,  
   long** prgLengths,  
   int nMaxLength);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgStrVals`  
 Ein Zeiger auf ein Array von **LPSTR** Werte. Dieses Array speichert die Daten aus der Datenquelle in das Recordset übertragen werden. Beachten Sie, dass mit der aktuellen Version von ODBC, um diese Werte können nicht Unicode.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von Ganzzahlen. Dieses Array speichert die Länge in Bytes der einzelnen Werte im Array auf die `prgStrVals`. Diese Länge schließt abschließendes null-Zeichen. Beachten Sie, dass der Wert **SQL_NULL_DATA** das entsprechende Datenelement enthält einen Nullwert gespeichert werden. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Werte im Array auf die gespeicherten `prgStrVals`, einschließlich der abschließendes null-Zeichen. Um sicherzustellen, dass die Daten nicht abgeschnitten werden, übergeben Sie einen Wert für das größte Datenelement ausreicht, das Sie erwarten.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können einen ODBC-Typ **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, oder **SQL_NUMERIC**. Das Recordset muss einen Felddatenmember vom Typ definieren **LPSTR**.  
  
 Wenn Sie initialisieren `prgStrVals` und `prgLengths` auf **NULL**, und klicken Sie dann die Arrays zeigen mit der Rowsetgröße gleich automatisch zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle in das Recordset-Objekt. Damit das Recordset aktualisierbar ist, verwenden Sie die ODBC-API-Funktion **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Sie müssen Aufrufe manuell schreiben, der `DoBulkFieldExchange` außer Kraft setzen. Dieses Beispiel zeigt einen Aufruf von `RFX_Text_Bulk`, sowie der Aufruf von `RFX_Long_Bulk`, für die Datenübertragung. Diese Aufrufe sind gekennzeichnet durch einen Aufruf von [CFieldExchange::](CFieldExchange::SetFieldType.md). Beachten Sie, dass für Parameter, die RFX-Funktionen anstelle der Bulk-RFX-Funktionen aufgerufen werden muss.  
  
```cpp  
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
``` 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="a-namedfxbinarya--dfxbinary"></a><a name="dfx_binary"></a>DFX_Binary
Arrays von Bytes zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Binary(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   CByteArray& value,  
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,  
   DWORD dwBindOptions = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nPreAllocSize`  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz als benötigt. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern. Die Standardgröße ist in der AFXDAO definiert. H-Datei als **AFX_DAO_BINARY_DEFAULT_SIZE**.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_DISABLE_FIELD_CACHE`ist nicht für die Verwendung doppelter Pufferung und müssen Sie aufrufen, [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst. Der mögliche Wert `AFX_DAO_ENABLE_FIELD_CACHE`, Doppelpufferung verwendet, und Sie keine zusätzliche Arbeit zum Markieren von Feldern modifiziert oder Null. Vermeiden Sie dieser Wert Gründen der Leistungsfähigkeit und Arbeitsspeicher, wenn die binären Daten relativ klein ist.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte wird durch die Einstellung für alle Felder standardmäßig gepuffert [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_BYTES** von DAO und Typ [CByteArray](cbytearray-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="a-namedfxboola--dfxbool"></a><a name="dfx_bool"></a>DFX_Bool
Boolesche Daten zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Bool(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **BOOL**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_BOOL** von DAO und Typ **BOOL** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxbytea--dfxbyte"></a><a name="dfx_byte"></a>DFX
Überträgt einzelner Bytes zwischen den Felddatenmembern ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Byte(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **BYTE**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_BYTES** von DAO und Typ **BYTE** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxcurrencya--dfxcurrency"></a><a name="dfx_currency"></a>DFX_Currency
Werden Währungsdaten zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Currency(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleCurrency& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Dieser Wert stammt für eine Übertragung vom Recordset die Datenquelle, aus den angegebenen Datenmember vom Typ [COleCurrency](colecurrency-class.md). Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_CURRENCY** von DAO und Typ [COleCurrency](colecurrency-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxdatetimea--dfxdatetime"></a><a name="dfx_datetime"></a>DFX_DateTime
Datum und Uhrzeit werden Daten zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_DateTime(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleDateTime& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Die Funktion akzeptiert einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt. Für eine Übertragung vom Recordset die Datenquelle wird dieser Wert aus den angegebenen Datenmember verwendet. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_DATE** von DAO und Typ [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) im Recordset.  
  
> [!NOTE]
>  `COleDateTime`ersetzt [CTime](../../atl-mfc-shared/reference/ctime-class.md) und **TIMESTAMP_STRUCT** zu diesem Zweck in den DAO-Klassen. `CTime`und **TIMESTAMP_STRUCT** werden weiterhin für die ODBC-basierten Datenzugriffsklassen verwendet.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxdoublea--dfxdouble"></a><a name="dfx_double"></a>DFX_Double
Überträgt **double-Float** Daten zwischen den Felddatenmembern ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Double(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   double& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_R8** von DAO und Typ **double-Float** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxlonga--dfxlong"></a><a name="dfx_long"></a>DFX
Lange ganze Zahl werden Daten zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Long(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   long& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **lang**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_I4** von DAO und Typ **lange** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="a-namedfxlongbinarya--dfxlongbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary
**Wichtige** es wird empfohlen, die Verwendung von [DFX_Binary](#dfx_binary) anstatt dieser Funktion.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_LongBinary(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   CLongBinary& value,  
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,  
   DWORD dwBindOptions = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs [CLongBinary](clongbinary-class.md), stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 *dwPreAllocSize*  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz als benötigt. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung **AFX_DISABLE_FIELD_CACHE**, doppelte Pufferung nicht verwenden. Der andere Wert ist `AFX_DAO_ENABLE_FIELD_CACHE`. Doppelpufferung verwendet, und Sie keine zusätzliche Arbeit zum Markieren von Feldern modifiziert oder Null. Vermeiden Sie dieser Wert Gründen der Leistungsfähigkeit und Arbeitsspeicher, wenn die binären Daten relativ klein ist.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 `DFX_LongBinary`wird für die Kompatibilität mit den MFC-ODBC-Klassen bereitgestellt werden. Die `DFX_LongBinary` Funktion überträgt Daten binary large-Object (BLOB) mithilfe der Klasse `CLongBinary` zwischen den Felddatenmembern ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle. Daten werden zwischen dem Typ zugeordnet **DAO_BYTES** von DAO und Typ [CLongBinary](clongbinary-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxshorta--dfxshort"></a><a name="dfx_short"></a>DFX_Short
Überträgt kurze ganzzahlige Daten zwischen den Felddatenmembern ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Short(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   short& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **kurze**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_I2** von DAO und Typ **kurze** im Recordset.  
  
> [!NOTE]
>  `DFX_Short`entspricht dem [RFX_Int](#rfx_int) für die ODBC-basierten Klassen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="a-namedfxsinglea--dfxsingle"></a><a name="dfx_single"></a>DFX_Single
Gleitkommadaten zwischen den Felddatenmembern übertragen ein [CDaoRecordset](cdaorecordset-class.md) Objekt und den Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Single(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   float& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs **Float**, stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_R4** von DAO und Typ **Float** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="a-namedfxtexta--dfxtext"></a><a name="dfx_text"></a>DFX_Text
Überträgt `CString` Daten zwischen den Felddatenmembern ein [CDaoRecordset](cdaorecordset-class.md) Objekt und Spalten eines Datensatzes in der Datenquelle.  
  
### <a name="syntax"></a>Syntax  
  
```
void AFXAPI DFX_Text(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   CString& value,  
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung vom Recordset in die Datenquelle, die den Wert des Typs [CString](../../atl-mfc-shared/reference/cstringt-class.md), stammt aus den angegebenen Datenmember. Für eine Übertragung Recordset aus der Datenquelle wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nPreAllocSize`  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz als benötigt. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern.  
  
 `dwBindOptions`  
 Eine Option, mit der Sie den Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung auf dieses Feld. Sie müssen Aufrufen [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten werden zwischen dem Typ zugeordnet **DAO_CHAR** in DAO (oder, wenn das Symbol **_UNICODE** definiert ist, **DAO_WCHAR aus**) und [CString](../../atl-mfc-shared/reference/cstringt-class.md) im Recordset.  n
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe `DFX_Text`. Beachten Sie auch die beiden Aufrufe von [CDaoFieldExchange:: SetFieldType](cdaofieldexchange-class.md#setfieldtype). Sie müssen beim ersten Aufruf schreiben `SetFieldType` und seine **DFX** aufrufen. Der zweite Aufruf und die zugehörigen **DFX** Aufrufe werden normalerweise durch den Code-Assistenten, der die Klasse generiert geschrieben.  
  
```cpp  
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CRecordset:: DoFieldExchange](crecordset-class.md#dofieldexchange)   
 [CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)   
 [CDaoRecordset:: DoFieldExchange](cdaorecordset-class.md#dofieldexchange)


