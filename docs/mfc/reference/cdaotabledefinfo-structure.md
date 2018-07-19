---
title: CDaoTableDefInfo-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: ac88b3fd55a81237e6c54dbad422f9537950c9e6
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335760"
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
 Eindeutig benennt das Tabledef-Objekt. Um den Wert dieser Eigenschaft direkt zu abzurufen, rufen Sie die Tabledef Objekts [GetName](../../mfc/reference/cdaotabledef-class.md#getname) Member-Funktion. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.  
  
 *m_bUpdatable*  
 Gibt an, ob Änderungen an der Tabelle vorgenommen werden können. Der schnellste Weg, zu bestimmen, ob eine Tabelle aktualisiert werden kann, besteht darin, öffnen ein `CDaoTableDef` Objekt für die Tabelle und Aufrufen des Objekts [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) Member-Funktion. `CanUpdate` Gibt immer zurück ungleich Null (TRUE) für eine neu erstellte Tabledef-Objekt, und 0 (FALSE) für ein Objekt angefügte Tabledef. Ein neues Tabledef-Objekt kann nur in eine Datenbank angefügt werden, für die der aktuelle Benutzer über Schreibberechtigungen verfügt. Wenn die Tabelle nur aktualisierbare Felder enthält `CanUpdate` gibt 0 zurück. Wenn ein oder mehrere Felder aktualisiert werden kann, sind `CanUpdate` ungleich NULL zurückgibt. Sie können nur die aktualisierbaren Felder bearbeiten. Weitere Informationen finden Sie im Thema "Aktualisierbare Property" in-DAO-Hilfe.  
  
 *m_lAttributes*  
 Gibt die Eigenschaften des in der Tabelle, die vom Tabledef Objekt dargestellt wird. Um die aktuellen Attribute einer Tabledef abzurufen, rufen die [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) Member-Funktion. Der zurückgegebene Wert kann es sich um eine Kombination dieser lange Konstanten (verwenden das bitweise OR (**&#124;**) Operator):  
  
- `dbAttachExclusive` Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Tabelle mit einer angefügten Tabelle, die für die ausschließliche Verwendung geöffnet ist.  
  
- `dbAttachSavePWD` Für Datenbanken, die Microsoft Jet-Datenbank-Engine zu verwenden, gibt an, dass die Benutzer-ID und das Kennwort für die verknüpfte Tabelle mit den Verbindungsinformationen gespeichert werden.  
  
- `dbSystemObject` Gibt an, dass die Tabelle eine Systemtabelle, die von der Microsoft Jet-Datenbank-Engine bereitgestellt wird. (Schreibgeschützt.)  
  
- `dbHiddenObject` Gibt an, dass die Tabelle eine ausgeblendete Tabelle, die von der Microsoft Jet-Datenbank-Engine (für die temporäre Verwendung) bereitgestellt wird. (Schreibgeschützt.)  
  
- `dbAttachedTable` Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer nicht-ODBC-Datenbank, z. B. eine Paradox-Datenbank ist.  
  
- `dbAttachedODBC` Gibt an, dass die Tabelle mit einer angefügten Tabelle aus einer ODBC-Datenbank, z. B. Microsoft SQL Server ist.  
  
 *m_dateCreated*  
 Das Datum und Uhrzeit der Erstellung die Tabelle. Um direkt Abrufen des Datums in der Tabelle erstellt wurde, rufen Sie die [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) Memberfunktion die `CDaoTableDef` Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.  
  
 *m_dateLastUpdated*  
 Das Datum und Uhrzeit der letzten Änderungen an den Entwurf der Tabelle. Um direkt Abrufen des Datums in der Tabelle zuletzt aktualisiert wurde, rufen Sie die [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) Memberfunktion die `CDaoTableDef` Objekt in der Tabelle zugeordnet. Weitere Informationen finden Sie in der Kommentare unten. Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.  
  
 *m_strSrcTableName*  
 Gibt den Namen einer angefügten Tabelle an, sofern vorhanden. Um direkt vom Namen der Quelltabelle abzurufen, rufen Sie die [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) Memberfunktion die `CDaoTableDef` Objekt in der Tabelle zugeordnet.  
  
 *m_strConnect*  
 Enthält Informationen zur Quelle für eine geöffnete Datenbank. Sehen Sie diese Eigenschaft durch Aufrufen der [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Memberfunktion Ihre `CDaoTableDef` Objekt. Weitere Informationen zum Verbinden von Zeichenfolgen, finden Sie unter `GetConnect`.  
  
 *m_strValidationRule*  
 Ein Wert, der die Daten in Feldern von Tabledef überprüft wird, geändert oder einer Tabelle hinzugefügt. Überprüfung wird nur für Datenbanken unterstützt, die Microsoft Jet-Datenbank-Engine zu verwenden. Um die Validierungsregel direkt abzurufen, rufen Sie die [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) Memberfunktion die `CDaoTableDef` Objekt in der Tabelle zugeordnet. Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" in-DAO-Hilfe.  
  
 *m_strValidationText*  
 Ein Wert, der den Text der Nachricht angibt, die Ihre Anwendung angezeigt werden soll, wenn die Validierungsregel, die von der ValidationRule-Eigenschaft angegebene nicht erfüllt wird. Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in-DAO-Hilfe.  
  
 *m_lRecordCount*  
 Die Anzahl der Datensätze, die in einem Tabledef-Objekt zugegriffen werden soll. Die Einstellung dieser Eigenschaft ist schreibgeschützt. Um die Anzahl der Datensätze direkt abzurufen, rufen Sie die [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) Memberfunktion die `CDaoTableDef` Objekt. Die Dokumentation für `GetRecordCount` wird beschrieben, die Anzahl der Datensätze weiter. Beachten Sie, dass diese Anzahl abrufen ein zeitaufwändiger Vorgang sein kann, wenn die Tabelle viele Datensätze enthält.  
  
## <a name="remarks"></a>Hinweise  
 Tabledef ist ein Objekt der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Die Verweise auf die primäre, sekundäre und alle oben angegeben, wie die Informationen zurückgegeben werden, indem die [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) Memberfunktion in Klasse `CDaoDatabase`.  
  
 Informationen, die abgerufen, indem die [CDaoDatabase:: GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) Member-Funktion befindet sich in einem `CDaoTableDefInfo` Struktur. Rufen Sie die `GetTableDefInfo` Memberfunktion die `CDaoDatabase` -Objekt, dessen TableDefs-Auflistung Tabledef-Objekts gespeichert ist. `CDaoTableDefInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoTableDefInfo` Objekt.  
  
 Die Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt oder zuletzt aktualisiert wurde. In einer mehrbenutzerumgebung erhalten Benutzer diese Einstellungen direkt vom Dateiserver auf Vermeidung von abweichungen in der DateCreated und LastUpdated-Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)
