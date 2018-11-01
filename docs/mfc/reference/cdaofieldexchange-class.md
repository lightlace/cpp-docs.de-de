---
title: CDaoFieldExchange-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: ef88486d14ade1d5871d614069dc1c202d6ad159
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654219"
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange-Klasse

Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden.

## <a name="syntax"></a>Syntax

```
class CDaoFieldExchange
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Gibt zurück, die ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des aktualisierten Felds.|
|[CDaoFieldExchange:: SetFieldType](#setfieldtype)|Gibt den Typ des Recordset-Datenmember, Spalte oder des Parameters – durch alle nachfolgenden Aufrufe DFX-Funktionen dargestellt wird, bis der nächste Aufruf von `SetFieldType`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDaoFieldExchange::](#m_noperation)|Der DFX-Vorgang ausgeführt wird, durch den aktuellen Aufruf des Recordsets `DoFieldExchange` Member-Funktion.|
|[CDaoFieldExchange::m_prs](#m_prs)|Ein Zeiger auf das Recordset, das für die, das DFX Vorgänge ausgeführt werden.|

## <a name="remarks"></a>Hinweise

`CDaoFieldExchange` eine Basisklasse keinen.

Verwenden Sie diese Klasse, wenn Sie für benutzerdefinierte Datentypen Data Exchange-Routinen schreiben; Andernfalls werden Sie diese Klasse nicht direkt verwendet. DFX-Datenaustausch zwischen den Felddatenmembern Ihre [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) -Objekt und den entsprechenden Feldern des aktuellen Datensatzes in der Datenquelle. DFX verwaltet den Datenaustausch in beide Richtungen, aus der Datenquelle und mit der Datenquelle. Finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) Informationen über die benutzerdefinierte DFX-Routinen schreiben.

> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC. Die DAO-basierten Klassen können Daten, einschließlich über ODBC-Treiber, über eigene Datenbank-Engine zugreifen. Sie unterstützen außerdem Vorgänge (Data Definition Language, Datendefinitionssprache), z. B. das Hinzufügen von Tabellen über die Klassen statt DAO selbst aufrufen.

> [!NOTE]
>  DAO-Datensatzfeldaustausch (DFX) ist sehr ähnlich Datensatzfeldaustausch (RFX) in den ODBC-basierten MFC-Datenbankklassen ( `CDatabase`, `CRecordset`). Wenn Sie RFX verstehen, können Sie benutzerfreundliche DFX finden.

Ein `CDaoFieldExchange` Objekt enthält Kontextinformationen erforderlich für-DAO-Datensatzfeldaustausch stattfinden soll. `CDaoFieldExchange` Objekte unterstützen eine Anzahl von Vorgängen, einschließlich Bindungsparameter und Felddatenmember und Festlegen von verschiedenen Flags für die Felder des aktuellen Datensatzes an. DFX-Vorgänge für Recordset-Klasse-Datenmember von Typen, die von definiert die **Enum** **FieldType** in `CDaoFieldExchange`. Mögliche **FieldType** Werte sind:

- `CDaoFieldExchange::outputColumn` für den Felddatenmembern.

- `CDaoFieldExchange::param` für die Parameter-Datenelemente.

Die [IsValidOperation](#isvalidoperation) Memberfunktion wird für Ihre eigenen benutzerdefinierten DFX-Routinen schreiben bereitgestellt. Verwenden Sie [SetFieldType](#setfieldtype) häufig in Ihre [CDaoRecordset:: DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktionen. Weitere Informationen zu den globalen DFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Informationen zum Schreiben von benutzerdefinierten DFX-Routinen für Ihre eigenen Datentypen finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDaoFieldExchange`

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation

Wenn Sie Ihre eigene DFX-Funktion schreiben, rufen Sie `IsValidOperation` am Anfang der Funktion zu bestimmen, ob der aktuelle Vorgang für ein bestimmtes Feld datenmembertyp ausgeführt werden kann (ein `CDaoFieldExchange::outputColumn` oder `CDaoFieldExchange::param`).

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der aktuelle Vorgang für den Typ des aktualisierten Felds geeignet ist.

### <a name="remarks"></a>Hinweise

Einige der Vorgänge ausgeführt werden, indem der DFX-Mechanismus gelten nur für eines der möglichen Feldtypen. Führen Sie das Modell für die vorhandenen DFX-Funktionen.

Weitere Informationen zu benutzerdefinierte DFX-Routinen schreiben, finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

##  <a name="m_noperation"></a>  CDaoFieldExchange::

Identifiziert den Vorgang ausgeführt werden die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, das Exchange-Objekt zugeordnet.

### <a name="remarks"></a>Hinweise

Die `CDaoFieldExchange` Objekt liefert den Kontext für eine Reihe von verschiedenen DFX-Vorgänge für das Recordset.

> [!NOTE]
>  Die PSEUDONULL beschrieben, die unter den unten aufgeführten Vorgänge MarkForAddNew und SetFieldNull ist ein Wert verwendet, um Felder Null zu markieren. In den Austauschmechanismus für DAO-Datensatzfeldaustausch (DFX) verwendet diesen Wert, um zu bestimmen, welche Felder Null explizit markiert wurden. PSEUDONULL ist nicht erforderlich, damit [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) und [COleCurrency](../../mfc/reference/colecurrency-class.md) Felder.

Mögliche Werte für `m_nOperation` sind:

|Vorgang|Beschreibung|
|---------------|-----------------|
|`AddToParameterList`|Erstellt die **Parameter** -Klausel der SQL-Anweisung.|
|`AddToSelectList`|Erstellt die **wählen** -Klausel der SQL-Anweisung.|
|`BindField`|Bindet ein Feld in der Datenbank an einem Speicherort in Ihrer Anwendung.|
|`BindParam`|Legt die Parameterwerte für die Abfrage des Recordsets.|
|`Fixup`|Legt fest, den Null-Status für ein Feld.|
|`AllocCache`|Ordnet den Cache verwendet, um für "dirty"-Felder im Recordset zu überprüfen.|
|`StoreField`|Speichert den aktuellen Datensatz im Cache.|
|`LoadField`|Stellt die zwischengespeicherten Daten Membervariablen im Recordset.|
|`FreeCache`|Gibt den Cache verwendet, um für "dirty"-Felder im Recordset überprüfen frei.|
|`SetFieldNull`|Legt ein Feld des Status auf Null und PSEUDONULL-Wert fest.|
|`MarkForAddNew`|Markierungen Felder "geändert" Wenn nicht PSEUDONULL.|
|`MarkForEdit`|Markiert Felder "dirty", wenn sie nicht, den Cache übereinstimmen.|
|`SetDirtyField`|Legt Feldwerte markiert als "fehlerhaft".|
|`DumpField`|Sichert eine Feldinhalt (nur Debug).|
|`MaxDFXOperation`|Für die eingabevalidierung verwendet.|

##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs

Enthält einen Zeiger auf die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugeordnete Objekt der `CDaoFieldExchange` Objekt.

### <a name="remarks"></a>Hinweise

##  <a name="setfieldtype"></a>  CDaoFieldExchange:: SetFieldType

Rufen Sie `SetFieldType` in Ihre `CDaoRecordset` Klasse `DoFieldExchange` außer Kraft setzen.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parameter

*nFieldType*<br/>
Der Wert der **Enum FieldType**, deklariert in `CDaoFieldExchange`, dies kann eine der folgenden sein:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Hinweise

Klassen-Assistent werden in der Regel dieser Aufruf für Sie schreibt. Wenn Sie Ihre eigene schreiben und des Assistenten zum Schreiben verwenden Ihrer `DoFieldExchange` Funktion, Ihre eigene Funktion außerhalb der feldzuordnung zu aufrufen hinzufügen. Wenn Sie den Assistenten nicht verwenden, wird es keine feldzuordnung. Der Aufruf steht DFX-Funktionen, eine für jedes felddatenelement von Ihrer Klasse aufrufen und identifiziert den Feldtyp als `CDaoFieldExchange::outputColumn`.

Wenn Sie die Recordset-Klasse parametrisieren, sollten Sie DFX-Aufrufe für alle Parameter Datenelemente (außerhalb der feldzuordnung) hinzufügen und vorausgehen diese Aufrufe durch einen Aufruf von `SetFieldType`. Übergeben Sie den Wert `CDaoFieldExchange::param`. (Sie können stattdessen mithilfe einer [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) und legen Sie die Werte der Parameter.)

Im Allgemeinen muss jede Gruppe von DFX-Funktionsaufrufen Felddatenmember oder Parameterdatenmember zugeordnet durch einen Aufruf von stehen `SetFieldType`. Die *nFieldType* Parameter der einzelnen `SetFieldType` Aufruf identifiziert den Typ der Datenmember, dargestellt durch die Aufrufe der DFX-Funktionen, die Folgen der `SetFieldType` aufrufen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)
