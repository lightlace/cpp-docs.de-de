---
title: CDaoQueryDefInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: 13
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
ms.openlocfilehash: 80e681345091ef54e2be2e3f1c1ea6ccaefd9d17
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo-Struktur
Die `CDaoQueryDefInfo` Struktur enthält Informationen zur Querydef-Objekts für Datenzugriffsobjekte (DAO) definiert.  
  
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
 Das Querydef-Objekt bezeichnet eindeutig. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe. Rufen Sie [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) dieser Eigenschaft direkt abgerufen.  
  
 `m_nType`  
 Ein Wert, der den Betrieb eines Querydef-Objekts angibt. Die folgenden Werte sind möglich:  
  
- **DbQSelect** auswählen, die Abfrage wählt Datensätze.  
  
- **DbQAction** Aktion, die Abfrage verschiebt oder Daten geändert, jedoch keine Datensätze zurückgibt.  
  
- **DbQCrosstab** Kreuztabelle – die Abfrage gibt Daten in einem Tabellenformat zurück.  
  
- **DbQDelete** löschen – Löscht die Abfrage angegebenen Zeilen.  
  
- **DbQUpdate** Update – die Abfrage ändert eine Gruppe von Datensätzen.  
  
- **DbQAppend** anfügen, die Abfrage fügt neue Datensätze am Ende einer Tabelle oder Abfrage.  
  
- **DbQMakeTable** Tabelle, die Abfrage erstellt eine neue Tabelle aus einem Recordset.  
  
- **DbQDDL** Datendefinition: die Abfrage wirkt sich auf die Struktur der Tabellen oder deren Komponenten.  
  
- **DbQSQLPassThrough** Pass-Through – die SQL-Anweisung wird direkt an die Datenbank-Back-End, ohne intermediate Verarbeitung übergeben.  
  
- **DbQSetOperation** Union-Abfrage erstellt eine Momentaufnahme vom Typ-Objekt, das mit Daten aus allen angegebenen Datensätzen in zwei oder mehr Tabellen, wobei doppelte Datensätze entfernt. Um die Duplikate einzuschließen, fügen Sie das Schlüsselwort **alle** in SQL-Anweisung der Querydef.  
  
- **DbQSPTBulk** mit verwendete **DbQSQLPassThrough** zum Angeben einer Abfrage, die keine Datensätze zurückgibt.  
  
> [!NOTE]
>  Um eine SQL-Pass-Through-Abfrage zu erstellen, legen Sie nicht die **DbQSQLPassThrough** konstant. Dies wird automatisch durch das Microsoft Jet-Datenbankmodul festgelegt, wenn Sie ein Querydef-Objekt erstellen, und legen Sie die Connect-Eigenschaft.  
  
 Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
 `m_dateCreated`  
 Das Datum und die Uhrzeit der Erstellung die Querydef. Rufen Sie direkt das Datum die Querydef erstellt wurde, rufen Sie die [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion der `CDaoTableDef` -Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie unter Kommentare. Außerdem finden Sie im Thema "DateCreated LastUpdated-Eigenschaften", DAO-Hilfe.  
  
 `m_dateLastUpdated`  
 Datum und Uhrzeit der letzten Änderung der Querydef. Rufen Sie direkt das Datum in der Tabelle zuletzt aktualisiert wurde, rufen Sie die [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) -Memberfunktion der Querydef. Weitere Informationen finden Sie unter Kommentare. Und finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob ein Querydef-Objekt geändert werden kann. Wenn diese Eigenschaft ist **TRUE**, Querydef aktualisierbar, andernfalls nicht. Aktualisierbar bedeutet, dass die Abfragedefinition für das Querydef-Objekt geändert werden kann. Die Updatable-Eigenschaft eines Querydef-Objekts auf festgelegt ist **TRUE** Wenn die Abfragedefinition aktualisiert werden kann, selbst wenn das resultierende Recordset nicht aktualisierbar ist. Um diese Eigenschaft direkt zu abzurufen, rufen Sie der Querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) Member-Funktion. Weitere Informationen finden Sie unter dem Thema "Aktualisierbare-Eigenschaft" in der DAO-Hilfe.  
  
 *m_bReturnsRecords*  
 Gibt an, ob eine SQL-Pass-Through-Abfrage für eine externe Datenbank Datensätze zurückgibt. Wenn diese Eigenschaft ist **TRUE**, die Abfrage Datensätze zurückgibt. Um diese Eigenschaft direkt abzurufen, rufen Sie [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Nicht alle SQL Pass-Through-Abfragen an externe Datenbanken geben Datensätze zurück. Z. B. eine SQL **UPDATE** Anweisung aktualisiert Datensätze, ohne Datensätze zurückzugeben, während eine SQL **wählen** Anweisung gibt Datensätze zurück. Weitere Informationen finden Sie unter dem Thema "ReturnsRecords-Eigenschaft" in der DAO-Hilfe.  
  
 *m_strSQL*  
 Die SQL-Anweisung, die die Abfrage ausgeführt, indem ein Querydef-Objekt definiert. Die SQL-Eigenschaft enthält die SQL-Anweisung, die bestimmt, wie Datensätze ausgewählt, gruppiert und sortiert werden, wenn Sie die Abfrage ausführen. Sie können die Abfrage verwenden, zum Auswählen von Datensätzen in einem Recordset-Objekt vom Typ Dynaset oder Snapshot aufgenommen. Außerdem können massenabfragen, um Daten zu ändern, ohne Datensätze zurückzugeben. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen der Querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) Member-Funktion.  
  
 `m_strConnect`  
 Enthält Informationen über die Quelle einer Datenbank in einer Pass-Through-Abfrage verwendet. Diese Informationen hat das Format einer Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen und Informationen direkt das Abrufen des Werts dieser Eigenschaft finden Sie unter der [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) Member-Funktion.  
  
 *m_nODBCTimeout*  
 Die Anzahl der Sekunden an, die das Microsoft Jet-Datenbankmodul, bevor ein Timeout-Fehler wartet tritt auf, wenn eine Abfrage auf eine ODBC-Datenbank ausgeführt wird. Bei Verwendung eine ODBC-Datenbank, z. B. Microsoft SQL Server kann aufgrund von Netzwerk-Netzwerkverkehrs oder extremer Nutzung des ODBC-Servers verzögert sein. Anstatt abzuwarten, können Sie angeben, wie lange das Microsoft Jet-Datenbankmodul wartet, bevor er einen Fehler erzeugt. Der Standard-Timeoutwert beträgt 60 Sekunden. Sie können den Wert dieser Eigenschaft abrufen, direkt durch Aufrufen der Querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) Member-Funktion. Weitere Informationen finden Sie unter dem Thema "ODBCTimeout-Eigenschaft" DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Querydef ist ein Objekt der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Die Verweise auf die primären, sekundären und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) Memberfunktion Klasse `CDaoDatabase`.  
  
 Informationen abgerufen werden, indem Sie die [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) -Memberfunktion befindet sich in einer `CDaoQueryDefInfo` Struktur. Rufen Sie `GetQueryDefInfo` für das Datenbankobjekt, in dessen QueryDefs-Auflistung das Querydef-Objekt gespeichert ist. `CDaoQueryDefInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoQueryDefInfo` Objekt. Klasse `CDaoDatabase` auch stellt Memberfunktionen zur direkten Zugriff auf alle Eigenschaften zurückgegeben, die einem `CDaoQueryDefInfo` Objekts müssen Sie wahrscheinlich nur in seltenen Fällen rufen Sie `GetQueryDefInfo`.  
  
 Wenn Sie ein neues Feld oder Parameter-Objekt an die Felder oder Parameter-Auflistung eines Querydef-Objekts anfügen, wird eine Ausnahme ausgelöst, wenn die zugrunde liegende Datenbank den für das neue Objekt angegebenen Datentyp nicht unterstützt.  
  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Querydef erstellt oder zuletzt aktualisiert wurde. In einer Umgebung mit mehreren Benutzern sollten Benutzer diese Einstellungen abrufen, direkt aus der Datei mithilfe der **net Time** Befehl aus, um die Unterschiede in den Einstellungen der Eigenschaft DateCreated und LastUpdated zu vermeiden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)

