---
title: CDaoTableDef-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: f678a00d4556cf81ad378088df2525038bbdd6a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426366"
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
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Erstellt ein `CDaoTableDef`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDaoTableDef::](#append)|Fügt eine neue Tabelle in der Datenbank an.|
|[CDaoTableDef::CanUpdate](#canupdate)|Gibt ungleich NULL, wenn die Tabelle aktualisiert werden kann (Sie können die Definition von Feldern oder Eigenschaften für die Tabelle ändern).|
|[CDaoTableDef::Close](#close)|Schließt einen geöffneten Tabledef an.|
|[CDaoTableDef::Create](#create)|Erstellt eine Tabelle, die mit der Datenbank hinzugefügt werden können [Append](#append).|
|[CDaoTableDef::CreateField](#createfield)|Wird aufgerufen, um ein Feld für eine Tabelle zu erstellen.|
|[CDaoTableDef::CreateIndex](#createindex)|Wird aufgerufen, um einen Index für eine Tabelle zu erstellen.|
|[CDaoTableDef::DeleteField](#deletefield)|Wird aufgerufen, um ein Feld aus einer Tabelle zu löschen.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|Wird aufgerufen, um einen Index aus einer Tabelle zu löschen.|
|[CDaoTableDef::GetAttributes](#getattributes)|Gibt einen Wert, der eine oder mehrere Merkmale angibt eine `CDaoTableDef` Objekt.|
|[CDaoTableDef::GetConnect](#getconnect)|Gibt einen Wert, der Informationen zur Quelle für eine Tabelle bereitstellt.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit der zugrunde liegenden Basistabelle eine `CDaoTableDef` Objekt erstellt wurde.|
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Gibt zurück, das Datum und Uhrzeit der letzten Änderung für das Design der Basistabelle.|
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in der Tabelle darstellt.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurück in der Tabelle.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|Gibt die Anzahl der Indizes der Tabelle zurück.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Gibt bestimmte Arten von Informationen zu den Indizes für die Tabelle zurück.|
|[CDaoTableDef::GetName](#getname)|Der benutzerdefinierte Name der Tabelle zurückgegeben.|
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in der Tabelle zurück.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Gibt einen Wert, der angibt, den Namen der angefügten Tabelle in der Quelldatenbank.|
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Ein Wert, der die Daten in einem Feld überprüft werden, da sie einer Tabelle hinzugefügt, geändert oder zurückgegeben.|
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Gibt einen Wert, der den Text der Nachricht, die Ihre Anwendung angezeigt angibt, wenn der Wert der Field-Objekt nicht über die angegebene Gültigkeitsprüfungsregel erfüllt.|
|[CDaoTableDef::IsOpen](#isopen)|Gibt zurück, die ungleich NULL, wenn die Tabelle öffnen.|
|[CDaoTableDef::Open](#open)|Öffnet eine vorhandene Tabledef in der Datenbank gespeichert ist TableDef Auflistung.|
|[CDaoTableDef::RefreshLink](#refreshlink)|Aktualisiert die Verbindungsinformationen für eine verknüpfte Tabelle an.|
|[CDaoTableDef::SetAttributes](#setattributes)|Legt einen Wert, der eine oder mehrere Merkmale angibt eine `CDaoTableDef` Objekt.|
|[CDaoTableDef::SetConnect](#setconnect)|Legt einen Wert, der Informationen zur Quelle für eine Tabelle bereitstellt.|
|[CDaoTableDef::SetName](#setname)|Legt den Namen der Tabelle.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Legt einen Wert, der angibt, der Name einer angefügten Tabelle in der Quelldatenbank.|
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Legt einen Wert, der die Daten in einem Feld überprüft, da sie geändert oder einer Tabelle hinzugefügt.|
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Legt einen Wert, der den Text der Nachricht, die Ihre Anwendung angezeigt angibt, wenn der Wert der Field-Objekt nicht über die angegebene Gültigkeitsprüfungsregel erfüllt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Ein Zeiger auf die zugrunde liegenden Objekt Tabledef DAO-Schnittstelle.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Source-Datenbank für diese Tabelle.|

## <a name="remarks"></a>Hinweise

Jedes Datenbankobjekt DAO verwaltet eine Sammlung mit dem Namen TableDefs, die alle gespeicherten DAO Tabledef Objekte enthält.

Sie ändern eine Tabelle mit einer `CDaoTableDef` Objekt. Sie haben unter anderem folgende Möglichkeiten:

- Überprüfen Sie die Struktur Feld und den Index einer lokalen, angefügte oder externen Tabelle in einer Datenbank.

- Rufen Sie die `SetConnect` und `SetSourceTableName` Memberfunktionen für verbundene Tabellen, und Verwenden der `RefreshLink` Member-Funktion zum Aktualisieren von Verbindungen mit angefügten Tabellen.

- Rufen Sie die `CanUpdate` Memberfunktion, um zu bestimmen, ob Sie Felddefinitionen in der Tabelle bearbeiten können.

- Abrufen oder Festlegen der Überprüfung von Bedingungen mit der `GetValidationRule` und `SetValidationRule`, und die `GetValidationText` und `SetValidationText` Memberfunktionen.

- Verwenden der `Open` Memberfunktion versucht, eine Tabelle, Dynaset oder Snapshot-Typ erstellen `CDaoRecordset` Objekt.

    > [!NOTE]
    >  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; die DAO-Klassen bieten im Allgemeinen überlegene Funktionen, da sie für die Microsoft Jet-Datenbank-Engine spezifisch sind.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Verwendung von Tabledef Objekte entweder mit einer vorhandenen Tabelle arbeiten oder eine neue Tabelle erstellen

1. In allen Fällen erstellen Sie zunächst eine `CDaoTableDef` -Objekt, indem einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekts, zu der die Tabelle gehört.

1. Führen Sie Folgendes, je nachdem, was soll:

   - Rufen Sie zum Verwenden einer vorhandenen Tabelle Speichern des Objekts Tabledef [öffnen](#open) Member-Funktion, die den Namen der gespeicherten Tabelle angeben.

   - Rufen Sie zum Erstellen einer neuen Tabelle des Objekts Tabledef [erstellen](#create) Member-Funktion, die den Namen der Tabelle angeben. Rufen Sie [CreateField](#createfield) und [CreateIndex](#createindex) Felder und Indizes der Tabelle hinzugefügt.

   - Rufen Sie [Append](#append) zum Speichern der Tabelle, indem er an der Datenbank TableDefs-Auflistung angehängt. `Create` versetzt Sie in den geöffneten Zustand Tabledef also nach dem Aufruf `Create` nicht aufrufen `Open`.

        > [!TIP]
        >  Die einfachste Möglichkeit zum Erstellen von gespeicherten Tabellen ist, die sie erstellen und speichern sie in der Datenbank mithilfe von Microsoft Access. Anschließend können Sie öffnen und in Ihrer MFC-Code verwenden.

Um Tabledef-Objekts verwenden Sie geöffnet oder erstellt haben, erstellen, und öffnen Sie eine `CDaoRecordset` -Objekt, wobei der Name des Tabledef mit einem `dbOpenTable` Wert in der *nOpenType* Parameter.

Ein Tabledef-Objekt verwendet wird, zum Erstellen einer `CDaoRecordset` Objekts, die Sie in der Regel erstellen oder öffnen eine Tabledef wie oben beschrieben, und erstellen ein Recordset-Objekts, die Übergabe eines Zeigers auf das Objekt Tabledef beim Aufrufen [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Tabledef, die Sie übergeben, muss sich im geöffneten Zustand. Weitere Informationen finden Sie in der Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Aufrufen, wenn Sie fertig sind, mit einem Tabledef-Objekt, dessen [schließen](../../mfc/reference/cdaorecordset-class.md#close) Member funktioniert, klicken Sie dann die Tabledef-Objekt zu zerstören.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="append"></a>  CDaoTableDef::

Rufen Sie diese Memberfunktion auf, nach dem Aufruf von [erstellen](#create) zum Erstellen eines neuen Tabledef-Objekts, um die Tabledef in der Datenbank zu speichern.

```
virtual void Append();
```

### <a name="remarks"></a>Hinweise

Die Funktion fügt das Objekt an der Datenbank TableDefs-Auflistung. Können Sie die Tabledef als temporäres Objekt und definieren sie es nicht anfügen, aber wenn Sie zu speichern und verwenden möchten, müssen Sie aufrufen `Append`.

> [!NOTE]
>  Wenn Sie versuchen, eine unbenannte Tabledef (mit einem NULL- bzw. leere Zeichenfolge) angefügt werden soll, löst MFC eine Ausnahme aus.

Weitere Informationen finden Sie unter dem Thema "Fügen Sie der Methode" in-DAO-Hilfe.

##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Definition der zugrunde liegenden Tabelle eine `CDaoTableDef` Objekt geändert werden kann.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Tabellenstruktur (Schema) geändert werden kann (hinzufügen oder Löschen von Feldern und Indizes), andernfalls 0.

### <a name="remarks"></a>Hinweise

Standardmäßig eine neu erstellte Tabelle zugrunde liegt ein `CDaoTableDef` Objekt kann aktualisiert werden, und einer angefügten Tabelle zugrunde liegenden eine `CDaoTableDef` Objekt kann nicht aktualisiert werden. Ein `CDaoTableDef` Objekt möglicherweise, aktualisiert werden kann, auch wenn das resultierende Recordset nicht aktualisiert werden kann.

Verwandte Informationen finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.

##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef

Erstellt ein `CDaoTableDef`-Objekt.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parameter

*pDatabase*<br/>
Ein Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Sie müssen nach dem Erstellen des Objekts Aufrufen der [erstellen](#create) oder [öffnen](#open) Member-Funktion. Wenn Sie mit dem Objekt fertig sind, müssen Sie Aufrufen der [schließen](#close) Member funktioniert und zerstört das `CDaoTableDef` Objekt.

##  <a name="close"></a>  CDaoTableDef::Close

Rufen Sie diese Memberfunktion zum Schließen und das Objekt Tabledef freizugeben.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

In der Regel nach dem Aufruf `Close`, wenn es zugeordnet wurde, löschen Sie das Tabledef-Objekt **neue**.

Rufen Sie [öffnen](#open) erneut nach dem Aufruf `Close`. Dadurch können Sie das Objekt Tabledef wiederverwenden.

Verwandte Informationen finden Sie im Thema "Close-Methode" in-DAO-Hilfe.

##  <a name="create"></a>  CDaoTableDef::Create

Rufen Sie diese Memberfunktion zum Erstellen einer neuen gespeicherte Tabelle.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Tabelle.

*lAttributes*<br/>
Ein Wert, der entsprechenden Merkmale der Tabelle durch das Tabledef-Objekt dargestellt wird. Sie können das bitweise OR verwenden, kombinieren Sie eines der folgenden Konstanten:

|Konstante|Beschreibung|
|--------------|-----------------|
|`dbAttachExclusive`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle, die für die ausschließliche Verwendung geöffnet ist.|
|`dbAttachSavePWD`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|
|`dbSystemObject`|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|
|`dbHiddenObject`|Gibt an, dass die Tabelle einen ausgeblendeten Tabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|

*lpszSrcTable*<br/>
Ein Zeiger auf eine Zeichenfolge mit dem Namen der Quelltabelle. Standardmäßig ist dieser Wert als NULL initialisiert.

*lpszConnect*<br/>
Ein Zeiger auf eine Zeichenfolge, die die standardmäßige Verbindungszeichenfolge enthält. Standardmäßig ist dieser Wert als NULL initialisiert.

### <a name="remarks"></a>Hinweise

Nachdem Sie die Tabledef benannt haben, rufen Sie anschließend [Append](#append) Tabledef in der Datenbank TableDefs-Auflistung zu speichern. Nach dem Aufruf `Append`Tabledef befindet sich im geöffneten Zustand und können Sie sie zum Erstellen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt.

Verwandte Informationen finden Sie im Thema "CreateTableDef Method" in-DAO-Hilfe.

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

*Wert*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen dieses Felds angeben.

*nType*<br/>
Ein Wert, der den Datentyp des Felds angibt. Die Einstellung kann einen der folgenden Werte sein:

|Typ|Größe (Byte)|Beschreibung|
|----------|--------------------|-----------------|
|`dbBoolean`|1 Byte|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|Währung ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|Datum/Uhrzeit ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Text ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long-Binärdatei (OLE-Objekt) [CLongBinary](../../mfc/reference/clongbinary-class.md) oder [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|Memo ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize beim Aufruf*<br/>
Ein Wert, der angibt, die maximale Größe in Bytes, der ein Feld, das Text enthält, oder die feste Größe von einem Feld, Text oder numerische Werte enthält. Die *lSize beim Aufruf* Parameter wird ignoriert, für alle bis auf Textfelder.

*lAttributes*<br/>
Ein Wert, der Eigenschaften des Felds und, kann mithilfe einer bitweisen OR kombiniert werden.

|Konstante|Beschreibung|
|--------------|-----------------|
|`dbFixedField`|Die Größe des Felds ist (Standard für numerische Felder) behoben.|
|`dbVariableField`|Die Größe des Felds ist die Variable (gilt nur für Text-Felder).|
|`dbAutoIncrField`|Der Feldwert für neue Datensätze wird auf eine eindeutige lange Ganzzahl, die nicht geändert werden kann, automatisch erhöht. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.|
|`dbUpdatableField`|Der Wert des Felds kann geändert werden.|
|`dbDescending`|Das Feld wird sortiert in absteigender (Z – A oder 0, 100) Reihenfolge (gilt nur für eine Field-Objekt in einer Fields-Auflistung eines Index-Objekts). Wenn Sie diese Konstante weglassen, wird das Feld in aufsteigender sortiert (A – Z oder 0 - 100) Reihenfolge (Standard).|

*FieldInfo*<br/>
Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.

### <a name="remarks"></a>Hinweise

Ein `DAOField` (OLE)-Objekt erstellt und angefügt werden, auf die Auflistung der Felder von der `DAOTableDef` (OLE)-Objekt. Neben dem deren Verwendung zum Untersuchen von Objekteigenschaften können Sie auch `CDaoFieldInfo` um einen Eingabeparameter für das Erstellen neuer Felder in einer Tabledef zu erstellen. Die erste Version des `CreateField` ist einfacher zu verwenden, aber wenn Sie eine präzisere Kontrolle wünschen, können Sie die zweite Version der `CreateField`, nimmt eine `CDaoFieldInfo` Parameter.

Bei Verwendung die Version von `CreateField` , akzeptiert eine `CDaoFieldInfo` Parameter, Sie müssen sorgfältig festlegen. jede der folgenden Elemente der `CDaoFieldInfo` Struktur:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Die restlichen Mitglieder des `CDaoFieldInfo` sollte festgelegt werden, um **0**, FALSE oder eine leere Zeichenfolge, nach Bedarf für das Element, oder ein `CDaoException` auftreten.

Verwandte Informationen finden Sie im Thema "CreateField Method" in-DAO-Hilfe.

##  <a name="createindex"></a>  CDaoTableDef::CreateIndex

Rufen Sie diese Funktion, um einen Index einer Tabelle hinzuzufügen.

```
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Parameter

*indexinfo*<br/>
Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.

### <a name="remarks"></a>Hinweise

Indizes legen die Reihenfolge der Datensätze, die auf das Sie über die Datenbanktabellen und davon, ob doppelte Datensätze akzeptiert werden. Indizes bieten auch effizienten Zugriff auf Daten.

Sie müssen keine Indizes für Tabellen zu erstellen, aber in großen Tabellen ohne Index, den Zugriff auf einen bestimmten Datensatz oder ein Recordset erstellen kann sehr lange dauern. Andererseits, erstellen zu viele Indizes verlangsamt, Update, Anfügen und Löschvorgänge, da alle Indizes automatisch aktualisiert werden. Beachten Sie diese Faktoren, wie Sie, welche Indizes entscheiden erstellen.

Die folgenden Elemente von der `CDaoIndexInfo` Struktur muss festgelegt werden:

- `m_strName` Ein Name muss angegeben werden.

- `m_pFieldInfos` Muss auf ein Array von verweisen `CDaoIndexFieldInfo` Strukturen.

- `m_nFields` Geben Sie die Anzahl der Felder muss in das Array von `CDaoFieldInfo` Strukturen.

Die verbleibenden Elemente werden ignoriert, wenn auf FALSE festgelegt werden. Darüber hinaus die `m_lDistinctCount` Member wird ignoriert, während der Erstellung des Indexes.

##  <a name="deletefield"></a>  CDaoTableDef::DeleteField

Rufen Sie diese Memberfunktion zum Entfernen von Feldern und erleichtern die nicht zugegriffen werden kann.

```
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen eines vorhandenen Felds ist.

*nIndex*<br/>
Der Index des Felds in der Tabelle nullbasierte Fields-Sammlung, für die Suche nach Index.

### <a name="remarks"></a>Hinweise

Sie können diese Memberfunktion auf ein neues Objekt, das nicht mit der Datenbank angefügt wurde oder wenn [CanUpdate](#canupdate) ungleich NULL zurückgibt.

Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.

##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex

Rufen Sie diese Memberfunktion, um einen Index in einer zugrunde liegenden Tabelle zu löschen.

```
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der den Namen eines vorhandenen Indexes ist.

*nIndex*<br/>
Der Arrayindex des Objekts Index in der Datenbank nullbasierte TableDefs-Auflistung, für die Suche nach Index.

### <a name="remarks"></a>Hinweise

Sie können diese Memberfunktion auf ein neues Objekt, das an die Datenbank angefügt wurde noch nicht verwenden oder wenn [CanUpdate](#canupdate) ungleich NULL zurückgibt.

Verwandte Informationen finden Sie im Thema "-Methode Delete" in-DAO-Hilfe.

##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes

Für eine `CDaoTableDef` -Objekt, der Rückgabewert gibt die Merkmale der Tabelle dargestellt durch die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:

```
long GetAttributes();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert, der eine oder mehrere Merkmale angibt eine `CDaoTableDef` Objekt.

### <a name="remarks"></a>Hinweise

|Konstante|Beschreibung|
|--------------|-----------------|
|`dbAttachExclusive`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle, die für die ausschließliche Verwendung geöffnet ist.|
|`dbAttachSavePWD`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|
|`dbSystemObject`|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|
|`dbHiddenObject`|Gibt an, dass die Tabelle einen ausgeblendeten Tabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|
|`dbAttachedTable`|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Paradox-Datenbank ist.|
|`dbAttachedODBC`|Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server ist.|

Eine Systemtabelle handelt es sich um eine Tabelle erstellt, die von der Microsoft Jet-Datenbank-Engine, die verschiedene internen Informationen enthalten.

Eine ausgeblendete Tabelle ist eine Tabelle, die von der Microsoft Jet-Datenbank-Engine zur vorübergehenden Verwendung erstellt.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getconnect"></a>  CDaoTableDef::GetConnect

Rufen Sie diese Memberfunktion zum Abrufen der Verbindungszeichenfolge für eine Datenquelle an.

```
CString GetConnect();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Pfad und den Datenbank-Typ für die Tabelle enthält.

### <a name="remarks"></a>Hinweise

Für eine `CDaoTableDef` -Objekt, das eine angefügten Tabelle stellt die `CString` -Objekt besteht aus einem oder zwei Teilen (ein Typspezifizierer der Datenbank und einen Pfad zu der Datenbank).

Der Pfad, wie in der folgenden Tabelle gezeigt ist der vollständige Pfad des Verzeichnisses, die die Datenbankdateien enthalten und muss durch den Bezeichner stehen "Datenbank =". In einigen Fällen (wie Microsoft Excel mit Microsoft Jet-Datenbanken) ein bestimmtes Dateinamens in der Datenbank-Pfadargument enthalten ist.

Die Tabelle in [CDaoTableDef::SetConnect](#setconnect) zeigt mögliche Datenbanktypen und ihre entsprechenden Datenbankbezeichner und Pfade:

Für Microsoft Jet-Datenbank-Basistabellen, ist der Bezeichner eine leere Zeichenfolge ("").

Wenn ein Kennwort erforderlich ist, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und ein weiteres Mal, wenn die Verbindung geschlossen und erneut geöffnet wird. Wenn es sich bei eine angefügte Tabelle verfügt über die `dbAttachSavePWD` -Attribut, zur Anmeldung aufgefordert wird nicht angezeigt werden, wenn die Tabelle erneut geöffnet wird.

Weitere Informationen finden Sie unter dem Thema "Connect-Eigenschaft" in-DAO-Hilfe.

##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated

Mit dieser Funktion werden um zu bestimmen, das Datum und die Uhrzeit der zugrunde liegende Tabelle die `CDaoTableDef` Objekt erstellt wurde.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, die Datum und Uhrzeit der Erstellung der zugrunde liegenden Tabelle enthält die `CDaoTableDef` Objekt.

### <a name="remarks"></a>Hinweise

Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung erhalten Benutzer diese Einstellungen direkt vom Dateiserver auf Vermeidung von abweichungen; Das heißt, alle Clients eine "standard" Zeitquelle verwenden sollten, z. B. von einem Server.

Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.

##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated

Mit dieser Funktion werden um zu bestimmen, das Datum und die Uhrzeit der zugrunde liegende Tabelle die `CDaoTableDef` Objekt zuletzt aktualisiert wurde.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der das Datum und die Uhrzeit der zugrunde liegende Tabelle enthält die `CDaoTableDef` Objekt zuletzt aktualisiert wurde.

### <a name="remarks"></a>Hinweise

Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung erhalten Benutzer diese Einstellungen direkt vom Dateiserver auf Vermeidung von abweichungen; Das heißt, alle Clients eine "standard" Zeitquelle verwenden sollten, z. B. von einem Server.

Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.

##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Feldern, die in der Tabelle definiert.

```
short GetFieldCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Felder in der Tabelle.

### <a name="remarks"></a>Hinweise

Wenn der Wert 0 ist, müssen Sie keine Objekte vorhanden sind, in der Auflistung.

Weitere Informationen finden Sie unter dem Thema "Count-Eigenschaft" in-DAO-Hilfe.

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

*nIndex*<br/>
Der Index des Feldobjekts in der Tabelle nullbasierte Fields-Sammlung, für die Suche nach Index.

*FieldInfo*<br/>
Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen über das Feld abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:

- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Typ, Größe und der Attribute. Verwenden Sie diese Option für die bestmögliche Leistung zu erzielen.

- `AFX_DAO_SECONDARY_INFO` Primäre Informationen sowie: Ordnungszahl ab, die erforderlich sind, ermöglichen Null Länge Reihenfolge sortieren, Fremdschlüssel, Feld "Quelle" Quelle Namenstabelle

- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären sowie: Validierungsregel Validierung von Text, Standardwert

*Wert*<br/>
Ein Zeiger auf den Namen der Field-Objekt, für die Suche anhand des Namens. Der Name ist eine Zeichenfolge mit bis zu 64 Zeichen, die das Feld eindeutig bezeichnet.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen zu suchen.

Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount

Rufen Sie diese Memberfunktion, um die Anzahl der Indizes für eine Tabelle zu erhalten.

```
short GetIndexCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Indizes für die Tabelle.

### <a name="remarks"></a>Hinweise

Wenn der Wert 0 ist, gibt es keine Indizes in der Auflistung an.

Weitere Informationen finden Sie unter dem Thema "Count-Eigenschaft" in-DAO-Hilfe.

##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo

Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einem Index in die Tabledef definiert.

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

*nIndex*<br/>
Der numerische Index des Objekts Index in der Tabelle nullbasierten Indexsammlung, für die Suche anhand seiner Position in der Auflistung.

*indexinfo*<br/>
Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen über den Index abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:

- `AFX_DAO_PRIMARY_INFO` Name, Feldinformationen, Felder. Verwenden Sie diese Option für die bestmögliche Leistung zu erzielen.

- `AFX_DAO_SECONDARY_INFO` Primäre Informationen sowie: primären, eindeutiger, gruppierter, ignorieren NULL-Werte erforderlich, Fremdschlüssel

- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären sowie: Distinct Count

*Wert*<br/>
Ein Zeiger auf den Namen des Index-Objekt, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie einen Index nach seiner Position in der Auflistung gesucht. Die andere Version können Sie einen Index nach Namen suchen.

Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getname"></a>  CDaoTableDef::GetName

Rufen Sie diese Memberfunktion um den benutzerdefinierten Namen der zugrunde liegenden Tabelle zu erhalten.

```
CString GetName();
```

### <a name="return-value"></a>Rückgabewert

Einen benutzerdefinierten Namen für eine Tabelle.

### <a name="remarks"></a>Hinweise

Dieser Name mit einem Buchstaben beginnen und darf maximal 64 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen, aber keine Interpunktionszeichen oder Leerzeichen enthalten.

Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount

Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze in sind eine `CDaoTableDef` Objekt.

```
long GetRecordCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Datensätze, die in einem Tabledef-Objekt zugegriffen werden soll.

### <a name="remarks"></a>Hinweise

Aufrufen von `GetRecordCount` für einen Tabellentyp `CDaoTableDef` Objekt gibt die ungefähre Anzahl der Datensätze in der Tabelle und wird sofort beeinflusst, wie Datensätze hinzugefügt und gelöscht werden. Rollback Transaktionen werden als Teil der Anzahl der Datensätze, bis Sie aufrufen [CDaoWorkspace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Ein `CDaoTableDef` Objekt ohne Datensätze hat eine Anzahl der Datensätze-eigenschafteneinstellung für 0. Bei der Arbeit mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` gibt immer-1 zurück.

Weitere Informationen finden Sie unter dem Thema "RecordCount-Eigenschaft" in-DAO-Hilfe.

##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName

Rufen Sie diese Memberfunktion um den Namen einer angefügten Tabelle in einer Quelldatenbank abzurufen.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Quellnamen einer angefügten Tabelle oder eine leere Zeichenfolge gibt an, wenn eine systemeigene Datentabelle.

### <a name="remarks"></a>Hinweise

Eine angefügte Tabelle ist eine Tabelle in einer anderen Datenbank, die mit Microsoft Jet-Datenbank verknüpft. Verbundene Tabellen die Daten verbleiben in der externen Datenbank, wenn Sie, wo es von anderen Anwendungen bearbeitet werden.

Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" in-DAO-Hilfe.

##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule

Rufen Sie diese Memberfunktion, um die Überprüfungsregel für ein Tabledef abzurufen.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das die Daten in einem Feld überprüft werden, da sie geändert oder einer Tabelle hinzugefügt.

### <a name="remarks"></a>Hinweise

Validierungsregeln werden im Zusammenhang mit der Update-Vorgänge verwendet. Eine Tabledef eine Validierungsregel enthält, müssen Updates für diese Tabledef vordefinierte Kriterien entsprechen, bevor die Daten geändert werden. Wenn die Änderung nicht die Kriterien, eine Ausnahme, die mit dem Wert des entspricht [GetValidationText](#getvalidationtext) ausgelöst. Für eine `CDaoTableDef` dieses-Objekt `CString` für eine verknüpfte Tabelle und die Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.

Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" in-DAO-Hilfe.

##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText

Rufen Sie diese Funktion zum Abrufen der Zeichenfolge angezeigt, wenn ein Benutzer Daten eingibt, die die Validierungsregel nicht übereinstimmen.

```
CString GetValidationText();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das gibt den Text angezeigt, wenn Daten eingegeben werden, die die Validierungsregel nicht übereinstimmen.

### <a name="remarks"></a>Hinweise

Für eine `CDaoTableDef` dieses-Objekt `CString` für eine verknüpfte Tabelle und die Lese-/Schreibzugriff für eine Basistabelle schreibgeschützt ist.

Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in-DAO-Hilfe.

##  <a name="isopen"></a>  CDaoTableDef::IsOpen

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoTableDef` Objekt ist momentan geöffnet.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CDaoTableDef` Objekt geöffnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase

Enthält einen Zeiger auf die [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt für diese Tabelle.

### <a name="remarks"></a>Hinweise

##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef

Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Tabledef-Objekt zugrunde liegenden der `CDaoTableDef` Objekt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen möchten.

##  <a name="open"></a>  CDaoTableDef::Open

Diese Memberfunktion zum Öffnen einer Tabledef zuvor in der Datenbank gespeicherten Aufruf ist TableDef Auflistung.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die einen Tabellennamen angibt.

### <a name="remarks"></a>Hinweise

##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink

Rufen Sie diese Memberfunktion, um die Verbindungsinformationen für eine verknüpfte Tabelle zu aktualisieren.

```
void RefreshLink();
```

### <a name="remarks"></a>Hinweise

Sie ändern die Verbindungsinformationen für eine verknüpfte Tabelle durch Aufrufen von [SetConnect](#setconnect) in der entsprechenden `CDaoTableDef` -Objekt, und klicken Sie dann mit der `RefreshLink` Memberfunktion versucht, die Informationen zu aktualisieren. Beim Aufruf `RefreshLink`, die verknüpfte Tabelle Eigenschaften nicht geändert werden.

Erzwingen, dass die geänderte Verbindung mit Informationen, um alle geöffneten wirksam [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte werden basierend auf diesem Tabledef müssen geschlossen werden.

Verwandte Informationen finden Sie im Thema "RefreshLink Method" in-DAO-Hilfe.

##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes

Legt einen Wert, der eine oder mehrere Merkmale angibt eine `CDaoTableDef` Objekt.

```
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Parameter

*lAttributes*<br/>
Merkmale der Tabelle dargestellt durch die `CDaoTableDef` Objekt und kann eine Summe der folgenden Konstanten:

|Konstante|Beschreibung|
|--------------|-----------------|
|`dbAttachExclusive`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle, die für die ausschließliche Verwendung geöffnet ist.|
|`dbAttachSavePWD`|Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.|
|`dbSystemObject`|Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|
|`dbHiddenObject`|Gibt an, dass die Tabelle einen ausgeblendeten Tabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird.|

### <a name="remarks"></a>Hinweise

Wenn Sie mehrere Attribute festlegen möchten, können Sie diese durch summieren die entsprechenden Konstanten, die mit dem bitweisen OR-Operator kombinieren. Festlegen von `dbAttachExclusive` erstellt eine Ausnahme für eine Tabelle. Kombinieren die folgenden Werte auch erzeugen eine Ausnahme:

- **DbAttachExclusive &#124; DbAttachedODBC**

- **DbAttachSavePWD &#124; DbAttachedTable**

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="setconnect"></a>  CDaoTableDef::SetConnect

Für eine `CDaoTableDef` Objekt, das eine angefügte Tabelle, die String-Objekt darstellt besteht aus einem oder zwei Teilen (ein Typspezifizierer der Datenbank und einen Pfad zu der Datenbank).

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parameter

*lpszConnect*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der zusätzliche Parameter zum Übergeben an die ODBC oder installierbaren ISAM-Treiber angibt.

### <a name="remarks"></a>Hinweise

Der Pfad, wie in der folgenden Tabelle gezeigt ist der vollständige Pfad des Verzeichnisses, die die Datenbankdateien enthalten und muss durch den Bezeichner stehen "Datenbank =". In einigen Fällen (wie Microsoft Excel mit Microsoft Jet-Datenbanken) ein bestimmtes Dateinamens in der Datenbank-Pfadargument enthalten ist.

> [!NOTE]
>  Schließen Sie Leerzeichen vor und hinter dem Gleichzeichen nicht in der Path-Anweisungen der Form "Datenbank = Laufwerk:\\\path". Dies führt in eine Ausnahme ausgelöst wird und die Verbindung ein.

Die folgende Tabelle zeigt mögliche Datenbanktypen und ihre entsprechenden Datenbankbezeichner und Pfade:

|Datenbanktyp|Bezeichner|Pfad|
|-------------------|---------------|----------|
|Datenbank mit der Jet-Datenbank-engine|"[ `database`];"|" `drive`:\\\ *Pfad*\\\ *Filename*. MDB"|
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
|Importieren von HTML|"HTML-importieren;"|" `drive`:\\\ *Pfad*\ *Filename*"|
|Der HTML-Export|"HTML-Export;"|" `drive`:\\\ *Pfad*"|
|Text|"Text;"|"Laufwerk:\\\path"|
|ODBC|"ODBC; Datenbank = `database`; UID = *Benutzer*; PWD = *Kennwort*; DSN = *%DataSourceName;* LOGINTIMEOUT = *Sekunden;*" (Dies eventuell nicht möglich, eine vollständige Verbindungszeichenfolge für alle Server, sondern nur ein Beispiel. Es ist sehr wichtig, keine Leerzeichen zwischen den Parametern enthalten.)|Keiner|
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *"folderPath"*;<br /><br /> [TABLETYPE = {0 &AMP;#124; 1};]<br /><br /> [Profil = *Profil*;]<br /><br /> [PWD = *Kennwort*;]<br /><br /> [DATABASE = `database`;] "|*"Laufwerk*:\\\ *Pfad*\\\ *Filename*. MDB"|

> [!NOTE]
>  Btrieve wird seit DAO 3.5 nicht mehr unterstützt.

Verwenden Sie einen doppelten umgekehrten Schrägstrich (\\\\) in den Verbindungszeichenfolgen. Wenn Sie eine vorhandene Verbindung mit die Eigenschaften geändert haben `SetConnect`, Sie müssen anschließend aufrufen [RefreshLink](#refreshlink). Wenn Sie die Verbindungseigenschaften mit initialisieren `SetConnect`, benötigen Sie nicht aufrufen `RefreshLink`, jedoch sollten Sie auch dazu, zuerst die Tabledef angefügt.

Wenn ein Kennwort erforderlich ist, aber nicht angegeben, zeigt der ODBC-Treiber eine Anmeldung Dialogfeld zum ersten Mal eine Tabelle zugegriffen wird und ein weiteres Mal, wenn die Verbindung geschlossen und erneut geöffnet wird.

Sie können festlegen, dass die Verbindungszeichenfolge für eine `CDaoTableDef` Objekts. Hierbei geben ein Quellargument, um die `Create` Member-Funktion. Sie können die Einstellung, um zu bestimmen, der Typ, Pfad, Benutzer-ID, Kennwort oder ODBC-Datenquelle der Datenbank überprüfen. Weitere Informationen finden Sie in der Dokumentation des Treibers.

Weitere Informationen finden Sie unter dem Thema "Connect-Eigenschaft" in-DAO-Hilfe.

##  <a name="setname"></a>  CDaoTableDef::SetName

Rufen Sie diese Memberfunktion auf einen benutzerdefinierten Namen für eine Tabelle festlegen.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Namen für eine Tabelle angibt.

### <a name="remarks"></a>Hinweise

Der Name muss mit einem Buchstaben beginnen und darf maximal 64 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen, aber keine Interpunktionszeichen oder Leerzeichen enthalten.

Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName

Rufen Sie diese Memberfunktion um den Namen einer angefügten Tabelle oder der Name der Basistabelle anzugeben, auf dem die `CDaoTableDef` Objekt basiert, wie sie in der ursprünglichen Quelle der Daten vorhanden sind.

```
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Parameter

*lpszSrcTableName*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Tabellennamen in der externen Datenbank angibt. Für eine Basistabelle, die Einstellung ist eine leere Zeichenfolge ("").

### <a name="remarks"></a>Hinweise

Sie müssen dann aufrufen [RefreshLink](#refreshlink). Die Einstellung dieser Eigenschaft ist leer, um eine Basis- und Lese-/Schreibzugriff für eine verknüpfte Tabelle oder ein Objekt, das nicht an eine Auflistung angefügt.

Verwandte Informationen finden Sie im Thema "SourceTableName-Eigenschaft" in-DAO-Hilfe.

##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule

Rufen Sie diese Memberfunktion, um eine Validierungsregel für einen Tabledef festzulegen.

```
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Parameter

*lpszValidationRule*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der einen Vorgang überprüft werden soll.

### <a name="remarks"></a>Hinweise

Validierungsregeln werden im Zusammenhang mit der Update-Vorgänge verwendet. Eine Tabledef eine Validierungsregel enthält, müssen Updates für diese Tabledef vordefinierte Kriterien entsprechen, bevor die Daten geändert werden. Wenn die Änderung nicht die Kriterien, mit dem Text der Ausnahme entspricht [GetValidationText](#getvalidationtext) wird angezeigt.

Überprüfung wird nur für Datenbanken unterstützt, die Microsoft Jet-Datenbank-Engine zu verwenden. Der Ausdruck kann nicht auf benutzerdefinierte Funktionen, Aggregatfunktionen für Domänen, SQL-Aggregatfunktionen oder Abfragen verweisen. Eine Validierungsregel für einen `CDaoTableDef` Objekt kann auf mehrere Felder in diesem Objekt verweisen.

Z. B. für Felder, die mit dem Namen *Hire_date* und *Termination_date*, eine Validierungsregel kann sein:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" in-DAO-Hilfe.

##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText

Rufen Sie diese Memberfunktion zum Festlegen der Text der Ausnahme einer Validierungsregel für einen `CDaoTableDef` Objekt mit einer zugrunde liegenden Basistabelle, die von der Microsoft Jet-Datenbank-Engine unterstützt werden.

```
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Parameter

*lpszValidationText*<br/>
Ein Zeiger auf einen Zeichenfolgenausdruck, der angibt, den Text angezeigt, wenn Daten eingegeben ist ungültig.

### <a name="remarks"></a>Hinweise

Sie können nicht den Text der Validierung einer angefügten Tabelle festlegen.

Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in-DAO-Hilfe.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)
