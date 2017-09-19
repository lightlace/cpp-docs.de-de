---
title: "Zeichnen Sie Funktionen für | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: acabc4e9469560b67c5fe10bcb845517e05c7854
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="record-field-exchange-functions"></a>Funktionen für den Datensatzfeldaustausch
Dieses Thema enthält die Datensatzfeldaustausch (RFX, Bulk-RFX und DFX) Funktionen verwendet, um die Übertragung von Daten zwischen einem Recordset-Objekt und dessen Datenquelle automatisiert und andere Vorgänge auf die Daten ausführen.  
  
 Wenn Sie die ODBC-basierten Klassen verwenden und einen Massenzeilenabruf implementiert haben, müssen Sie die `DoBulkFieldExchange` -Memberfunktion des `CRecordset` manuell überschreiben, indem Sie die Bulk-RFX-Funktionen für jedes Datenelement aufrufen, das einer Datenquellspalte entspricht.  
  
 Wenn Sie den Massenzeilenabruf in den ODBC-basierten Klassen implementiert haben oder die DAO-basierten Klassen verwenden, dann überschreibt der ClassWizard die `DoFieldExchange` -Memberfunktion von `CRecordset` oder `CDaoRecordset` durch Aufrufen der RFX-Funktionen (für ODBC-Klassen) oder der DFX-Funktionen (für DAO-Klassen) für jedes Felddatenelement im Recordset.  
  
 Die Datensatzfeldaustausch-Funktionen übertragen jedes Mal Daten, wenn das Framework `DoFieldExchange` oder `DoBulkFieldExchange`aufruft. Jede Funktion überträgt einen bestimmten Datentyp.  
  
 Weitere Informationen zur Verwendung dieser Funktionen finden Sie in den Artikeln [Datensatzfeldaustausch: wie RFX Works (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Für Datenspalten, die Sie dynamisch binden, können Sie auch die RFX- oder DFX-Funktionen selbst aufrufen, wie in den Artikeln erläutert [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Darüber hinaus können Sie Ihre eigenen benutzerdefinierten RFX- oder DFX-Routinen schreiben, wie im technischen Hinweis erläutert [43](../../mfc/tn043-rfx-routines.md) (für ODBC) und im technischen Hinweis [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (für DAO).  
  
 Ein Beispiel für RFX und Bulk-RFX-Funktionen wie in der `DoFieldExchange` und `DoBulkFieldExchange` -Funktionen finden Sie unter [RFX_Text](#rfx_text) und [RFX_Text_Bulk] #Rfx_text_bulk). DFX-Funktionen sind den RFX-Funktionen sehr ähnlich.  
  
### <a name="rfx-functions-odbc"></a>RFX-Funktionen (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary](#rfx_binary)|Überträgt Arrays von Bytes vom Typ [CByteArray](cbytearray-class.md).|  
|[RFX_Bool](#rfx_bool)|Überträgt boolesche Daten.|  
|[RFX](#rfx_byte)|Überträgt ein einzelnes Byte an Daten.|  
|[RFX_Date](#rfx_date)|Überträgt Uhrzeit- und Datumsdaten mit [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder **TIMESTAMP_STRUCT**.|  
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
|[DFX_Binary](#dfx_binary)|Überträgt Arrays von Bytes vom Typ [CByteArray](cbytearray-class.md).|  
|[DFX_Bool](#dfx_bool)|Überträgt boolesche Daten.|  
|[DFX](#dfx_byte)|Überträgt ein einzelnes Byte an Daten.|  
|[DFX_Currency](#dfx_currency)|Überträgt Währungsdaten vom Typ [COleCurrency](colecurrency-class.md).|  
|[DFX_DateTime](#dfx_datetime)|Überträgt Datums- und Uhrzeitdaten vom Typ [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX_Double](#dfx_double)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|  
|[DFX](#dfx_long)|Überträgt lange Ganzzahldaten.|  
|[DFX_LongBinary](#dfx_longbinary)|Überträgt BLOB-Daten (Binary Large Object) mit einem Objekt der `CLongBinary` -Klasse. Bei DAO wird empfohlen, dass Sie verwenden [DFX_Binary](#dfx_binary) stattdessen.|  
|[DFX_Short](#dfx_short)|Überträgt kurze Ganzzahldaten.|  
|[DFX_Single](#dfx_single)|Überträgt Gleitkommadaten.|  
|[DFX_Text](#dfx_text)|Überträgt Zeichenfolgendaten.|  

 =============================================

## <a name="rfx_binary"></a>RFX_Binary
Überträgt Arrays von Bytes zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_BINARY**, **SQL_VARBINARY**, oder **SQL_LONGVARBINARY**.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Zeichenfolge oder des Arrays, die übertragen werden. Der Standardwert von `nMaxLength` ist 255. Zulässige Werte sind 1 bis zu `INT_MAX`. Das Framework reserviert diese Menge des Speicherplatzes für die Daten an. Übergeben Sie den Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, für die optimale Leistung.  
  
### <a name="remarks"></a>Hinweise  
 Daten in der Datenquelle dieser Typen in und aus dem Typ zugeordnet ist `CByteArray` im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_bool"></a>RFX_Bool
Überträgt boolesche Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_BIT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Bool(  
   CFieldExchange* pFX,  
   const char* szName,  
   BOOL& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **BOOL**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_byte"></a>RFX
Übertragungen einzelner Bytes zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_TINYINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Byte(  
   CFieldExchange* pFX,  
   const char* szName,  
   BYTE& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **BYTE**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_date"></a>RFX_Date
Übertragungen `CTime` oder **TIMESTAMP_STRUCT** Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_DATE**, **SQL_TIME**, oder **SQL_TIMESTAMP**.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert; der Wert, der übertragen werden. Die verschiedenen Versionen der Funktion führen Sie für den Wert unterschiedliche Datentypen:  
  
 Die erste Version der Funktion akzeptiert einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt. Für eine Übertragung vom Recordset-Datenquelle ist dieser Wert aus den angegebenen Datenmember verwendet. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 Die zweite Version der Funktion akzeptiert einen Verweis auf eine **TIMESTAMP_STRUCT** Struktur. Sie müssen diese Struktur selbst vor dem Aufruf einrichten. Weder Dialogdatenaustausch (DDX) unterstützt, noch Code-Assistenten-Unterstützung für diese Version verfügbar ist. Die dritte Version der Funktion funktioniert auf ähnliche Weise auf die erste Version, außer dass es sich um einen Verweis auf verwendet eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTime` Version der Funktion erzwingt den Mehraufwand für fortgeschrittene verarbeiten und hat einen Bereich eingeschränkten. Wenn Sie entweder diese Faktoren beschränken zu finden, verwenden Sie die zweite Version der Funktion. Beachten Sie jedoch die mangelndes Code-Assistenten und DDX-Unterstützung und die Anforderung, die Sie die Struktur selbst eingerichtet.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_double"></a>RFX_Double
Übertragungen **vom Typ double Float** Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_DOUBLE**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Double(  
   CFieldExchange* pFX,  
   const char* szName,  
   double& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_int"></a>RFX_Int
Überträgt Ganzzahldaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs `int`, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_long"></a>RFX
Überträgt lange Ganzzahldaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_INTEGER**.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **lang**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="rfx_longbinary"></a>RFX_LongBinary
Überträgt Daten binary large Object (BLOB), die mithilfe der Klasse [CLongBinary](clongbinary-class.md) zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_LONGVARBINARY** oder **SQL_LONGVARCHAR**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_LongBinary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CLongBinary& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs `CLongBinary`, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_single"></a>RFX_Single
Überträgt Gleitkommadaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_REAL**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Single(  
   CFieldExchange* pFX,  
   const char* szName,  
   float& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **"float"**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  

## <a name="rfx_text"></a>RFX_Text
Übertragungen `CString` Daten zwischen den Felddatenmembern eine `CRecordset` Objekt und Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, oder **SQL_NUMERIC**.  
  
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
 Ein Zeiger auf ein Objekt der Klasse `CFieldExchange`. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs `CString`, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Zeichenfolge oder des Arrays, die übertragen werden. Der Standardwert von `nMaxLength` ist 255. Zulässige Werte sind 1 bis zu `INT_MAX`). Das Framework reserviert diese Menge des Speicherplatzes für die Daten an. Übergeben Sie den Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, für die optimale Leistung.  
  
 *nColumnType*  
 Wird hauptsächlich für Parameter verwendet. Eine ganze Zahl, die den Datentyp des Parameters angibt. Der Typ ist ein ODBC-Datentyp des Formulars **SQL_XXX**.  
  
 `nScale`  
 Gibt die Skalierung für Werte vom Typ ODBC **SQL_DECIMAL** oder **SQL_NUMERIC**. `nScale`Dieser ist ist nur nützlich, wenn Sie Parameterwerte festlegen. Weitere Informationen finden Sie im Thema "Genauigkeit, Dezimalstellen, Länge und Anzeigegröße" in Anhang D der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Daten in der Datenquelle, der alle diese Typen zugeordnet ist, in den und aus `CString` im Recordset.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe `RFX_Text`. Beachten Sie auch die beiden Aufrufe von `CFieldExchange::SetFieldType`. Für Parameter müssen Sie den Aufruf von schreiben `SetFieldType` und den RFX-Aufruf abgeschlossen. Der Aufruf der Ausgabe-Spalte und seine zugehörigen RFX-Aufrufe werden normalerweise von einem Code-Assistenten geschrieben.  
  
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


## <a name="rfx_binary_bulk"></a>RFX_Binary_Bulk
Übertragen mehrerer Datenzeilen Byte aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgByteVals`  
 Ein Zeiger auf ein Array von **BYTE** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgByteVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Werte im Array verweist gespeicherten `prgByteVals`. Um sicherzustellen, dass Daten nicht abgeschnitten werden, übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können als ODBC-Typ **SQL_BINARY**, **SQL_VARBINARY**, oder **SQL_LONGVARBINARY**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **BYTE**.  
  
 Wenn Sie initialisieren `prgByteVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_bool_bulk"></a>RFX_Bool_Bulk
Übertragen mehrerer booleschen Datenzeilen aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgBoolVals`  
 Ein Zeiger auf ein Array von **BOOL** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgBoolVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen einen ODBC-Typ des **SQL_BIT**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **BOOL**.  
  
 Wenn Sie initialisieren `prgBoolVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_byte_bulk"></a>RFX_Byte_Bulk
Übertragen von einzelbytes mehrere Zeilen aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgByteVals`  
 Ein Zeiger auf ein Array von **BYTE** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgByteVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen einen ODBC-Typ des **SQL_TINYINT**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **BYTE**.  
  
 Wenn Sie initialisieren `prgByteVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="rfx_date_bulk"></a>RFX_Date_Bulk
Überträgt die mehrere Zeilen mit **TIMESTAMP_STRUCT** Daten aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgTSVals`  
 Ein Zeiger auf ein Array von **TIMESTAMP_STRUCT** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen. Weitere Informationen zu den **TIMESTAMP_STRUCT** -Datentyp, finden Sie im Thema "C-Datentypen" in Anhang D der *ODBC SDK Programmer's Reference*.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgTSVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können als ODBC-Typ **SQL_DATE**, **SQL_TIME**, oder **SQL_TIMESTAMP**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **TIMESTAMP_STRUCT**.  
  
 Wenn Sie initialisieren `prgTSVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_double_bulk"></a>RFX_Double_Bulk
Übertragen mehrerer Datenzeilen mit doppelter Genauigkeit, ein Gleitkommawert aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgDblVals`  
 Ein Zeiger auf ein Array von **doppelte** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgDblVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen einen ODBC-Typ des **SQL_DOUBLE**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **doppelte**.  
  
 Wenn Sie initialisieren `prgDblVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_int_bulk"></a>RFX_Int_Bulk
Überträgt Ganzzahldaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes in der Datenquelle vom Typ ODBC **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Syntax  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf ein Objekt der Klasse [CDBException](cfieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen zu den Vorgängen ein `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs `int`, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_long_bulk"></a>RFX_Long_Bulk
Übertragen mehrerer Datenzeilen long integer-Wert aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgLongVals`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgLongVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen einen ODBC-Typ des **SQL_INTEGER**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **lang**.  
  
 Wenn Sie initialisieren `prgLongVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

## <a name="rfx_single_bulk"></a>RFX_Single_Bulk
Übertragen mehrerer Gleitkomma Datenzeilen aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgFltVals`  
 Ein Zeiger auf ein Array von **"float"** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgFltVals`. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte benötigen einen ODBC-Typ des **SQL_REAL**. Das Recordset muss einen Feldmember Daten vom typzeiger auf definieren **"float"**.  
  
 Wenn Sie initialisieren `prgFltVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  

## <a name="rfx_text_bulk"></a>RFX_Text_Bulk
Überträgt die mehrere Zeilen mit Zeichendaten aus einer Spalte mit einer ODBC-Datenquelle in eine entsprechende Array in eine `CRecordset`-abgeleitetes Objekt.  
  
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
 Ein Zeiger auf eine [CDBException](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 `prgStrVals`  
 Ein Zeiger auf ein Array von **LPSTR** Werte. Dieses Array speichert die Daten aus der Datenquelle auf das Recordset übertragen werden sollen. Beachten Sie, dass mit der aktuellen Version von ODBC, um diese Werte können nicht Unicode.  
  
 `prgLengths`  
 Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes, der jeden Wert im Array verweist `prgStrVals`. Diese Länge schließt null-Abschlusszeichen. Beachten Sie, dass der Wert **SQL_NULL_DATA** werden gespeichert werden, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLBindCol** in der *ODBC SDK Programmer's Reference*.  
  
 `nMaxLength`  
 Die maximal zulässige Länge der Werte im Array verweist gespeicherten `prgStrVals`, einschließlich des Zeichens null-Terminierung. Um sicherzustellen, dass Daten nicht abgeschnitten werden, übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten.  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquellenspalte können als ODBC-Typ **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, oder **SQL_NUMERIC**. Das Recordset muss einen Felddatenmember vom Typ definieren **LPSTR**.  
  
 Wenn Sie initialisieren `prgStrVals` und `prgLengths` auf **NULL**, und klicken Sie dann den Arrays, die sie verweisen, automatisch mit der Größe entspricht der Rowsetgröße zugeordnet werden.  
  
> [!NOTE]
>  Massen-Datensatzfeldaustausch überträgt nur Daten aus der Datenquelle auf das Recordsetobjekt. Um das Recordset aktualisierbar zu machen, müssen Sie die ODBC-API-Funktion verwenden **SQLSetPos**.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Beispiel  
 Sie müssen die Aufrufe manuell schreiben, Ihrem `DoBulkFieldExchange` außer Kraft setzen. Dieses Beispiel zeigt einen Aufruf von `RFX_Text_Bulk`, sowie einen Aufruf von `RFX_Long_Bulk`, für die Datenübertragung. Diese Aufrufe werden durch einen Aufruf von vorangestellt [CFieldExchange::](CFieldExchange::SetFieldType.md). Beachten Sie, dass für Parameter, die RFX-Funktionen, anstatt die Bulk-RFX-Funktionen aufgerufen werden muss.  
  
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

## <a name="dfx_binary"></a>DFX_Binary
Überträgt Arrays von Bytes zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nPreAllocSize`  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz nach Bedarf. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern. Die Standardgröße ist in der AFXDAO definiert. H-Datei als **AFX_DAO_BINARY_DEFAULT_SIZE**.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_DISABLE_FIELD_CACHE`ist nicht für die Verwendung doppelter Pufferung und rufen Sie [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst. Der mögliche Wert `AFX_DAO_ENABLE_FIELD_CACHE`, Doppelpufferung verwendet, und Sie müssen keine zusätzliche Aufgaben zum Markieren von Feldern modifizierte Seiten oder "Null". Leistung und Arbeitsspeicher Gründen vermeiden dieser Wert an, sofern die binären Daten relativ gering ist.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelten hierfür für alle Felder standardmäßig gepuffert [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_BYTES** in DAO und Datentyp [CByteArray](cbytearray-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="dfx_bool"></a>DFX_Bool
Überträgt boolesche Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **BOOL**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_BOOL** in DAO und Datentyp **BOOL** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_byte"></a>DFX
Übertragungen einzelner Bytes zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **BYTE**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_BYTES** in DAO und Datentyp **BYTE** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_currency"></a>DFX_Currency
Überträgt Währungsdaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Dieser Wert stammt für eine Übertragung vom Recordset-Datenquelle, aus den angegebenen Datenmember des Typs [COleCurrency](colecurrency-class.md). Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_CURRENCY** in DAO und Datentyp [COleCurrency](colecurrency-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_datetime"></a>DFX_DateTime
Überträgt Datums- und Uhrzeitdaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Die Funktion akzeptiert einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt. Für eine Übertragung vom Recordset-Datenquelle ist dieser Wert aus den angegebenen Datenmember verwendet. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_DATE** in DAO und Datentyp [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) im Recordset.  
  
> [!NOTE]
>  `COleDateTime`ersetzt [CTime](../../atl-mfc-shared/reference/ctime-class.md) und **TIMESTAMP_STRUCT** zu diesem Zweck in den DAO-Klassen. `CTime`und **TIMESTAMP_STRUCT** werden weiterhin für die ODBC-basierten Datenzugriffsklassen verwendet.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_double"></a>DFX_Double
Übertragungen **vom Typ double Float** Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_R8** in DAO und Datentyp **vom Typ double Float** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_long"></a>DFX
Überträgt lange Ganzzahldaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **lang**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_I4** in DAO und Datentyp **lange** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="dfx_longbinary"></a>DFX_LongBinary
**Wichtige** es wird empfohlen, die Verwendung von [DFX_Binary](#dfx_binary) statt diese Funktion.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs [CLongBinary](clongbinary-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 *dwPreAllocSize*  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz nach Bedarf. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung **AFX_DISABLE_FIELD_CACHE**, doppelte Pufferung nicht verwendet. Der andere Wert ist `AFX_DAO_ENABLE_FIELD_CACHE`. Verwendet die doppelte Pufferung, und Sie müssen keine zusätzliche Aufgaben zum Markieren von Feldern modifizierte Seiten oder "Null". Leistung und Arbeitsspeicher Gründen vermeiden dieser Wert an, sofern die binären Daten relativ gering ist.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 `DFX_LongBinary`wird für die Kompatibilität mit den MFC-ODBC-Klassen bereitgestellt werden. Die `DFX_LongBinary` Funktion überträgt binary large-Object (BLOB)-Daten mithilfe der Klasse `CLongBinary` zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle. Daten zwischen dem Typ zugeordnet ist **DAO_BYTES** in DAO und Datentyp [CLongBinary](clongbinary-class.md) im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_short"></a>DFX_Short
Überträgt kurze Ganzzahldaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **kurze**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_I2** in DAO und Datentyp **kurze** im Recordset.  
  
> [!NOTE]
>  `DFX_Short`entspricht dem [RFX_Int](#rfx_int) für die ODBC-basierten Klassen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  

## <a name="dfx_single"></a>DFX_Single
Überträgt Gleitkommadaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und die Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs **"float"**, stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_R4** in DAO und Datentyp **"float"** im Recordset.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

## <a name="dfx_text"></a>DFX_Text
Übertragungen `CString` Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) Objekt und Spalten eines Datensatzes in der Datenquelle.  
  
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
 Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, um den Kontext für jeden Aufruf der Funktion zu definieren.  
  
 `szName`  
 Der Name einer Datenspalte.  
  
 *value*  
 Der Wert in den angegebenen Datenmember gespeichert – der Wert, der übertragen werden. Für eine Übertragung von Recordset zur Datenquelle, den Wert des Typs [CString](../../atl-mfc-shared/reference/cstringt-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung von der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.  
  
 `nPreAllocSize`  
 Das Framework reserviert diese Menge an Arbeitsspeicher. Wenn Ihre Daten größer ist, wird das Framework belegt mehr Speicherplatz nach Bedarf. Legen Sie diese Größe für eine bessere Leistung auf einen Wert, der groß genug ist, um neuzuordnungen zu verhindern.  
  
 `dwBindOptions`  
 Eine Option, mit dem Sie das Nutzen von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordsetfelder, die geändert wurden. Die Standardeinstellung `AFX_DAO_ENABLE_FIELD_CACHE`, doppelte Pufferung verwendet. Der andere Wert ist `AFX_DAO_DISABLE_FIELD_CACHE`. Wenn Sie diesen Wert angeben, wird MFC keine Prüfung auf dieses Feld. Rufen Sie [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst.  
  
> [!NOTE]
>  Sie können steuern, ob Daten doppelgeklickt standardmäßig gepuffert werden werden, indem Sie festlegen [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Hinweise  
 Daten zwischen dem Typ zugeordnet ist **DAO_CHAR** über DAO (oder, wenn das Symbol **_UNICODE** definiert ist, **DAO_WCHAR aus**), und geben [CString](../../atl-mfc-shared/reference/cstringt-class.md) im Recordset.  n
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe `DFX_Text`. Beachten Sie auch die beiden Aufrufe von [CDaoFieldExchange:: SetFieldType](cdaofieldexchange-class.md#setfieldtype). Sie müssen den ersten Aufruf von schreiben `SetFieldType` und seine **DFX** aufrufen. Der zweite Aufruf und die zugehörigen **DFX** Aufrufe werden normalerweise durch den Code-Assistenten, die die Klasse generiert geschrieben.  
  
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


