---
title: "CDaoTableDef Class"
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
  - "CDaoTableDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDef class"
  - "Datenbankklassen [C++], DAO"
  - "database tables [C++], attached table definition"
  - "database tables [C++], base table definition"
  - "tabledefs [C++]"
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoTableDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die gespeicherte Definition einer Basistabelle oder der umschlossenen Tabelle dar.  
  
## Syntax  
  
```  
class CDaoTableDef : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](../Topic/CDaoTableDef::CDaoTableDef.md)|Erstellt ein Objekt **CDaoTableDef** .|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoTableDef::Append](../Topic/CDaoTableDef::Append.md)|Fügt eine neue Tabelle der Datenbank.|  
|[CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn die Tabelle aktualisiert werden kann \(Sie können die Definition von Feldern oder von Tabelleneigenschaften ändern\).|  
|[CDaoTableDef::Close](../Topic/CDaoTableDef::Close.md)|Schließt geöffnete tabledef\-.|  
|[CDaoTableDef::Create](../Topic/CDaoTableDef::Create.md)|Enthält eine Tabelle, die zur Datenbank mithilfe [Fügen Sie an](../Topic/CDaoTableDef::Append.md) hinzugefügt werden kann.|  
|[CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md)|Aufgerufen, um ein Feld für eine Tabelle zu erstellen.|  
|[CDaoTableDef::CreateIndex](../Topic/CDaoTableDef::CreateIndex.md)|Aufgerufen, um einen Index für eine Tabelle zu erstellen.|  
|[CDaoTableDef::DeleteField](../Topic/CDaoTableDef::DeleteField.md)|Aufgerufen, um ein Feld aus einer Tabelle zu löschen.|  
|[CDaoTableDef::DeleteIndex](../Topic/CDaoTableDef::DeleteIndex.md)|Aufgerufen, um einen Index aus einer Tabelle zu löschen.|  
|[CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)|Gibt einen Wert zurück, der eine oder mehrere Eigenschaften eines `CDaoTableDef`\-Objekts angibt.|  
|[CDaoTableDef::GetConnect](../Topic/CDaoTableDef::GetConnect.md)|Gibt einen Wert zurück, der Informationen über die Quelle einer Tabelle enthält.|  
|[CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)|Gibt das Datum und die Uhrzeit zurück, die die zugrunde liegende Basistabelle ein `CDaoTableDef`\-Objekt erstellt wurde.|  
|[CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)|Gibt das Datum und die Uhrzeit der letzten Änderung zurück, die am Entwurf der Basistabelle vorgenommen wird.|  
|[CDaoTableDef::GetFieldCount](../Topic/CDaoTableDef::GetFieldCount.md)|Gibt einen Wert zurück, der die Anzahl von Feldern in der Tabelle darstellt.|  
|[CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)|Gibt bestimmte Arten von Informationen über die Felder in der Tabelle zurück.|  
|[CDaoTableDef::GetIndexCount](../Topic/CDaoTableDef::GetIndexCount.md)|Gibt die Anzahl von Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)|Gibt bestimmte Arten von Informationen über die Indizes für die Tabelle zurück.|  
|[CDaoTableDef::GetName](../Topic/CDaoTableDef::GetName.md)|Gibt den benutzerdefinierten Namen der Tabelle zurück.|  
|[CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)|Gibt die Anzahl von Datensätzen in der Tabelle zurück.|  
|[CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)|Gibt einen Wert zurück, der den Namen der Tabelle umschlossenen in der Quelldatenbank angibt.|  
|[CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)|Gibt einen Wert zurück, der die Daten in einem Feld überprüft, während es an eine Tabelle geändert oder hinzugefügt wird.|  
|[CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)|Gibt einen Wert zurück, der den Text der Meldung angibt, die die Anwendung angezeigt wird, wenn der Wert eines Feldobjekts nicht die angegebene Validierungsregel erfüllt.|  
|[CDaoTableDef::IsOpen](../Topic/CDaoTableDef::IsOpen.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn die Tabelle geöffnet ist.|  
|[CDaoTableDef::Open](../Topic/CDaoTableDef::Open.md)|Der vorhandene tabledef\-, die in der Tabledefs der Datenbank Auflistung gespeichert wird.|  
|[CDaoTableDef::RefreshLink](../Topic/CDaoTableDef::RefreshLink.md)|Aktualisiert die Verbindungsinformationen für eine umschlossene Tabelle.|  
|[CDaoTableDef::SetAttributes](../Topic/CDaoTableDef::SetAttributes.md)|Legt einen Wert fest, der eine oder mehrere Eigenschaften eines `CDaoTableDef`\-Objekts angibt.|  
|[CDaoTableDef::SetConnect](../Topic/CDaoTableDef::SetConnect.md)|Legt einen Wert fest, der Informationen über die Quelle einer Tabelle enthält.|  
|[CDaoTableDef::SetName](../Topic/CDaoTableDef::SetName.md)|Legt den Namen der Tabelle fest.|  
|[CDaoTableDef::SetSourceTableName](../Topic/CDaoTableDef::SetSourceTableName.md)|Legt einen Wert fest, der den Namen einer Tabelle umschlossenen in der Quelldatenbank angibt.|  
|[CDaoTableDef::SetValidationRule](../Topic/CDaoTableDef::SetValidationRule.md)|Legt einen Wert fest, der die Daten in einem Feld überprüft, während es an eine Tabelle geändert oder hinzugefügt wird.|  
|[CDaoTableDef::SetValidationText](../Topic/CDaoTableDef::SetValidationText.md)|Legt einen Wert fest, der den Text der Meldung angibt, die die Anwendung angezeigt wird, wenn der Wert eines Feldobjekts nicht die angegebene Validierungsregel erfüllt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoTableDef::m\_pDAOTableDef](../Topic/CDaoTableDef::m_pDAOTableDef.md)|Ein Zeiger auf die zugrunde liegenden DAO\-Schnittstelle das Tabledef\-Objekt.|  
|[CDaoTableDef::m\_pDatabase](../Topic/CDaoTableDef::m_pDatabase.md)|Quelldatenbank für diese Tabelle.|  
  
## Hinweise  
 Jedes DAO\-Datenbank\-Objekt verwaltet eine Auflistung, TableDefs aufgerufen, das alle gespeicherten Objekte DAO tabledef\- enthält.  
  
 Sie bearbeiten eine Tabellendefinition mithilfe eines `CDaoTableDef`\-Objekts.  Sie haben unter anderem folgende Möglichkeiten:  
  
-   Überprüfen Sie die Feld\- und Indexstruktur jeder lokalen, angefügten oder externen Tabelle in einer Datenbank.  
  
-   Rufen Sie die `SetConnect` und `SetSourceTableName`\-Memberfunktionen für umbrochene Tabellen, und verwenden Sie die `RefreshLink`\-Memberfunktion, um Verbindungen zu den umschlossenen Tabellen zu aktualisieren.  
  
-   Rufen Sie die `CanUpdate`\-Memberfunktion auf, um zu ermitteln, wenn Sie Eingabefelddefinitionen in der Tabelle können.  
  
-   Abrufen oder Festlegen Validierungszustände mithilfe `GetValidationRule` und `SetValidationRule` und die `GetValidationText` und `SetValidationText`\-Memberfunktionen fest.  
  
-   Verwenden Sie die **Öffnen**\-Memberfunktion, um eine Tabelle, ein Dynaset oder ein Objekt zu erstellen `CDaoRecordset` vom Typ Momentaufnahme.  
  
    > [!NOTE]
    >  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen; DAO\-Klassen bieten im Allgemeinen überlegene Funktionen, da sie an Microsoft Jet\-Datenbankmodul spezifisch sind.  
  
### So Tabledef\-Objekte entweder mit einer vorhandenen Tabelle verwenden oder eine neue Tabelle erstellen  
  
1.  In allen Fällen erstellen Sie zuerst ein `CDaoTableDef`\-Objekt und einen Zeiger angeben zu einem [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)\-Objekt, dem die Tabelle gehört.  
  
2.  Führen Sie dann das folgende, je nachdem, was Sie möchten:  
  
    -   Um eine vorhandene gespeicherte Tabelle zu verwenden, rufen Sie die [Open](../Topic/CDaoTableDef::Open.md)\-Memberfunktion des Tabledef\-Objekts auf, und geben Sie den Namen der gespeicherten Tabelle an.  
  
    -   Um eine neue Tabelle zu erstellen, rufen Sie die [Create](../Topic/CDaoTableDef::Create.md)\-Memberfunktion des Tabledef\-Objekts auf, und geben Sie den Namen der Tabelle an.  Rufen Sie [CreateField](../Topic/CDaoTableDef::CreateField.md) und [CreateIndex](../Topic/CDaoTableDef::CreateIndex.md) auf, um Felder und Indizes der Tabelle hinzuzufügen.  
  
    -   Rufen Sie [Fügen Sie an](../Topic/CDaoTableDef::Append.md) auf, um die Tabelle zu speichern, indem Sie sie in die TableDefs\-Auflistung der Datenbank anfügen.  **Create** setzt tabledef\- in einen geöffneten Zustand, sodass, nachdem es **Create** aufgerufen hat, die Sie nicht **Öffnen** aufrufen.  
  
        > [!TIP]
        >  Die einfachste Möglichkeit, gespeicherte Tabellen zu erstellen, sind sie erstellen und sie in der Datenbank mit Microsoft Access zu speichern.  Anschließend können Sie sie im MFC\-Code öffnen und verwenden.  
  
 Um das Tabledef\-Objekt zu verwenden, das Sie haben sich erstellt oder geöffnet, erstellen und öffnen Sie ein `CDaoRecordset`\-Objekt und den Namen Tabledefs mit einem **dbOpenTable**\-Wert im `nOpenType`\-Parameter angeben.  
  
 Um ein Tabledef\-Objekt mit `CDaoRecordset` ein Objekt zu erstellen, erstellen Sie in der Regel oder öffnen tabledef\- wie oben beschrieben, erstellen ein Recordset\-Objekt und übergeben einen Zeiger auf dem Tabledef\-Objekt wenn Sie [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) aufrufen.  tabledef\-, die an übergeben, muss in einem geöffneten Zustand befinden.  Weitere Informationen finden Sie unter [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)\-Klasse.  
  
 Wenn Sie beenden, ein Tabledef\-Objekt zu verwenden, rufen Sie seine [Schließen Sie](../Topic/CDaoRecordset::Close.md)\-Memberfunktion auf; zerstören Sie dann das Tabledef\-Objekt.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)