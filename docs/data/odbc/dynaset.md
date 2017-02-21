---
title: "Dynaset | Microsoft Docs"
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
  - "Cursorbibliothek [ODBC], Dynasetverfügbarkeit"
  - "Cursor [ODBC], Schlüsselgruppengesteuerte Cursor in Dynasets"
  - "Dynasets"
  - "Schlüsselgruppengesteuerte Cursor in Dynasets"
  - "ODBC-Cursorbibliothek [ODBC], Dynasets"
  - "ODBC-Recordsets, Dynasets"
  - "Recordsets [C++], Dynasets"
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Dynaset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden Dynasets und deren [Verfügbarkeit](#_core_availability_of_dynasets) beschrieben.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen, einschließlich [CRecordset](../../mfc/reference/crecordset-class.md).  Informationen zu Dynasets in den DAO\-Klassen finden Sie unter [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  Mit DAO können Recordsets vom Typ **Dynaset** geöffnet werden.  
  
 Ein Dynaset ist ein Recordset mit dynamischen Eigenschaften.  Während seiner Lebensdauer wird ein Recordset\-Objekt im Dynasetmodus \(normalerweise einfach als "Dynaset" bezeichnet\) auf folgende Weise mit der Datenquelle synchronisiert:  In einer Mehrbenutzerumgebung können andere Benutzer Datensätze löschen oder bearbeiten, die im Dynaset enthalten sind. Ebenso können sie Datensätze zu der Tabelle hinzufügen, die durch das Dynaset repräsentiert wird.  Datensätze, die die Anwendung dem Recordset hinzufügt oder daraus löscht, werden im Dynaset entsprechend wiedergegeben.  Datensätze, die andere Benutzer der Tabelle hinzufügen, werden nicht im Dynaset wiedergegeben, bis Sie das Dynaset durch Aufruf seiner **Requery**\-Memberfunktion neu erstellen.  Wenn andere Benutzer Datensätze löschen, überspringt der MFC\-Code die gelöschten Datensätze im Recordset.  Die von anderen Benutzern vorgenommenen Änderungen an vorhandenen Datensätzen werden im Dynaset wiedergegeben, sobald Sie zum jeweiligen Datensatz wechseln.  
  
 Ebenso werden Änderungen, die Sie an Datensätzen eines Dynasets vorgenommen haben, in Dynasets anderer Benutzer angezeigt.  Datensätze, die Sie hinzugefügt haben, werden in den Dynasets anderer Benutzer so lange nicht angezeigt, bis diese ihre Dynasets neu abfragen.  Datensätze, die Sie gelöscht haben, werden in den Recordsets anderer Benutzer als "gelöscht" markiert.  Falls mehrere Verbindungen mit derselben Datenbank bestehen \(mehrere `CDatabase`\-Objekte\), weisen die über diese Verbindungen verknüpften Recordsets denselben Status auf wie die Recordsets anderer Benutzer.  
  
 Dynasets sind besonders nützlich, wenn Daten dynamisch verwaltet werden müssen, z. B. beim Reservierungssystem einer Fluggesellschaft.  
  
> [!NOTE]
>  Um Dynasets verwenden zu können, muss ein ODBC\-Treiber für die Datenquelle verfügbar sein, der Dynasets unterstützt. Außerdem darf die ODBC\-Cursorbibliothek nicht geladen sein.  Weitere Informationen hierzu finden Sie unter [Verfügbarkeit von Dynasets](#_core_availability_of_dynasets).  
  
 Um festzulegen, dass ein Recordset ein Dynaset sein soll, übergeben Sie im ersten Parameter der **Open**\-Memberfunktion des Recordset\-Objekts den Wert **CRecordset::dynaset**.  
  
> [!NOTE]
>  Für aktualisierbare Dynasets muss der ODBC\-Treiber entweder positionierbare Aktualisierungsanweisungen oder die **::SQLSetPos**\-ODBC\-API\-Funktion unterstützen.  Werden beide unterstützt, verwendet MFC aus Effizienzgründen **::SQLSetPos**.  
  
##  <a name="_core_availability_of_dynasets"></a> Verfügbarkeit von Dynasets  
 Die MFC\-Datenbankklassen unterstützen Dynasets, falls die folgenden Erfordernisse erfüllt sind:  
  
-   Die ODBC\-Cursorbibliotheks\-DLL darf nicht für diese Datenquelle verwendet werden.  
  
     Falls die Cursorbibliothek verwendet wird, überdeckt sie einen Teil der Funktionalität des zugrunde liegenden ODBC\-Treibers, die für die Dynasetunterstützung benötigt wird.  Wenn Sie Dynasets verwenden möchten und der ODBC\-Treiber die erforderliche Dynasetfunktionalität aufweist, die später in diesem Abschnitt beschrieben wird, können Sie MFC bei der Erstellung eines `CDatabase`\-Objekts veranlassen, die Cursorbibliothek nicht zu laden.  Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) sowie in den Beschreibungen der [OpenEx](../Topic/CDatabase::OpenEx.md)\-Memberfunktion oder der [Open](../Topic/CDatabase::Open.md)\-Memberfunktion der `CDatabase`\-Klasse.  
  
     In der ODBC\-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet.  Ein Cursor ist ein Tool, um die Position innerhalb eines Recordsets zu verwalten.  
  
-   Der ODBC\-Treiber für die Datenquelle muss keysetgesteuerte Cursor unterstützen.  
  
     Keysetgesteuerte Cursor verwalten Daten einer Tabelle, indem sie einen Satz von Schlüsseln abrufen und speichern.  Mithilfe der Schlüssel werden die aktuellen Daten der Tabelle abgerufen, sobald der Benutzer zu einem bestimmten Datensatz wechselt.  Um herauszufinden, ob ein Treiber diese Unterstützung bietet, rufen Sie die **::SQLGetInfo**\-ODBC\-API\-Funktion mit dem **SQL\_SCROLL\_OPTIONS**\-Parameter auf.  
  
     Falls Sie versuchen, ein Dynaset ohne Keysetunterstützung zu öffnen, wird eine `CDBException` mit dem Rückgabecodewert **AFX\_SQL\_ERROR\_DYNASET\_NOT\_SUPPORTED** ausgelöst.  
  
-   Der ODBC\-Treiber für die Datenquelle muss das erweiterte Abrufen unterstützen.  
  
     Erweitertes Abrufen ist die Fähigkeit, vorwärts und rückwärts zwischen den Ergebnisdatensätzen einer SQL\-Abfrage zu wechseln.  Um herauszufinden, ob der aktuelle Treiber diese Unterstützung bietet, rufen Sie die **::SQLGetFunctions**\-ODBC\-API\-Funktion mit dem **SQL\_API\_SQLEXTENDEDFETCH**\-Parameter auf.  
  
 Wenn Sie aktualisierbare Dynasets oder Momentaufnahmen benötigen, muss der ODBC\-Treiber außerdem entweder die **::SQLSetPos**\-ODBC\-API\-Funktion oder positionierbare Aktualisierungen unterstützen.  Mithilfe der **::SQLSetPos**\-Funktion ist MFC in der Lage, die Datenquelle zu aktualisieren, ohne SQL\-Anweisungen zu senden.  Wenn diese Unterstützung zur Verfügung steht, wird sie durch MFC verwendet, statt Aktualisierungen mit SQL durchzuführen.  Um herauszufinden, ob der aktuelle Treiber **::SQLSetPos** unterstützt, rufen Sie die **::SQLGetInfo**\-ODBC\-API\-Funktion mit dem **SQL\_POS\_OPERATIONS**\-Parameter auf.  
  
 Syntax der positionierbaren Aktualisierungen wird mithilfe der SQL\-Syntax Formular **WHERE CURRENT OF** \<cursorname\>\) zu einer bestimmten Zeile in der Tabelle der Datenquelle identifiziert.  Um herauszufinden, ob der aktuelle Treiber positionierbare Aktualisierungen unterstützt, rufen Sie die **::SQLGetInfo**\-ODBC\-API\-Funktion mit dem **SQL\_POSITIONED\_STATEMENTS**\-Parameter auf.  
  
 Im Allgemeinen erfordern MFC\-Dynasets, nicht jedoch Vorwärts\-Recordsets, einen Level 2 API\-konformen ODBC\-Treiber.  Falls der Treiber für die Datenquelle dem Level 1 API\-Satz entspricht, können zwar sowohl aktualisierbare, schreibgeschützte Momentaufnahmen und Vorwärts\-Recordsets verwendet werden, jedoch keine Dynasets.  Ein Level 1\-Treiber kann allerdings Dynasets unterstützen, falls er erweiterte Abfragen und keysetgesteuerte Cursor unterstützt.  Weitere Informationen über ODBC\-Konformitätsebenen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Wenn sowohl Momentaufnahmen als auch Dynasets verwendet werden sollen, müssen diese auf zwei verschiedenen `CDatabase`\-Objekten, also zwei unterschiedlichen Verbindungen basieren.  
  
 Im Gegensatz zu Momentaufnahmen, die eine temporäre Speicherung verwenden, die durch die ODBC\-Cursorbibliothek verwaltet wird, werden Datensätze bei Dynasets direkt bei der Datenquelle abgefragt, sobald zu dem Datensatz gewechselt wird.  So bleiben die ursprünglich von dem Dynaset ausgewählten Datensätze mit der Datenquelle synchronisiert.  
  
 Eine Liste der in dieser Version von Visual C\+\+ mitgelieferten ODBC\-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC\-Treiber](../../data/odbc/odbc-driver-list.md).  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)