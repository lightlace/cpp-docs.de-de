---
title: Klasse CDaoFieldExchange | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- DAO (Data Access Objects), record field exchange (DFX)
- field exchange
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- field exchange, record for DAO classes
- exchanging data between databases and recordsets
- DFX (DAO record field exchange), DAO Record Field Exchange
- RFX (record field exchange)
- CDaoFieldExchange class
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 31b7121f8e93f85ed73b5d095ac0995f3ddee721
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange-Klasse
Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Gibt einen Wert ungleich NULL, wenn der aktuelle Vorgang ist geeignet für den Typ des Felds aktualisiert wird.|  
|[CDaoFieldExchange:: SetFieldType](#setfieldtype)|Gibt den Typ des Recordset-Datenmember – Spalten- oder Parameternamen, dargestellt durch alle nachfolgenden Aufrufe von DFX-Funktionen bis zum nächsten Aufruf von `SetFieldType`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoFieldExchange::](#m_noperation)|Der DFX-Vorgang ausgeführt wird, durch den aktuellen Aufruf an des Recordsets `DoFieldExchange` Member-Funktion.|  
|[CDaoFieldExchange::m_prs](#m_prs)|Ein Zeiger auf das Recordset für die, das DFX Vorgänge ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CDaoFieldExchange`eine Basisklasse keinen.  
  
 Verwenden Sie diese Klasse, wenn Sie für benutzerdefinierte Datentypen Data Exchange Routinen schreiben; Andernfalls werden Sie diese Klasse nicht direkt verwendet. DFX tauscht Daten zwischen den Felddatenmembern Ihre [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt und die entsprechenden Felder des aktuellen Datensatzes in der Datenquelle. DFX verwaltet den Austausch in beide Richtungen an, aus der Datenquelle und mit der Datenquelle. Finden Sie unter [Technische Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) Informationen über das benutzerdefinierte DFX-Routinen schreiben.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können immer noch Zugriff auf ODBC-Datenquellen mit DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die ODBC-basierten MFC-Klassen. DAO-basierte Klassen können Daten, einschließlich der über ODBC-Treiber, über ihre eigenen Datenbank-Engine zugreifen. Sie unterstützen auch Vorgänge (Data Definition Language, Datendefinitionssprache), z. B. das Hinzufügen von Tabellen über die Klassen, anstatt die DAO selbst aufrufen.  
  
> [!NOTE]
>  DAO-Datensatzfeldaustausch (DFX) ähnelt dem Datensatzfeldaustausch (RFX) in den ODBC-basierten MFC-Datenbankklassen ( `CDatabase`, `CRecordset`). Wenn Sie RFX kennen, können Sie benutzerfreundliche DFX finden.  
  
 Ein `CDaoFieldExchange` Objekt enthält die Kontextinformationen erforderlich für-DAO-Datensatzfeldaustausch stattfinden soll. `CDaoFieldExchange`Objekte unterstützen eine Reihe von Vorgängen, einschließlich Bindungsparameter Felddatenmember und verschiedene-Flags für die Felder des aktuellen Datensatzes festlegen. DFX-Vorgänge für Recordset-Klasse Datenmember von Typen definiert durch die `enum` **FieldType** in `CDaoFieldExchange`. Mögliche **FieldType** Werte sind:  
  
- **CDaoFieldExchange::outputColumn** Felddatenmember.  
  
- **CDaoFieldExchange::param** für Parameterdatenmember.  
  
 Die [IsValidOperation](#isvalidoperation) Memberfunktion zum Schreiben eigene benutzerdefinierten DFX-Routinen zur Verfügung. Verwenden Sie [SetFieldType](#setfieldtype) häufig in Ihrer [CDaoRecordset:: DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktionen. Ausführliche Informationen zu den globalen DFX-Funktionen finden Sie unter [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md). Informationen über das Schreiben von benutzerdefinierten DFX-Routinen für Ihre eigenen Datentypen finden Sie unter [Technische Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation  
 Wenn Sie eigene DFX-Funktion zu schreiben, rufen Sie `IsValidOperation` am Anfang der Funktion zu bestimmen, ob der aktuelle Vorgang für ein bestimmtes Feld Member Datentyp ausgeführt werden kann (eine **CDaoFieldExchange::outputColumn** oder **CDaoFieldExchange::param**).  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Vorgang für den Typ des aktualisierten Felds ist.  
  
### <a name="remarks"></a>Hinweise  
 Einige der Vorgänge ausgeführt, indem der DFX-Mechanismus gelten nur für eines der möglichen Feldtypen. Befolgen Sie die vorhandenen DFX-Funktionen.  
  
 Weitere Informationen über benutzerdefinierte DFX-Routinen schreiben, finden Sie unter [Technische Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
##  <a name="m_noperation"></a>CDaoFieldExchange::  
 Identifiziert den Vorgang werden die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, das mit dem Feld Exchange-Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Das `CDaoFieldExchange` Objekt liefert den Kontext für eine Reihe von verschiedenen DFX-Operationen für das Recordset.  
  
> [!NOTE]
>  Die **PSEUDONULL** unter MarkForAddNew und SetFieldNull Vorgänge, die weiter unten beschrieben ist ein Wert verwendet, um Felder Null zu markieren. Die DAO-Datensatzfeldaustausch-Mechanismus (DFX) verwendet diesen Wert, um zu bestimmen, welche Felder Null explizit markiert wurden. **PSEUDONULL** ist nicht erforderlich für [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) und [COleCurrency](../../mfc/reference/colecurrency-class.md) Felder.  
  
 Mögliche Werte für **M_nOperation** sind:  
  
|Vorgang|Beschreibung|  
|---------------|-----------------|  
|**AddToParameterList**|Erstellt die **Parameter** -Klausel der SQL-Anweisung.|  
|**AddToSelectList**|Erstellt die **wählen** -Klausel der SQL-Anweisung.|  
|**BindField**|Bindet ein Feld in der Datenbank auf einen Speicherbereich in Ihrer Anwendung.|  
|**BindParam**|Legt die Parameterwerte für die Abfrage des Recordsets.|  
|**Fixup**|Der Null-Status für ein Feld festgelegt.|  
|**AllocCache**|Ordnet den Cache verwendet "unsaubere" Felder im Recordset überprüfen.|  
|**StoreField**|Speichert den aktuellen Datensatz im Cache.|  
|**LoadField**|Stellt die zwischengespeicherten Daten Membervariablen im Recordset.|  
|**FreeCache**|Gibt den Cache "unsaubere" Felder im Recordset geprüft wird, frei.|  
|`SetFieldNull`|Legt ein Feld Status auf Null und der Wert auf **PSEUDONULL**.|  
|**MarkForAddNew**|Felder "fehlerhaft" markiert, wenn nicht **PSEUDONULL**.|  
|**MarkForEdit**|Kennzeichnet Felder "unsaubere", wenn sie den Cache nicht übereinstimmen.|  
|**SetDirtyField**|Legt Feldwerte, die als "geändert".|  
|**DumpField**|Gibt ein Feld Inhalt (nur Debug).|  
|**MaxDFXOperation**|Zum Überprüfen von Eingabe verwendet.|  
  
##  <a name="m_prs"></a>CDaoFieldExchange::m_prs  
 Enthält einen Zeiger auf die [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugeordnete Objekt der `CDaoFieldExchange` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setfieldtype"></a>CDaoFieldExchange:: SetFieldType  
 Rufen Sie `SetFieldType` in Ihrer `CDaoRecordset` -Klasse `DoFieldExchange` außer Kraft setzen.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parameter  
 `nFieldType`  
 Der Wert der **Enum FieldType**, deklariert in `CDaoFieldExchange`, dies kann eine der folgenden sein:  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>Hinweise  
 In der Regel schreibt ClassWizard dieser Aufruf für Sie. Wenn Sie Ihre eigene schreiben und des Assistenten zum Schreiben mithilfe werden der `DoFieldExchange` Funktion, eine eigene Funktion außerhalb der Zuordnung zu aufrufen hinzufügen. Wenn Sie den Assistenten nicht verwenden, werden es eine Zuordnung. Der Aufruf vorausgeht DFX-Funktionen, eine für jeden Felddatenmember Ihrer Klasse aufrufen und identifiziert den Feldtyp als **CDaoFieldExchange::outputColumn**.  
  
 Recordset-Klasse zu parametrisieren, Sie DFX-Aufrufe für alle Parameterdatenmember (außerhalb der Zuordnung) hinzufügen und diese Aufrufe mit einem Aufruf von vorausgehen `SetFieldType`. Übergeben Sie den Wert **CDaoFieldExchange::param**. (Sie können stattdessen mithilfe einer [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) , und legen Sie die Werte der Parameter.)  
  
 Im Allgemeinen muss jede Gruppe von DFX-Funktionsaufrufe Felddatenmember oder Parameterdatenmember zugeordnet vorangestellt werden, durch einen Aufruf von `SetFieldType`. Die `nFieldType` Parameter der einzelnen `SetFieldType` Aufruf identifiziert den Typ der Datenmember, dargestellt durch die DFX-Funktionsaufrufe, die Folgen der `SetFieldType` aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)

