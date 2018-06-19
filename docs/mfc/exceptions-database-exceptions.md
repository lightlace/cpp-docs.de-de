---
title: 'Ausnahmen: Datenbank-Ausnahmen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2168bc530accfdde6fad4d41cd68e94d3088f153
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354300"
---
# <a name="exceptions-database-exceptions"></a>Ausnahmen: Datenbankausnahmen
In diesem Artikel wird erläutert, wie Datenbankausnahmen behandelt. Die meisten der Materialien, die in diesem Artikel angewendet wird, ob Sie mit der MFC-Klassen für Open Database Connectivity (ODBC) oder die MFC-Klassen für Datenzugriffsobjekte (DAO) arbeiten. Materialien, die spezifisch für eine oder das andere Modell wird explizit markiert. Folgende Themen werden behandelt:  
  
-   [Ansätze zur Behandlung von Ausnahmen](#_core_approaches_to_exception_handling)  
  
-   [Ein Beispiel für die Datenbank für die Ausnahmebehandlung](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Ansätze zur Behandlung von Ausnahmen  
 Der Ansatz entspricht dem, ob es sich bei der Arbeit mit DAO oder ODBC.  
  
 Sie sollten immer Ausnahmehandler um Ausnahmesituationen schreiben.  
  
 Der am häufigsten pragmatische Ansatz zum Abfangen von Datenbankausnahmen besteht darin, die Anwendung mit Ausnahme von Szenarien zu testen. Bestimmen Sie die wahrscheinlichen Ausnahmen, die für einen Vorgang im Code auftreten, und erzwingen die Ausnahme auftritt. Klicken Sie dann überprüfen Sie die Ablaufverfolgungsausgabe, um festzustellen, welche Ausnahme ausgelöst wird, oder Überprüfen Sie die zurückgegebenen Fehlerinformationen im Debugger. Dadurch können Sie die Rückgabecodes kennen, die Sie für die Ausnahme Szenarien sehen, die Sie verwenden.  
  
### <a name="error-codes-used-for-odbc-exceptions"></a>Fehlercodes für ODBC-Ausnahmen  
 Zusätzlich zu den Rückgabecodes, die vom Framework definiert, wofür Namen im Format **AFX_SQL_ERROR_XXX**, einige [CDBExceptions](../mfc/reference/cdbexception-class.md) basieren auf [ODBC](../data/odbc/odbc-basics.md) Rückgabecodes. Die Rückgabecodes für solche Ausnahmen haben Namen im Format **SQL_ERROR_XXX**.  
  
 Die Rückgabecodes – Framework definierte sowohl ODBC definiert –, die Datenbankklassen zurückkehren können diesbezügliche Dokumentation finden Sie unter der [M_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) Datenmember der Klasse `CDBException`. Zusätzliche Informationen zu den Rückgabecodes, die von ODBC definiert finden Sie im ODBC SDK *Programmer's Reference* in der MSDN Library.  
  
### <a name="error-codes-used-for-dao-exceptions"></a>Fehlercodes für DAO-Ausnahmen  
 Für DAO-Ausnahmen sind weitere Informationen in der Regel verfügbar. Sie können Fehlerinformationen über drei Datenmember eines abgefangenen zugreifen [CDaoException](../mfc/reference/cdaoexception-class.md) Objekt:  
  
-   [M_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) enthält einen Zeiger auf eine [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) Objekt, das Fehlerinformationen in DAO Auflistung der Error-Objekte, die der Datenbank zugeordnete kapselt.  
  
-   [M_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) enthält einen erweiterter Fehlercode aus den MFC-DAO-Klassen. Diese Fehlercodes, deren Namen im Format **AFX_DAO_ERROR_XXX an**, diesbezügliche Dokumentation finden Sie unter den Datenmember in `CDaoException`.  
  
-   [M_scode](../mfc/reference/cdaoexception-class.md#m_scode) enthält eine OLE `SCODE` von DAO, falls zutreffend. Sie müssen nur selten mit diesem Fehlercode jedoch arbeiten. Weitere Informationen ist in der Regel in die anderen zwei Data-Member verfügbar. Finden Sie unter den Datenmember weitere `SCODE` Werte.  
  
 Zusätzliche Informationen über DAO-Fehler, der Objekttyp des DAO-Fehler und DAO Errors-Auflistung finden Sie unter Klasse [CDaoException](../mfc/reference/cdaoexception-class.md).  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> Ein Beispiel für die Datenbank für die Ausnahmebehandlung  
 Im folgenden Beispiel wird versucht, erstellen eine [CRecordset](../mfc/reference/crecordset-class.md)-abgeleitetes Objekt auf dem Heap mit der **neue** -Operator, und öffnen Sie dann das Recordset (für eine ODBC-Datenquelle). Ein ähnliches Beispiel für den DAO-Klassen Siehe "DAO Ausnahme" unten aufgeführte Beispiel.  
  
### <a name="odbc-exception-example"></a>Beispiel für ODBC-Ausnahmen  
 Die [öffnen](../mfc/reference/crecordset-class.md#open) Memberfunktion kann eine Ausnahme auslösen (vom Typ [CDBException](../mfc/reference/cdbexception-class.md) für die ODBC-Klassen), sodass diese code Klammern der **öffnen** rufen Sie mit einer **versuchen**  Block. Die nachfolgenden **catch** catch-Block wird ein `CDBException`. Sie könnten das Ausnahmeobjekt selbst aufgerufen überprüfen `e`, aber in diesem Fall reicht es zu wissen, dass der Versuch, erstellen Sie ein Recordset fehlgeschlagen ist. Die **catch** Block zeigt ein Meldungsfenster an und führt eine Bereinigung durch Löschen des Recordset-Objekts.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]  
  
### <a name="dao-exception-example"></a>Beispiel für DAO-Ausnahme  
 Die DAO-Beispiel ist ähnlich wie im Beispiel für ODBC, aber Sie können verschiedene Arten von Informationen in der Regel abrufen. Der folgende Code versucht auch, ein Recordset zu öffnen. Wenn der Versuch, eine Ausnahme auslöst, können Sie einen Datenmember des Ausnahmeobjekts für Fehlerinformationen untersuchen. Wie im vorherigen Beispiel für ODBC es wahrscheinlich ist ausreichend zu wissen, dass Fehler beim Erstellen von einem Recordset.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]  
  
 Dieser Code Ruft die Zeichenfolge mit einer Fehlermeldung aus der [M_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) Mitglied das Ausnahmeobjekt. MFC füllt bei diesem Member auf, wenn es sich um die Ausnahme auslöst.  
  
 Eine Erläuterung der Fehlerinformationen, die durch eine `CDaoException` Objekt, finden Sie in Klassen [CDaoException](../mfc/reference/cdaoexception-class.md) und [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).  
  
 Bei der Arbeit mit Datenbanken von Microsoft Jet (.mdb) und in den meisten Fällen bei der Arbeit mit ODBC, werden nur ein Error-Objekt. Im seltenen Fall, wenn Sie eine ODBC-Datenquelle verwenden und mehrere Fehler vorliegen, können Sie eine Schleife über DAO Errors-Auflistung, die basierend auf der Anzahl von Fehlern zurückgegebenes [CDaoException:: GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Rufen Sie bei jedem Durchlaufen der Schleife [CDaoException:: GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) zum Auffüllen der `m_pErrorInfo` -Datenmember.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

