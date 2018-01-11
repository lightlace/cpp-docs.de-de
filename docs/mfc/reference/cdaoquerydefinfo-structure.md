---
title: CDaoQueryDefInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoQueryDefInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e476fd8e95b48b59bbb3bae41d9ad84829ca8fa9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo-Struktur
Die `CDaoQueryDefInfo` Struktur enthält Informationen zu einem Querydef-Objekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoQueryDefInfo  
{  
    CString m_strName;               // Primary  
    short m_nType;   // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    BOOL m_bUpdatable;               // Secondary  
    BOOL m_bReturnsRecords;          // Secondary  
    CString m_strSQL;                // All  
    CString m_strConnect;            // All  
    short m_nODBCTimeout;            // All  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Eindeutig benennt das Querydef-Objekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe. Rufen Sie [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) diese Eigenschaft direkt abgerufen.  
  
 `m_nType`  
 Ein Wert, der die operative Typ eines Objekts Querydef angibt. Der Wert kann in folgenden Formen vorliegen:  
  
- **DbQSelect** auswählen – die Abfrage wählt Datensätze.  
  
- **DbQAction** Aktion, die Abfrage verschiebt, oder Daten geändert, jedoch keine Datensätze zurückgibt.  
  
- **DbQCrosstab** Kreuztabelle – die Abfrage gibt Daten in eine Kalkulationstabelle-ähnlichen Format zurück.  
  
- **DbQDelete** löschen – die Abfrage wird einen Satz von angegebenen Zeilen gelöscht.  
  
- **DbQUpdate** Update – die Abfrage ändert sich, eine Gruppe von Datensätzen.  
  
- **DbQAppend** anfügen, die Abfrage fügt neue Datensätze am Ende einer Tabelle oder Abfrage.  
  
- **DbQMakeTable** Tabellenerstellungsabfrage – die Abfrage erstellt eine neue Tabelle aus einem Recordset.  
  
- **DbQDDL** Datendefinition – die Abfrage wirkt sich auf die Struktur der Tabellen oder deren Bestandteile.  
  
- **DbQSQLPassThrough** Pass-Through – die SQL-Anweisung wird direkt an die Datenbank-Back-End, ohne intermediate Verarbeitung übergeben.  
  
- **DbQSetOperation** Union – die Abfrage erstellt eine Momentaufnahme-Type-Recordset-Objekt, das mit Daten aus allen angegebenen Datensätze in zwei oder mehr Tabellen mit doppelte Datensätze entfernt. Um die Duplikate einzuschließen, fügen Sie das Schlüsselwort **alle** in die Querydef SQL-Anweisung.  
  
- **DbQSPTBulk** mit verwendet **DbQSQLPassThrough** eine Abfrage angeben, die keinen Datensätze zurückgibt.  
  
> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die **DbQSQLPassThrough** konstant. Dies wird automatisch vom Microsoft Jet-Datenbankmodul festgelegt, wenn Sie eine Querydef-Objekt erstellen, und legen Sie die Connect-Eigenschaft.  
  
 Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
 `m_dateCreated`  
 Das Datum und Uhrzeit der Erstellung die Querydef. Um direkt das Datum abzurufen Querydef erstellt wurde, rufen Sie die [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion der `CDaoTableDef` Objekt, das mit der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Außerdem finden Sie im Thema "DateCreated LastUpdated-Eigenschaften", DAO-Hilfe zu erhalten.  
  
 `m_dateLastUpdated`  
 Datum und Uhrzeit der letzten Änderung der Querydef. Rufen Sie direkt das Datum der letzten die Tabelle Aktualisierung Aufrufen der [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) Memberfunktion der Querydef. Weitere Informationen finden Sie in der Kommentare unten. Und finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob ein Querydef-Objekt geändert werden kann. Wenn diese Eigenschaft ist **"true"**Querydef andernfalls aktualisierbaren, nicht. Aktualisierbar bedeutet, dass der Querydef Objektdefinition Abfrage geändert werden kann. Die aktualisierbare Eigenschaft eines Querydef-Objekts wird festgelegt, um **"true"** Wenn die Abfragedefinition aktualisiert werden kann, selbst wenn das resultierende Recordset nicht aktualisierbar ist. Um diese Eigenschaft direkt abzurufen, rufen Sie der Querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) Memberfunktion. Weitere Informationen finden Sie im Thema "Aktualisierbare Property" in der DAO-Hilfe.  
  
 *m_bReturnsRecords*  
 Gibt an, ob eine SQL-Pass-Through-Abfrage einer externen Datenbank Datensätze zurückgibt. Wenn diese Eigenschaft ist **"true"**, die Abfrage gibt die Datensätze zurück. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Nicht alle Pass-Through-SQL-Abfragen für externe Datenbanken werden Datensätze zurückgegeben. Z. B. eine SQL **UPDATE** Anweisung Datensätze aktualisiert, ohne Datensätze zurückzugeben, während eine SQL **wählen** Anweisung gibt Datensätze zurück. Weitere Informationen finden Sie im Thema "ReturnsRecords-Eigenschaft" DAO-Hilfe.  
  
 *m_strSQL*  
 Die SQL-Anweisung, die die Abfrage ausgeführt, indem ein Querydef-Objekt definiert. Die SQL-Eigenschaft enthält die SQL-Anweisung, die bestimmt, wie Datensätze ausgewählt, gruppiert und sortiert werden, wenn Sie die Abfrage ausführen. Sie können die Abfrage verwenden, zum Auswählen von Datensätzen in einem Recordset-Objekt vom Typ Dynaset oder Snapshot eingeschlossen werden sollen. Sie können auch die Bulk-Abfragen, um Daten zu ändern, ohne Datensätze zurückzugeben definieren. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen der Querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) Memberfunktion.  
  
 `m_strConnect`  
 Enthält Informationen über die Quelle einer Datenbank in einer Pass-Through-Abfrage verwendet. Diese Informationen hat das Format einer Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen und Informationen direkt das Abrufen des Werts dieser Eigenschaft finden Sie unter der [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Memberfunktion.  
  
 *m_nODBCTimeout*  
 Die Anzahl der Sekunden, die das Microsoft Jet-Datenbankmodul, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Bei Verwendung eine ODBC-Datenbank, z. B. Microsoft SQL Server, können möglicherweise aufgrund Netzwerkverkehrs oder Extreme Nutzung des ODBC-Servers verzögert werden. Anstatt unbegrenzt wartet, können Sie angeben, wie lange das Microsoft Jet-Modul wartet, bevor er einen Fehler erzeugt. Der Standard-Timeoutwert ist 60 Sekunden. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen der Querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) Memberfunktion. Weitere Informationen finden Sie im Thema "Timeoutfehlers warten soll Property" in der DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Querydef ist ein Objekt der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) Memberfunktion in Klasse `CDaoDatabase`.  
  
 Informationen, die abgerufen, indem die [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) Memberfunktion befindet sich in einer `CDaoQueryDefInfo` Struktur. Rufen Sie `GetQueryDefInfo` für das Datenbankobjekt im Element, dessen QueryDefs-Auflistung der Querydef Objekt gespeichert ist. `CDaoQueryDefInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoQueryDefInfo` Objekt. Klasse `CDaoDatabase` auch stellt Memberfunktionen zur direkten Zugriff auf alle Eigenschaften zurückgegeben, die einem `CDaoQueryDefInfo` Objekt, sodass Sie wahrscheinlich nur selten aufrufen, müssen `GetQueryDefInfo`.  
  
 Wenn Sie ein neues Feld oder Parameter-Objekt an die Felder oder Parameter-Auflistung eines Objekts Querydef anfügen, wird eine Ausnahme ausgelöst, wenn die zugrunde liegenden Datenbank für das neue Objekt angegebenen Datentyp nicht unterstützt.  
  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Querydef erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung sollten Benutzer diese Einstellungen erhalten, direkt aus der Datei mithilfe der **net Time** Befehl aus, um abweichungen in den Einstellungen der Eigenschaft DateCreated und LastUpdated zu vermeiden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
