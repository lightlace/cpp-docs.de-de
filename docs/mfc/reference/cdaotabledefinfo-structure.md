---
title: "CDaoTableDefInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoTableDefInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDefInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), TableDefs-Auflistung"
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoTableDefInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoTableDefInfo`\-Struktur enthält Informationen über ein Tabledef\-Objekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
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
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Tabledef\-Objekt.  Um den Wert dieser Eigenschaft direkt abrufen, rufen Sie die [GetName](../Topic/CDaoTableDef::GetName.md) Tabledef\- Memberfunktion des Objekts auf.  Weitere Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob Änderungen vorgenommen werden können der Tabelle.  Die schnelle Möglichkeit zu bestimmen, ob eine Tabelle aktualisierbar ist, ist, ein `CDaoTableDef`\-Objekt für die Tabelle zu öffnen und die [CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)\-Memberfunktion des Objekts aufzurufen.  `CanUpdate` gibt immer ungleich 0 \(null\) \(**TRUE**\) für ein neu erstelltes Objekt tabledef\- und 0 \(**FALSE**\) für ein angefügtes Tabledef\-Objekt zurück.  Ein neues Tabledef\-Objekt kann angefügt werden nur zu einer Datenbank, für die der aktuelle Benutzer Schreibberechtigung hat.  Wenn die Tabelle nur nonupdatable Felder enthält, `CanUpdate` gibt 0 zurück.  Wenn eine oder mehrere Felder aktualisierbar sind, gibt `CanUpdate` ungleich 0 \(null\) zurück.  Sie können nur die aktualisierbaren Felder bearbeiten.  Weitere Informationen finden Sie im Thema "aktualisierbare Eigenschaft" in der DAO\-Hilfe.  
  
 `m_lAttributes`  
 Gibt Eigenschaften der Tabelle an, die vom Tabledef\-Objekt dargestellt wird.  Um die aktuellen Attribute einer tabledef\- abzurufen, rufen Sie die zugehörige Memberfunktion [GetAttributes](../Topic/CDaoTableDef::GetAttributes.md) auf.  Der zurückgegebene Wert kann eine Kombination dieser langen Konstanten sein \(unter Verwendung des bitweisen OR \(  **&#124;**\) Operator\):  
  
-   **dbAttachExclusive** für Datenbanken, die das Microsoft Jet\-Datenbankmodul verwenden, gibt der Tabelle ist eine umschlossene Tabelle an, die für die exklusive Verwendung geöffnet ist.  
  
-   **dbAttachSavePWD** für Datenbanken, die das Microsoft Jet\-Datenbankmodul verwenden, gibt an, dass die Benutzer\-ID und Kennwort für die umschlossene Tabelle mit den eingetragenen Verbindungsinformationen gespeichert werden.  
  
-   **dbSystemObject** gibt der Tabelle ist eine Systemtabelle an, die vom Microsoft Jet\-Datenbankmodul bereitgestellt wird. \(Schreibgeschützt.\)  
  
-   **dbHiddenObject** gibt der Tabelle ist eine verborgene Tabelle an, die vom Microsoft Jet\-Datenbankmodul bereitgestellt wird \(für temporäre verwenden\). \(Schreibgeschützt.\)  
  
-   **dbAttachedTable** gibt der Tabelle ist eine umschlossene Tabelle aus einer Datenbank NichtODBC, wie einer Paradoxdatenbank an.  
  
-   **dbAttachedODBC** gibt der Tabelle ist eine umschlossene Tabelle einer ODBC\-Datenbank, wie Microsoft SQL Server an.  
  
 `m_dateCreated`  
 Das Datum und die Uhrzeit, die die Tabelle erstellt wurde.  Um das Datum direkt abzurufen, das die Tabelle erstellt, die die [GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)`CDaoTableDef`\-Memberfunktion des Objekts aufgerufen Sie wurde, das der Tabelle zugeordnet ist.  Siehe Kommentare unten weitere Informationen.  Weitere Informationen finden Sie im Thema "DateCreated, LastUpdated\-Eigenschaften" in der DAO\-Hilfe.  
  
 `m_dateLastUpdated`  
 Das Datum und die Uhrzeit der letzten Änderung vorgenommen am Entwurf der Tabelle.  Um das Datum direkt abzurufen, das die Tabelle zuletzt aktualisiert, die [GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)`CDaoTableDef`\-Memberfunktion des Objekts aufgerufen Sie wurde, das der Tabelle zugeordnet ist.  Siehe Kommentare unten weitere Informationen.  Weitere Informationen finden Sie im Thema "DateCreated, LastUpdated\-Eigenschaften" in der DAO\-Hilfe.  
  
 *m\_strSrcTableName*  
 Gibt den Namen einer Tabelle umschlossenen ggf. an.  Um den Quelltabellennamen direkt abrufen, rufen Sie die [GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)`CDaoTableDef`\-Memberfunktion des Objekts auf, das der Tabelle zugeordnet ist.  
  
 `m_strConnect`  
 Stellt Informationen zu Quelle einer geöffneten Datenbank.  Sie können diese Eigenschaft überprüfen, indem Sie die Memberfunktion [GetConnect](../Topic/CDaoTableDef::GetConnect.md) des `CDaoTableDef`\-Objekts aufrufen.  Weitere Informationen über Zeichenfolgen schließen Sie, `GetConnect` an.  
  
 `m_strValidationRule`  
 Ein Wert, der die Daten der tabledef\- überprüft, fängt auf, während sie in eine Tabelle geändert oder hinzugefügt werden.  Validierung wird nur für Datenbanken unterstützt, die das Microsoft Jet\-Datenbankmodul verwenden.  Um die Validierungsregel direkt abrufen, rufen Sie die [GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)`CDaoTableDef`\-Memberfunktion des Objekts auf, das der Tabelle zugeordnet ist.  Weitere Informationen finden Sie im Thema "ValidationRule\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_strValidationText`  
 Ein Wert, der den Text der Meldung angibt, die von der Anwendung anzeigen soll, wenn die Validierungsregel, die durch die ValidationRule\-Eigenschaft angegeben ist, nicht erfüllt ist.  Weitere Informationen finden Sie im Thema "ValidationText\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_lRecordCount*  
 Die Anzahl von Datensätzen in einem Tabledef\-Objekt zugegriffen.  Diese Eigenschaft ist schreibgeschützt.  Um die Anzahl der Datensätze direkt abrufen, rufen Sie die [GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)`CDaoTableDef`\-Memberfunktion des Objekts auf.  Die Dokumentation für `GetRecordCount` beschreibt die Anzahl der Datensätze weiter.  Beachten Sie, dass diese Anzahl abruft, kann einen zeitaufwändigen Vorgang darstellen, wenn die Tabelle zahlreiche Datensätze enthält.  
  
## Hinweise  
 Die tabledef\- ist ein Objekt der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md).  Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die [GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)\-Memberfunktion in der `CDaoDatabase`\- Klasse zurückgegeben werden.  
  
 Die Informationen, die von der [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoTableDefInfo`\-Struktur gespeichert.  Rufen Sie die Memberfunktion `GetTableDefInfo` des `CDaoDatabase`\-Objekts auf, in dessen Tabledef\-Auflistung das Tabledef\-Objekt gespeichert wird.  `CDaoTableDefInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoTableDefInfo`\-Objekts zu speichern.  
  
 Die Datums\- Uhrzeiteinstellungen werden vom Computer abgeleitet, auf dem die Basistabelle erstellt oder zuletzt aktualisiert.  In einer Mehrbenutzerumgebung sollten Benutzer diese Einstellungen direkt vom Dateiserver abrufen, um Diskrepanzen in den Eigenschafteneinstellungen DateCreated und LastUpdated zu vermeiden.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)   
 [CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)   
 [CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)   
 [CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)   
 [CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)   
 [CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)   
 [CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)   
 [CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)