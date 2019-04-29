---
title: 'Recordset: Dynamisches Binden von Datenspalten (ODBC)'
ms.date: 11/19/2018
helpviewer_keywords:
- ODBC recordsets [C++], binding columns dynamically
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- columns [C++], binding to recordsets
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
ms.openlocfilehash: c2f2a6a6696f46fb5b8f2777c6c911269c9e7a80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397892"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Recordset: Dynamisches Binden von Datenspalten (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Durch Recordsets verwalten, Bindungstabellenspalten, die Sie zur Entwurfszeit angeben, aber es gibt Fälle, wenn Sie Spalten, die Ihnen unbekannt, zur Entwurfszeit Waren zu binden möchten. In diesem Thema wird Folgendes erläutert:

- [Wenn Sie möchten möglicherweise dynamische Bindung von Spalten zu einem Recordset](#_core_when_you_might_bind_columns_dynamically).

- [Binden von Spalten dynamisch zur Laufzeit](#_core_how_to_bind_columns_dynamically).

> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Die in der Regel beschriebenen Verfahren werden nicht empfohlen, wenn Sie gesammelte verwenden. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_when_you_might_bind_columns_dynamically"></a> Wenn Sie Spalten dynamisch gebunden

Zur Entwurfszeit den MFS-Anwendungsassistenten oder [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (von **Klasse hinzufügen**) Recordset-Klassen basierend auf den bekannten Tabellen und Spalten an der Datenquelle erstellt. Datenbanken können ändern, zwischen beim Entwerfen Sie und höher, wenn Ihre Anwendung Tabellen und Spalten zur Laufzeit verwendet. Sie oder ein anderer Benutzer möglicherweise hinzufügen oder Löschen einer Tabelle hinzufügen oder Löschen von Spalten aus einer Tabelle, der Ihrer Anwendung Recordset verwendet. Dies wahrscheinlich nicht relevant ist für alle Anwendungen der Datenzugriff, aber wenn dies für Ihren eigenen ist, wie Sie stellt Änderungen in das Datenbankschema, außer durch die Umgestaltung und neu kompilieren zu müssen? Der Zweck dieses Themas werden diese Frage zu beantworten.

In diesem Thema wird beschrieben, die am häufigste Vorkommen in der Sie Spalten dynamisch gebunden – ein Recordset basierend auf einem bekannten Datenbankschema begonnen wurde, Sie möchten zusätzliche Spalten zur Laufzeit zu verarbeiten. Das Thema weiter wird davon ausgegangen, dass die zusätzlichen Spalten zuordnen `CString` Feld der Datenmember, die den meisten Fällen auch Vorschläge helfen Ihnen beim Verwalten von anderen Datentypen angegeben werden.

Mit einer geringeren Menge an zusätzlichem Code können Sie folgende Aktionen ausführen:

- [Bestimmen, welche Spalten verfügbar sind, zur Laufzeit](#_core_how_to_bind_columns_dynamically).

- [Binden Sie die zusätzliche Spalten an das Recordset dynamisch zur Laufzeit](#_core_adding_the_columns).

Das Recordset enthält weiterhin Datenelemente für die Spalten, die Sie zur Entwurfszeit bekannt. Außerdem enthält eine kleine Menge an zusätzlichem Code, der dynamisch bestimmt, ob die Zieltabelle alle neuen Spalten hinzugefügt wurden und, wenn dies der Fall ist, bindet diesen neuen Spalten dynamisch zugeordneten Speicher (anstatt auf Recordsetdatenmember).

Dieses Thema deckt sich nicht auf andere dynamische Bindung-Fällen, z. B. gelöschte Tabellen oder Spalten aus. Für diese Fälle müssen Sie ODBC-API-Aufrufe direkt zu verwenden. Informationen finden Sie in der ODBC-SDK *Programmer's Reference* auf der MSDN Library-CD.

##  <a name="_core_how_to_bind_columns_dynamically"></a> Wie Sie dynamisch binden von Spalten

Um Spalten dynamisch zu binden, müssen Sie wissen (oder ermitteln) die Namen der zusätzlichen Spalten. Sie müssen auch belegen von Speicher für die zusätzliche Felddatenmember, ihre Namen und ihre Typen und geben Sie die Anzahl der Spalten, die Sie hinzufügen möchten.

Die folgende erläuterungen werden zwei verschiedene Recordsets behandelt. Die erste ist die Haupt-Recordset, das Datensätze aus der Zieltabelle auswählt. Die zweite ist eine spezielle Spalte-Recordset, das zum Abrufen von Informationen zu den Spalten in die Zieltabelle verwendet werden.

###  <a name="_core_the_general_process"></a> Allgemeine Prozess

Auf der höchsten allgemeinen, gehen Sie folgendermaßen vor:

1. Erstellen Sie Ihre wichtigsten Recordset-Objekt.

   Übergeben Sie optional einen Zeiger auf eine offene `CDatabase` Objekt oder in der Lage, Verbindungsinformationen auf andere Weise auf die Spalte anzugeben.

1. Führen Sie die Schritte aus, um Spalten dynamisch hinzuzufügen.

   Finden Sie im folgenden Abschnitt beschriebenen Prozess aus.

1. Öffnen Sie Ihre Haupt-Recordset.

   Das Recordset werden Datensätze ausgewählt und Datensatzfeldaustausch (RFX) verwendet, um sowohl die statische Spalten (die Recordset-Felddatenmembern) als auch die dynamische Spalten (zugeordnet zu zusätzlichen Speicherplatz, der zugewiesen werden) zu binden.

###  <a name="_core_adding_the_columns"></a> Hinzufügen von Spalten

Dynamisches Binden von hinzugefügt Spalten zur Laufzeit erfordert die folgenden Schritte aus:

1. Bestimmen Sie zur Laufzeit, welche Spalten in der Zieltabelle enthalten sind. Extrahieren Sie anhand dieser Informationen eine Liste der Spalten, die in der Tabelle hinzugefügt wurden, seit die Recordset-Klasse entworfen wurde.

   Ein guter Ansatz ist die Verwendung eine Spalte Recordset-Klasse, die dazu vorgesehen, die die Datenquelle für die Spalteninformationen für die Zieltabelle (z. B. Name und Typ) abzufragen.

1. Bereitstellen von Speicher für den neuen Felddatenmembern. Da die Haupt-Recordset-Klasse nicht Felddatenmember für unbekannte Spalten verfügt, müssen Sie einen Ort zum Speichern der Namen, Ergebniswerte und möglicherweise Informationen, (wenn die Spalten unterschiedliche Datentypen sind) bereitstellen.

   Ein Ansatz ist die Erstellung eine oder mehrere dynamische Listen, einen Namen für die neuen Spalten, eine andere für die Ergebniswerte und eine dritte für ihre Datentypen (falls erforderlich). Diese Listen, insbesondere der Werteliste, geben Sie die Informationen und der notwendigen Speicher für die Bindung. Die folgende Abbildung veranschaulicht das Erstellen von Listen.

   ![Erstellen von Listen für dynamisch gebundene Spalten](../../data/odbc/media/vc37w61.gif "Erstellen von Listen für dynamisch gebundene Spalten")<br/>
   Erstellen von Listen für dynamisch gebundene Spalten

1. Hinzufügen von RFX-Funktion in Ihrer Haupt-Recordsets `DoFieldExchange` -Funktion für jede Spalte hinzugefügt. Diese Aufrufe RFX erledigen der Arbeit einen Datensatz abrufen, einschließlich der zusätzlichen Spalten und Binden der Spalten auf Recordsetdatenmember oder dynamisch bereitgestellten Speicher für diese.

   Ein Ansatz besteht darin, eine Schleife des main Recordsets hinzufügen `DoFieldExchange` -Funktion, die der Liste mit den neuen Spalten, die die entsprechende RFX-Funktionen aufrufen, für jede Spalte in der Liste durchläuft. Übergeben Sie bei jedem Aufruf RFX einen Spaltennamen aus der Liste der Spaltennamen und einen Speicherort in den entsprechenden Member der Liste der Ergebnis-Wert.

###  <a name="_core_lists_of_columns"></a> Listen von Spalten

Die vier aufgelistet, denen Sie zusammenarbeiten möchten, werden in der folgenden Tabelle angezeigt.

|||
|-|-|
|**Current-Table-Columns**| (Liste 1 in der Abbildung) Eine Liste der Spalten derzeit in der Tabelle in der Datenquelle. Diese Liste kann die Liste der Spalten, die derzeit im Recordset gebunden übereinstimmen.|
|**Bound-Recordset-Columns**| (Liste 2 in der Abbildung) Eine Liste der Spalten, die in Recordsets gebunden werden. Diese Spalten verfügen bereits über RFX-Anweisungen in Ihre `DoFieldExchange` Funktion.|
|**Columns-To-Bind-Dynamically**| (Liste 3 in der Abbildung) Eine Liste der Spalten in der Tabelle, aber nicht im Recordset. Dies sind die Spalten, die Sie dynamisch binden möchten.|
|**Dynamic-Spaltenwerte**| (Liste 4 in der Abbildung) Eine Liste mit Speicher für die Werte, die aus den Spalten, die Sie dynamisch binden abgerufen werden. Elemente der Liste entsprechen den in Spalten um-dynamisch, 1: 1.|

###  <a name="_core_building_your_lists"></a> Erstellen der Listen

Beachten Sie die allgemeine Strategie können Sie zu aktivieren. Die Verfahren in den weiteren Verlauf dieses Themas, in dem Sie zeigen, wie Sie die aufgeführten Listen erstellen [Spaltenlisten](#_core_lists_of_columns). Die Verfahren führen Sie durch:

- [Bestimmen der Namen von Spalten nicht im Recordset](#_core_determining_which_table_columns_are_not_in_your_recordset).

- [Bereitstellen von dynamischem Speicher für neu zur Tabelle hinzugefügten Spalten](#_core_providing_storage_for_the_new_columns).

- [Dynamisches Hinzufügen von RFX Aufrufe für neue Spalten](#_core_adding_rfx_calls_to_bind_the_columns).

###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> Bestimmen die Tabelle Spalten sind nicht im Recordset

Erstellen Sie eine Liste (Recordset-Spalten, wie in Liste 2 in der Abbildung), die enthält eine Liste der Spalten im Hauptmenü Recordsets gebunden. Dann erstellen Sie eine Liste (Spalten--dynamisch gebundene, Aktuelle-Tabellenspalten und gebundene Recordsets Spalten abgeleitet), die Spaltennamen enthält, die in der Tabelle für die Datenquelle jedoch nicht im Hauptmenü Recordset befinden.

##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Um zu bestimmen, die Namen der Spalten nicht im Recordset (-Bind-dynamisch Spalten)

1. Erstellt eine Dateiliste (Recordset-Spalten), die Spalten, die bereits im Hauptmenü Recordset gebunden.

   Ein Ansatz besteht darin Recordset-Spalten zur Entwurfszeit zu erstellen. Sie können in der Recordsets RFX-Funktionsaufrufe visuell untersuchen `DoFieldExchange` Funktion, um diese Namen abzurufen. Richten Sie dann der Liste ein, als ein Array mit den Namen initialisiert.

   Die Abbildung zeigt z. B. die gebundene Recordsets Spalten (Liste 2) mit drei Elementen. Recordset-Spalten fehlt die Phone-Spalte in der aktuellen Tabelle-Spalten (Liste 1) dargestellt.

1. Vergleichen Sie die aktuellen-Tabellenspalten und Recordset-Spalten, um eine Liste der Spalten, die noch nicht im Hauptmenü Recordset gebunden (-Bind-dynamisch Spalten) zu erstellen.

   Ein Ansatz ist die Liste der Spalten in der Tabelle zur Laufzeit (Aktuelle-Tabellenspalten) und die Liste der Spalten, die bereits im Recordset (Recordset-Spalten) gebunden sind, parallel durchlaufen. Fügen Sie in Spalten um-dynamisch alle Namen in der aktuellen Tabelle-Spalten, die nicht in die gebundene Recordsets Spalten angezeigt werden.

   Die Abbildung zeigt beispielsweise-Bind-dynamisch Spalten (Liste 3) mit einem Element: der Phone-Spalte, die gefunden wurde, in der aktuellen Tabelle-Spalten (Liste 1), aber nicht in die gebundene Recordsets Spalten (Liste 2).

1. Erstellen Sie eine Liste der dynamischen Werte (wie in der Liste 4 in der Abbildung), in dem die Datenwerte, die für jeden Spaltennamen in der Liste mit den für dynamisch gebundene Spalten gespeichert (Spalten--dynamisch gebundene) gespeichert.

   Die Elemente dieser Liste spielen die Rolle des neuen Recordset-Felddatenmember. Sie sind die Speicherorte, an denen die dynamische Spalten gebunden sind. Beschreibungen der Listen, finden Sie unter [Spaltenlisten](#_core_lists_of_columns).

###  <a name="_core_providing_storage_for_the_new_columns"></a> Bereitstellen von Speicher für die neuen Spalten

Richten Sie als Nächstes Speicherorte für die Spalten dynamisch gebunden werden. Die Idee ist, geben Sie ein Listenelement in der jede Spalte der Wert gespeichert. Diese Speicherorte parallel die Recordset-Membervariablen, die die Regel gebundenen Spalten zu speichern.

#### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Von dynamischen Speicher für neue Spalten (Dynamic-Spaltenwerte)

1. Erstellen Sie dynamische Werte, parallel zur Spalten--dynamisch gebundene, den Wert der Daten in den einzelnen Spalten enthalten.

   Die Abbildung zeigt z. B. dynamische Werte (Liste 4) mit einem Element: eine `CString` -Objekt, das die tatsächliche Telefonnummer für den aktuellen Datensatz enthält: "555-1212".

   Im häufigsten Fall hat Dynamic-Spaltenwerte Elemente des Typs `CString`. Wenn Sie mit Spalten mit unterschiedlichen Datentypen arbeiten, benötigen Sie eine Liste, die Elemente einer Vielzahl von Typen enthalten kann.

Das Ergebnis der vorherigen Prozeduren ist die zwei wichtigsten Listen: Bind-dynamisch Spalten mit den Namen der Spalten und dynamische Werte, die die Werte in den Spalten für den aktuellen Datensatz.

> [!TIP]
> Wenn die neuen Spalten nicht alle den gleichen Datentyp sind, sollten Sie eine weitere Liste Elemente enthält, die den Typ der entsprechenden Elemente irgendwie in der Liste der Spalten zu definieren. (Können Sie die Werte AFX_RFX_BOOL AFX_RFX_BYTE und so weiter, für diesen, wenn Sie möchten. Diese Konstanten sind in AFXDB definiert. H.) Wählen Sie eine Liste basierend auf, wie Sie die Spaltendatentypen darstellen.

###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> Hinzufügen von RFX-Aufrufe zum Binden von Spalten

Bereiten Sie die dynamische Bindung platzieren ausgeführt werden, indem RFX-Aufrufe für die neuen Spalten in Ihrer `DoFieldExchange` Funktion.

##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>RFX-Aufrufe für neue Spalten dynamisch hinzugefügt

1. In Ihrer Haupt-Recordsets `DoFieldExchange` Member funktioniert, fügen Sie Code, der die Liste der neuen Spalten (Spalten--dynamisch gebundene) durchläuft. Extrahieren Sie in jeder Schleife einen Spaltennamen aus-Bind-dynamisch Spalten und einen Ergebniswert für die Spalte aus der dynamischen Werte aus. Übergeben Sie diese Elemente auf ein Funktionsaufruf RFX entsprechenden in den Datentyp der Spalte. Beschreibungen der Listen, finden Sie unter [Spaltenlisten](#_core_lists_of_columns).

In den meisten Fällen in Ihre `RFX_Text` Funktionsaufrufe, die Sie extrahieren `CString` Objekte aus den Listen, wie in der folgenden Codezeilen, in denen-Bind-dynamisch Spalten ist eine `CStringList` aufgerufen `m_listName` und Dynamic-Spaltenwerte ist eine `CStringList` namens `m_listValue`:

```cpp
RFX_Text( pFX,
            m_listName.GetNext( posName ),
            m_listValue.GetNext( posValue ));
```

Weitere Informationen über RFX-Funktionen finden Sie unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in die *Klassenbibliotheksreferenz*.

> [!TIP]
> Wenn die neuen Spalten verschiedene Datentypen sind, verwenden Sie eine Switch-Anweisung in der Schleife, um die entsprechenden RFX-Funktionen für jeden Typ aufzurufen.

Wenn das Framework ruft `DoFieldExchange` während der `Open` Prozess zum Binden von Spalten an das Recordset, Aufrufe der RFX, für die statische Spalten die Spalten zu binden. Klicken Sie dann ruft Ihre Schleife wiederholt RFX-Funktionen für die dynamische Spalten.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Arbeiten mit großen Datenelementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)