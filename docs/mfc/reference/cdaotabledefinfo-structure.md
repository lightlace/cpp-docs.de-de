---
title: CDaoTableDefInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
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
ms.openlocfilehash: 4d1ac5ca00f98f8c34332ce2eb1a180ab715e6ba
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo-Struktur
Die `CDaoTableDefInfo` Struktur enthält Informationen über ein Tabledef-Objekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Das Tabledef-Objekt bezeichnet eindeutig. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Tabledef-Objekts [GetName](../../mfc/reference/cdaotabledef-class.md#getname) Member-Funktion. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob die Tabelle geändert werden kann. Der schnellste Weg, zu bestimmen, ob eine Tabelle aktualisierbar ist zu öffnen ist ein `CDaoTableDef` Objekt für die Tabelle, und rufen Sie des Objekts [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) Member-Funktion. `CanUpdate`Gibt immer einen Wert ungleich Null (**TRUE**) für eine neu erstellte Tabledef-Objekt und 0 (**FALSE**) für eine angefügte Tabledef-Objekt. Ein neues Tabledef-Objekt kann nur an eine Datenbank angefügt werden, für die der aktuelle Benutzer über Schreibberechtigungen verfügt. Wenn die Tabelle nur aktualisierbare Felder enthält `CanUpdate` gibt 0 zurück. Wenn ein oder mehrere Felder aktualisierbar sind `CanUpdate` gibt einen Wert ungleich NULL zurück. Sie können nur die aktualisierbaren Felder bearbeiten. Weitere Informationen finden Sie unter dem Thema "Aktualisierbare-Eigenschaft" in der DAO-Hilfe.  
  
 `m_lAttributes`  
 Gibt die Eigenschaften der Tabelle durch das Tabledef-Objekt dargestellt wird. Rufen Sie zum Abrufen der aktuellen Attribute einer Tabledef seine [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) Member-Funktion. Der zurückgegebene Wert kann eine Kombination der folgenden long-Konstanten (mit dem bitweisen OR (**|**) Operator):  
  
- **DbAttachExclusive** für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt die Tabelle ist eine verknüpfte Tabelle, die für die exklusive Verwendung geöffnet.  
  
- **DbAttachSavePWD** für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.  
  
- **DbSystemObject** gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbankmodul bereitgestellt. (Schreibgeschützt.)  
  
- **DbHiddenObject** gibt an, in der Tabelle ist eine verborgene Tabelle, die von der Microsoft Jet-Datenbankmodul (für die temporäre Verwendung) bereitgestellt. (Schreibgeschützt.)  
  
- **DbAttachedTable** gibt an, in der Tabelle ist eine verknüpfte Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Paradox-Datenbank.  
  
- **DbAttachedODBC** gibt an, in der Tabelle ist eine verknüpfte Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server.  
  
 `m_dateCreated`  
 Das Datum und die Uhrzeit der Erstellung die Tabelle. Rufen Sie direkt das Datum in der Tabelle erstellt wurde, rufen Sie die [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion der `CDaoTableDef` -Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie unter Kommentare. Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
 `m_dateLastUpdated`  
 Datum und Uhrzeit der letzten Änderung für den Entwurf der Tabelle. Aufrufen, rufen Sie direkt das Datum der letzten die Tabelle Aktualisierung der [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) Memberfunktion der `CDaoTableDef` -Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie unter Kommentare. Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
 *m_strSrcTableName*  
 Gibt den Namen einer angefügten Tabelle an, sofern vorhanden. Um Namen der Quelltabelle direkt abzurufen, rufen Sie die [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) Memberfunktion der `CDaoTableDef` -Objekt in der Tabelle zugeordnet.  
  
 `m_strConnect`  
 Enthält Informationen über die Quelle einer geöffneten Datenbank. Sehen Sie diese Eigenschaft durch Aufrufen der [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Memberfunktion Ihrer `CDaoTableDef` Objekt. Weitere Informationen zu Verbindungszeichenfolgen, finden Sie unter `GetConnect`.  
  
 `m_strValidationRule`  
 Ein Wert, der die Daten in Feldern Tabledef überprüft werden soll, wenn sie eine Tabelle hinzugefügt oder geändert werden. Überprüfung wird nur für Datenbanken unterstützt, die das Microsoft Jet-Datenbankmodul verwenden. Um die Validierungsregel direkt abzurufen, rufen die [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) Memberfunktion der `CDaoTableDef` -Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie unter dem Thema "ValidationRule-Eigenschaft" in der DAO-Hilfe.  
  
 `m_strValidationText`  
 Ein Wert, der den Text der Nachricht angibt, die die Anwendung angezeigt werden soll, wenn durch die ValidationRule-Eigenschaft angegebenen nicht erfüllt wird. Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in der DAO-Hilfe.  
  
 *m_lRecordCount*  
 Die Anzahl der Datensätze, die in einem Tabledef-Objekt zugegriffen. Die Einstellung dieser Eigenschaft ist schreibgeschützt. Um die Anzahl der Datensätze direkt abzurufen, rufen die [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) Memberfunktion der `CDaoTableDef` Objekt. Die Dokumentation für `GetRecordCount` beschreibt die Anzahl der Datensätze weiter. Beachten Sie, dass diese Anzahl abrufen ein zeitaufwändiger Vorgang sein kann, wenn die Tabelle viele Datensätze enthält.  
  
## <a name="remarks"></a>Hinweise  
 Tabledef ist ein Objekt der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Die Verweise auf die primären, sekundären und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) Memberfunktion Klasse `CDaoDatabase`.  
  
 Informationen abgerufen werden, indem Sie die [CDaoDatabase:: GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) -Memberfunktion befindet sich in einer `CDaoTableDefInfo` Struktur. Rufen Sie die `GetTableDefInfo` Memberfunktion der `CDaoDatabase` -Objekt, dessen TableDefs-Auflistung Tabledef-Objekts gespeichert ist. `CDaoTableDefInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoTableDefInfo` Objekt.  
  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer Umgebung mit mehreren Benutzern sollten die Benutzer diese Einstellungen direkt vom Dateiserver zu Vermeidung von abweichungen in der DateCreated und LastUpdated-Eigenschaft abrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)

