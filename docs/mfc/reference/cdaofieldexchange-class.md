---
title: CDaoFieldExchange Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
dev_langs:
- C++
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4f702f619eb06a11cbbf7ec5be7407d12f7f445
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368728"
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
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Gibt, die ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des aktualisierten Felds.|  
|[CDaoFieldExchange:: SetFieldType](#setfieldtype)|Gibt den Typ des Recordset-Datenmember – Spalten- oder Parameternamen, dargestellt durch alle nachfolgenden Aufrufe von DFX-Funktionen bis zum nächsten Aufruf von `SetFieldType`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoFieldExchange::](#m_noperation)|Der DFX-Vorgang ausgeführt wird, durch den aktuellen Aufruf an des Recordsets `DoFieldExchange` Memberfunktion.|  
|[CDaoFieldExchange::m_prs](#m_prs)|Ein Zeiger auf das Recordset, für welche, das DFX Vorgänge ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CDaoFieldExchange` eine Basisklasse verfügt nicht über.  
  
 Verwenden Sie diese Klasse, wenn Sie Daten Exchange Routinen für benutzerdefinierte Datentypen schreiben; Andernfalls werden Sie diese Klasse nicht direkt verwendet. DFX tauscht Daten zwischen den Felddatenmembern eines Ihrer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt und den entsprechenden Feldern des aktuellen Datensatzes in der Datenquelle. DFX verwaltet den Austausch in beide Richtungen weisenden Pfeilen, aus der Datenquelle und mit der Datenquelle. Finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) Informationen zum Schreiben von benutzerdefinierten DFX-Routinen.  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC. Die DAO-basierten Klassen können Daten, einschließlich der ODBC-Treiber, über eigene Datenbankmodul zugreifen. Außerdem unterstützen (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Hinzufügen von Tabellen über die Klassen anstatt DAO selbst aufrufen.  
  
> [!NOTE]
>  DAO-Datensatzfeldaustausch (DFX) ähnelt stark Datensatzfeldaustausch (RFX) in den ODBC-basierten MFC-Datenbankklassen ( `CDatabase`, `CRecordset`). Wenn Sie RFX verstanden haben, werden Sie es einfach zu verwendende DFX gefunden.  
  
 Ein `CDaoFieldExchange` -Objekt stellt die Kontextinformationen erforderlich für DAO Datensatzfeldaustausch stattfinden. `CDaoFieldExchange` Objekte unterstützen eine Reihe von Vorgängen, einschließlich Bindungsparameter und Felddatenmember und Festlegen von verschiedenen Flags für die Felder des aktuellen Datensatzes. Recordset-Klasse Datenmember von definierten Typen DFX-Vorgänge ausgeführt werden die `enum` **FieldType** in `CDaoFieldExchange`. Mögliche **FieldType** Werte sind:  
  
- **CDaoFieldExchange::outputColumn** für Felddatenmember.  
  
- **CDaoFieldExchange::param** für Parameterdatenmember.  
  
 Die [IsValidOperation](#isvalidoperation) Member-Funktion wird zum Schreiben von eigenen benutzerdefinierten DFX-Routinen bereitgestellt. Verwenden Sie [SetFieldType](#setfieldtype) häufig in Ihre [CDaoRecordset:: DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktionen. Ausführliche Informationen zu den globalen DFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Informationen über das Schreiben von benutzerdefinierten DFX-Routinen für Ihre eigenen Datentypen finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation  
 Wenn Sie Ihre eigene DFX-Funktion schreiben, rufen Sie `IsValidOperation` am Anfang der Funktion, um zu bestimmen, ob der aktuelle Vorgang für ein bestimmtes Feld-Member-Datentyp ausgeführt werden kann (eine **CDaoFieldExchange::outputColumn** oder ein **CDaoFieldExchange::param**).  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Vorgang für den Typ des aktualisierten Felds geeignet ist.  
  
### <a name="remarks"></a>Hinweise  
 Einige der Vorgänge ausgeführt werden, mithilfe des Mechanismus DFX gelten nur für eine der möglichen Feldtypen. Führen Sie das Modell der vorhandenen DFX-Funktionen.  
  
 Weitere Informationen zum Schreiben von benutzerdefinierten DFX-Routinen finden Sie unter [technischen Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
##  <a name="m_noperation"></a>  CDaoFieldExchange::  
 Identifiziert den Vorgang zu validierenden der [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, das mit dem Feld Exchange-Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Die `CDaoFieldExchange` Objekt stellt den Kontext für eine Reihe von verschiedenen DFX-Vorgänge für das Recordset.  
  
> [!NOTE]
>  Die **PSEUDONULL** unter den nachfolgenden Vorgänge MarkForAddNew und SetFieldNull beschrieben ist ein Wert verwendet, um Felder Null zu markieren. In den Austauschmechanismus für DAO-Datensatzfeldaustausch (DFX) verwendet diesen Wert, um zu bestimmen, welche Felder Null explizit markiert wurden. **PSEUDONULL** ist nicht erforderlich für [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) und [COleCurrency](../../mfc/reference/colecurrency-class.md) Felder.  
  
 Mögliche Werte für **M_nOperation** sind:  
  
|Vorgang|Beschreibung|  
|---------------|-----------------|  
|**AddToParameterList**|Erstellt die **Parameter** -Klausel der SQL-Anweisung.|  
|**AddToSelectList**|Erstellt die **wählen** -Klausel der SQL-Anweisung.|  
|**BindField**|Bindet ein Feld in der Datenbank auf einen Speicherbereich in der Anwendung an.|  
|**BindParam**|Legt die Parameterwerte für die Abfrage des Recordsets.|  
|**Fixup**|Legt fest, die Null-Status für ein Feld.|  
|**AllocCache**|Ordnet den Cache verwendet, um die Prüfung auf "unsaubere" Felder im Recordset.|  
|**StoreField**|Speichert den aktuellen Datensatz in den Cache.|  
|**LoadField**|Stellt die zwischengespeicherten Daten Membervariablen im Recordset.|  
|**FreeCache**|Gibt den Cache verwendet, um die Prüfung auf "unsaubere" Felder im Recordset frei.|  
|`SetFieldNull`|Legt ein Feld Status Null und Wert **PSEUDONULL**.|  
|**MarkForAddNew**|Felder "unsaubere" markiert, ist dies nicht der **PSEUDONULL**.|  
|**MarkForEdit**|Kennzeichnet Felder "unsaubere", wenn sie den Cache nicht übereinstimmen.|  
|**SetDirtyField**|Legt Feldwerte markiert als "fehlerhaft".|  
|**DumpField**|Gibt ein Feld Inhalt (nur Debug).|  
|**MaxDFXOperation**|Zur Überprüfung der Eingabe verwendet.|  
  
##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs  
 Enthält einen Zeiger auf die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugeordnete Objekt der `CDaoFieldExchange` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfieldtype"></a>  CDaoFieldExchange:: SetFieldType  
 Rufen Sie `SetFieldType` in Ihrer `CDaoRecordset` Klasse `DoFieldExchange` außer Kraft setzen.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parameter  
 `nFieldType`  
 Der Wert der **Enum FieldType**, die im deklariert `CDaoFieldExchange`, kann die eines der folgenden sein:  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>Hinweise  
 ClassWizard schreibt in der Regel wird dieser Aufruf, für Sie. Wenn Sie Ihre eigene Funktion zu schreiben und des Assistenten zum Schreiben verwenden Ihrer `DoFieldExchange` -Funktion, die Ihre eigene Funktion außerhalb der feldzuordnung zu aufrufen hinzufügen. Wenn Sie den Assistenten nicht verwenden, ist es keine feldzuordnung. Der Aufruf vorausgeht DFX-Funktionen, eine für jedes felddatenelement Ihrer Klasse aufrufen und identifiziert den Feldtyp als **CDaoFieldExchange::outputColumn**.  
  
 Wenn Recordset-Klasse zu parametrisieren, Sie sollten DFX-Aufrufe für alle Parameterdatenmember (außerhalb der feldzuordnung) hinzufügen und diese Aufrufe mit einem Aufruf von vorausgehen `SetFieldType`. Übergeben Sie den Wert **CDaoFieldExchange::param**. (Sie können stattdessen mithilfe einer [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) und legen Sie die Parameterwerte.)  
  
 Im Allgemeinen muss jede Gruppe von zugeordneten Felddatenmember oder Parameterdatenmember DFX-Funktionsaufrufe durch einen Aufruf von stehen `SetFieldType`. Die `nFieldType` Parameter jeder `SetFieldType` Aufruf identifiziert den Typ der Datenmember, dargestellt durch Aufrufe der DFX-Funktionen, die Folgen der `SetFieldType` aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)
