---
title: Klasse CDaoTableDef | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], DAO
- tabledefs [C++]
- CDaoTableDef class
- database tables [C++], attached table definition
- database tables [C++], base table definition
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8bfd0ef3c63c243cabb0a4f841ba278fbeed4ae8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledef-class"></a>CDaoTableDef-Klasse
Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Erstellt eine **CDaoTableDef** Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::](#append)|Fügt eine neue Tabelle in der Datenbank.|  
|[CDaoTableDef::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn die Tabelle aktualisiert werden kann (Sie können die Definition von Feldern oder Eigenschaften für die Tabelle ändern).|  
|[CDaoTableDef::Close](#close)|Schließt eine Tabledef öffnen.|  
|[CDaoTableDef::Create](#create)|Erstellt eine Tabelle, die in die Datenbank hinzugefügt werden können [Append](#append).|  
|[CDaoTableDef::CreateField](#createfield)|Wird aufgerufen, um ein Feld für eine Tabelle erstellen.|  
|[CDaoTableDef::CreateIndex](#createindex)|Wird aufgerufen, um einen Index für eine Tabelle erstellen.|  
|[CDaoTableDef::DeleteField](#deletefield)|Wird aufgerufen, um ein Feld aus einer Tabelle zu löschen.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|Wird aufgerufen, um einen Index aus einer Tabelle löschen.|  
|[CDaoTableDef::GetAttributes](#getattributes)|Gibt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.|  
|[CDaoTableDef::GetConnect](#getconnect)|Gibt einen Wert, der Informationen über die Quelle einer Tabelle bereitstellt.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit der zugrunde liegenden Basistabelle ein `CDaoTableDef` Objekt erstellt wurde.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Gibt Datum und Uhrzeit der letzten Änderung des Entwurfs der Basistabelle.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in der Tabelle darstellt.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurückgegeben in der Tabelle.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|Gibt die Anzahl der Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Gibt bestimmte Arten von Informationen über die Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetName](#getname)|Der benutzerdefinierte Name der Tabelle zurückgegeben.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in der Tabelle zurück.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Gibt einen Wert, der den Namen der angefügten Tabelle in der Quelldatenbank angibt.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Gibt einen Wert, der die Daten in einem Feld überprüft, wie es geändert oder einer Tabelle hinzugefügt.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Gibt einen Wert, der den Text der Nachricht, die der Anwendung angezeigt angibt, wenn der Wert eines Field-Objekts nicht die angegebene Gültigkeitsprüfungsregel erfüllt.|  
|[CDaoTableDef::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn die Tabelle öffnen.|  
|[CDaoTableDef::Open](#open)|Öffnet eine vorhandene Tabledef in der Datenbank gespeichert, einer TableDef Auflistung.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|Aktualisiert die Verbindungsinformationen für eine verknüpfte Tabelle an.|  
|[CDaoTableDef::SetAttributes](#setattributes)|Legt einen Wert ein oder mehrere Merkmale der an eine `CDaoTableDef` Objekt.|  
|[CDaoTableDef::SetConnect](#setconnect)|Legt einen Wert, der Informationen über die Quelle einer Tabelle bereitstellt.|  
|[CDaoTableDef::SetName](#setname)|Legt den Namen der Tabelle.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Legt einen Wert, der den Namen einer angefügten Tabelle in der Quelldatenbank angibt.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Legt einen Wert, der die Daten in einem Feld überprüft, wie es geändert oder einer Tabelle hinzugefügt.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Legt einen Wert, der den Text der Nachricht, die der Anwendung angezeigt angibt, wenn der Wert eines Field-Objekts nicht die angegebene Gültigkeitsprüfungsregel erfüllt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Ein Zeiger auf die zugrunde liegenden Objekt Tabledef DAO-Schnittstelle.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Die Quelldatenbank für diese Tabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Jedes DAO-Datenbankobjekt verwaltet eine Sammlung namens TableDefs, die alle gespeicherten DAO Tabledef-Objekte enthält.  
  
 Sie ändern eine Tabelle mit einem `CDaoTableDef` Objekt. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Untersuchen Sie die Feld- und Index einer lokalen, angefügte oder externen Tabelle in einer Datenbank.  
  
-   Rufen Sie die `SetConnect` und `SetSourceTableName` Memberfunktionen für verbundene Tabellen und der `RefreshLink` Member-Funktion zum Aktualisieren von Verbindungen mit Tabellen zugeordnet.  
  
-   Rufen Sie die `CanUpdate` Member-Funktion, um festzustellen, ob Sie die Definitionen der Felder in der Tabelle bearbeiten können.  
  
-   Abrufen oder Festlegen der Validierung Startbedingungen mit der `GetValidationRule` und `SetValidationRule`, und die `GetValidationText` und `SetValidationText` Memberfunktionen.  
  
-   Verwenden der **öffnen** Member-Funktion zum Erstellen einer Tabelle, Dynaset oder Snapshot-Typ `CDaoRecordset` Objekt.  
  
    > [!NOTE]
    >  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können immer noch Zugriff auf ODBC-Datenquellen mit DAO-Klassen. die DAO-Klassen bieten im Allgemeinen überlegene Funktionen, da sie für das Microsoft Jet-Datenbankmodul spezifisch sind.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Tabledef-Objekte zum Arbeiten mit einer vorhandenen Tabelle oder zum Erstellen einer neuen Tabelle verwendet.  
  
1.  In allen Fällen erstellen Sie zuerst eine `CDaoTableDef` -Objekt, indem einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, zu dem die Tabelle gehört.  
  
2.  Führen Sie die folgenden, je nachdem, was Sie:  
  
    -   Um ein vorhandenes gespeichertes Tabelle zu verwenden, rufen Sie des Tabledef-Objekts [öffnen](#open) Member-Funktion, die den Namen der gespeicherten Tabelle angeben.  
  
    -   Um eine neue Tabelle zu erstellen, rufen Sie des Tabledef-Objekts [erstellen](#create) Member-Funktion, die den Namen der Tabelle angeben. Rufen Sie [CreateField](#createfield) und [CreateIndex](#createindex) Felder und Indizes der Tabelle hinzufügen.  
  
    -   Rufen Sie [Append](#append) zum Speichern der Tabelle, indem Sie an der Datenbank TableDefs-Auflistung angefügt. **Erstellen** versetzt Tabledef in den geöffneten Zustand, daher nach dem Aufruf von **erstellen** rufen Sie **öffnen**.  
  
        > [!TIP]
        >  Die einfachste Möglichkeit zum Erstellen von gespeicherter Tabellen wird Sie erstellt und in der Datenbank mithilfe von Microsoft Access zu speichern. Sie können dann öffnen und in der MFC-Code verwenden.  
  
 Um Tabledef-Objekts verwenden Sie geöffnet oder erstellt haben, und öffnen Sie ein `CDaoRecordset` -Objekt, wobei der Name des Tabledef mit einem **übergeben** Wert in der `nOpenType` Parameter.  
  
 Ein Tabledef-Objekt verwendet wird, zum Erstellen einer `CDaoRecordset` Objekt, die Sie in der Regel erstellen oder öffnen eine Tabledef wie oben beschrieben, und erstellen Sie dann ein Recordset-Objekt, einen Zeiger auf das Tabledef-Objekt übergeben, wenn Sie aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Im geöffneten Zustand muss Tabledef, die Sie übergeben werden. Weitere Informationen finden Sie unter Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Aufrufen, wenn Sie fertig sind, mit einem Tabledef-Objekt, dessen [schließen](../../mfc/reference/cdaorecordset-class.md#close) Member-Funktion; anschließend zerstören Tabledef-Objekts.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::  
 Rufen Sie diese Memberfunktion aufrufen, nachdem Sie [erstellen](#create) zum Erstellen eines neuen Tabledef-Objekts, um die Tabledef in der Datenbank zu speichern.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion fügt das Objekt an der Datenbank TableDefs-Auflistung. Sie können Tabledef als temporäres Objekt verwenden, bei der Definition von nicht angefügt, aber Sie speichern und verwenden möchten, rufen Sie **Append**.  
  
> [!NOTE]
>  Wenn Sie versuchen, eine unbenannte Tabledef (mit null oder eine leere Zeichenfolge) angefügt werden soll, wird von MFC eine Ausnahme auslöst.  
  
 Weitere Informationen finden Sie im Thema "Append-Methode" in der DAO-Hilfe.  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Definition der zugrunde liegenden Tabelle eine `CDaoTableDef` Objekt geändert werden kann.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Struktur der Tabelle (Schema) geändert werden kann (hinzufügen oder Löschen von Feldern und Indizes), andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung eine neu erstellte Tabelle zugrunde liegt ein `CDaoTableDef` Objekt aktualisiert werden kann, und einer angefügten Tabelle zugrunde liegenden ein `CDaoTableDef` Objekt kann nicht aktualisiert werden. Ein `CDaoTableDef` Objekt möglicherweise aktualisiert werden kann, auch wenn das resultierende Recordset nicht aktualisierbar ist.  
  
 Verwandte Informationen finden Sie unter "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 Erstellt eine **CDaoTableDef** Objekt.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Ein Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die [erstellen](#create) oder [öffnen](#open) Member-Funktion. Wenn Sie mit dem Objekt haben, müssen Sie Aufrufen seiner [schließen](#close) Member-Funktion und Zerstören der `CDaoTableDef` Objekt.  
  
##  <a name="close"></a>CDaoTableDef::Close  
 Rufen Sie diese Memberfunktion zum Schließen und das Tabledef-Objekt frei.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel nach dem Aufruf von **schließen**, wenn es mit belegt wurde, löschen Sie das Tabledef-Objekt **neue**.  
  
 Rufen Sie [öffnen](#open) erneut nach dem Aufruf von **schließen**. Dadurch können Sie das Tabledef-Objekt wiederverwenden.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" in der DAO-Hilfe.  
  
##  <a name="create"></a>CDaoTableDef::Create  
 Rufen Sie diese Memberfunktion zum Erstellen einer neuen gespeicherten Tabelle.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der Tabelle enthält.  
  
 `lAttributes`  
 Ein Wert für Merkmale der Tabelle durch das Tabledef-Objekt dargestellt wird. Der bitweise OR-können Sie eine der folgenden Konstanten kombinieren:  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die exklusive Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine verborgene Tabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
  
 *lpszSrcTable*  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Quelltabelle. Standardmäßig wird dieser Wert als initialisiert **NULL**.  
  
 `lpszConnect`  
 Ein Zeiger auf eine Zeichenfolge mit Standard-Verbindungszeichenfolge. Standardmäßig wird dieser Wert als initialisiert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Sobald Sie die Tabledef benannt haben, rufen Sie anschließend [Append](#append) Tabledef in der TableDefs-Auflistung der Datenbank zu speichern. Nach dem Aufruf von **Append**Tabledef ist im geöffneten Zustand und können Sie sie zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.  
  
 Verwandte Informationen finden Sie im Thema "CreateTableDef Method" in der DAO-Hilfe.  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 Rufen Sie diese Memberfunktion zum Hinzufügen eines Felds in der Tabelle.  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen dieses Felds angeben.  
  
 `nType`  
 Ein Wert, der den Datentyp des Felds angibt. Die Einstellung kann einen der folgenden Werte sein:  
  
|Typ|Größe (Byte)|Beschreibung|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 Byte|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|8|Währung ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|frei verschieben|  
|**dbDouble**|8|double|  
|**dbDate**|8|Datum/Uhrzeit ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 – 255|Text ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Long Binary (OLE-Objekt) [CLongBinary](../../mfc/reference/clongbinary-class.md) oder [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**Wert dbMemo**|0|Memo ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 Ein Wert, der angibt, die maximale Größe in Bytes, der ein Feld mit Text oder feste Größe für ein Feld, Text oder numerische Werte enthält. Die `lSize` Parameter wird ignoriert, für alle Textfelder.  
  
 `lAttributes`  
 Ein Wert ab, der Merkmale des Felds und, kann mithilfe von eine bitweise OR-Operation kombiniert werden.  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbFixedField**|Die Feldgröße ist (Standard für numerische Felder) fest.|  
|**dbVariableField**|Die Feldgröße ist Variable (nur Textfelder).|  
|**dbAutoIncrField festgelegt**|Der Feldwert für neue Datensätze wird automatisch auf eine eindeutige lange ganze Zahl erhöht, die nicht geändert werden kann. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.|  
|**dbUpdatableField**|Der Wert des Felds kann geändert werden.|  
|**dbDescending**|Das Feld wird in absteigender sortiert (Z – A oder 100 – 0) Reihenfolge (gilt nur für ein Field-Objekt in einer felderauflistung eines Objekts Index). Wenn Sie diese Konstante auslassen, wird das Feld sortiert in aufsteigender (A – Z oder 0-100) Reihenfolge (Standard).|  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Ein **DAOField** (OLE)-Objekt erstellt und an die Fields-Auflistung des angefügt ist die **DAOTableDef** (Objekt). Neben seiner Verwendung zum Untersuchen von Objekteigenschaften, können Sie auch `CDaoFieldInfo` Eingabeparameter für das Erstellen neuer Felder in einer Tabledef erstellt. Die erste Version des `CreateField` ist einfacher zu verwenden, aber wenn Sie eine genauere Kontrolle wünschen, können die zweite Version der `CreateField`, nimmt ein `CDaoFieldInfo` Parameter.  
  
 Wenn Sie die Version von `CreateField` , akzeptiert eine `CDaoFieldInfo` -Parameter verwenden, müssen Sie sorgfältig Festlegen aller folgenden Elemente von der `CDaoFieldInfo` Struktur:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 Die restlichen Mitglieder des `CDaoFieldInfo` sollte festgelegt werden, um **0**, **FALSE**, oder eine leere Zeichenfolge, entsprechend der Einstellung für das Element oder ein `CDaoException` auftreten.  
  
 Verwandte Informationen finden Sie im Thema "CreateField Method" in der DAO-Hilfe.  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 Rufen Sie diese Funktion, um einen Index zu einer Tabelle hinzuzufügen.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>Parameter  
 `indexinfo`  
 Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Indizes geben die Reihenfolge der Datensätze, die auf das Sie über die Datenbanktabellen und davon, ob doppelte Datensätze akzeptiert werden. Indizes bieten auch effizienten Zugriff auf Daten.  
  
 Sie müssen keine Indizes für Tabellen erstellen, aber in großen Tabellen ohne Index, den Zugriff auf einen bestimmten Datensatz oder das Erstellen einer Datensatzgruppe kann sehr lange dauern. Andererseits, erstellen zu viele Indizes verlangsamt, Update und delete-Operationen wie alle Indizes automatisch aktualisiert werden angefügt. Berücksichtigen Sie folgende Faktoren, wie Sie, welche Indizes entscheiden zu erstellen.  
  
 Die folgenden Mitglieder der `CDaoIndexInfo` Struktur muss festgelegt werden:  
  
- **M_strName** muss ein Name angegeben werden.  
  
- `m_pFieldInfos`Muss einen Verweis auf ein Array von `CDaoIndexFieldInfo` Strukturen.  
  
- `m_nFields`Geben Sie die Anzahl der Felder müssen im Array der `CDaoFieldInfo` Strukturen.  
  
 Die verbleibenden Elemente werden ignoriert, wenn auf den **FALSE**. Darüber hinaus die **M_lDistinctCount** Element wird ignoriert, während der Erstellung des Indexes.  
  
##  <a name="deletefield"></a>CDaoTableDef::DeleteField  
 Rufen Sie diese Memberfunktion zum Entfernen eines Felds, und stellen es nicht zugegriffen werden kann.  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen eines vorhandenen Felds ist.  
  
 `nIndex`  
 Der Index des Felds in der Tabelle nullbasierte Fields-Auflistung, für die Suche nach Index.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion auf ein neues Objekt, das nicht an die Datenbank angefügt wurde oder wenn [CanUpdate](#canupdate) gibt einen Wert ungleich NULL zurück.  
  
 Verwandte Informationen finden Sie im Thema "Delete-Methode" in der DAO-Hilfe.  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 Rufen Sie diese Memberfunktion zum Löschen eines Indexes in einer zugrunde liegenden Tabelle.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen eines vorhandenen Indexes ist.  
  
 `nIndex`  
 Der Arrayindex des Indexobjekts in der Datenbank nullbasierte TableDefs-Auflistung, für die Suche nach Index.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion auf ein neues Objekt, das noch nicht an die Datenbank angefügt wurde oder wenn [CanUpdate](#canupdate) gibt einen Wert ungleich NULL zurück.  
  
 Verwandte Informationen finden Sie im Thema "Delete-Methode" in der DAO-Hilfe.  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 Für eine `CDaoTableDef` -Objekt, der Rückgabewert gibt die Eigenschaften des durch dargestellten Tabelle die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die exklusive Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine verborgene Tabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbAttachedTable**|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Paradox-Datenbank ist.|  
|**dbAttachedODBC**|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server ist.|  
  
 Eine Systemtabelle handelt es sich um eine Tabelle erstellt, die vom Microsoft Jet-Datenbankmodul auf interne Informationen enthalten.  
  
 Eine ausgeblendete Tabelle ist eine Tabelle, die von der Microsoft Jet-Datenbankmodul für die temporäre Verwendung erstellt.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge für eine Datenquelle.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Pfad und den Datenbank-Typ für die Tabelle enthält.  
  
### <a name="remarks"></a>Hinweise  
 Für eine `CDaoTableDef` -Objekt, das eine angefügte Tabelle, stellt die `CString` -Objekt besteht aus einem oder zwei Teilen (einem Datenbank-Typspezifizierer und einen Pfad zu der Datenbank).  
  
 Der Pfad, wie in der folgenden Tabelle dargestellt ist der vollständige Pfad des Verzeichnisses, die Datenbankdateien enthalten und muss der Bezeichner vorangestellt werden "DATABASE =". In einigen Fällen (wie Microsoft Excel und Microsoft Jet-Datenbanken) ein bestimmten Dateinamen im Pfadargument Datenbank enthalten ist.  
  
 Die Tabelle in [CDaoTableDef::SetConnect](#setconnect) zeigt mögliche Datenbanktypen und die entsprechenden Datenbankbezeichner und Pfade:  
  
 Für Microsoft Jet-Datenbank-Basistabellen ist der Bezeichner ist eine leere Zeichenfolge ("").  
  
 Wenn ein Kennwort ist erforderlich, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und wenn die Verbindung geschlossen und erneut geöffnet wird. Wenn eine angefügte Tabelle hat die **DbAttachSavePWD** -Attribut, die Anmeldung aufgefordert wird beim erneuten die Tabelle öffnen nicht angezeigt.  
  
 Verwandte Informationen finden Sie im Thema "Connect-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 Rufen Sie diese Funktion, um zu bestimmen, das Datum und die Uhrzeit der zugrunde liegenden Tabelle der `CDaoTableDef` Objekt erstellt wurde.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der Datum und Uhrzeit der Erstellung der zugrunde liegenden Tabelle mit den `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer Umgebung mit mehreren Benutzern sollten Benutzer diese Einstellungen direkt vom Dateiserver zur Vermeidung von Diskrepanzen abrufen; Das heißt, alle Clients "standard" Zeitquelle verwenden sollte – vielleicht von einem Server.  
  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 Rufen Sie diese Funktion, um zu bestimmen, das Datum und die Uhrzeit der zugrunde liegenden Tabelle der **CDaoTableDef** Objekt zuletzt aktualisiert wurde.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der das Datum und die Uhrzeit der zugrunde liegenden Tabelle enthält die **CDaoTableDef** Objekt zuletzt aktualisiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer Umgebung mit mehreren Benutzern sollten Benutzer diese Einstellungen direkt vom Dateiserver zur Vermeidung von Diskrepanzen abrufen; Das heißt, alle Clients "standard" Zeitquelle verwenden sollte – vielleicht von einem Server.  
  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Felder in der Tabelle definiert.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder in der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert 0 ist, müssen Sie keine Objekte vorhanden sind, in der Auflistung.  
  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen zu einem Feld in der Tabledef definierten erhalten.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Field-Objekts in der Tabelle nullbasierte Fields-Auflistung, für die Suche nach Index.  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ, Größe und der Attribute. Verwenden Sie diese Option für die optimale Leistung zu erzielen.  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Ordnungszahl Position ist erforderlich, ermöglichen Null Länge Reihenfolge sortieren Foreign Namen Quellfeld Quelltabelle  
  
- `AFX_DAO_ALL_INFO`Informationen über primäre und sekundäre plus: Validierungsregel Validation Text, Standardwert  
  
 `lpszName`  
 Ein Zeiger auf den Namen des Field-Objekts, für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 64 Zeichen, die das Feld eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Indizes für eine Tabelle zu erhalten.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Indizes für die Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert 0 ist, müssen Sie keine Indizes vorhanden sind, in der Auflistung.  
  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen zu einem in der Tabledef definierten Index zu erhalten.  
  
```  
void GetIndexInfo(
    int nIndex,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetIndexInfo(
    LPCTSTR lpszName,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der numerische Index des Index-Objekts in der Tabelle nullbasierten Indizes Auflistung, für die Suche anhand seiner Position in der Auflistung.  
  
 `indexinfo`  
 Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über den Index abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`Name, Feldinformationen, Felder. Verwenden Sie diese Option für die optimale Leistung zu erzielen.  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: primäre, eindeutiger, gruppierter, ignorieren NULL-Werte erforderlich, Fremd  
  
- `AFX_DAO_ALL_INFO`Informationen über primäre und sekundäre plus: Distinct Count  
  
 `lpszName`  
 Ein Zeiger auf den Namen des Index-Objekts, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie einen Index nach seiner Position in der Auflistung suchen. Die andere Version können Sie einen Index nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 Rufen Sie diese Memberfunktion um den benutzerdefinierten Namen der zugrunde liegenden Tabelle zu erhalten.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein benutzerdefinierter Name für eine Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Name mit einem Buchstaben beginnt und kann maximal 64 Zeichen enthalten. Es kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze in sind ein `CDaoTableDef` Objekt.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Datensätze, die in einem Tabledef-Objekt zugegriffen.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `GetRecordCount` für einen Tabellentyp `CDaoTableDef` -Objekt gibt die ungefähre Anzahl der Datensätze in der Tabelle und wird sofort beeinflusst, wie die Datensätze hinzugefügt und gelöscht werden. Rollback Transaktionen werden als Teil der Anzahl der Datensätze angezeigt, bis zum Aufruf von [CDaoWorkspace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Ein `CDaoTableDef` -Objekt ohne Datensätze Datensatzanzahl-Eigenschaft die Einstellung 0 hat. Beim Arbeiten mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` gibt immer-1 zurück.  
  
 Verwandte Informationen finden Sie im Thema "RecordCount Property" in der DAO-Hilfe.  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens einer angefügten Tabelle in einer Quelldatenbank.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das den Quellnamen einer angefügten Tabelle oder eine leere Zeichenfolge gibt an, wenn eine native Datentabelle.  
  
### <a name="remarks"></a>Hinweise  
 Eine verknüpfte Tabelle ist eine Tabelle in einer anderen Datenbank, die mit Microsoft Jet-Datenbank verknüpft. Daten verbundene Tabellen verbleiben in der externen Datenbank, wo es von einer anderen Anwendung bearbeitet werden.  
  
 Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 Rufen Sie diese Memberfunktion zum Abrufen der Validierungsregel für eine Tabledef.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **CString** -Objekt, das die Daten in einem Feld überprüft, wie es geändert oder einer Tabelle hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Validierungsregeln sind Update-Vorgänge verwendet. Enthält eine Tabledef eine Validierungsregel, müssen Aktualisierungen, Tabledef vorher festgelegten Kriterien übereinstimmen, bevor die Daten geändert werden. Entspricht die Änderung nicht die Kriterien, eine Ausnahme mit dem Wert des [GetValidationText](#getvalidationtext) ausgelöst. Für eine `CDaoTableDef` -Objekt, das `CString` für eine verknüpfte Tabelle und Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.  
  
 Weitere Informationen finden Sie unter dem Thema "ValidationRule-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 Rufen Sie diese Funktion zum Abrufen der Zeichenfolge an, wenn ein Benutzer Daten eingibt, die die Überprüfungsregel nicht übereinstimmen.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das gibt den Text angezeigt, wenn Daten eingegeben werden, die die Überprüfungsregel nicht übereinstimmen.  
  
### <a name="remarks"></a>Hinweise  
 Für eine `CDaoTableDef` -Objekt, das `CString` für eine verknüpfte Tabelle und Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.  
  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoTableDef` Objekt ist derzeit geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoTableDef` Objekt wird geöffnet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt für diese Tabelle.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO Tabledef-Objekt zugrunde liegenden der `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie auf die DAO-Schnittstelle direkt zugreifen müssen.  
  
##  <a name="open"></a>CDaoTableDef::Open  
 Diese Memberfunktion eine Tabledef öffnen in der Datenbank gespeicherte Aufruf einer TableDef Auflistung.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die einen Tabellennamen angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 Rufen Sie diese Memberfunktion, um die Verbindungsinformationen für eine verknüpfte Tabelle zu aktualisieren.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie ändern die Verbindungsinformationen für eine verknüpfte Tabelle durch Aufrufen von [SetConnect](#setconnect) des entsprechenden `CDaoTableDef` -Objekt, und klicken Sie dann mit der `RefreshLink` Member-Funktion zum Aktualisieren der Informationen. Beim Aufruf von `RefreshLink`, die verknüpfte Tabelle Eigenschaften nicht geändert werden.  
  
 Erzwingen, dass die geänderte Verbindung mit Informationen, um alle geöffneten wirksam wird, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte auf Grundlage dieser Tabledef müssen geschlossen werden.  
  
 Verwandte Informationen finden Sie im Thema "RefreshLink Method" in der DAO-Hilfe.  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 Legt einen Wert ein oder mehrere Merkmale der an eine `CDaoTableDef` Objekt.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>Parameter  
 `lAttributes`  
 Merkmale der Tabelle dargestellt werden, indem die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die exklusive Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine verborgene Tabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie mehrere Attribute festlegen, können Sie diese kombinieren, indem Sie die entsprechenden Konstanten mit dem bitweisen OR-Operator addieren. Festlegen von **DbAttachExclusive** bei einer nicht angefügten Tabelle erzeugt eine Ausnahme. Kombinieren die folgenden Werte auch erzeugen eine Ausnahme:  
  
- **DbAttachExclusive | dbAttachedODBC**  
  
- **DbAttachSavePWD | dbAttachedTable**  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 Für ein `CDaoTableDef` -Objekt, das eine angefügte Tabelle, das String-Objekt stellt besteht aus einem oder zwei Teilen (einem Datenbank-Typspezifizierer und einen Pfad zu der Datenbank).  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnect`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der zusätzliche Parameter zur Übergabe an ODBC oder installierbare ISAM-Treiber angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Pfad, wie in der folgenden Tabelle dargestellt ist der vollständige Pfad des Verzeichnisses, die Datenbankdateien enthalten und muss der Bezeichner vorangestellt werden "DATABASE =". In einigen Fällen (wie Microsoft Excel und Microsoft Jet-Datenbanken) ein bestimmten Dateinamen im Pfadargument Datenbank enthalten ist.  
  
> [!NOTE]
>  Nehmen Sie Leerzeichen, um das Gleichheitszeichen nicht in Pfadangaben im Format "DATABASE = Laufwerk:\\\path". Dies führt zu einer Ausnahme und die fehlerhafte Verbindung.  
  
 Die folgende Tabelle zeigt mögliche Datenbanktypen und die entsprechenden Datenbankbezeichner und Pfade:  
  
|Datenbanktyp|Bezeichner|Pfad|  
|-------------------|---------------|----------|  
|Datenbank mit dem Jet-Datenbankmodul|"[ `database`];"|" `drive`:\\\ *path*\\\ *filename*. MDB"|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *path*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *path*"|  
|dBASE 5|"dBASE 5.0;"|" `drive`:\\\ *path*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *path*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *path*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *path*"|  
|Excel 3.0|"Excel 3.0;"|" `drive`:\\\ *path*\\\ *filename*. XLS"|  
|Excel 4.0|"Excel 4.0".|" `drive`:\\\ *path*\\\ *filename*. XLS"|  
|Excel 5.0 oder Excel 95|"Excel 5.0";|" `drive`:\\\ *path*\\\ *filename*. XLS"|  
|Excel 97|"Excel 8.0;"|" `drive`:\\\ *path*\ *filename*. XLS"|  
|HTML-Import|"HTML-Import";|" `drive`:\\\ *path*\ *filename*"|  
|Der HTML-Export|"HTML-Export";|" `drive`:\\\ *path*"|  
|Text|"Text".|"Laufwerk:\\\path"|  
|ODBC|"ODBC; Datenbank = `database`; UID= *user*; PWD = *Kennwort*; DSN = *%DataSourceName;* LOGINTIMEOUT = *Sekunden;*" (Dies möglicherweise nicht für alle Server eine vollständige Verbindungszeichenfolge; es ist nur ein Beispiel. Es ist sehr wichtig, keine Leerzeichen zwischen den Parametern enthalten.)|Keine|  
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *Folderpath*;<br /><br /> [TABLETYPE = {0 | 1};]<br /><br /> [Profil = *Profil*;]<br /><br /> [PWD = *Kennwort*;]<br /><br /> [DATABASE = `database`;] "|*"drive*:\\\ *path*\\\ *filename*. MDB"|  
  
> [!NOTE]
>  Btrieve wird zum Zeitpunkt der Erstellung DAO 3.5 nicht mehr unterstützt.  
  
 Verwenden Sie einen doppelten umgekehrten Schrägstrich (\\\\) in der Verbindungszeichenfolge. Wenn Sie die Eigenschaften einer bestehenden Verbindung mit geändert haben `SetConnect`, müssen Sie anschließend aufrufen [RefreshLink](#refreshlink). Wenn Sie die Verbindungseigenschaften, die mithilfe von initialisieren `SetConnect`, Sie benötigen keine Aufruf `RefreshLink`, jedoch sollten Sie dazu entschließen, zuerst die Tabledef angefügt.  
  
 Wenn ein Kennwort ist erforderlich, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und wenn die Verbindung geschlossen und erneut geöffnet wird.  
  
 Sie können festlegen, dass die Verbindungszeichenfolge für eine `CDaoTableDef` Objekt, indem ein Quellargument, um die **erstellen** Member-Funktion. Sie können die Einstellung bestimmt den Typ, Pfad, Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank überprüfen. Weitere Informationen finden Sie in der Dokumentation des Treibers.  
  
 Verwandte Informationen finden Sie im Thema "Connect-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 Rufen Sie diese Memberfunktion einen benutzerdefinierten Namen für eine Tabelle festlegen.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Namen für eine Tabelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss mit einem Buchstaben beginnen und kann maximal 64 Zeichen enthalten. Es kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 Rufen Sie diese Memberfunktion um den Namen einer angefügten Tabelle oder der Name der Basistabelle angeben, auf denen die `CDaoTableDef` -Objekt basiert, wie sie in der ursprünglichen Quelle der Daten vorhanden sind.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSrcTableName*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Tabellennamen in der externen Datenbank angibt. Für eine Basistabelle, die Einstellung ist eine leere Zeichenfolge ("").  
  
### <a name="remarks"></a>Hinweise  
 Anschließend müssen Sie aufrufen [RefreshLink](#refreshlink). Die Einstellung dieser Eigenschaft ist für eine Basistabelle und Lese-/Schreibzugriff für eine verknüpfte Tabelle oder ein Objekt, das nicht an eine Auflistung angefügt.  
  
 Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 Rufen Sie diese Memberfunktion, um eine Validierungsregel für eine Tabledef festzulegen.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszValidationRule*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Vorgang überprüft werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Validierungsregeln sind Update-Vorgänge verwendet. Enthält eine Tabledef eine Validierungsregel, müssen Aktualisierungen, Tabledef vorher festgelegten Kriterien übereinstimmen, bevor die Daten geändert werden. Wenn die Änderung nicht die Kriterien, mit dem Text der Ausnahme übereinstimmt [GetValidationText](#getvalidationtext) wird angezeigt.  
  
 Überprüfung wird nur für Datenbanken unterstützt, die das Microsoft Jet-Datenbankmodul verwenden. Der Ausdruck kann nicht auf benutzerdefinierte Funktionen, Aggregatfunktionen für Domänen, SQL-Aggregatfunktionen oder Abfragen verweisen. Eine Validierungsregel für einen `CDaoTableDef` Objekt kann auf mehrere Felder in diesem Objekt verweisen.  
  
 Z. B. für Felder mit dem Namen `hire_date` und `termination_date`, eine Validierungsregel kann sein:  
  
 [!code-cpp[NVC_MFCDatabase&#34;](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 Weitere Informationen finden Sie unter dem Thema "ValidationRule-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 Rufen Sie diese Memberfunktion zum Festlegen der Text der Ausnahme einer Validierungsregel für einen `CDaoTableDef` -Objekt mit einer zugrunde liegenden Basistabelle, die von der Microsoft Jet-Datenbankmodul unterstützt werden.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszValidationText*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der angibt, den Text angezeigt, wenn Daten eingegeben ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Überprüfung Text einer angefügten Tabelle kann nicht festgelegt werden.  
  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in der DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)

