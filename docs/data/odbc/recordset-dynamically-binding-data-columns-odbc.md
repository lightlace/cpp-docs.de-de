---
title: 'Recordset: Dynamisches Binden von Datenspalten (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets [C++], binding columns dynamically
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- columns [C++], binding to recordsets
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9fe71707de20ba02228039e5693cab9c9401d560
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093385"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Recordset: Dynamisches Binden von Datenspalten (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Recordsets verwalten Bindungstabellenspalten, die Sie zur Entwurfszeit angeben, aber es gibt Fälle, wenn Sie Spalten, die Sie nicht bekannt, zur Entwurfszeit Waren zu binden möchten. In diesem Thema wird Folgendes erläutert:  
  
-   [Wenn Sie möchten möglicherweise Spalten dynamisch zu einem Recordset binden](#_core_when_you_might_bind_columns_dynamically).  
  
-   [Binden von Spalten dynamisch zur Laufzeit](#_core_how_to_bind_columns_dynamically).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. In der Regel beschriebenen Techniken werden nicht empfohlen, wenn Sie gesammelte verwenden. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_when_you_might_bind_columns_dynamically"></a> Wenn Sie Spalten dynamisch gebunden  
 Zur Entwurfszeit, MFC-Anwendung-Assistenten oder [MFC-ODBC-Consumer-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (aus **Klasse hinzufügen**)-Recordset-Klassen basierend auf bekannten Tabellen und Spalten für die Datenquelle erstellt. Das Wechseln von Datenbanken können zwischen beim Entwerfen, wenn Ihre Anwendung Tabellen und Spalten zur Laufzeit verwendet. Sie oder ein anderer Benutzer möglicherweise hinzufügen oder löschen eine Tabelle oder hinzufügen oder Löschen von Spalten aus einer Tabelle, der Ihre Anwendung Recordset abhängt Dies ist möglicherweise nicht relevant für alle formularbasierten datenzugriffsanwendungen, jedoch ist für Ihre, wie können Sie eine mit Änderungen am Datenbankschema, außer durch die Neugestaltung und neu kompilieren zu müssen? In diesem Thema dient diese Frage zu beantworten.  
  
 In diesem Thema wird beschrieben, die am häufigste Vorkommen in der Spalten dynamisch binden, müssen mit einem Recordset basierend auf einer bekannten Datenbankschema begonnen, zur Laufzeit zusätzliche Spalten behandelt werden sollen. Das Thema weiter wird davon ausgegangen, dass die zusätzlichen Spalten zuordnen `CString` Felddatenmember, der häufigste Fall ist, obwohl Vorschläge zum helfen Ihnen beim Verwalten von anderen Datentypen angegeben werden.  
  
 Mit minimalem zusätzlichen Code können Sie folgende Aktionen ausführen:  
  
-   [Bestimmen, welche Spalten zur Laufzeit verfügbar sind](#_core_how_to_bind_columns_dynamically).  
  
-   [Binden Sie die zusätzliche Spalten an das Recordset dynamisch zur Laufzeit](#_core_adding_the_columns).  
  
 Das Recordset enthält weiterhin Datenmember für die Spalten, die Sie zur Entwurfszeit kennen. Außerdem enthält eine kleine Menge an zusätzlichem Code, der dynamisch bestimmt, ob die Zieltabelle keine neuen Spalten hinzugefügt wurden und, wenn dies der Fall ist, bindet diese neuen Spalten dynamisch zugeordneten Speicher (anstatt Recordset Datenmembern).  
  
 Dieses Thema deckt sich nicht auf andere dynamische Bindung-Fällen, z. B. gelöschten Tabellen oder Spalten aus. Für diesen Fällen müssen Sie ODBC-API-Aufrufe direkt verwenden. Informationen finden Sie im ODBC-SDK *Programmer's Reference* auf der MSDN Library-CD.  
  
##  <a name="_core_how_to_bind_columns_dynamically"></a> Gewusst wie: Dynamisches Binden von Spalten  
 Um Spalten dynamisch zu binden, müssen Sie wissen, (oder bestimmen können) die Namen der zusätzlichen Spalten. Sie müssen auch Zuordnen von Speicher für die zusätzlichen Felddatenmember, geben Sie ihren Namen und ihre Typen und geben Sie die Anzahl der Spalten, die Sie hinzufügen.  
  
 Die folgende Darstellung bietet behandelt zwei verschiedene Recordsets. Das erste ist die Haupt-Recordset, das Datensätze aus der Zieltabelle auswählt. Das zweite ist eine spezielle Spaltenrecordset wird zum Abrufen von Informationen zu den Spalten in die Zieltabelle.  
  
###  <a name="_core_the_general_process"></a> Allgemeiner Prozess  
 Die allgemeinste Ebene gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie Ihre wichtigsten Recordset-Objekt.  
  
     Übergeben Sie optional einen Zeiger auf ein offenes `CDatabase` Objekt oder werden Verbindungsinformationen für die Spaltenrecordset auf andere Weise bereitstellen können.  
  
2.  Führen Sie die Schritte aus, um Spalten dynamisch hinzuzufügen.  
  
     Finden Sie unter Hinzufügen von Spalten, die unten beschriebenen Prozess.  
  
3.  Öffnen Sie die Haupt-Recordset.  
  
     Das Recordset wählt Datensätze und Datensatzfeldaustausch (RFX) verwendet, um die statischen Spalten (die Recordset-Felddatenmembern zugeordnet sind) und die dynamische Spalten (zugeordnet zu zusätzlichen Speicherplatz, der zugewiesen werden) zu binden.  
  
###  <a name="_core_adding_the_columns"></a> Hinzufügen von Spalten  
 Dynamisches Binden von hinzugefügt Spalten zur Laufzeit erfordert die folgenden Schritte aus:  
  
1.  Zur Laufzeit bestimmen Sie, welche Spalten in der Zieltabelle sind. Extrahieren von Informationen eine Liste der Spalten, die in der Tabelle hinzugefügt wurden, da Recordset-Klasse entworfenen.  
  
     Ein guter Ansatz ist die Verwendung eine Spalte Recordset-Klasse, die zum Abfragen der Datenquelle für die Spalteninformationen für die Zieltabelle (z. B. Name und Typ) entwickelt.  
  
2.  Bereitstellen von Speicher für den neuen Felddatenmembern. Da die Haupt-Recordset-Klasse keine Felddatenmember für unbekannte Spalten, müssen Sie einen Ort zum Speichern von Namen, Ergebniswerte und möglicherweise Datentypinformationen (wenn die Spalten unterschiedliche Datentypen sind) bereitstellen.  
  
     Eine Möglichkeit besteht darin mindestens eine dynamische Liste, eine für die neuen Spalten Namen, einen anderen für ihre Ergebniswerte und eine dritte für ihre Datentypen (falls erforderlich) erstellen. Diese Listen, insbesondere der Werteliste, geben Sie die Informationen und der notwendigen Speicher für die Bindung. Die folgende Abbildung veranschaulicht die Listen erstellen.  
     ![Erstellen von Listen für dynamisch gebundene Spalten](../../data/odbc/media/vc37w61.gif "vc37w61")  
Erstellen von Listen für dynamisch gebundene Spalten  
  
3.  Fügen Sie einen RFX-Funktionsaufruf in des Haupt-Recordsets `DoFieldExchange` -Funktion für jede Spalte hinzugefügt. Abrufen eines Datensatzes, einschließlich der zusätzlichen Spalten gebunden, und die Spalten Recordset Datenmembern oder dynamisch bereitgestellten Speicher für sie passen diese RFX-Aufrufe.  
  
     Eine Möglichkeit besteht darin, eine Schleife die Haupt-Recordsets hinzufügen `DoFieldExchange` -Funktion, die die Liste der neuen Spalten, die entsprechende RFX-Funktion für jede Spalte in der Liste aufrufen durchläuft. Übergeben Sie bei jedem Aufruf RFX einen Spaltennamen aus der Liste der Spaltennamen und einen Speicherort in das entsprechende Element in der Ergebnisliste Wert ein.  
  
###  <a name="_core_lists_of_columns"></a> Listen von Spalten  
 In der folgenden Tabelle werden die vier Listen mit benötigten angezeigt.  
  
 **Aktuelle-Tabellenspalten (Liste 1 in der Abbildung)** eine Liste der Spalten derzeit in der Tabelle für die Datenquelle. Diese Liste kann die Liste der Spalten, die derzeit im Recordset gebunden überein.  
  
 **Gebundene Recordset Spalten (Liste 2 in der Abbildung)**  
 Eine Liste der Spalten, die im Recordset gebunden werden. Diese Spalten verfügen bereits über RFX-Anweisungen in Ihrem `DoFieldExchange` Funktion.  
  
 **Spalten--dynamisch gebundene (Liste 3 in der Abbildung)**  
 Eine Liste der Spalten in der Tabelle jedoch nicht im Recordset. Dies sind die Spalten, die Sie dynamisch binden möchten.  
  
 **Dynamic-Spaltenwerte (Liste 4 in der Abbildung)**  
 Eine Liste mit Speicher für die Werte, die aus den Spalten, die Sie dynamisch binden abgerufen werden. Elemente dieser Liste entsprechen den in Spalten um-dynamisch gebundene, eins zu eins.  
  
###  <a name="_core_building_your_lists"></a> Erstellen Ihre Listen  
 Eine allgemeine Strategie Bedenken können Sie in den Details deaktivieren. Die Verfahren in diesem Thema veranschaulichen das Erstellen Sie der Listen gezeigt [Spaltenlisten](#_core_lists_of_columns). Die Schritte führen Sie durch:  
  
-   [Bestimmen die Namen der Spalten, die nicht im Recordset](#_core_determining_which_table_columns_are_not_in_your_recordset).  
  
-   [Bereitstellen von dynamischen Speicher für Spalten der Tabelle neu hinzugefügt](#_core_providing_storage_for_the_new_columns).  
  
-   [Dynamisches Hinzufügen von RFX-Aufrufe für neue Spalten](#_core_adding_rfx_calls_to_bind_the_columns).  
  
###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> Bestimmen die Tabelle Spalten sind nicht in Recordsets  
 Erstellen Sie eine Liste ("im Recordset gebundene Spalten, wie in der Liste 2 in der Abbildung), die eine Liste der Spalten, die bereits im Hauptfenster Recordset gebunden enthält. Anschließend erstellen Sie eine Liste (Spalten--dynamisch gebundene, Aktuelle Tabellenspalten und Recordset gebundene Spalten abgeleitet), die Spaltennamen enthält, die in der Tabelle für die Datenquelle jedoch nicht in die Haupt-Recordset sind.  
  
##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Um zu bestimmen, die Namen der Spalten, die nicht im Recordset (Spalten--dynamisch gebundene)  
  
1.  Erstellt eine Dateiliste (gebundene Recordset Spalten) der Spalten, die bereits im Hauptfenster Recordset gebunden.  
  
     Ein Ansatz besteht darin Recordset gebundene Spalten zur Entwurfszeit zu erstellen. Sie können die RFX-Funktionsaufrufe in des Recordsets visuell untersuchen `DoFieldExchange` Funktion, um diese Namen abrufen. Richten Sie dann der Liste ein, als ein Array mit den Namen initialisiert.  
  
     Die Abbildung zeigt z. B. gebundene Recordset Spalten (Liste 2) mit drei Elementen. Recordset gebundene Spalten fehlt die Phone-Spalte in der aktuellen Tabelle Spalten (Liste 1) dargestellt.  
  
2.  Vergleichen Sie die aktuelle Tabellenspalten und Recordset gebundene Spalten aus, um eine Liste der Spalten, die nicht bereits im Hauptfenster Recordset gebunden (Spalten--dynamisch gebundene) zu erstellen.  
  
     Ein besteht Ansatz darin, durchlaufen Sie die Liste der Spalten in der Tabelle zur Laufzeit (Aktuelle-Tabellenspalten) und die Liste der Spalten, die bereits im Recordset (Recordset-Spalten) parallel gebunden. Fügen Sie in Spalten um-dynamisch gebundene alle Namen in der aktuellen Tabelle-Spalten, die nicht im Recordset gebundene Spalten angezeigt werden.  
  
     Die Abbildung zeigt beispielsweise Spalten--dynamisch gebundene (Liste 3) mit je einem Element: der Phone-Spalte in der aktuellen Tabelle Spalten (Liste 1), jedoch nicht in der Liste "im Recordset gebundene Spalten" (Liste 2) gefunden.  
  
3.  Erstellen Sie eine Liste der dynamische Werte (wie in der Liste 4 in der Abbildung), in dem die Datenwerte entspricht jeder Spaltenname in der Liste der für dynamisch gebundene Spalten gespeichert (Spalten--dynamisch gebundene) gespeichert.  
  
     Die Elemente dieser Liste spielen eine Rolle des neuen Recordset Felddatenmember. Sie sind die Speicherorte, an denen die dynamische Spalten gebunden sind. Beschreibungen der Listen, finden Sie unter [Spaltenlisten](#_core_lists_of_columns).  
  
###  <a name="_core_providing_storage_for_the_new_columns"></a> Bereitstellen von Speicher für die neuen Spalten  
 Richten Sie als Nächstes Speicherorte für die Spalten dynamisch gebunden werden. Die Idee ist, geben Sie ein Listenelement in der jede Spalte Wert gespeichert. Diese Speicherorte parallele Membervariablen der Recordsets, die die Regel gebundenen Spalten zu speichern.  
  
##### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Zum Bereitstellen von dynamischen Speicher für neue Spalten (Dynamic-Spaltenwerte)  
  
1.  Erstellen Sie dynamische Werte, parallel zur Spalten--dynamisch gebundene, den Wert der Daten in den einzelnen Spalten enthalten.  
  
     Die Abbildung zeigt z. B. Dynamic-Spaltenwerte (Liste 4) mit je einem Element: eine `CString` Objekt, das die tatsächliche Nummer für den aktuellen Datensatz enthält: "555-1212".  
  
     In den meisten Fällen hat Dynamic-Spaltenwerte Elemente des Typs `CString`. Wenn Sie mit Spalten mit unterschiedlichen Datentypen arbeiten, benötigen Sie eine Liste, die Elemente einer Reihe verschiedener Typen enthalten kann.  
  
 Das Ergebnis der vorherigen Prozeduren ist zwei wichtigsten Listen:-Bind-dynamisch Spalten mit den Namen der Spalten und Dynamic--Spaltenwerte mit den Werten in den Spalten für den aktuellen Datensatz.  
  
> [!TIP]
>  Wenn die neuen Spalten nicht alle den gleichen Datentyp sind, sollten Sie eine weitere Liste Elemente enthält, die den Typ der entsprechenden Elemente in der Spaltenliste aus irgendeinem Grund definieren. (Verwenden Sie die Werte **AFX_RFX_BOOL**, **AFX_RFX_BYTE**und so weiter für diesen, wenn Sie möchten. Diese Konstanten werden in AFXDB definiert. H.) Wählen Sie eine Liste basierend auf wie die Spaltendatentypen darstellen.  
  
###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> Hinzufügen von RFX-Aufrufe zum Binden von Spalten  
 Bereiten Sie die dynamische Bindung durch Platzieren von sein RFX-Aufrufe für die neue Spalten in Ihrer `DoFieldExchange` Funktion.  
  
##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>RFX-Aufrufe für neue Spalten dynamisch hinzufügen  
  
1.  In des Haupt-Recordsets `DoFieldExchange` Member-Funktion, fügen Sie Code, der die Liste der neuen Spalten (Spalten--dynamisch gebundene) durchläuft. Extrahieren Sie in jeder Schleife einen Spaltennamen aus den Spalten "dynamisch" und "für die Spalte aus der dynamischen Spaltenwerte einen Ergebniswert. Übergeben Sie diese Elemente für einen RFX-Funktionsaufruf in den Datentyp der Spalte geeignet. Beschreibungen der Listen, finden Sie unter [Spaltenlisten](#_core_lists_of_columns).  
  
 In den meisten Fällen in Ihrem `RFX_Text` Funktionsaufrufe, die Sie extrahieren `CString` Objekte aus den Listen, wie in den folgenden Codezeilen, die Spalten--dynamisch gebundene steht eine `CStringList` aufgerufen `m_listName` und dynamische Spaltenwerte ist eine `CStringList` aufgerufen `m_listValue`:  
  
```  
RFX_Text( pFX,   
            m_listName.GetNext( posName ),   
            m_listValue.GetNext( posValue ));  
```  
  
 Weitere Informationen über RFX-Funktionen finden Sie unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in der *Klassenbibliotheksreferenz*.  
  
> [!TIP]
>  Wenn die neuen Spalten unterschiedliche Datentypen aufweisen, verwenden Sie eine Switch-Anweisung in der Schleife, um die entsprechende RFX-Funktion für jeden Typ aufzurufen.  
  
 Wenn das Framework ruft `DoFieldExchange` während der **öffnen** Prozess zum Binden von Spalten an das Recordset, die Aufrufe der RFX, für die statische Spalten die Spalten zu binden. Anschließend ruft die Schleife wiederholt RFX-Funktionen für die dynamische Spalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Arbeiten mit großen Datenelementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)