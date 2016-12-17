---
title: "CDaoQueryDefInfo-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDaoQueryDefInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDefInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), QueryDefs-Auflistung"
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoQueryDefInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoQueryDefInfo`\-Struktur enthält Informationen über ein Querydef\-Objekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoQueryDefInfo  
{  
   CString m_strName;               // Primary  
   short m_nType;                   // Primary  
   COleDateTime m_dateCreated;      // Secondary  
   COleDateTime m_dateLastUpdated;  // Secondary  
   BOOL m_bUpdatable;               // Secondary  
   BOOL m_bReturnsRecords;          // Secondary  
   CString m_strSQL;                // All  
   CString m_strConnect;            // All  
   short m_nODBCTimeout;            // All  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Querydef\-Objekt.  Weitere Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  Aufruf [CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md), um diese Eigenschaft direkt abrufen.  
  
 `m_nType`  
 Ein Wert, der dem Betriebstyp eines Querydef\-Objekts angibt.  Folgende Werte sind zulässig:  
  
-   **dbQSelect** ausgewählt \- Abfrage wählt Datensätze aus.  
  
-   **dbQAction** \- Aktion die Abfrage werden verschoben oder die Änderungsdaten jedoch keine Datensätze zurück.  
  
-   **dbQCrosstab** Kreuztabelle \- Abfrage gibt Daten in einem Arbeitsblatt ähnlichen Format zurück.  
  
-   **dbQDelete** Löschen \- Abfrage löscht einen angegebene Gruppe von Zeilen.  
  
-   Aktualisieren \-**dbQUpdate** die Abfrage ändert eine Gruppe von Datensätzen.  
  
-   Fügen **dbQAppend** \- die Abfrage fügt neue Datensätze am Ende einer Tabelle oder der Abfrage hinzu.  
  
-   **dbQMakeTable** Machen\-Tabelle \- Abfrage wird eine neue Tabelle aus einem Recordset erstellt.  
  
-   **dbQDDL** \- die Datendefinition Abfrage auswirkt die Struktur von Tabellen oder ihrer Teile.  
  
-   Bereitstellung **dbQSQLPassThrough** \- SQL\-Anweisung wird direkt dem Datenbank\-Back\-End, ohne verursacht übergeben.  
  
-   Union **dbQSetOperation** \- die Abfrage erstellt ein Recordset\-Objekt vom Typ Momentaufnahme, das Daten von allen angegebenen Datensätze in zwei oder mehr Tabellen enthält mit einem doppelten Datensätzen entfernt.  Um die Duplikate einzuschließen, fügen Sie das Schlüsselwort **ALLE** in die SQL\-Anweisung der Querydef hinzu.  
  
-   **dbQSPTBulk** mit **dbQSQLPassThrough** verwendet, um eine Abfrage anzugeben, die keine Datensätze zurückgibt.  
  
> [!NOTE]
>  Wenn Sie eine SQL Pass\-Through\-Abfrage zu erstellen, legen Sie die **dbQSQLPassThrough** Konstante fest.  Dies wird automatisch vom Microsoft Jet\-Datenbankmodul festgelegt, wenn Sie ein Querydef\-Objekt erstellen und die Connect\-Eigenschaft festlegen.  
  
 Weitere Informationen finden Sie im Thema "Typeigenschaft" in der DAO\-Hilfe.  
  
 `m_dateCreated`  
 Das Datum und die Uhrzeit, die die Querydef erstellt wurde.  Um das Datum direkt abgerufen, das die Querydef erstellt, die die [GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)`CDaoTableDef`\-Memberfunktion des Objekts aufgerufen Sie wurde, das der Tabelle zugeordnet ist.  Siehe Kommentare unten weitere Informationen.  Siehe auch das Thema "DateCreated, LastUpdated\-Eigenschaften" in der DAO\-Hilfe.  
  
 `m_dateLastUpdated`  
 Das Datum und die Uhrzeit der letzten Änderung vorgenommen an der Querydef.  Um das Datum direkt abzurufen, das die Tabelle zuletzt aktualisiert, die [GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)\-Memberfunktion der Querydef Aufrufen Sie wurde.  Siehe Kommentare unten weitere Informationen.  Und finden Sie im Thema "DateCreated, LastUpdated\-Eigenschaften" in der DAO\-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob Änderungen vorgenommen werden können an einem Querydef\-Objekt.  Wenn diese Eigenschaft **TRUE** ist, ist die Querydef aktualisierbar; andernfalls ist sie nicht.  Aktualisierbares Möglichkeit die Abfragedefinition des Querydef\-Objekts kann geändert werden.  Die aktualisierbare Eigenschaft eines Querydef\-Objekts wird auf **TRUE** festgelegt, wenn die Abfragedefinition aktualisiert werden kann, wenn das resultierende Recordset nicht aktualisierbar ist.  Um diese Eigenschaft direkt abrufen, rufen Sie die [CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)\-Memberfunktion der Querydef auf.  Weitere Informationen finden Sie im Thema "aktualisierbare Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_bReturnsRecords*  
 Gibt an, ob eine SQL Pass\-Through\-Abfrage zu einer externen Datenbank Datensätze zurückgibt.  Wenn diese Eigenschaft **TRUE** ist, gibt die Abfrage Datensätze zurück.  Um diese Eigenschaft direkt abrufen, rufen Sie [CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md) auf.  Nicht alle SQL Pass\-Through\-Abfragen zu den Rückgabedatensätzen der externe Datenbanken.  aktualisiert beispielsweise eine SQL\- **UPDATE** Datensätze, ohne die Datensätze zurückzugeben, während eine SQL\- **AUSWÄHLEN** Datensätze zurückgibt.  Weitere Informationen finden Sie im Thema "ReturnsRecords\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strSQL*  
 Die SQL\-Anweisung, die die Abfrage definiert, kann durch ein Querydef\-Objekt aus.  Die SQL\-Eigenschaft enthält die SQL\-Anweisung, die bestimmt, wie Datensätze ausgewählt, gruppiert und sortiert werden, wenn Sie die Abfrage ausführen.  Sie können die Abfrage verwenden, um Datensätze auszuwählen, die in einem Dynaset oder Recordset\-Objekt einzuschließen in einem vom Typ Momentaufnahme.  Sie können Massenabfragen auch definieren, um Daten zu ändern, ohne die Datensätze zurückzugeben.  Sie können den Wert dieser Eigenschaft direkt abrufen, indem Sie die [GetSQL](../Topic/CDaoQueryDef::GetSQL.md)\-Memberfunktion der Querydef aufrufen.  
  
 `m_strConnect`  
 Stellt Informationen zu Quelle einer Datenbank bereit, die in einer Pass\-Through\-Abfrage verwendet wird.  Diese Informationen akzeptieren die Form einer Verbindungszeichenfolge an.  Weitere Informationen zu schließen Sie Zeichenfolgen und nach Informationen über den Wert dieser Eigenschaft direkt abrufen, finden die Memberfunktion [CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md) an.  
  
 *m\_nODBCTimeout*  
 Die Anzahl von Sekunden, die das Microsoft Jet\-Datenbankmodul wartet, bevor ein Timeoutfehler auftritt, wenn eine Abfrage auf eine ODBC\-Datenbank ausgeführt wird.  Wenn Sie eine ODBC\-Datenbank, wie Microsoft SQL Server verwenden, gibt es möglicherweise Verzögerungen aufgrund des Netzwerkdatenverkehrs oder der Beanspruchung Grafikoperationen des ODBC\-Servers.  Statt unbegrenzt warten, können Sie angeben, wie lange das Microsoft Jet\-Modul wartet, bevor ein Fehler generiert.  Der Standardtimeoutwert ist 60 Sekunden.  Sie können den Wert dieser Eigenschaft direkt abrufen, indem Sie die [GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)\-Memberfunktion der Querydef aufrufen.  Weitere Informationen finden Sie im Thema "ODBCTimeout\-Eigenschaft" in der DAO\-Hilfe.  
  
## Hinweise  
 Die Querydef ist ein Objekt der Klasse [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md).  Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die [GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)\-Memberfunktion in der `CDaoDatabase`\- Klasse zurückgegeben werden.  
  
 Die Informationen, die von der [CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoQueryDefInfo`\-Struktur gespeichert.  Rufen Sie `GetQueryDefInfo` für das Datenbankobjekt auf, in dessen Querydefauflistung das Querydef\-Objekt gespeichert wird.  `CDaoQueryDefInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoQueryDefInfo`\-Objekts zu speichern.  `CDaoDatabase`\-Klasse stellt auch Memberfunktionen für alle Eigenschaften direkt zugreifen, die in einem `CDaoQueryDefInfo`\-Objekt zurückgegeben werden, müssen Sie wahrscheinlich selten `GetQueryDefInfo` aufrufen.  
  
 Wenn Sie ein neues oder Feld\- Parameterobjekt zu Feldern oder die Parameterauflistung eines Querydef\-Objekts anfügen, wird eine Ausnahme ausgelöst, wenn die zugrunde liegende Datenbank nicht den Datentyp unterstützt, der für das neue Objekt angegeben wird.  
  
 Die Datums\- Uhrzeiteinstellungen werden vom Computer abgeleitet, auf dem die Querydef erstellt oder zuletzt aktualisiert.  In einer Mehrbenutzerumgebung sollten Benutzer diese Einstellungen direkt vom Dateiserver mithilfe des Befehls **net time** abrufen, Diskrepanzen in den Eigenschafteneinstellungen DateCreated und LastUpdated zu vermeiden.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)