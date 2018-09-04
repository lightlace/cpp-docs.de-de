---
title: CFieldExchange-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76167793f7252540dbe9feedbb2d83678ebdcacb
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688385"
---
# <a name="cfieldexchange-class"></a>CFieldExchange-Klasse
Unterstützt die von den Datenbankklassen verwendeten Routinen für den Datensatzfeldaustausch (Record Field Exchange, RFX) und den Massen-Datensatzfeldaustausch (Bulk-RFX).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Gibt zurück, die ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des aktualisierten Felds.|  
|[CFieldExchange::](#setfieldtype)|Gibt den Typ des Recordset-Datenmember, Spalte oder des Parameters – durch alle folgenden Aufrufe von RFX-Funktionen dargestellt wird, bis der nächste Aufruf von `SetFieldType`.|  
  
## <a name="remarks"></a>Hinweise  
 `CFieldExchange` eine Basisklasse keinen.  
  
 Verwenden Sie diese Klasse, wenn Sie Data Exchange-Routinen schreiben, für die benutzerdefinierten Datentypen oder wenn Sie die gesammelte implementiert werden; Andernfalls werden Sie diese Klasse nicht direkt verwendet. RFX und Bulk-RFX-Datenaustausch zwischen den Felddatenmembern eines Recordset-Objekts und den entsprechenden Feldern des aktuellen Datensatzes in der Datenquelle.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt mit der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Programming Overview: Datenbank](../../data/data-access-programming-mfc-atl.md).  
  
 Ein `CFieldExchange` Objekt stellt die Kontextinformationen benötigt für den Datensatzfeldaustausch oder massenaustausch zu platzieren. `CFieldExchange` Objekte unterstützen eine Anzahl von Vorgängen, einschließlich Bindungsparameter und Felddatenmember und Festlegen von verschiedenen Flags für die Felder des aktuellen Datensatzes an. RFX und Bulk-RFX-Vorgänge für Recordset-Klasse-Datenmember von Typen, die von definiert die **Enum** **FieldType** in `CFieldExchange`. Mögliche **FieldType** Werte sind:  
  
- `CFieldExchange::outputColumn` für den Felddatenmembern.  
  
- `CFieldExchange::inputParam` oder `CFieldExchange::param` für Datenelemente der input-Parameters.  
  
- `CFieldExchange::outputParam` für die Datenelemente der Ausgabe-Parameter.  
  
- `CFieldExchange::inoutParam` für die Datenelemente der Eingabe-/Ausgabeparameter.  
  
 Die meisten Member Funktionen und Datenmember der Klasse werden für Ihre eigenen benutzerdefinierten RFX-Routinen schreiben bereitgestellt. Verwenden Sie `SetFieldType` häufig. Weitere Informationen finden Sie in den Artikeln [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md) und [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md). Informationen zu gesammelten Abrufens von Zeilen, finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen zu den globalen RFX und Bulk-RFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md) im MFC-Makros und Globals Abschnitt des Verweises.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CFieldExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="isfieldtype"></a>  CFieldExchange::IsFieldType  
 Wenn Sie Ihre eigene RFX-Funktion schreiben, rufen Sie `IsFieldType` am Anfang der Funktion zu bestimmen, ob der aktuelle Vorgang für ein bestimmtes Feld oder Parameter datenmembertyp ausgeführt werden kann (ein `CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, oder `CFieldExchange::inoutParam`).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Parameter  
 *pnField*  
 Die fortlaufende Nummer des Datenmembers Felds oder Parameters wird in diesem Parameter zurückgegeben. Dies entspricht den Datenmember-Reihenfolge, in der [CRecordset:: DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn der aktuelle Vorgang für den aktuellen Felds oder Parameters Typ ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie das Modell für die vorhandenen RFX-Funktionen.  
  
##  <a name="setfieldtype"></a>  CFieldExchange::  
 Sie benötigen einen Aufruf von `SetFieldType` in der Recordset-Klasse [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) außer Kraft setzen.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parameter  
 *nFieldType*  
 Der Wert der `enum FieldType`, deklariert in `CFieldExchange`, stehen die folgenden:  
  
- `CFieldExchange::outputColumn`  
  
- `CFieldExchange::inputParam`  
  
- `CFieldExchange::param`  
  
- `CFieldExchange::outputParam`  
  
- `CFieldExchange::inoutParam`  
  
### <a name="remarks"></a>Hinweise  
 Felddatenmember, müssen Sie aufrufen `SetFieldType` mit dem Parameter `CFieldExchange::outputColumn`, gefolgt von Aufrufen an die RFX- oder der Bulk-RFX-Funktionen. Wenn Sie nicht massenzeilenabruf implementiert haben, wird dies Klassen-Assistent sorgt `SetFieldType` rufen Sie im Feldabschnitt der Karte `DoFieldExchange`.  
  
 Wenn Sie die Recordset-Klasse parametrisieren, müssen Sie aufrufen `SetFieldType` erneut, außerhalb jeder Kartenbereich Feld, gefolgt von RFX-Aufrufe für alle Parameterdatenmember. Jeder Typ von Parameter-Datenmember muss eine eigene verfügen `SetFieldType` aufrufen. In der folgende Tabelle unterscheidet, die verschiedenen Werte, die Sie an übergeben können `SetFieldType` zur Darstellung der Parameter-Datenmember der Klasse:  
  
|Parameterwert SetFieldType|Typ der Parameter-Datenmember|  
|----------------------------------|-----------------------------------|  
|`CFieldExchange::inputParam`|Input-Parameters. Ein Wert, der in der Recordsets Abfrage oder gespeicherte Prozedur übergeben wird.|  
|`CFieldExchange::param` | Identisch mit `CFieldExchange::inputParam`.|  
|`CFieldExchange::outputParam`|Output-Parameter. Ein Rückgabewert der gespeicherten Prozedur des Recordsets.|  
|`CFieldExchange::inoutParam`|Eingabe-/Ausgabeparameter. Ein Wert, der übergeben wird, in und aus dem Recordset gespeicherten Prozedur zurückgegeben.|  
  
 Im Allgemeinen muss jede Gruppe von Felddatenmember oder Parameterdatenmember zugeordneten RFX-Funktionsaufrufe durch einen Aufruf von stehen `SetFieldType`. Die *nFieldType* Parameter der einzelnen `SetFieldType` Aufruf gibt den Typ der Datenmember verhältnisschwellenwert RFX-Funktionsaufrufe, die Folgen der `SetFieldType` aufrufen.  
  
 Weitere Informationen zum Behandeln von Ausgabe und Eingabe/Ausgabe-Parameter finden Sie unter den `CRecordset` Memberfunktion [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Weitere Informationen zu den RFX und Bulk-RFX-Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe RFX-Funktionen mit zugehörigen Aufrufe `SetFieldType`. Beachten Sie, dass `SetFieldType` aufgerufen wird, über die `pFX` Zeiger auf eine `CFieldExchange` Objekt.  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
