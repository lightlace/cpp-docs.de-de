---
title: Dynaset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5bd6abb1985ca50e7f63e600452b826972d403f1
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340429"
---
# <a name="dynaset"></a>Dynaset
In diesem Thema wird beschrieben, Dynasets und erläutert deren [Verfügbarkeit](#_core_availability_of_dynasets).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC-ODBC-Klassen, einschließlich [CRecordset](../../mfc/reference/crecordset-class.md). Informationen zu Dynasets in den DAO-Klassen finden Sie unter [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). Sie können mit DAO Recordsets vom Typ Dynaset öffnen.  
  
 Ein Dynaset ist ein Recordset mit dynamischen Eigenschaften. Während seiner Lebensdauer bleibt einem Recordset-Objekt im Dynasetmodus (in der Regel als ein Dynaset bezeichnet) auf folgende Weise mit der Datenquelle synchronisiert. In einer mehrbenutzerumgebung anderen Benutzern möglicherweise bearbeiten oder Löschen von Datensätzen, die im Dynaset oder Hinzufügen von Datensätzen in die Tabelle, die Dynaset darstellt. Datensätze, die Ihre Anwendung hinzufügt oder löscht aus dem Recordset werden im Dynaset wiedergegeben. Datensätze, die in der Tabelle weitere Benutzer hinzufügen werden nicht im Dynaset wiedergegeben werden, bis Sie Dynaset durch Aufrufen von neu erstellen, dessen `Requery` Member-Funktion. Wenn andere Benutzer Einträge löschen, werden die löschungen im Recordset MFC-Code übersprungen. Anderer Benutzer Änderungen an vorhandenen Datensätze werden in Dynaset wiedergegeben, sobald Sie auf den betreffenden Eintrag scrollen.  
  
 Auf ähnliche Weise werden Änderungen an Datensätzen in ein Dynaset in Dynasets verwendet von anderen Benutzern übernommen. Datensätze, die Sie hinzufügen, werden nicht in anderer Benutzer wiedergegeben, bis sie ihre Dynasets requery. Datensätze, die Sie löschen, werden als "in Recordsets anderer Benutzer gelöscht" markiert. Wenn Sie mehrere Verbindungen mit der gleichen Datenbank haben (mehrere `CDatabase` Objekte), Recordsets, die diese Verbindungen zugeordnet haben denselben Status wie die Recordsets anderer Benutzer.  
  
 Dynasets sind besonders nützlich, wenn die Daten dynamisch als (z. B.) an ein Fluglinien-Reservierungssystem werden müssen.  
  
> [!NOTE]
>  Um Dynasets verwenden zu können, benötigen Sie einen ODBC-Treiber für die Datenquelle, die Dynasets unterstützt, und die ODBC-Cursorbibliothek nicht geladen werden muss. Weitere Informationen finden Sie unter [Verfügbarkeit von Dynasets](#_core_availability_of_dynasets).  
  
 Übergeben, um anzugeben, dass ein Recordset ein Dynaset `CRecordset::dynaset` als erster Parameter an die `Open` -Memberfunktion des Recordset-Objekts.  
  
> [!NOTE]
>  Für Dynasets aktualisierbare, muss der ODBC-Treiber unterstützen entweder positionierte Update-Anweisungen oder `::SQLSetPos` ODBC API-Funktion. Beide unterstützt, verwendet MFC `::SQLSetPos` für Effizienz.  
  
##  <a name="_core_availability_of_dynasets"></a> Verfügbarkeit von Dynasets  
 Die MFC-Datenbankklassen unterstützen Dynasets aus, wenn die folgenden Anforderungen erfüllt sind:  
  
-   Die ODBC-Cursorbibliothek DLL muss nicht für diese Datenquelle verwendet werden.  
  
     Wenn die Cursorbibliothek verwendet wird, maskiert es einige Funktionen des zugrunde liegenden ODBC-Treibers, der für die Dynasetunterstützung erforderlich ist. Wenn Sie Dynasets verwenden möchten (und des ODBC-Treibers für Dynasets, erforderliche Funktionalität wie in den restlichen Teil dieses Abschnitts beschrieben), Sie können dazu führen, dass MFC nicht über die Cursorbibliothek zu laden, bei der Erstellung einer `CDatabase` Objekt. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [OpenEx](../../mfc/reference/cdatabase-class.md#openex) oder [öffnen](../../mfc/reference/cdatabase-class.md#open) Memberfunktion der Klasse `CDatabase`.  
  
     In der ODBC-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet. Ein Cursor ist ein Mechanismus zum Verfolgen von seiner Position in einem Recordset.  
  
-   Der ODBC-Treiber für die Datenquelle muss es sich um keysetgesteuerte Cursor unterstützen.  
  
     Keysetgesteuerte Cursor verwalten Sie Daten aus einer Tabelle abrufen und speichern Sie einen Satz von Schlüsseln. Der Schlüssel werden verwendet, um die aktuelle Daten aus der Tabelle abrufen, wenn der Benutzer auf einen bestimmten Datensatz verschiebt. Aufrufen, um zu bestimmen, ob ein Treiber diese Unterstützung bietet, die `::SQLGetInfo` ODBC-API-Funktion mit dem *SQL_SCROLL_OPTIONS* Parameter.  
  
     Wenn Sie versuchen, ein Dynaset ohne Keysetunterstützung öffnen, erhalten Sie eine `CDBException` mit dem Rückgabecode Wert AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ausgelöst.  
  
-   Der ODBC-Treiber für die Datenquelle muss die erweiterte Abrufen unterstützen.  
  
     Abrufen der erweiterten ist die Möglichkeit, einen Bildlauf rückwärts als auch über die sich ergebende Datensätze von der SQL-Abfrage weiterleiten. Aufrufen, um zu bestimmen, ob Ihr Treiber diese Möglichkeit unterstützt, die `::SQLGetFunctions` ODBC-API-Funktion mit dem *SQL_API_SQLEXTENDEDFETCH* Parameter.  
  
 Sie aktualisierbare Dynasets (oder Momentaufnahmen, eigentlich) können Ihren ODBC-Treiber muss auch unterstützen entweder die `::SQLSetPos` ODBC API-Funktion oder positionierte Updates. Die `::SQLSetPos` Funktion ermöglicht es MFC ermöglicht, die Datenquelle zu aktualisieren, ohne SQL-Anweisungen zu senden. Wenn diese Unterstützung verfügbar ist, verwendet MFC es gegenüber Werten bevorzugt, Durchführen von Updates mithilfe von SQL an. Um festzustellen, ob der Treiber unterstützt `::SQLSetPos`, rufen Sie `::SQLGetInfo` mit der *SQL_POS_OPERATIONS* Parameter.  
  
 SQL-Syntax für positionierte Updates verwenden (im Format **WHERE CURRENT OF** \<Cursorname >) um eine bestimmte Zeile in der Tabelle in der Datenquelle zu identifizieren. Aufrufen, um zu bestimmen, ob Ihr Treiber positionierte Updates unterstützt, `::SQLGetInfo` mit der *SQL_POSITIONED_STATEMENTS* Parameter.  
  
 Im allgemeinen MFC Dynasets (aber nicht Forward-only-Recordsets) ist einen ODBC-Treiber mit der Stufe 2-API-Standards erforderlich. Wenn der Treiber für die Datenquelle der API-Satz von Ebene 1 entspricht, können Sie weiterhin aktualisierbar und schreibgeschützt Momentaufnahmen und Forward-only-Recordsets, jedoch keine Dynasets. Allerdings kann die ein Treiber auf Ebene 1 Dynasets, falls dies erweiterte Abrufen unterstützt und keysetgesteuerte Cursor unterstützen. Weitere Informationen zu ODBC-Konformitätsgrad, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Wenn Sie sowohl Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei verschiedene Verbindungen).  
  
 Im Gegensatz zu Momentaufnahmen, bei die temporäre Speicherung von der ODBC-Cursorbibliothek verwaltet verwenden, werden Dynasets Datensatz direkt aus der Datenquelle wird, sobald Sie damit einen Bildlauf durchführen. Auf diese Weise die Datensätze, die mit der Datenquelle synchronisiert Dynaset ursprünglich ausgewählt.  
  
 Eine Liste der in dieser Version von Visual C++ mitgelieferten ODBC-Treiber sowie Informationen zum Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC-Treiber](../../data/odbc/odbc-driver-list.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)