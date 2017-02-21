---
title: "Recordset: Dynamisches Binden von Datenspalten (ODBC) | Microsoft Docs"
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
  - "Spalten [C++], Binden an Recordsets"
  - "Datenbindung [C++], Spalten in Recordsets"
  - "Datenbindung [C++], Recordsetspalten"
  - "ODBC-Recordsets [C++], Binden von Spalten (dynamisch)"
  - "Recordsets [C++], Binden von Daten"
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset: Dynamisches Binden von Datenspalten (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Recordsets verwalten das Binden von Tabellenspalten, die Sie in der Entwurfsphase festlegen. Es gibt jedoch Fälle, in denen Sie Spalten binden müssen, die Ihnen während der Entwurfszeit noch nicht bekannt waren.  In diesem Thema wird Folgendes erläutert:  
  
-   [Wann Sie Spalten dynamisch an ein Recordset binden können](#_core_when_you_might_bind_columns_dynamically).  
  
-   [Wie Sie Spalten zur Laufzeit dynamisch binden](#_core_how_to_bind_columns_dynamically).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Die beschriebenen Techniken werden im Allgemeinen nicht empfohlen, falls Sie das gesammelte Abrufen von Zeilen verwenden.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_when_you_might_bind_columns_dynamically"></a> Wann Sie Spalten dynamisch binden können  
 Zur Entwurfszeit werden basierend auf bekannten Tabellen und Spalten der Datenquelle Recordset\-Klassen durch den MFC\-Anwendungs\-Assistenten oder den [MFC\-ODBC\-Consumer\-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) \(unter **Klasse hinzufügen**\) erstellt.  Datenbanken können sich nach der Entwurfszeit ändern, wenn eine Anwendung zur Laufzeit auf diese Tabellen und Spalten zugreift.  Sie und andere Benutzer könnten eine Tabelle hinzufügen oder löschen bzw. Spalten zu einer Tabelle hinzufügen oder löschen. Dies kann auch Tabellen betreffen, auf denen das Recordset der Anwendung basiert.  Dieses Problem betrifft nicht alle Datenzugriffsanwendungen. Wie können Sie jedoch bei Bedarf Änderungen am Datenbankschema vornehmen, ohne die Anwendung neu zu entwerfen und zu kompilieren?  Diese Frage wird in diesem Thema beantwortet.  
  
 In diesem Thema werden die häufigsten Fälle beschrieben, in denen Spalten dynamisch gebunden werden. Bereits erwähnt wurde der Fall eines Recordsets, das auf einem bekannten Datenbankschema basiert und das zur Laufzeit weitere Spalten verarbeiten muss.  In diesem Thema wird vorausgesetzt, dass die zusätzlichen Spalten `CString`\-Felddatenmembern zugeordnet werden. Dieser Fall tritt am häufigsten auf. Wenn Sie außerdem weitere Datentypen benötigen, finden Sie auch hierzu einige Hinweise.  
  
 Mit relativ wenig zusätzlichem Code können Sie:  
  
-   [feststellen, welche Spalten zur Laufzeit zur Verfügung stehen](#_core_to_determine_the_columns_in_a_table_at_run_time);  
  
-   [zur Laufzeit zusätzliche Spalten dynamisch an das Recordset binden](#_core_adding_the_columns).  
  
 Das Recordset enthält weiterhin Datenmember für die Spalten, die in der Entwurfszeit bekannt waren.  Zusätzlich enthält es einige Zeilen Code, der dynamisch ermittelt, ob neue Spalten zur Zieltabelle hinzugefügt wurden, und der in diesem Fall die Spalten an dynamisch reservierten Speicher anbindet \(statt an Datenmember des Recordsets\).  
  
 In diesem Thema werden keine weiteren Fälle dynamischer Bindung z. B. gelöschte Tabellen oder Spalten behandelt.  Für solche Fälle müssen Sie direktere ODBC\-API\-Aufrufe einsetzen.  Weitere Informationen hierzu finden Sie auf der MSDN Library\-CD unter *ODBC SDK Programmer's Reference*.  
  
##  <a name="_core_how_to_bind_columns_dynamically"></a> Dynamisches Binden von Spalten  
 Zum dynamischen Binden von Spalten müssen Sie die Namen der zusätzlichen Spalten kennen oder bestimmen können.  Außerdem müssen Sie für die zusätzlichen Felddatenmember Speicher reservieren, ihre Namen und Typen angeben sowie die Anzahl der hinzugefügten Spalten festlegen.  
  
 In der folgenden Beschreibung werden zwei verschiedene Recordsets behandelt.  Das erste ist das Hauptrecordset, das Datensätze aus der Zieltabelle auswählt.  Das zweite ist ein spezielles Spaltenrecordset, mit dem Sie Informationen über die Spalten in der Zieltabelle ermitteln.  
  
###  <a name="_core_the_general_process"></a> Allgemeine Vorgehensweise  
 Prinzipiell führen Sie folgende Schritte aus:  
  
1.  Konstruieren Sie das Haupt\-Recordset\-Objekt.  
  
     Bei Bedarf können Sie auch einen Zeiger auf ein geöffnetes `CDatabase`\-Objekt übergeben oder dem Spaltenrecordset die Verbindungsinformationen auf andere Weise zur Verfügung stellen.  
  
2.  Fügen Sie dynamisch Spalten hinzu.  
  
     Dieser Prozess wird im folgenden Abschnitt beschrieben.  
  
3.  Öffnen Sie das Hauptrecordset.  
  
     Das Recordset wählt Datensätze aus und bindet mithilfe des Datensatzfeldaustauschs \(Record Field Exchange, RFX\) sowohl die statischen Spalten \(die mit den Felddatenmembern des Recordsets verknüpft sind\) als auch die dynamischen Spalten \(die mit zusätzlich reserviertem Speicher verknüpft sind\).  
  
###  <a name="_core_adding_the_columns"></a> Hinzufügen der Spalten  
 Für das dynamische Binden der hinzugefügten Spalten zur Laufzeit sind folgende Schritte nötig:  
  
1.  Ermitteln Sie zur Laufzeit, welche Spalten die Zieltabelle enthält.  Erstellen Sie aufgrund dieser Informationen eine Liste der Spalten, die zu der Tabelle hinzugefügt wurden, seit die Recordset\-Klasse entworfen wurde.  
  
     Ein guter Ansatz ist der Einsatz einer Spaltenrecordset\-Klasse, mit der Spalteninformationen zur Zieltabelle \(z. B. Spaltenname und Datentyp\) aus der Datenquelle abgerufen werden können.  
  
2.  Stellen Sie Speicher für die neuen Felddatenmember bereit.  Die Hauptrecordset\-Klasse enthält keine Felddatenmember für unbekannte Spalten. Daher müssen Sie einen Platz bereitstellen, an dem die Namen, Ergebniswerte und möglicherweise Datentypinformationen \(falls die Spalten unterschiedliche Datentypen enthalten\) gespeichert werden.  
  
     Ein möglicher Ansatz ist das Erstellen einer oder mehrerer dynamischer Listen, eine für die Namen der neuen Spalten, eine für deren Ergebniswerte und eine dritte für die Datentypen \(bei Bedarf\).  Diese Listen \(besonders die Wertliste\) stellen die Informationen und den notwendigen Speicher für den Bindevorgang zur Verfügung.  Die folgende Abbildung zeigt, wie die Listen erstellt werden.  
  
     ![Listen für dynamisch gebundene Spalten werden erstellt](../../data/odbc/media/vc37w61.png "vc37W61")  
Erstellen von Listen für dynamisch gebundene Spalten  
  
3.  Fügen Sie für jede neu hinzugefügte Spalte einen RFX\-Funktionsaufruf in die `DoFieldExchange`\-Funktion des Hauptrecordsets ein.  Diese RFX\-Aufrufe erledigen die Arbeit, die zum Abrufen eines Datensatzes nötig ist, sowie zum Aufnehmen zusätzlicher Spalten und zum Binden der Spalten an Datenmember des Recordsets oder an dynamisch bereitgestellten Speicher.  
  
     Ein möglicher Ansatz ist es, eine Schleife in die `DoFieldExchange`\-Funktion des Hauptrecordsets einzufügen, in der die Liste der neuen Spalten abgearbeitet und für jede Spalte die entsprechende RFX\-Funktion aufgerufen wird.  Bei jedem RFX\-Aufruf übergeben Sie den Namen einer Spalte aus der Liste der Spaltennamen sowie die Position des zugehörigen Speichermembers in der Liste der Ergebniswerte.  
  
###  <a name="_core_lists_of_columns"></a> Spaltenlisten  
 In der folgenden Tabelle werden die vier Listen aufgeführt, die Sie benötigen.  
  
 [Aktuelle Tabellenspalten \(Liste 1 in der Abbildung\)](#_core_illustration_dynamic)  
 Eine Liste der Spalten, aus denen sich die Tabelle in der Datenquelle momentan zusammensetzt.  Diese Liste stimmt möglicherweise mit der Liste der aktuell im Recordset eingebundenen Spalten überein.  
  
 [Im Recordset gebundene Spalten \(Liste 2 in der Abbildung\)](#_core_illustration_dynamic)  
 Eine Liste der im Recordset gebundenen Spalten.  Für diese Spalten sind bereits RFX\-Anweisungen in der `DoFieldExchange`\-Funktion eingetragen.  
  
 [Dynamisch gebundene Spalten \(Liste 3 in der Abbildung\)](#_core_illustration_dynamic)  
 Eine Liste der Spalten, die in der Tabelle enthalten sind, aber nicht im Recordset.  Diese Spalten müssen Sie dynamisch binden.  
  
 [Werte der dynamisch gebundenen Spalten \(Liste 4 in der Abbildung\)](#_core_illustration_dynamic)  
 Eine Liste mit Speicher für die Werte, die aus den dynamisch gebundenen Spalten abgerufen werden.  Die Elemente dieser Liste sind mit den Spalten verknüpft, die sich an derselben Position in der Liste 3 befinden.  
  
###  <a name="_core_building_your_lists"></a> Erstellen der Listen  
 Nachdem Sie die allgemeine Strategie kennen, können Sie sich den Details zuwenden.  Die im Folgenden beschriebene Vorgehensweise veranschaulicht, wie Sie die im Abschnitt [Spaltenlisten](#_core_lists_of_columns) aufgeführten Listen erstellen.  Die Anleitungen zeigen folgende Schritte:  
  
-   [Ermitteln der Namen aller Spalten, die nicht im Recordset enthalten sind](#_core_determining_which_table_columns_are_not_in_your_recordset)  
  
-   [Bereitstellen von dynamischem Speicher für neu hinzugefügte Tabellenspalten](#_core_providing_storage_for_the_new_columns)  
  
-   [Dynamisches Hinzufügen von RFX\-Aufrufen für neue Spalten](#_core_adding_rfx_calls_to_bind_the_columns)  
  
###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> Ermitteln der Namen aller Spalten, die nicht im Recordset enthalten sind  
 Erstellen Sie eine Liste \("Im Recordset gebundene Spalten" wie in Liste 2 der [Abbildung](#_core_illustration_dynamic)\), die alle im Hauptrecordset gebunden Spalten enthält.  Anschließend erstellen Sie eine Liste \("Dynamisch gebundene Spalten", ermittelt aus den Listen "Aktuelle Tabellenspalten" und "Im Recordset gebundene Spalten"\), die die Namen aller Spalten enthält, die in der Tabelle der Datenquelle enthalten sind, aber nicht im Hauptrecordset.  
  
##### So ermitteln Sie die Namen der Spalten, die nicht im Recordset gebunden sind \(Dynamisch gebundene Spalten\)  
  
1.  Erstellen Sie eine Liste der Spalten \("Im Recordset gebundene Spalten"\), die bereits im Hauptrecordset gebunden sind.  
  
     Ein möglicher Ansatz hierfür ist, die Liste "Im Recordset gebundene Spalten" bereits während der Entwurfszeit zu erstellen.  Sie können die Aufrufe der RFX\-Funktionen in der `DoFieldExchange`\-Funktion des Recordsets visuell untersuchen, um diese Namen zu ermitteln.  Erstellen Sie die Liste anschließend als Array, das mit diesen Namen initialisiert wird.  
  
     Beispielsweise enthält die [Abbildung](#_core_illustration_dynamic) eine Liste "Im Recordset gebundene Spalten" \(Liste 2\) mit drei Elementen.  In der Liste "Im Recordset gebundene Spalten" fehlt die Spalte "Phone", die in der Liste "Aktuelle Tabellenspalten" \(Liste 1\) enthalten ist.  
  
2.  Vergleichen Sie die Listen "Aktuelle Tabellenspalten" und "Im Recordset gebundene Spalten", und erstellen Sie eine Liste der Spalten \("Dynamisch gebundene Spalten"\), die nicht im Hauptrecordset gebunden sind.  
  
     Ein möglicher Ansatz hierfür ist, die beiden Listen "Aktuelle Tabellenspalten" und "Im Recordset gebundene Spalten" zur Laufzeit parallel in einer Schleife zu durchsuchen.  In die Liste "Dynamisch gebundene Spalten" fügen Sie alle Namen der Liste "Aktuelle Tabellenspalten" ein, die nicht in der Liste "Im Recordset gebundene Spalten" angezeigt werden.  
  
     Beispielsweise enthält die [Abbildung](#_core_illustration_dynamic) die Liste "Dynamisch gebundene Spalten" \(Liste 3\) mit einem Element: Der Phone\-Spalte, die in der Liste "Aktuelle Tabellenspalten" \(Liste 1\) gefunden wurde, aber nicht in der Liste "Im Recordset gebundene Spalten" \(Liste 2\).  
  
3.  Erstellen Sie die Liste "Werte der dynamisch gebundenen Spalten" \(Liste 4 in der [Abbildung](#_core_illustration_dynamic)\), in der die Datenwerte gespeichert werden, die den einzelnen Spaltennamen entsprechen, die in der Liste "Dynamisch gebundene Spalten" enthalten sind.  
  
     Die Elemente dieser Liste übernehmen die Rolle neuer Felddatenmember des Recordsets.  Sie stellen die Speicherpositionen dar, an die die dynamischen Spalten gebunden werden.  Eine Beschreibung dieser Listen finden Sie unter [Spaltenlisten](#_core_lists_of_columns).  
  
###  <a name="_core_providing_storage_for_the_new_columns"></a> Bereitstellen von dynamischem Speicher für neu hinzugefügte Tabellenspalten  
 In diesem Schritt richten Sie den Speicher für die dynamisch gebundenen Spalten ein.  Dabei stellen Sie zum Speichern des Werts jeder Spalte ein Listenelement bereit.  Diese Speicherpositionen haben die gleiche Funktion wie die Membervariablen der Recordsets, in denen die Werte statisch gebundener Spalten gespeichert werden.  
  
##### So stellen Sie dynamischen Speicher für neue Spalten bereit \(Werte der dynamisch gebundenen Spalten\)  
  
1.  Erstellen Sie basierend auf den Informationen in der Liste "Dynamisch gebundene Spalten" die Liste "Werte der dynamisch gebundenen Spalten". Diese Liste enthält die Werte der Spaltendaten.  
  
     Beispielsweise enthält die [Abbildung](#_core_illustration_dynamic) eine Liste "Werte der dynamisch gebundenen Spalten" \(Liste 4\) mit einem Element, einem `CString`\-Objekt, das die Telefonnummer aus dem aktuellen Datensatz enthält: "555\-1212".  
  
     In den meisten Fällen unterstützt die Liste "Werte der dynamisch gebundenen Spalten" Elemente des Typs `CString`.  Wenn Sie mit Spalten arbeiten müssen, die verschiedene Datentypen enthalten, benötigen Sie eine Liste, die Elemente verschiedener Datentypen speichern kann.  
  
 Wenn Sie diese Anleitung befolgen, erhalten Sie zwei wichtige Listen: die Liste "Dynamisch gebundene Spalten" enthält die Namen der Spalten und die Liste "Werte der dynamisch gebundenen Spalten" enthält die Werte des aktuellen Datensatzes in diesen Spalten.  
  
> [!TIP]
>  Wenn die neuen Spalten unterschiedliche Datentypen enthalten, können Sie eine weitere Liste anlegen, in der die Typen der entsprechenden Elemente der Spaltenliste definiert sind. \(Sie können dazu die Werte **AFX\_RFX\_BOOL**, **AFX\_RFX\_BYTE** usw. verwenden. Diese Konstanten sind in AFXDB.H definiert.\)  Diese Konstanten sind in AFXDB.H definiert.\) Wählen Sie einen Listentyp, der sich für die Repräsentation der Datentypen eignet.  
  
###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> Hinzufügen von RFX\-Aufrufen zur Bindung der Spalten  
 Bereiten Sie zuletzt die dynamische Bindung vor, indem Sie für die neuen Spalten RFX\-Aufrufe in die `DoFieldExchange`\-Funktion einfügen.  
  
##### So fügen Sie dynamisch RFX\-Aufrufe für neue Spalten hinzu  
  
1.  Fügen Sie in die `DoFieldExchange`\-Memberfunktion des Hauptrecordsets eine Schleife ein, die die Liste der neuen Spalten bearbeitet \(Liste "Dynamisch gebundene Spalten"\).  Extrahieren Sie in jedem Schleifendurchgang einen Spaltennamen aus der Liste "Dynamisch gebundene Spalten" sowie einen Ergebniswert für diese Spalte aus der Liste "Werte der dynamisch gebundenen Spalten".  Übergeben Sie diese Elemente an die zum jeweiligen Datentyp passende RFX\-Funktion.  Eine Beschreibung dieser Listen finden Sie unter [Spaltenlisten](#_core_lists_of_columns).  
  
 In den meisten Fällen extrahieren Sie in `RFX_Text`\-Funktionsaufrufen `CString`\-Objekte aus den Listen. Im folgenden Codeausschnitt ist die Liste "Dynamisch gebundene Spalten" eine `CStringList` mit dem Namen `m_listName`. Die Liste "Dynamisch gebundene Spalten" ist eine `CStringList` mit der Bezeichnung `m_listValue`:  
  
```  
RFX_Text( pFX,   
            m_listName.GetNext( posName ),   
            m_listValue.GetNext( posValue ));  
```  
  
 Weitere Informationen über RFX\-Funktionen finden Sie unter [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md) \(nur auf Englisch verfügbar\) in der *Class Library Reference*.  
  
> [!TIP]
>  Wenn die neuen Spalten unterschiedliche Datentypen aufweisen, können Sie in der Schleife eine switch\-Anweisung verwenden, um die zum jeweiligen Typ passende RFX\-Funktion aufzurufen.  
  
 Wenn das Framework während des **Open**\-Prozesses `DoFieldExchange` aufruft, um Spalten an das Recordset zu binden, werden die statischen Spalten durch die RFX\-Aufrufe gebunden.  Anschließend werden in der von Ihnen eingefügten Schleife wiederholt die RFX\-Funktionen für die dynamischen Spalten aufgerufen.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Arbeiten mit großen Datenelementen \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)