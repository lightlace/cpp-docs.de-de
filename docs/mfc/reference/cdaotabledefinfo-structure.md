---
title: CDaoTableDefInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80c1422c4d0e45599ca8bc2e9c86a4263b8ac9b6
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955608"
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
 *m_strName*  
 Eindeutig benennt das Tabledef-Objekt. Um den Wert dieser Eigenschaft direkt abzurufen, rufen Sie des Tabledef-Objekts [GetName](../../mfc/reference/cdaotabledef-class.md#getname) Memberfunktion. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *m_bUpdatable*  
 Gibt an, ob die Tabelle geändert werden können. Die schnelle Möglichkeit zu bestimmen, ob eine Tabelle aktualisiert werden kann, besteht darin, Öffnen einer `CDaoTableDef` Objekt für die Tabelle, und rufen Sie des Objekts [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) Memberfunktion. `CanUpdate` Gibt immer ungleich Null (**"true"**) für eine neu erstellte Tabledef-Objekt und 0 (**"false"**) für eine angefügte Tabledef-Objekt. Ein neues Tabledef-Objekt kann nur in eine Datenbank angefügt werden, für die der aktuelle Benutzer über Schreibberechtigungen verfügt. Wenn die Tabelle nur aktualisierbare Felder enthält `CanUpdate` gibt 0 zurück. Wenn ein oder mehrere Felder aktualisiert werden kann, sind `CanUpdate` ungleich NULL zurückgegeben. Sie können nur die aktualisierbaren Felder bearbeiten. Weitere Informationen finden Sie im Thema "Aktualisierbare Property" in der DAO-Hilfe.  
  
 *m_lAttributes*  
 Gibt die Eigenschaften der Tabelle durch das Tabledef-Objekt dargestellt wird. Rufen Sie zum Abrufen der aktuellen Attribute auf einer Tabledef seine [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) Memberfunktion. Der zurückgegebene Wert kann eine Kombination aus diesen lange Konstanten (mit dem bitweisen OR-(**&#124;**) Operator):  
  
- **DbAttachExclusive** für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt die Tabelle ist eine verknüpfte Tabelle, die für die ausschließliche Verwendung geöffnet.  
  
- **DbAttachSavePWD** für Datenbanken, die das Microsoft Jet-Datenbankmodul verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.  
  
- **DbSystemObject** gibt an, dass die Tabelle eine Systemtabelle bereitgestellt, die vom Microsoft Jet-Datenbankmodul. (Schreibgeschützt.)  
  
- **DbHiddenObject** gibt an, die Tabelle ist eine verborgene Tabelle, die vom Microsoft Jet-Datenbankmodul (für die temporäre Verwendung) bereitgestellt. (Schreibgeschützt.)  
  
- **DbAttachedTable** gibt an, dass die Tabelle einer angefügten Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Datenbank Paradox.  
  
- **DbAttachedODBC** gibt an, dass die Tabelle einer angefügten Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server.  
  
 *m_dateCreated*  
 Das Datum und Uhrzeit der Erstellung die Tabelle. Rufen Sie direkt das Datum der Erstellung der Tabelle Aufrufen der [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion von der `CDaoTableDef` Objekt, das mit der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
 *m_dateLastUpdated*  
 Das Datum und die Uhrzeit der letzten Änderung am Entwurf der Tabelle. Rufen Sie direkt das Datum der letzten die Tabelle Aktualisierung Aufrufen der [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) Memberfunktion von der `CDaoTableDef` Objekt, das mit der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
 *m_strSrcTableName*  
 Gibt den Namen einer angefügten Tabelle an, sofern vorhanden. Um direkt vom Namen der Quelltabelle abzurufen, rufen Sie die [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) Memberfunktion der `CDaoTableDef` Objekt, das mit der Tabelle zugeordnet.  
  
 *m_strConnect*  
 Enthält Informationen zur Quelle des eine geöffnete Datenbank. Sehen Sie sich diese Eigenschaft durch Aufrufen der [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Memberfunktion von Ihrem `CDaoTableDef` Objekt. Weitere Informationen zu Verbindungszeichenfolgen, finden Sie unter `GetConnect`.  
  
 *m_strValidationRule*  
 Ein Wert, der die Daten in Feldern Tabledef überprüft, wie deren Änderung oder einer Tabelle hinzugefügt. Überprüfung wird nur für Datenbanken unterstützt, die das Microsoft Jet-Datenbankmodul verwenden. Um die Validierungsregel direkt abzurufen, rufen Sie die [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) Memberfunktion von der `CDaoTableDef` Objekt, das mit der Tabelle zugeordnet. Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" DAO-Hilfe.  
  
 *m_strValidationText*  
 Ein Wert, der den Text der Nachricht angibt, die die Anwendung angezeigt werden soll, wenn die von der ValidationRule-Eigenschaft angegebene Gültigkeitsprüfungsregel nicht erfüllt wird. Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" DAO-Hilfe.  
  
 *m_lRecordCount*  
 Die Anzahl der Datensätze in einem Tabledef-Objekt zugegriffen. Die Einstellung dieser Eigenschaft ist schreibgeschützt. Um die Anzahl der Datensätze direkt abzurufen, rufen Sie die [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) Memberfunktion der `CDaoTableDef` Objekt. Die Dokumentation für `GetRecordCount` wird beschrieben, die Anzahl der Datensätze weiter. Beachten Sie, dass diese Zahl abrufen einen zeitaufwändigen Vorgang sein kann, wenn die Tabelle viele Datensätze enthält.  
  
## <a name="remarks"></a>Hinweise  
 Tabledef ist ein Objekt der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) Memberfunktion in Klasse `CDaoDatabase`.  
  
 Informationen, die abgerufen, indem die [CDaoDatabase:: GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) Memberfunktion befindet sich in einer `CDaoTableDefInfo` Struktur. Rufen Sie die `GetTableDefInfo` Memberfunktion von der `CDaoDatabase` -Objekt, dessen TableDefs-Auflistung Tabledef-Objekts gespeichert wird. `CDaoTableDefInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoTableDefInfo` Objekt.  
  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung sollten Benutzer diese Einstellungen direkt vom Dateiserver zur Vermeidung von abweichungen in der DateCreated und LastUpdated eigenschaftseinstellungen erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
