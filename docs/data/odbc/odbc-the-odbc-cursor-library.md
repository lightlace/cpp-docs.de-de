---
title: "ODBC: Die ODBC-Cursorbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cursorbibliothek [ODBC]"
  - "Cursorbibliothek [ODBC], Snapshots"
  - "Cursor, ODBC-Cursorbibliothek"
  - "Level 1-ODBC-Treiber"
  - "ODBC-Cursorbibliothek [ODBC]"
  - "ODBC-Treiber, Cursorunterstützung"
  - "ODBC-Treiber, Ebene 1"
  - "ODBC, Zeitstempel"
  - "Positionierte Aktualisierungen"
  - "Positionieren von Cursorn"
  - "Snapshots, Unterstützung in ODBC"
  - "Statische Cursor"
  - "Timestamps, ODBC-Timestampspalten"
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ODBC: Die ODBC-Cursorbibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die ODBC\-Cursorbibliothek beschrieben und ihre Verwendung erläutert.  Weitere Informationen finden Sie unter:  
  
-   [Cursorbibliothek und Level 1\-ODBC\-Treiber](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [Positionierbare Aktualisierungen und Timestampspalten](#_core_positioned_updates_and_timestamp_columns)  
  
-   [Verwenden der Cursorbibliothek](#_core_using_the_cursor_library)  
  
 Die ODBC\-Cursorbibliothek ist eine Dynamic Link Library \(DLL\), die mit dem ODBC\-Treiber\-Manager und dem Treiber zusammenwirkt.  In ODBC\-Terminologie ausgedrückt unterhält der Treiber einen Cursor, um seine Position innerhalb des Recordsets zu verwalten.  Der Cursor markiert die Position innerhalb des Recordsets, zu dem Sie bereits gescrollt sind – dem aktuellen Datensatz.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> Cursorbibliothek und Level 1\-ODBC\-Treiber  
 Die ODBC\-Cursorbibliothek verleiht Level 1\-Treibern folgende zusätzliche Fähigkeiten:  
  
-   Vorwärts\- und Rückwärtsscrollen.  Für Level 2\-Treiber ist keine Cursorbibliothek erforderlich, da sie bereits scrollbar sind.  
  
-   Unterstützung für Momentaufnahmen.  Die Cursorbibliothek verwaltet einen Puffer mit den Datensätzen der Momentaufnahme.  Dieser Puffer gibt vom Programm vorgenommene Änderungen wieder \(gelöschte und geänderte Datensätze\), jedoch keine Änderungen, die von anderen Benutzern vorgenommen wurden \(hinzugefügte, gelöschte und geänderte Datensätze\).  Die Momentaufnahme ist daher nur so aktuell wie der Puffer der Cursorbibliothek.  Der Puffer gibt hinzugefügte Einträge solange nicht wieder, bis **Requery** aufgerufen wurde.  Dynasets verwenden nicht die Cursorbibliothek.  
  
 Die Cursorbibliothek stellt selbst dann Momentaufnahmen \(statische Cursor\) zur Verfügung, wenn sie vom Treiber nicht unterstützt werden.  Falls der Treiber bereits statische Cursor unterstützt, müssen Sie die Cursorbibliothek nicht laden, um Unterstützung für Momentaufnahmen zu erhalten.  Falls Sie die Cursorbibliothek einsetzen, können Sie ausschließlich Momentaufnahmen und Vorwärts\-Recordsets verwenden.  Falls der Treiber Dynasets \(KEYSET\_DRIVEN\-Cursor\) unterstützt und Sie die Dynasets einsetzen möchten, dürfen Sie die Cursorbibliothek nicht verwenden.  Falls Sie sowohl Momentaufnahmen als auch Dynasets einsetzen möchten, müssen Sie zwei verschiedene `CDatabase`\-Objekte \(zwei verschiedene Verbindungen\) einsetzen, es sei denn, der Treiber unterstützt sowohl Momentaufnahmen als auch Dynasets.  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a> Positionierbare Aktualisierungen und Timestampspalten  
  
> [!NOTE]
>  Auf ODBC\-Datenquellen können Sie über die MFC\-ODBC\-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC\-Datenzugriffsobjekt\-Klassen \(DAO\-Klassen\).  
  
> [!NOTE]
>  Wenn der ODBC\-Treiber **SQLSetPos** unterstützt \(wird von MFC verwendet, falls vorhanden\), können Sie dieses Thema überspringen.  
  
 Die meisten Level 1\-Treiber bieten keine Unterstützung für positionierbare Aktualisierungen.  Für solche Treiber muss die Cursorbibliothek die Fähigkeiten von Level 2\-Treibern emulieren.  Die Cursorbibliothek emuliert die Unterstützung für positionierbare Aktualisierungen, indem sie eine Suchaktualisierung der unveränderlichen Felder durchführt.  
  
 In einigen Fällen kann ein Recordset als eines dieser unveränderlichen Felder eine Timestampspalte enthalten.  Es sind zwei Aspekte zu beachten, wenn MFC\-Recordsets mit Tabellen eingesetzt werden, die Timestampspalten enthalten.  
  
 Der erste Aspekt betrifft aktualisierbare Momentaufnahmen von Tabellen mit Timestampspalten.  Falls die Tabelle, an die die Momentaufnahme gebunden ist, eine Timestampspalte enthält, müssen Sie **Requery** nach dem Aufruf von **Edit** und **Update** aufrufen.  Andernfalls können Sie denselben Datensatz möglicherweise nicht erneut bearbeiten.  Wenn Sie erst **Edit** und dann **Update** aufrufen, wird der Datensatz in die Datenquelle geschrieben, und die Timestampspalte wird aktualisiert.  Falls Sie **Requery** nicht aufrufen, entspricht der Wert des Timestamps des Datensatzes in der Momentaufnahme nicht mehr dem entsprechenden Timestamp in der Datenquelle.  Wenn Sie dann erneut versuchen, den Datensatz zu aktualisieren, verbietet die Datenquelle wegen dieser Diskrepanz möglicherweise die Aktualisierung.  
  
 Der zweite Aspekt betrifft die Beschränkungen der [CTime](../../atl-mfc-shared/reference/ctime-class.md)\-Klasse, wenn diese mit der Funktion `RFX_Date` zur Übertragung von Zeit\- und Datumsinformationen in eine oder aus einer Tabelle verwendet wird.  Die Verarbeitung des `CTime`\-Objekts verursacht Verwaltungsaufwand in Form zusätzlicher Zwischenberechnungen während des Datentransfers.  Außerdem ist der Datumsbereich der `CTime`\-Objekte für manche Anwendungen möglicherweise zu eingeschränkt.  Eine neue Version der `RFX_Date`\-Funktion verwendet als Parameter statt eines `CTime`\-Objekts den ODBC\-Typ **TIMESTAMP\_STRUCT**.  Weitere Informationen finden Sie unter `RFX_Date` unter [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) \(nur auf Englisch verfügbar\) in der *MFC\-Referenz*.  
  
##  <a name="_core_using_the_cursor_library"></a> Verwenden der Cursorbibliothek  
 Wenn Sie die Verbindung zu einer Datenquelle aufbauen, indem Sie [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) oder [CDatabase::Open](../Topic/CDatabase::Open.md) aufrufen, können Sie angeben, ob die Cursorbibliothek für die Datenquelle verwendet werden soll.  Wenn Sie für die Datenquelle Momentaufnahmen anlegen möchten, geben Sie im `dwOptions`\-Parameter von `OpenEx` die Option **CDatabase::useCursorLib** an, oder geben Sie im **bUseCursorLib**\-Parameter von **Open** den Wert **TRUE** an \(**TRUE** ist der Standardwert\).  Verwenden Sie die Cursorbibliothek nicht, falls der ODBC\-Treiber Dynasets unterstützt und Sie Dynasets der Datenquelle öffnen möchten \(hierdurch wird ein Teil der Funktionalität des Treibers überdeckt, die für Dynasets erforderlich ist\).  Übergeben Sie in diesem Fall nicht **CDatabase::useCursorLib** an `OpenEx` oder im **bUseCursorLib**\-Parameter von **Open** den Wert **FALSE**.  
  
## Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)