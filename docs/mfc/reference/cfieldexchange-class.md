---
title: CDBException Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- enum FieldType, CFieldExchange
- RFX (record field exchange) [C++]
- RFX (record field exchange) [C++], classes for
- CFieldExchange class
- FieldType enumeration
- data types [C++], custom
- enum FieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 948f13dc54fcd83941bab8e63b2ab2704d84cb87
ms.lasthandoff: 02/24/2017

---
# <a name="cfieldexchange-class"></a>CDBException-Klasse
Unterstützt die von den Datenbankklassen verwendeten Routinen für den Datensatzfeldaustausch (Record Field Exchange, RFX) und den Massen-Datensatzfeldaustausch (Bulk-RFX).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Gibt einen Wert ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des Felds aktualisiert wird.|  
|[CFieldExchange::](#setfieldtype)|Gibt den Typ des Recordset-Datenmember-Spalte oder des Parameters – dargestellt durch alle folgenden Aufrufe RFX-Funktionen bis zum nächsten Aufruf von `SetFieldType`.|  
  
## <a name="remarks"></a>Hinweise  
 `CFieldExchange`eine Basisklasse keinen.  
  
 Verwenden Sie diese Klasse, wenn Sie Daten Exchange Routinen schreiben, für benutzerdefinierte Datentypen oder wenn Sie implementieren gesammelte; Andernfalls werden Sie diese Klasse nicht direkt verwendet. RFX und Sammel-RFX tauscht Daten zwischen den Felddatenmembern des Recordset-Objekts und die entsprechenden Felder des aktuellen Datensatzes in der Datenquelle.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Programming Overview: Datenbank](../../data/data-access-programming-mfc-atl.md).  
  
 Ein `CFieldExchange` Objekt enthält Kontextinformationen benötigt Datensatzfeldaustausch oder Massen-Datensatzfeldaustausch auszuführende platzieren. `CFieldExchange`Objekte unterstützen eine Reihe von Vorgängen, einschließlich Bindungsparameter Felddatenmember und verschiedene-Flags für die Felder des aktuellen Datensatzes festlegen. RFX und Sammel-RFX-Vorgänge für Recordset-Klasse Datenmember von Typen definiert durch die `enum` **FieldType** in `CFieldExchange`. Mögliche **FieldType** Werte sind:  
  
- **CFieldExchange::outputColumn** Felddatenmember.  
  
- **CFieldExchange::inputParam** oder **CFieldExchange::param** für Eingabeparameter-Datenmember.  
  
- **CFieldExchange::outputParam** für Parameterdatenmember Ausgabe.  
  
- **CFieldExchange::inoutParam** für Eingabe-/Ausgabeparameter-Datenmember.  
  
 Die meisten Member und Datenmember der Klasse für Ihre eigenen benutzerdefinierten RFX-Routinen schreiben bereitgestellt. Verwenden Sie `SetFieldType` häufig. Weitere Informationen finden Sie in den Artikeln [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md) und [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Ausführliche Informationen zu den globalen RFX und Sammel-RFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md) im Abschnitt MFC-Makros und globale Variablen des Verweises.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CFieldExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 Wenn Sie eigene RFX-Funktion zu schreiben, rufen Sie `IsFieldType` am Anfang der Funktion zu bestimmen, ob der aktuelle Vorgang auf einem bestimmten Feld oder Parameter Member Datentyp ausgeführt werden kann (eine **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, oder **CFieldExchange::inoutParam**).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Parameter  
 *pnField*  
 In diesem Parameter wird die laufende Nummer des Datenmembers Feld oder Parameter zurückgegeben. Dies entspricht den Datenmember-Reihenfolge, in der [CRecordset:: DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Vorgang für den aktuellen Typ Feld oder Parameter durchgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Befolgen Sie die vorhandenen RFX-Funktionen.  
  
##  <a name="setfieldtype"></a>CFieldExchange::  
 Sie benötigen einen Aufruf von `SetFieldType` in der Recordset-Klasse [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) außer Kraft setzen.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parameter  
 `nFieldType`  
 Der Wert der **Enum FieldType**, deklariert in `CFieldExchange`, dies kann einer der folgenden sein:  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Hinweise  
 Felddatenmember, rufen Sie `SetFieldType` mit einem Parameter des **CFieldExchange::outputColumn**, gefolgt von RFX oder Bulk-RFX-Funktionen. Wenn Sie haben nicht die gesammelte implementiert und Klassen-Assistent Dies legt `SetFieldType` rufen Sie im Feld Map-Abschnitt der `DoFieldExchange`.  
  
 Wenn Sie die Recordset-Klasse zu parametrisieren, müssen Sie aufrufen `SetFieldType` erneut, außerhalb jeder Karte Feldabschnitt, gefolgt von RFX-Aufrufe für alle Parameterdatenmember. Jede Art von Parameterdatenmember benötigen Sie einen eigenen `SetFieldType` aufrufen. In der folgenden Tabelle unterscheidet, die anderen Werte können Sie übergeben `SetFieldType` Parameterdatenmember der Klasse dargestellt:  
  
|SetFieldType Parameterwert|Typ der Parameter-Datenmember|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Der Eingabeparameter. Ein Wert, der in der Recordsets Abfrage oder gespeicherte Prozedur übergeben wird.|  
|**CFieldExchange::param**|Identisch mit **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Output-Parameter. Ein Rückgabewert einer gespeicherten Prozedur des Recordsets.|  
|**CFieldExchange::inoutParam**|Eingabe-/Ausgabeparameter. Ein Wert, der übergeben und aus dem Recordset gespeicherten Prozedur zurückgegeben wird.|  
  
 Im Allgemeinen muss jede Gruppe von zugeordneten Felddatenmember oder Parameterdatenmember RFX-Funktionsaufrufe durch einen Aufruf von stehen `SetFieldType`. Die `nFieldType` Parameter der einzelnen `SetFieldType` Aufruf gibt den Typ der Datenmember dargestellte RFX-Funktionsaufrufe, die Folgen der `SetFieldType` aufrufen.  
  
 Weitere Informationen zur Behandlung von Ausgabe und Eingabe/Ausgabe-Parameter finden Sie unter der `CRecordset` Memberfunktion [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Weitere Informationen über RFX und Sammel-RFX-Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt mehrere Aufrufe RFX-Funktionen mit Aufrufen von `SetFieldType`. Beachten Sie, dass `SetFieldType` wird aufgerufen, durch die `pFX` Zeiger auf ein `CFieldExchange` Objekt.  
  
 [!code-cpp[NVC_MFCDatabase&33;](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)

