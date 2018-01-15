---
title: CDBException Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs: C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d20a89e48475a0226d76ac719459b1b99cc4e355
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cfieldexchange-class"></a>CDBException-Klasse
Unterstützt die von den Datenbankklassen verwendeten Routinen für den Datensatzfeldaustausch (Record Field Exchange, RFX) und den Massen-Datensatzfeldaustausch (Bulk-RFX).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Gibt, die ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des aktualisierten Felds.|  
|[CFieldExchange::](#setfieldtype)|Gibt den Typ des Recordset-Datenmember – Spalten- oder Parameter – alle folgenden Aufrufen der RFX-Funktionen dargestellt, bis zum nächsten Aufruf von `SetFieldType`.|  
  
## <a name="remarks"></a>Hinweise  
 `CFieldExchange`eine Basisklasse verfügt nicht über.  
  
 Verwenden Sie diese Klasse, wenn Sie Daten Exchange Routinen schreiben, für die benutzerdefinierten Datentypen oder wenn Sie implementieren gesammelte; Andernfalls werden Sie diese Klasse nicht direkt verwendet. RFX und Bulk-RFX tauscht Daten zwischen den Felddatenmembern eines Recordset-Objekt und den entsprechenden Feldern des aktuellen Datensatzes für die Datenquelle ein.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Ein `CFieldExchange` -Objekt stellt die Kontextinformationen benötigt für den Datensatzfeldaustausch oder Massen-Datensatzfeldaustausch auszuführenden platzieren. `CFieldExchange`Objekte unterstützen eine Reihe von Vorgängen, einschließlich Bindungsparameter und Felddatenmember und Festlegen von verschiedenen Flags für die Felder des aktuellen Datensatzes. Recordset-Klasse Datenmember von definierten Typen RFX und Bulk-RFX-Vorgänge ausgeführt werden die `enum` **FieldType** in `CFieldExchange`. Mögliche **FieldType** Werte sind:  
  
- **CFieldExchange::outputColumn** für Felddatenmember.  
  
- **CFieldExchange::inputParam** oder **CFieldExchange::param** für Eingabeparameter Datenelemente.  
  
- **CFieldExchange::outputParam** für Parameterdatenmember Ausgabe.  
  
- **CFieldExchange::inoutParam** für Datenelemente Eingabe-/Ausgabeparameter.  
  
 Die meisten Member Funktionen und Datenmember der Klasse werden für das Schreiben von eigenen benutzerdefinierten RFX-Routinen bereitgestellt. Verwenden Sie `SetFieldType` häufig. Weitere Informationen finden Sie in den Artikeln [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md) und [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Informationen über das gesammelte, finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Ausführliche Informationen zu den globalen RFX und Bulk-RFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md) im MFC-Makros und Globals Abschnitt des Verweises.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CFieldExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 Wenn Sie Ihre eigene RFX-Funktion schreiben, rufen Sie `IsFieldType` am Anfang der Funktion, um zu bestimmen, ob der aktuelle Vorgang auf einem bestimmten Feld oder einen Parameter Member Datentyp ausgeführt werden kann (eine **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, oder **CFieldExchange::inoutParam** ).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Parameter  
 *pnField*  
 In diesem Parameter wird die laufende Nummer des Datenmembers Feld oder einen Parameter zurückgegeben. Dies entspricht den Datenmember-Reihenfolge, in der [CRecordset:: DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Vorgang für den aktuellen Typ von Feld oder einen Parameter ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie das Modell von der vorhandenen RFX-Funktionen.  
  
##  <a name="setfieldtype"></a>CFieldExchange::  
 Sie benötigen einen Aufruf von `SetFieldType` in der Recordset-Klasse [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) außer Kraft setzen.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parameter  
 `nFieldType`  
 Der Wert der **Enum FieldType**, die im deklariert `CFieldExchange`, können die eines der folgenden sein:  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Hinweise  
 Felddatenmember, rufen Sie `SetFieldType` mit einem Parameter des **CFieldExchange::outputColumn**, gefolgt von Aufrufen an die RFX- oder der Bulk-RFX-Funktionen. Wenn Sie nicht massenzeilenabruf implementiert haben, ClassWizard setzt dies `SetFieldType` rufen Sie im Feldabschnitt der Karte `DoFieldExchange`.  
  
 Wenn Sie die Recordset-Klasse zu parametrisieren, müssen Sie aufrufen `SetFieldType` erneut außerhalb der Zuordnung alle Feldabschnitt gefolgt von RFX-Aufrufe für alle Parameterdatenmember. Jeder Typ des Parameters-Datenmember benötigt einen eigenen `SetFieldType` aufrufen. In der folgenden Tabelle unterscheidet, die anderen Werte können Sie übergeben `SetFieldType` zur Darstellung der Parameter-Datenmember der Klasse:  
  
|SetFieldType Parameterwert|Typ der Parameter-Datenmember|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Input-Parameters. Ein Wert, der an des Recordsets Abfrage oder gespeicherte Prozedur übergeben wird.|  
|**CFieldExchange::param**|Identisch mit **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Output-Parameter. Ein Rückgabewert einer gespeicherten Prozedur das Recordset.|  
|**CFieldExchange::inoutParam**|Eingabe-/Ausgabeparameter. Ein Wert, der an übergeben und von einer gespeicherten Prozedur das Recordset zurückgegeben.|  
  
 Im Allgemeinen muss jede Gruppe von RFX-Funktionsaufrufe Felddatenmember oder Parameterdatenmember zugeordnet vorangestellt werden, durch einen Aufruf von `SetFieldType`. Die `nFieldType` Parameter jeder `SetFieldType` Aufruf gibt den Typ der Datenmember, dargestellt durch die RFX-Funktionsaufrufe, die Folgen der `SetFieldType` aufrufen.  
  
 Weitere Informationen zur Behandlung von Ausgabe und Eingabe/Ausgabe-Parameter finden Sie unter der `CRecordset` Memberfunktion [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Weitere Informationen zu den RFX und Bulk-RFX-Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe RFX-Funktionen mit zugehörigen Aufrufe `SetFieldType`. Beachten Sie, dass `SetFieldType` aufgerufen wird, über die `pFX` Zeiger auf eine `CFieldExchange` Objekt.  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
