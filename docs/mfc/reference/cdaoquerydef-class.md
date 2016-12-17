---
title: "CDaoQueryDef Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDaoQueryDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDef class"
  - "Abfragen [Visual Studio], Definieren"
  - "QueryDef objects"
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoQueryDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Abfragedefinition oder Querydef "," normalerweise eine dar, die in einer Datenbank gespeichert ist.  
  
## Syntax  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](../Topic/CDaoQueryDef::CDaoQueryDef.md)|Erstellt ein Objekt **CDaoQueryDef** .  Folgender Aufruf **Öffnen** oder **Create**, je nach Anforderungen.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoQueryDef::Append](../Topic/CDaoQueryDef::Append.md)|Fügt die Querydef zur Querydefauflistung der Datenbank wie gespeicherte Abfrage an.|  
|[CDaoQueryDef::CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)|Gibt Wert ungleich 0 zurück, wenn die Abfrage die Datenbank aktualisiert werden kann.|  
|[CDaoQueryDef::Close](../Topic/CDaoQueryDef::Close.md)|Schließt das Querydef\-Objekt.  Zerstören Sie das C\+\+\-Objekt, wenn Sie damit beenden.|  
|[CDaoQueryDef::Create](../Topic/CDaoQueryDef::Create.md)|Erstellt das zugrunde liegende DAO\-Querydef\-Objekt.  Verwenden Sie die Querydef als temporäre Abfrage oder Aufruf **Append**, um sie in der Datenbank zu speichern.|  
|[CDaoQueryDef::Execute](../Topic/CDaoQueryDef::Execute.md)|Führt die Abfrage aus, die vom Querydef\-Objekt definiert ist.|  
|[CDaoQueryDef::GetConnect](../Topic/CDaoQueryDef::GetConnect.md)|Gibt die Verbindungszeichenfolge zurück, die mit der Querydef zugeordnet ist.  Die Verbindungszeichenfolge identifiziert die Datenquelle.  \(Nur SQL Pass\-Through\-Abfragen; andernfalls eine leere Zeichenfolge\).|  
|[CDaoQueryDef::GetDateCreated](../Topic/CDaoQueryDef::GetDateCreated.md)|Gibt das Datum zurück, das die gespeicherte Abfrage erstellt wurde.|  
|[CDaoQueryDef::GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)|Gibt das Datum zurück, das die gespeicherte Abfrage zuletzt aktualisiert wurde.|  
|[CDaoQueryDef::GetFieldCount](../Topic/CDaoQueryDef::GetFieldCount.md)|Gibt die Anzahl von Feldern zurück, die von der Querydef definiert werden.|  
|[CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)|Gibt Informationen über ein bestimmtes Feld zurück, die in der Abfrage definiert ist.|  
|[CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md)|Gibt den Namen der Querydefs zurück.|  
|[CDaoQueryDef::GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)|Gibt den Timeoutwert zurück, der von ODBC verwendet wird \(für eine ODBC\-Abfrage\) wenn die Querydef ausgeführt wird.  Dies bestimmt, wie lange die Aktion der Abfrage abzuschließen zulässt.|  
|[CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)|Gibt die Anzahl von Parametern zurück, die für die Abfrage definiert werden.|  
|[CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)|Gibt Informationen zu einem angegebenen Parameter an die Abfrage zurück.|  
|[CDaoQueryDef::GetParamValue](../Topic/CDaoQueryDef::GetParamValue.md)|Gibt den Wert eines angegebenen Parameters zur Abfrage zurück.|  
|[CDaoQueryDef::GetRecordsAffected](../Topic/CDaoQueryDef::GetRecordsAffected.md)|Gibt die Anzahl der Datensätze zurück, die von einer Aktionsabfrage beeinflusst werden.|  
|[CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md)|Gibt Wert ungleich 0 zurück, wenn die Abfrage, die von der Querydef definiert ist, Datensätze zurückgibt.|  
|[CDaoQueryDef::GetSQL](../Topic/CDaoQueryDef::GetSQL.md)|Gibt die SQL\-Zeichenfolge zurück, die die Abfrage angibt, die von der Querydef definiert ist.|  
|[CDaoQueryDef::GetType](../Topic/CDaoQueryDef::GetType.md)|Gibt den Abfragetyp zurück: Löschen, Aktualisieren, fügen MachenTabelle, usw. an.|  
|[CDaoQueryDef::IsOpen](../Topic/CDaoQueryDef::IsOpen.md)|Gibt Wert ungleich 0 zurück, wenn die Querydef geöffnet ist und ausgeführt werden kann.|  
|[CDaoQueryDef::Open](../Topic/CDaoQueryDef::Open.md)|Öffnet eine vorhandene Querydef, die in der Querydefauflistung der Datenbank gespeichert wird.|  
|[CDaoQueryDef::SetConnect](../Topic/CDaoQueryDef::SetConnect.md)|Legt die Verbindungszeichenfolge für eine SQL Pass\-Through\-Abfrage auf einer ODBC\-Datenquelle fest.|  
|[CDaoQueryDef::SetName](../Topic/CDaoQueryDef::SetName.md)|Legt den Namen der gespeicherten Abfrage fest und in Verwendung ersetzt den Namen, die als Querydef erstellt wurde.|  
|[CDaoQueryDef::SetODBCTimeout](../Topic/CDaoQueryDef::SetODBCTimeout.md)|Legt den Timeoutwert fest, der von ODBC verwendet wird \(für eine ODBC\-Abfrage\) wenn die Querydef ausgeführt wird.|  
|[CDaoQueryDef::SetParamValue](../Topic/CDaoQueryDef::SetParamValue.md)|Legt den Wert eines angegebenen Parameters zur Abfrage fest.|  
|[CDaoQueryDef::SetReturnsRecords](../Topic/CDaoQueryDef::SetReturnsRecords.md)|Gibt an, ob die Querydef Datensätze zurückgibt.  Dieses Attribut zu **TRUE** festzulegen ist für SQL Pass\-Through\-Abfragen nur gültig.|  
|[CDaoQueryDef::SetSQL](../Topic/CDaoQueryDef::SetSQL.md)|Legt die SQL\-Zeichenfolge fest, die die Abfrage angibt, die von der Querydef definiert ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoQueryDef::m\_pDAOQueryDef](../Topic/CDaoQueryDef::m_pDAOQueryDef.md)|Ein Zeiger auf die OLE\-Schnittstelle für das zugrunde liegende DAO\-Querydef\-Objekt.|  
|[CDaoQueryDef::m\_pDatabase](../Topic/CDaoQueryDef::m_pDatabase.md)|Ein Zeiger auf `CDaoDatabase`\-Objekt, mit dem die Querydef zugeordnet ist.  Die Querydef würde in der Datenbank oder nicht gespeichert.|  
  
## Hinweise  
 Eine Querydef ist ein Datenzugriffsobjekt, das die SQL\-Anweisung, die eine Abfrage beschreibt und seine Eigenschaften enthält, wie "Der" und "ODBC\-Timeout Datum". Sie können temporäre querydef\-Objekte auch erstellen, ohne sie zu speichern, aber es ist zweckmäßig \- und viel effizienter \- häufig wiederverwendete Abfragen in einer Datenbank zu speichern.  Ein Objekt [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) verwaltet eine Auflistung, die Querydefauflistung aufgerufen, die die gespeicherten Querydef enthält.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen.  Im Allgemeinen sind die MFC\-Klassen auf Grundlage DAO besser geeignet als die MFC\-Klassen auf Grundlage ODBC; die DAO\-basierten Klassen machen die Daten ein und enthalten durch ODBC\-Treiber, über ein eigenes Datenbankmodul.  Die DAO\-basierten Klassen unterstützen auch Operationen der Datendefinitionssprache \(Data Definition Language\), wie das Hinzufügen von Tabellen zu Klassen, ohne zu müssen, DAO direkt aufzurufen.  
  
## Verwendung  
 Verwendungsquerydef\-objekte entweder mit einer vorhandenen gespeicherten Abfrage oder eine neue gespeicherte Abfrage oder temporäre Abfrage erstellen:  
  
1.  In allen Fällen erstellen Sie zuerst ein `CDaoQueryDef`\-Objekt und einen Zeiger angeben [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) zum Objekt, das die Abfrage gehört.  
  
2.  Führen Sie dann das folgende, je nachdem, was Sie möchten:  
  
    -   Um eine vorhandene gespeicherte Abfrage zu verwenden, die Memberfunktion aufrufen [Öffnen Sie](../Topic/CDaoQueryDef::Open.md) des Querydef\-Objekts und hat den Namen der gespeicherten Abfrage an.  
  
    -   Um eine neue gespeicherte Abfrage zu erstellen, rufen Sie die Memberfunktion des [Erstellen Sie](../Topic/CDaoQueryDef::Create.md) Querydef\-Objekts auf und den Namen der Abfrage angeben.  Rufen Sie dann [Fügen Sie an](../Topic/CDaoQueryDef::Append.md) auf, um die Abfrage zu speichern, indem Sie sie der Querydefauflistung der Datenbank anfügen.  **Create** setzt die Querydef in einen geöffneten Zustand, sodass, nachdem es **Create** aufgerufen hat, die Sie nicht **Öffnen** aufrufen.  
  
    -   Um eine temporäre Querydef zu erstellen, rufen Sie **Create** auf.  Führen Sie eine leere Zeichenfolge für den Abfragenamen.  Rufen Sie nicht **Append** auf.  
  
 Wenn Sie beenden, ein Querydef\-Objekt zu verwenden, rufen Sie seine [Schließen Sie](../Topic/CDaoQueryDef::Close.md)\-Memberfunktion auf; zerstören Sie dann das Querydef\-Objekt.  
  
> [!TIP]
>  Die einfachste Möglichkeit, gespeicherte Abfragen erstellen, ist sie zu erstellen und in der Datenbank mit Microsoft Access zu speichern.  Anschließend können Sie sie im MFC\-Code öffnen und verwenden.  
  
## Zweck  
 Sie können ein Querydef\-Objekt auf eine der folgenden Zwecken verwenden:  
  
-   So fügen Sie ein Objekt erstellen `CDaoRecordset`  
  
-   Um die **Execute**\-Memberfunktion des Objekts aufrufen, um eine Aktionsabfrage oder eine SQL Pass\-Through\-Abfrage direkt auszuführen  
  
 Sie können ein Querydef\-Objekt für jeden Typ Abfrage, einschließlich Select\-, Aktion, Kreuztabelle, Löschen, Aktualisieren, anfügen, MachenTabelle, Datendefinition, SQL Pass\-Through, Union und Massenenabfragen verwenden.  Der Typ der Abfrage wird durch den Inhalt der SQL\-Anweisung bestimmt, die Sie bereitstellen.  Informationen zum Abfragetypen, finden Sie unter **Execute** und die [GetType](../Topic/CDaoQueryDef::GetType.md)\-Memberfunktionen.  Recordsets werden häufig für Zeilen zurückgebende Abfragen verwendet, normalerweise die mithilfe der **SELECT... FROM**\-Schlüsselwörter.  **Execute** wird für Massenvorgänge am häufigsten verwendet.  Weitere Informationen finden Sie unter [Führen Sie aus](../Topic/CDaoQueryDef::Execute.md) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## Querydef und Recordsets  
 Um ein Querydef\-Objekt mit `CDaoRecordset` ein Objekt zu erstellen, erstellen Sie in der Regel öffnen oder eine Querydef wie oben beschrieben.  Erstellen Sie dann ein Recordset\-Objekt und einen Zeiger auf das Querydef\-Objekt übergeben, wenn Sie [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) aufrufen.  Die Querydef, die an übergeben, muss in einem geöffneten Zustand befinden.  Weitere Informationen finden Sie unter [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)\-Klasse.  
  
 Sie können eine Querydef nicht verwenden, um ein Recordset \(die häufigste Verwendung für eine Querydef\) erstellen, sofern sie nicht in einem geöffneten Zustand befindet.  Legen Sie die Querydef in einen geöffneten Zustand, indem Sie entweder **Öffnen** oder **Create** aufrufen.  
  
## Externe Datenbanken  
 querydef\-Objekte sind die bevorzugte Methode, den Dialekt des systemeigene SQL eines Moduls der externen Datenbank zu verwenden.  Beispielsweise können Sie eine Transact\-SQL\-Abfrage erstellen \(wie in Microsoft SQL Server verwendet\) und in einem Querydef\-Objekt speichern.  Wenn Sie eine SQL\-Abfrage nicht basierend auf das Microsoft Jet\-Datenbankmodul verwenden, müssen Sie eine Verbindungszeichenfolge bereitstellen, die mit der externen Datenquelle zeigt.  Abfragen mit gültigen Verbindungszeichenfolgen umgehen das Datenbankmodul und führen die Abfrage direkt an den Server der externen Datenbank für die Verarbeitung.  
  
> [!TIP]
>  Die bevorzugte Methode, mit ODBC\-Tabellen besteht darin, sie einer Microsoft Jet\-Datenbankmoduls \(.MDB\) anfügen.  
  
 Weitere Informationen finden Sie in den Themen "Querydef\-Objekt", "Querydef\-Auflistung" und "CdbDatabase\-Objekt" im DAO SDK.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)