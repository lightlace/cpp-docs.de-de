---
title: Dynaset | Microsoft Docs
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
ms.openlocfilehash: ec71b5b00b26564f9c8dc3c2d98f53f8182b0ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092317"
---
# <a name="dynaset"></a>Dynaset
In diesem Thema wird beschrieben, Dynasets und erläutert deren [Verfügbarkeit](#_core_availability_of_dynasets).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC-ODBC-Klassen, einschließlich [CRecordset](../../mfc/reference/crecordset-class.md). Informationen zu Dynasets in den DAO-Klassen finden Sie unter [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). Öffnen Sie mit DAO Recordsets Dynaset-Typ.  
  
 Ein Dynaset ist ein Recordset mit dynamischen Eigenschaften. Während seiner Lebensdauer bleibt einem Recordset-Objekt im Dynasetmodus (normalerweise ein Dynaset genannt) auf folgende Weise mit der Datenquelle synchronisiert wird. In einer mehrbenutzerumgebung anderen Benutzern möglicherweise bearbeiten oder Löschen von Datensätzen, die im Dynaset sind oder Datensätze hinzufügen, auf die Tabelle, die Dynaset darstellt. Ihre Anwendung hinzugefügt oder aus dem Recordset Löscht Datensätze werden im Dynaset wiedergegeben. Datensätze, die andere Benutzer zur Tabelle hinzufügen werden nicht im Dynaset wiedergegeben werden, bis Sie das Dynaset durch Aufrufen von neu erstellen, dessen **Requery** Memberfunktion. Wenn andere Benutzer Datensätze löschen, überspringt der MFC-Code der Löschvorgang im Recordset. Bearbeitung Änderungen anderer Benutzer in vorhandenen Datensätze werden in Dynaset wiedergegeben, sobald Sie auf den betroffenen Datensatz einen Bildlauf durchführen.  
  
 Auf ähnliche Weise werden die Änderungen an Datensätzen in einem Dynaset von anderen Benutzern in Dynasets verwendet wiedergegeben. Datensätze, die Sie hinzufügen, werden nicht in anderer Benutzer berücksichtigt, bis sie ihre Dynasets requery. Datensätze, die Sie löschen, werden als "in Recordsets anderer Benutzer gelöscht" gekennzeichnet. Wenn Sie mehrere Verbindungen mit der gleichen Datenbank haben (mehrere `CDatabase` Objekte), Recordsets, die diese Verbindungen zugeordnet haben, als die Recordsets anderer Benutzer den gleichen Status.  
  
 Dynasets sind besonders hilfreich, wenn Daten dynamisch und als (z. B.) in einem bestimmten Reservierungssystem sein müssen.  
  
> [!NOTE]
>  Um Dynasets verwenden zu können, benötigen Sie einen ODBC-Treiber für die Datenquelle, die Dynasets unterstützt und muss nicht die ODBC-Cursorbibliothek geladen werden. Weitere Informationen finden Sie unter [Verfügbarkeit von Dynasets](#_core_availability_of_dynasets).  
  
 Übergeben, um anzugeben, dass ein Recordset ein Dynaset **CRecordset:: Dynaset** als erster Parameter an die **öffnen** -Memberfunktion des Recordset-Objekts.  
  
> [!NOTE]
>  Der ODBC-Treiber muss für aktualisierbare Dynasets entweder positionierte Update-Anweisungen unterstützen oder die **:: SQLSetPos** ODBC API-Funktion. Wenn beide unterstützt, verwendet MFC **:: SQLSetPos** Gründen der Effizienz.  
  
##  <a name="_core_availability_of_dynasets"></a> Verfügbarkeit von Dynasets  
 MFC-Datenbankklassen unterstützen Dynasets, wenn die folgenden Anforderungen erfüllt sind:  
  
-   Der ODBC-Cursorbibliothek DLL muss nicht für diese Datenquelle verwendet werden.  
  
     Wenn die Cursorbibliothek verwendet wird, maskiert er bestimmte Funktionen des zugrunde liegenden ODBC-Treiber, der für Dynasetunterstützung erforderlich ist. Wenn Sie Dynasets verwenden möchten (und der ODBC-Treiber für Dynasets, erforderliche Funktionalität wurde wie in den restlichen Teil dieses Abschnitts beschrieben), veranlassen Sie, dass MFC nicht an die Cursorbibliothek geladen werden, bei der Erstellung einer `CDatabase` Objekt. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [OpenEx](../../mfc/reference/cdatabase-class.md#openex) oder [öffnen](../../mfc/reference/cdatabase-class.md#open) Memberfunktion der Klasse `CDatabase`.  
  
     In der ODBC-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet. Ein Cursor ist ein Mechanismus zum Nachverfolgen der seine Position in einem Recordset.  
  
-   Der ODBC-Treiber für die Datenquelle muss keysetgesteuerte Cursor unterstützen.  
  
     Keysetgesteuerte Cursor verwalten Daten aus einer Tabelle abrufen und speichern einen Satz von Schlüsseln. Die Schlüssel werden verwendet, um die aktuelle Daten aus der Tabelle abrufen, wenn der Benutzer zu einem bestimmten Datensatz wechselt. Aufrufen, um zu bestimmen, ob Ihr Treiber diese Unterstützung ermöglicht, die **:: SQLGetInfo** ODBC API-Funktion mit dem **SQL_SCROLL_OPTIONS** Parameter.  
  
     Wenn Sie versuchen, ein Dynaset ohne Keysetunterstützung öffnen, erhalten Sie eine `CDBException` mit dem Wert des Rückgabecodes **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ausgelöst**.  
  
-   Der ODBC-Treiber für die Datenquelle muss die erweiterte Abrufen unterstützen.  
  
     Erweiterte abrufen, ist die Fähigkeit, einen Bildlauf rückwärts als auch über die resultierenden Datensätze von der SQL-Abfrage weiterleiten. Aufrufen, um zu bestimmen, ob Ihr Treiber diese Fähigkeit unterstützt, die **:: SQLGetFunctions** ODBC API-Funktion mit dem **SQL_API_SQLEXTENDEDFETCH** Parameter.  
  
 Wenn Sie aktualisierbar Dynasets (oder Momentaufnahmen zu) möchten, der ODBC-Treiber muss auch unterstützen entweder die **:: SQLSetPos** ODBC API-Funktion oder positionierte Updates. Die **:: SQLSetPos** Funktion ermöglicht es MFC ermöglicht, die Datenquelle zu aktualisieren, ohne SQL-Anweisungen zu senden. Wenn diese Unterstützung verfügbar ist, verwendet MFC Instanzenmethode vor der Durchführung von Aktualisierungen mit SQL. Um zu bestimmen, ob der Treiber unterstützt **:: SQLSetPos**, rufen Sie **:: SQLGetInfo** mit der **SQL_POS_OPERATIONS** Parameter.  
  
 SQL-Syntax für positionierte Updates verwenden (im Format **WHERE CURRENT OF** \<Cursorname >) um eine bestimmte Zeile in der Tabelle für die Datenquelle zu identifizieren. Um zu bestimmen, ob Ihr Treiber positionierte Updates unterstützt, rufen **:: SQLGetInfo** mit der **SQL_POSITIONED_STATEMENTS** Parameter.  
  
 Im allgemeinen MFC Dynasets (jedoch nicht Forward-only-Recordsets) ist einen ODBC-Treiber mit Level 2-API-Konformität erforderlich. Wenn der Treiber für die Datenquelle der Ebene 1-API-Satz entspricht, können Sie weiterhin aktualisierbar und schreibgeschützt sind und Momentaufnahmen und Forward-only-Recordsets, jedoch keine Dynasets verwenden. Allerdings kann ein Treiber auf Ebene 1 Dynasets, sofern dies erweiterte Abrufen unterstützt und keysetgesteuerte Cursor unterstützt. Weitere Informationen zu ODBC-Übereinstimmungsebenen, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Wenn Sie Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei unterschiedliche Verbindungen).  
  
 Im Gegensatz zu Momentaufnahmen, bei die Zwischenspeicherung verwaltet die ODBC-Cursorbibliothek verwenden, fetch Dynasets einen Datensatz direkt aus der Datenquelle an, sobald Sie ihm einen Bildlauf durchführen. Dadurch wird verhindert, die Datensätze, die ursprünglich ausgewählt, von dem Dynaset mit der Datenquelle synchronisiert.  
  
 Eine Liste der in dieser Version von Visual C++ mitgelieferten ODBC-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC-Treiber](../../data/odbc/odbc-driver-list.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)