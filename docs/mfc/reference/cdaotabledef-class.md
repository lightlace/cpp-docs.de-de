---
title: CDaoTableDef Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff62b77e6bdec6b796750d27357d12667eb16386
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378307"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef-Klasse
Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Erstellt eine **CDaoTableDef** Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::](#append)|Fügt eine neue Tabelle mit der Datenbank an.|  
|[CDaoTableDef::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn die Tabelle aktualisiert werden kann (Sie können die Definition von Feldern oder anhand der Tabelleneigenschaften ändern).|  
|[CDaoTableDef::Close](#close)|Schließt eine offene Tabledef an.|  
|[CDaoTableDef::Create](#create)|Erstellt eine Tabelle, die die Datenbank mit hinzugefügt werden kann [Append](#append).|  
|[CDaoTableDef::CreateField](#createfield)|Wird aufgerufen, um ein Feld für eine Tabelle zu erstellen.|  
|[CDaoTableDef::CreateIndex](#createindex)|Wird aufgerufen, um einen Index für eine Tabelle zu erstellen.|  
|[CDaoTableDef::DeleteField](#deletefield)|Wird aufgerufen, um ein Feld aus einer Tabelle zu löschen.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|Wird aufgerufen, um einen Index aus einer Tabelle zu löschen.|  
|[CDaoTableDef::GetAttributes](#getattributes)|Gibt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.|  
|[CDaoTableDef::GetConnect](#getconnect)|Gibt einen Wert, der Informationen über die Quelle einer Tabelle bereitstellt.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit des zugrunde liegenden Basistabelle eine `CDaoTableDef` Objekt erstellt wurde.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum und die Uhrzeit der letzten Änderung am Entwurf der Basistabelle.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in der Tabelle darstellt.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurück in der Tabelle.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|Gibt die Anzahl der Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Gibt bestimmte Arten von Informationen über die Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetName](#getname)|Der benutzerdefinierte Name der Tabelle zurückgegeben.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in der Tabelle zurück.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Gibt einen Wert, der den Namen des angefügten Tabelle in der Quelldatenbank angibt.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Gibt einen Wert, der die Daten in einem Feld überprüft werden, da sie einer Tabelle hinzugefügt, geändert oder zurück.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Gibt einen Wert, der den Text der Nachricht, in dem die Anwendung angezeigt angibt, wenn der Wert der Field-Objekt nicht über die angegebene Gültigkeitsprüfungsregel erfüllt.|  
|[CDaoTableDef::IsOpen](#isopen)|Gibt, die ungleich NULL, wenn die Tabelle öffnen.|  
|[CDaoTableDef::Open](#open)|In der Auflistung des TableDef werden öffnet eine vorhandene Tabledef in der Datenbank gespeichert.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|Aktualisiert die Verbindungsinformationen für eine verknüpfte Tabelle an.|  
|[CDaoTableDef::SetAttributes](#setattributes)|Legt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.|  
|[CDaoTableDef::SetConnect](#setconnect)|Legt einen Wert, der Informationen über die Quelle einer Tabelle bereitstellt.|  
|[CDaoTableDef::SetName](#setname)|Legt den Namen der Tabelle.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Legt einen Wert, der den Namen einer angefügten Tabelle in der Quelldatenbank angibt.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Einen Wert, der die Daten in einem Feld überprüft werden, da sie einer Tabelle hinzugefügt, geändert oder legt sie fest.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Legt einen Wert, der den Text der Nachricht, in dem die Anwendung angezeigt angibt, wenn der Wert der Field-Objekt nicht über die angegebene Gültigkeitsprüfungsregel erfüllt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Ein Zeiger auf die zugrunde liegenden Objekt Tabledef DAO-Schnittstelle.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Die Quelldatenbank für diese Tabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Jedes Datenbankobjekt DAO verwaltet eine Auflistung mit dem Namen TableDefs, die alle gespeicherte DAO Tabledef Objekte enthält.  
  
 Sie ändern eine Tabelle mit einer `CDaoTableDef` Objekt. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Untersuchen Sie die Feld- und Index einer beliebigen lokalen, angefügte oder externen Tabelle in einer Datenbank.  
  
-   Rufen Sie die `SetConnect` und `SetSourceTableName` Memberfunktionen für verbundene Tabellen, und verwenden Sie die `RefreshLink` Memberfunktion zum Aktualisieren von Verbindungen mit angefügten Tabellen.  
  
-   Rufen Sie die `CanUpdate` Member-Funktion, um festzustellen, ob Sie Felddefinitionen in der Tabelle bearbeiten können.  
  
-   Abrufen oder Festlegen der Validierung Bedingungen, die mit der `GetValidationRule` und `SetValidationRule`, und die `GetValidationText` und `SetValidationText` Memberfunktionen.  
  
-   Verwenden der **öffnen** Memberfunktion versucht, eine Tabelle, Dynaset oder-Diagramm nach der Momentaufnahme erstellen `CDaoRecordset` Objekt.  
  
    > [!NOTE]
    >  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; DAO-Klassen bieten im Allgemeinen überlegene Funktionen auf, da sie mit dem Microsoft Jet-Datenbankmodul spezifisch sind.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Tabledef Objekte zur Bearbeitung einer vorhandenen Tabelle oder zum Erstellen einer neuen Tabelle verwenden  
  
1.  In allen Fällen erstellen Sie zuerst eine `CDaoTableDef` -Objekt, indem ein Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt, zu dem die Tabelle gehört.  
  
2.  Führen Sie dann die folgenden Einträge, je nachdem, was soll:  
  
    -   Rufen Sie zum Verwenden einer vorhandenen Tabelle Speichern des Objekts Tabledef [öffnen](#open) Member-Funktion, die den Namen der gespeicherten Tabelle angeben.  
  
    -   Um eine neue Tabelle zu erstellen, rufen Sie des Tabledef Objekts [erstellen](#create) Memberfunktion, die den Namen der Tabelle angeben. Rufen Sie [CreateField](#createfield) und [CreateIndex](#createindex) zum Hinzufügen von Feldern und Indizes der Tabelle.  
  
    -   Rufen Sie [Append](#append) zum Speichern der Tabelle, indem er TableDefs-Auflistung für die Datenbank angefügt werden. **Erstellen** versetzt Tabledef in den geöffneten Zustand daher nach dem Aufruf **erstellen** rufen Sie nicht **öffnen**.  
  
        > [!TIP]
        >  Die einfachste Möglichkeit zum Erstellen von gespeicherten Tabellen wird Sie erstellt und in der Datenbank mit Microsoft Access zu speichern. Sie können dann öffnen und in der MFC-Code zu verwenden.  
  
 Um Tabledef-Objekts verwenden Sie geöffnet oder erstellt haben, erstellen und öffnen Sie eine `CDaoRecordset` Objekt, das Angeben des Namens des Tabledef mit einem **übergeben** Wert in der `nOpenType` Parameter.  
  
 Ein Tabledef-Objekt verwendet wird, zum Erstellen einer `CDaoRecordset` -Objekts können Sie in der Regel erstellen oder öffnen eine Tabledef wie oben beschrieben, und erstellen ein Recordset-Objekts, die Übergabe eines Zeigers für Ihr Objekt Tabledef beim Aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Tabledef, die Sie übergeben, muss sich im geöffneten Zustand. Weitere Informationen finden Sie in der Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Aufrufen, wenn Sie fertig sind, mithilfe eines Tabledef-Objekts, dessen [schließen](../../mfc/reference/cdaorecordset-class.md#close) Member-Funktion; zerstören Sie das Tabledef-Objekt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="append"></a>  CDaoTableDef::  
 Rufen Sie diese Memberfunktion auf, nach dem Aufruf [erstellen](#create) zum Erstellen eines neuen Tabledef-Objekts, um die Tabledef in der Datenbank zu speichern.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion fügt das Objekt, auf die Datenbank TableDefs-Auflistung. Sie können Tabledef als temporäres Objekt verwenden, bei der Definition von nicht angefügt, aber Sie speichern, und sie verwenden möchten, müssen Sie aufrufen **Append**.  
  
> [!NOTE]
>  Wenn Sie versuchen, eine unbenannte Tabledef (mit einem NULL- oder leere Zeichenfolge) angefügt werden soll, löst MFC eine Ausnahme aus.  
  
 Verwandte Informationen finden Sie im Thema "Append-Methode" DAO-Hilfe.  
  
##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Definition der zugrunde liegenden Tabelle eine `CDaoTableDef` Objekt geändert werden kann.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Tabellenstruktur (Schema) geändert werden kann (hinzufügen oder Löschen von Feldern und Indizes), andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig ein zugrunde liegendes neu erstellten Tabelle eine `CDaoTableDef` Objekt kann aktualisiert werden, und einer angefügten Tabelle zugrunde liegenden ein `CDaoTableDef` Objekt kann nicht aktualisiert werden. Ein `CDaoTableDef` Objekt kann aktualisiert werden kann, werden, auch wenn das resultierende Recordset nicht aktualisierbar ist.  
  
 Verwandte Informationen finden Sie im Thema "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef  
 Erstellt eine **CDaoTableDef** Objekt.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Ein Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die [erstellen](#create) oder [öffnen](#open) Memberfunktion. Wenn Sie mit dem Objekt abgeschlossen haben, müssen Sie Aufrufen seiner [schließen](#close) Member-Funktion und zu zerstören der `CDaoTableDef` Objekt.  
  
##  <a name="close"></a>  CDaoTableDef::Close  
 Rufen Sie diese Memberfunktion zum Schließen und das Objekt Tabledef freizugeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel nach dem Aufruf **schließen**, wenn er mit belegt wurde, löschen Sie das Tabledef-Objekt **neue**.  
  
 Sie können Aufrufen [öffnen](#open) erneut nach dem Aufruf **schließen**. Dadurch können Sie jedoch stattdessen das Tabledef wiederverwenden.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" DAO-Hilfe.  
  
##  <a name="create"></a>  CDaoTableDef::Create  
 Rufen Sie diese Memberfunktion zum Erstellen einer neuen gespeicherten Tabellenstatus.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Tabelle.  
  
 `lAttributes`  
 Ein Wert entspricht der Merkmale der Tabelle durch das Tabledef-Objekt dargestellt wird. Der bitweise OR-können Sie eine der folgenden Konstanten kombinieren:  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die ausschließliche Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die vom Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine ausgeblendete vom Microsoft Jet-Datenbankmodul bereitgestellt ist.|  
  
 *lpszSrcTable*  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Quelltabelle. Standardmäßig ist dieser Wert als initialisiert **NULL**.  
  
 `lpszConnect`  
 Ein Zeiger auf eine Zeichenfolge, enthält die Standard-Verbindungszeichenfolge. Standardmäßig ist dieser Wert als initialisiert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem Sie die Tabledef genannt haben, rufen Sie anschließend [Append](#append) Tabledef in der Datenbank TableDefs-Auflistung zu speichern. Nach dem Aufruf **Append**Tabledef befindet sich im geöffneten Zustand und können es zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.  
  
 Verwandte Informationen finden Sie im Thema "CreateTableDef Method" DAO-Hilfe.  
  
##  <a name="createfield"></a>  CDaoTableDef::CreateField  
 Rufen Sie diese Memberfunktion zum Hinzufügen eines Felds in die Tabelle ein.  
  
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
|**dbSingle**|4|float|  
|**dbDouble**|8|double|  
|**DBDate fest**|8|Datum/Uhrzeit ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Text ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Lange Binärdatei (OLE-Objekts), [CLongBinary](../../mfc/reference/clongbinary-class.md) oder [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**Wert dbMemo**|0|Memo ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 Ein Wert, der angibt, die maximale Größe in Bytes, der ein Feld, das Text enthält, oder die feste Größe von einem Feld, Text oder numerische Werte enthält. Die `lSize` Parameter wird ignoriert, für alle Textfelder.  
  
 `lAttributes`  
 Ein Wert, der Merkmale des Felds, und die entsprechenden kann mithilfe einer bitweisen OR kombiniert werden.  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbFixedField**|Die Feldgröße ist (Standardeinstellung für numerische Felder) korrigiert.|  
|**dbVariableField**|Die Feldgröße ist Variable (gilt nur für Textfelder).|  
|**dbAutoIncrField festgelegt**|Der Wert des Felds für neue Datensätze wird automatisch auf eine eindeutige lange ganze Zahl erhöht werden, die nicht geändert werden kann. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.|  
|**dbUpdatableField**|Der Wert des Felds kann geändert werden.|  
|**dbDescending**|Das Feld wird in absteigender sortiert (Z - A oder 0, 100) Reihenfolge (gilt nur für ein Field-Objekt in der Fields-Auflistung eines Objekts Index). Wenn Sie diese Konstante weglassen, wird das Feld sortiert in aufsteigender (A - Z oder 0 - 100) Reihenfolge (Standard).|  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Ein **DAOField** (OLE)-Objekt erstellt und angefügt werden, auf die Auflistung der Felder von der **DAOTableDef** (OLE)-Objekt. Neben dessen Verwendung zum Untersuchen von Objekteigenschaften, können Sie auch `CDaoFieldInfo` um einen Eingabeparameter für das Erstellen neuer Felder in einer Tabledef zu erstellen. Die erste Version des `CreateField` ist einfacher zu verwenden, aber wenn Sie eine genauere Steuerung des möchten, können Sie die zweite Version der `CreateField`, nimmt ein `CDaoFieldInfo` Parameter.  
  
 Bei Verwendung der Version des `CreateField` , akzeptiert eine `CDaoFieldInfo` Parameter müssen Sie sorgfältig Festlegen aller folgenden Elemente von der `CDaoFieldInfo` Struktur:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 Die verbleibenden Elemente der `CDaoFieldInfo` sollte festgelegt werden, um **0**, **"false"**, oder eine leere Zeichenfolge, entsprechend der Einstellung für das Element oder ein `CDaoException` auftreten.  
  
 Verwandte Informationen finden Sie im Thema "CreateField Method" DAO-Hilfe.  
  
##  <a name="createindex"></a>  CDaoTableDef::CreateIndex  
 Rufen Sie diese Funktion, um einen Index zu einer Tabelle hinzuzufügen.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>Parameter  
 `indexinfo`  
 Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Indizes geben die Reihenfolge der Datensätze, die auf das Sie über die Datenbanktabellen und davon, ob doppelte Datensätze akzeptiert werden. Indizes bieten auch effizienten Zugriff auf Daten.  
  
 Sie müssen keine Indizes für Tabellen zu erstellen, aber in großen Tabellen ohne Index, den Zugriff auf einen bestimmten Datensatz oder ein Recordset erstellen kann sehr lange dauern. Andererseits, erstellen zu viele Indizes verlangsamt, Update, Anfügen und Löschvorgänge, da alle Indizes automatisch aktualisiert werden. Berücksichtigen Sie folgende Faktoren, wie Sie, welche Indizes entscheiden zu erstellen.  
  
 Die folgenden Member der `CDaoIndexInfo` Struktur muss festgelegt werden:  
  
- **M_strName** ein Name muss angegeben werden.  
  
- `m_pFieldInfos` Zeigen Sie mit der muss auf ein Array von `CDaoIndexFieldInfo` Strukturen.  
  
- `m_nFields` Muss, geben Sie die Anzahl der Felder im Array der `CDaoFieldInfo` Strukturen.  
  
 Die verbleibenden Elemente wird ignoriert, wenn auf festgelegt **"false"**. Darüber hinaus die **M_lDistinctCount** Element wird ignoriert, während der Erstellung des Indexes.  
  
##  <a name="deletefield"></a>  CDaoTableDef::DeleteField  
 Rufen Sie diese Memberfunktion zum Entfernen von Feldern, und stellen es kann nicht zugegriffen werden.  
  
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
 Sie können diese Memberfunktion auf ein neues Objekt, das nicht an die Datenbank angefügt wurde oder wenn [CanUpdate](#canupdate) ungleich NULL zurückgegeben.  
  
 Verwandte Informationen finden Sie im Thema "Methode Delete", DAO-Hilfe.  
  
##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex  
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
 Sie können diese Memberfunktion auf ein neues Objekt, das noch nicht an die Datenbank angefügt wurde oder wenn [CanUpdate](#canupdate) ungleich NULL zurückgegeben.  
  
 Verwandte Informationen finden Sie im Thema "Methode Delete", DAO-Hilfe.  
  
##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes  
 Für eine `CDaoTableDef` -Objekt, der Rückgabewert gibt die Eigenschaften der Tabelle, dargestellt durch die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die ausschließliche Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die vom Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine ausgeblendete vom Microsoft Jet-Datenbankmodul bereitgestellt ist.|  
|**dbAttachedTable**|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Paradox-Datenbank ist.|  
|**dbAttachedODBC**|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server ist.|  
  
 Eine Systemtabelle handelt es sich um eine Tabelle erstellt, die vom Microsoft Jet-Datenbankmodul verschiedene interne Informationen enthalten.  
  
 Eine ausgeblendete Tabelle ist eine Tabelle, für die temporäre Verwendung erstellt, durch das Microsoft Jet-Datenbankmodul.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getconnect"></a>  CDaoTableDef::GetConnect  
 Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge für eine Datenquelle an.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Pfad und den Datenbank-Typ für die Tabelle enthält.  
  
### <a name="remarks"></a>Hinweise  
 Für eine `CDaoTableDef` -Objekt, das eine angefügte Tabelle stellt die `CString` Objekt besteht aus einem oder zwei Teilen (einem Datenbank-Typspezifizierer und einen Pfad zu der Datenbank).  
  
 Der Pfad, wie in der folgenden Tabelle gezeigt ist der vollständige Pfad des Verzeichnisses, das die Datenbankdateien enthalten und muss der Bezeichner vorangestellt werden "Datenbank =". In einigen Fällen (wie Microsoft Excel und Microsoft Jet-Datenbanken) ein bestimmter Dateinamen im Pfadargument Datenbank enthalten ist.  
  
 Die Tabelle in [CDaoTableDef::SetConnect](#setconnect) zeigt mögliche Datenbanktypen und ihre entsprechenden Datenbankbezeichner und Pfade:  
  
 Für Microsoft Jet-Datenbank der Basistabellen, die Spezifizierer ist eine leere Zeichenfolge ("").  
  
 Wenn ein Kennwort ist erforderlich, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und ein zweites Mal, wenn die Verbindung geschlossen und erneut geöffnet wird. Wenn es sich bei eine angefügte Tabelle hat die **DbAttachSavePWD** -Attribut, die anmeldeaufforderung nicht angezeigt, wenn die Tabelle erneut geöffnet wird.  
  
 Verwandte Informationen finden Sie im Thema "Verbinden der Eigenschaft" DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated  
 Mit dieser Funktion wird zum Ermitteln von Datum und Uhrzeit der zugrunde liegende Tabelle die `CDaoTableDef` Objekt erstellt wurde.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, enthält das Datum und die Uhrzeit der Erstellung der Tabelle zugrunde liegenden der `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. Benutzer sollten diese Einstellungen direkt vom Dateiserver zur Vermeidung von abweichungen abrufen, in einer mehrbenutzerumgebung; Das heißt, alle Clients eine "standard" Zeitquelle verwenden sollten – vielleicht von einem Server.  
  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated  
 Mit dieser Funktion wird zum Ermitteln von Datum und Uhrzeit der zugrunde liegende Tabelle die **CDaoTableDef** Objekt zuletzt aktualisiert wurde.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der das Datum und die Uhrzeit des zugrunde liegenden Tabelle enthält die **CDaoTableDef** Objekt zuletzt aktualisiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. Benutzer sollten diese Einstellungen direkt vom Dateiserver zur Vermeidung von abweichungen abrufen, in einer mehrbenutzerumgebung; Das heißt, alle Clients eine "standard" Zeitquelle verwenden sollten – vielleicht von einem Server.  
  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Feldern, die in der Tabelle definiert.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder in der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert 0 ist, müssen Sie keine Objekte vorhanden sind, in der Auflistung.  
  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getfieldinfo"></a>  CDaoTableDef::GetFieldInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einem Feld in der Tabledef definiert.  
  
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
 Der Index der Field-Objekt in der Tabelle nullbasierte Fields-Auflistung, für die Suche nach Index.  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Typ, Größe und der Attribute. Verwenden Sie diese Option für die höchste Geschwindigkeit.  
  
- `AFX_DAO_SECONDARY_INFO` Primäre Informationen plus: Ordnungszahl Position ist erforderlich, können 0 (null) Länge Reihenfolge sortieren ausländischen Name, Quellfeld Quelltabelle  
  
- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären plus: Validierungsregel, Text zu, Standardwert  
  
 `lpszName`  
 Ein Zeiger auf den Namen der Field-Objekt, für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 64 Zeichen, die das Feld eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Indizes für eine Tabelle zu erhalten.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Indizes für die Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert 0 ist, müssen Sie keine Indizes vorhanden sind, in der Auflistung.  
  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo  
 Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einem Index in der Tabledef definiert.  
  
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
 Optionen, die angeben, welche Informationen über den Index abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- `AFX_DAO_PRIMARY_INFO` Name, Feldinformationen, Felder. Verwenden Sie diese Option für die höchste Geschwindigkeit.  
  
- `AFX_DAO_SECONDARY_INFO` Primäre Informationen plus: primäre, UNIQUE-, Clustered, ignorieren NULL-Werte erforderlich, Fremdschlüssel  
  
- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären plus: Distinct Count  
  
 `lpszName`  
 Ein Zeiger auf den Namen des Index-Objekts, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie einen Index anhand seiner Position in der Auflistung gesucht. Die andere Version können Sie einen Index nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getname"></a>  CDaoTableDef::GetName  
 Rufen Sie diese Memberfunktion um den benutzerdefinierten Namen der zugrunde liegenden Tabelle zu erhalten.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein benutzerdefinierter Name für eine Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Name beginnt mit einem Buchstaben und darf maximal 64 Zeichen lang sein. Er kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount  
 Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze im sind ein `CDaoTableDef` Objekt.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Datensätze in einem Tabledef-Objekt zugegriffen.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `GetRecordCount` für einen Tabellentyp `CDaoTableDef` Objekt gibt die ungefähre Anzahl von Datensätzen in der Tabelle wieder und ist direkt betroffen, wenn Datensätze hinzugefügt oder gelöscht werden. Rollback Transaktionen werden als Teil der Anzahl der Datensätze, bis Sie rufen [CDaoWorkspace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Ein `CDaoTableDef` Objekt ohne Datensätze hat Datensatzanzahl-Eigenschaft die Einstellung 0. Beim Arbeiten mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` gibt immer-1 zurück.  
  
 Verwandte Informationen finden Sie im Thema "RecordCount-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName  
 Rufen Sie diese Memberfunktion um den Namen einer angefügten Tabelle in einer Quelldatenbank abzurufen.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das den Quellnamen einer angefügten Tabelle oder eine leere Zeichenfolge gibt an, wenn eine native Datentabelle.  
  
### <a name="remarks"></a>Hinweise  
 Eine angefügte Tabelle ist eine Tabelle in einer anderen Datenbank, die mit einer Microsoft Jet-Datenbank verknüpft. Daten für die verbundene Tabellen bleibt in der externen Datenbank, in dem sie von einer anderen Anwendung bearbeitet werden.  
  
 Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule  
 Rufen Sie diese Memberfunktion, um die Validierungsregel für eine Tabledef abzurufen.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **CString** -Objekt, das die Daten in einem Feld überprüft, da sie geändert oder einer Tabelle hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Validierungsregeln werden im Zusammenhang mit der Update-Vorgänge verwendet. Enthält eine Tabledef eine Validierungsregel, müssen Updates für diese Tabledef vordefinierte Kriterien entsprechen, bevor die Daten geändert werden. Die Änderung der Kriterien, eine Ausnahme mit dem Wert des stimmt nicht überein [GetValidationText](#getvalidationtext) ausgelöst wird. Für eine `CDaoTableDef` -Objekt, das `CString` für eine verknüpfte Tabelle und Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.  
  
 Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText  
 Mit dieser Funktion wird zum Abrufen der Zeichenfolge angezeigt, wenn ein Benutzer Daten eingibt, die die Validierungsregel nicht übereinstimmen.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das gibt den Text angezeigt, wenn der Benutzer Daten eingibt, die die Validierungsregel nicht übereinstimmen.  
  
### <a name="remarks"></a>Hinweise  
 Für eine `CDaoTableDef` -Objekt, das `CString` für eine verknüpfte Tabelle und Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.  
  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" DAO-Hilfe.  
  
##  <a name="isopen"></a>  CDaoTableDef::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoTableDef` Objekt ist derzeit geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDaoTableDef` Objekt ist, geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase  
 Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt für diese Tabelle.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO Tabledef-Objekt zugrunde liegenden der `CDaoTableDef` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie this-Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen müssen.  
  
##  <a name="open"></a>  CDaoTableDef::Open  
 Diese Memberfunktion zum Öffnen einer Tabledef zuvor in der Datenbank gespeicherten Aufruf der TableDefs Auflistung werden.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die einen Tabellennamen angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink  
 Rufen Sie diese Memberfunktion, um die Verbindungsinformationen für eine verknüpfte Tabelle zu aktualisieren.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie ändern die Verbindungsinformationen für eine verknüpfte Tabelle durch Aufrufen von [SetConnect](#setconnect) des entsprechenden `CDaoTableDef` -Objekt, und klicken Sie dann mit der `RefreshLink` Memberfunktion versucht, die Informationen zu aktualisieren. Beim Aufruf `RefreshLink`, die verknüpfte Tabelle Eigenschaften werden nicht geändert.  
  
 Erzwingen der geänderten Verbindung mit Informationen, um alle geöffneten wirksam wird, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte werden basierend auf diesem Tabledef müssen geschlossen werden.  
  
 Verwandte Informationen finden Sie im Thema "RefreshLink Method" DAO-Hilfe.  
  
##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes  
 Legt einen Wert an eine oder mehrere Merkmale einer `CDaoTableDef` Objekt.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>Parameter  
 `lAttributes`  
 Merkmale der Tabelle, dargestellt durch die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:  
  
|Konstante|Beschreibung|  
|--------------|-----------------|  
|**dbAttachExclusive**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle für die ausschließliche Verwendung geöffnet ist.|  
|**dbAttachSavePWD**|Für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|  
|**dbSystemObject**|Gibt an, dass die Tabelle eine Systemtabelle, die vom Microsoft Jet-Datenbankmodul bereitgestellt wird.|  
|**dbHiddenObject**|Gibt an, dass die Tabelle eine ausgeblendete vom Microsoft Jet-Datenbankmodul bereitgestellt ist.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie mehrere Attribute festlegen möchten, können Sie diese kombinieren, indem er die entsprechenden Konstanten, die mit dem bitweisen OR-Operator hat. Festlegen von **DbAttachExclusive** für eine Tabelle Laufzeitstruktur erzeugt eine Ausnahme. Kombinieren die folgenden Werte auch eine Ausnahme generieren:  
  
- **DbAttachExclusive &#124; DbAttachedODBC**  
  
- **DbAttachSavePWD &#124; DbAttachedTable**  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="setconnect"></a>  CDaoTableDef::SetConnect  
 Für eine `CDaoTableDef` Objekt, das eine angefügte Tabelle, die String-Objekt darstellt besteht aus einem oder zwei Teilen (einem Datenbank-Typspezifizierer und einen Pfad zu der Datenbank).  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnect`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der zusätzliche Parameter zur Übergabe an die ODBC oder ISAM-Treiber mit installierbar angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Pfad, wie in der folgenden Tabelle gezeigt ist der vollständige Pfad des Verzeichnisses, das die Datenbankdateien enthalten und muss der Bezeichner vorangestellt werden "Datenbank =". In einigen Fällen (wie Microsoft Excel und Microsoft Jet-Datenbanken) ein bestimmter Dateinamen im Pfadargument Datenbank enthalten ist.  
  
> [!NOTE]
>  Verwenden Sie keine Leerstellen um das Gleichheitszeichen in pfadanweisungen des Formulars "Datenbank = Laufwerk:\\\path". Dadurch wird eine Ausnahme ausgelöst wird, und die fehlerhafte Verbindung zurückgeben.  
  
 Die folgende Tabelle zeigt mögliche Datenbanktypen und ihre entsprechenden Datenbankbezeichner und Pfade:  
  
|Datenbanktyp|Bezeichner|Pfad|  
|-------------------|---------------|----------|  
|Datenbank mit der Jet-Datenbankmodul|"[ `database`];"|" `drive`:\\\ *Pfad*\\\ *Filename*. MDB"|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *Pfad*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *Pfad*"|  
|dBASE 5|"dBASE 5.0;"|" `drive`:\\\ *Pfad*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *Pfad*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *Pfad*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *Pfad*"|  
|Excel-3.0|"Excel 3.0;"|" `drive`:\\\ *Pfad*\\\ *Filename*. XLS"|  
|Excel 4.0|"Excel 4.0;"|" `drive`:\\\ *Pfad*\\\ *Filename*. XLS"|  
|Excel 5.0 oder Excel 95|"Excel 5.0;"|" `drive`:\\\ *Pfad*\\\ *Filename*. XLS"|  
|Excel 97|"Excel 8.0;"|" `drive`:\\\ *Pfad*\ *Filename*. XLS"|  
|HTML-Import|"HTML"Import der;|" `drive`:\\\ *Pfad*\ *Filename*"|  
|Der HTML-Export|"HTML"Export";|" `drive`:\\\ *Pfad*"|  
|Text|"Text;"|"Laufwerk:\\\path"|  
|ODBC|"ODBC; Datenbank = `database`; UID = *Benutzer*; PWD = *Kennwort*; DSN = *%DataSourceName;* LOGINTIMEOUT = *Sekunden;*" (Dies möglicherweise keine vollständige Verbindungszeichenfolge für alle Server; es ist nur ein Beispiel. Es ist sehr wichtig, nicht auf Leerzeichen zwischen den Parametern enthalten.)|Keiner|  
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *Folderpath*;<br /><br /> [TABLETYPE = {0 &AMP;#124; 1};]<br /><br /> [Profil = *Profil*;]<br /><br /> [PWD = *Kennwort*;]<br /><br /> [DATABASE = `database`;] "|*"Laufwerk*:\\\ *Pfad*\\\ *Filename*. MDB"|  
  
> [!NOTE]
>  Btrieve ab DAO 3.5 nicht mehr unterstützt.  
  
 Verwenden Sie einen doppelten umgekehrten Schrägstrich (\\\\) in den Verbindungszeichenfolgen. Wenn Sie eine vorhandene Verbindung mithilfe der Eigenschaften geändert haben `SetConnect`, müssen Sie anschließend aufrufen [RefreshLink](#refreshlink). Wenn Sie die Verbindungseigenschaften mit initialisieren `SetConnect`, benötigen Sie keine Aufruf `RefreshLink`, jedoch sollten Sie dies auswählen, zuerst die Tabledef angefügt.  
  
 Wenn ein Kennwort ist erforderlich, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und ein zweites Mal, wenn die Verbindung geschlossen und erneut geöffnet wird.  
  
 Sie können festlegen, dass die Verbindungszeichenfolge für eine `CDaoTableDef` -Objekt durch Bereitstellen einer Quellargument auf die **erstellen** Memberfunktion. Sie können die Einstellung bestimmt den Typ, Pfad, Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank überprüfen. Weitere Informationen finden Sie in der Dokumentation des Treibers.  
  
 Verwandte Informationen finden Sie im Thema "Verbinden der Eigenschaft" DAO-Hilfe.  
  
##  <a name="setname"></a>  CDaoTableDef::SetName  
 Rufen Sie diese Memberfunktion, um einen benutzerdefinierten Namen für eine Tabelle festzulegen.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Namen für eine Tabelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss mit einem Buchstaben beginnen und darf maximal 64 Zeichen lang sein. Er kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName  
 Rufen Sie diese Memberfunktion um den Namen einer angefügten Tabelle oder der Name der Basistabelle auf dem Angeben der `CDaoTableDef` Objekt basieren, wie er in die ursprüngliche Quelle der Daten ist.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSrcTableName*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Tabellennamen in der externen Datenbank angibt. Für eine Basistabelle, die Einstellung ist eine leere Zeichenfolge ("").  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen dann aufrufen [RefreshLink](#refreshlink). Die Einstellung dieser Eigenschaft ist für eine Basistabelle und Lese-/Schreibzugriff für eine verknüpfte Tabelle oder ein Objekt, das nicht an eine Auflistung angefügt leer.  
  
 Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule  
 Rufen Sie diese Memberfunktion, um eine Validierungsregel für eine Tabledef festzulegen.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszValidationRule*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Vorgang überprüft.  
  
### <a name="remarks"></a>Hinweise  
 Validierungsregeln werden im Zusammenhang mit der Update-Vorgänge verwendet. Enthält eine Tabledef eine Validierungsregel, müssen Updates für diese Tabledef vordefinierte Kriterien entsprechen, bevor die Daten geändert werden. Die Änderung der Kriterien, mit dem Text der Ausnahme stimmt nicht überein [GetValidationText](#getvalidationtext) wird angezeigt.  
  
 Überprüfung wird nur für Datenbanken unterstützt, die das Microsoft Jet-Datenbankmodul verwenden. Der Ausdruck kann nicht für benutzerdefinierte Funktionen, Aggregatfunktionen für Domänen, SQL-Aggregatfunktionen oder Abfragen verweisen. Eine Validierungsregel für eine `CDaoTableDef` Objekt kann auf mehrere Felder in diesem Objekt verweisen.  
  
 Z. B. für Felder mit dem Namen `hire_date` und `termination_date`, eine Validierungsregel kann sein:  
  
 [!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText  
 Rufen Sie diese Memberfunktion zum Festlegen der Text der Ausnahme einer Validierungsregel für eine `CDaoTableDef` Objekt mit einer zugrunde liegenden Basistabelle, die vom Microsoft Jet-Datenbankmodul unterstützt.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszValidationText*  
 Ein Zeiger auf einen Zeichenfolgenausdruck, der angibt, den Text angezeigt, wenn Daten eingegeben ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Sie können nicht den Text zu einer angefügten Tabelle festlegen.  
  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)
