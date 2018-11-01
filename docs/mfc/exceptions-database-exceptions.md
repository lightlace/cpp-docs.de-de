---
title: 'Ausnahmen: Datenbankausnahmen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 17a52787462301e839cb2e960fad8b480380ba49
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492796"
---
# <a name="exceptions-database-exceptions"></a>Ausnahmen: Datenbankausnahmen

In diesem Artikel wird erläutert, wie Datenbankausnahmen behandelt werden. Die meisten das Material in diesem Artikel gilt, ob Sie mit der MFC-Klassen für Open Database Connectivity (ODBC) oder die MFC-Klassen für Datenzugriffsobjekte (DAO) arbeiten. Materialien, die spezifisch für eine oder das andere Modell wird explizit markiert. Folgende Themen werden behandelt:

- [Ansätze zur Behandlung von Ausnahmen](#_core_approaches_to_exception_handling)

- [Ein Beispiel für die Datenbank für die Ausnahmebehandlung](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a> Ansätze zur Behandlung von Ausnahmen

Der Ansatz ist gleich, ob Sie mit DAO oder ODBC-arbeiten.

Sie sollten immer Ausnahmehandler zum Behandeln von Ausnahmebedingungen schreiben.

Der praktischste Ansatz zum Abfangen von Datenbankausnahmen ist zum Testen Ihrer Anwendung mit Ausnahmeszenarios. Bestimmen Sie, die wahrscheinlichen Ausnahmen, die für einen Vorgang im Code auftreten, und erzwingen, dass die Ausnahme auftritt. Klicken Sie dann überprüfen Sie die Ausgabe der Ablaufverfolgung, um festzustellen, welche Ausnahme ausgelöst wird, oder Überprüfen Sie die zurückgegebenen Fehlerinformationen im Debugger. Dadurch können Sie die Rückgabecodes kennen, die Sie für die Ausnahmeszenarios sehen, die Sie verwenden.

### <a name="error-codes-used-for-odbc-exceptions"></a>Fehlercodes für ODBC-Ausnahmen

Zusätzlich zu den Rückgabecodes, die vom Framework definiert sind, haben die Namen im Format **AFX_SQL_ERROR_XXX**einige [CDBExceptions](../mfc/reference/cdbexception-class.md) basieren auf [ODBC](../data/odbc/odbc-basics.md) Rückgabecodes. Die Rückgabecodes für solche Ausnahmen haben Namen im Format **SQL_ERROR_XXX**.

Die Rückgabecodes – Framework definierten sowohl ODBC-definierten –, die Datenbankklassen zurückkehren können, sind unter dokumentiert die [M_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) Datenmember der Klasse `CDBException`. Weitere Informationen zu Rückgabecodes, die von ODBC definiert sind verfügbar, in der ODBC-SDK *Programmer's Reference* in der MSDN Library.

### <a name="error-codes-used-for-dao-exceptions"></a>Fehlercodes für DAO-Ausnahmen

DAO-Ausnahmen sind weitere Informationen in der Regel zur Verfügung. Sie können auf Informationen zugreifen, über drei Datenmember eines abgefangenen [CDaoException](../mfc/reference/cdaoexception-class.md) Objekt:

- [M_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) enthält einen Zeiger auf eine [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) Objekt, das Fehlerinformationen in der DAO-Auflistung der Error-Objekte, die der Datenbank zugeordnete kapselt.

- [M_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) enthält einen erweiterter Fehlercode, die von den MFC-DAO-Klassen. Diese Fehlercodes, deren Namen im Format **AFX_DAO_ERROR_XXX an**, sind unter der Datenmember in dokumentiert `CDaoException`.

- [M_scode](../mfc/reference/cdaoexception-class.md#m_scode) enthält eine OLE **SCODE** von DAO, falls zutreffend. Sie müssen nur selten mit diesem Fehlercode jedoch zu arbeiten. In der Regel ist die Informationen in die anderen zwei Mitglieder verfügbar. Finden Sie unter den Datenmember für Weitere Informationen zu **SCODE** Werte.

Weitere Informationen zu den DAO-Fehler, der Objekttyp von DAO-Fehler und die fehlerauflistung für DAO finden Sie unter Klasse [CDaoException](../mfc/reference/cdaoexception-class.md).

##  <a name="_core_a_database_exception.2d.handling_example"></a> Ein Beispiel für die Datenbank für die Ausnahmebehandlung

Im folgenden Beispiel wird versucht, erstellen eine [CRecordset](../mfc/reference/crecordset-class.md)-abgeleitetes Objekt, auf dem Heap mit der **neue** -Operator, und öffnen Sie das Recordset (für eine ODBC-Datenquelle). Ein ähnliches Beispiel für den DAO-Klassen finden Sie unter "DAO-Ausnahme Example" unten.

### <a name="odbc-exception-example"></a>Beispiel für ODBC-Ausnahme

Die [öffnen](../mfc/reference/crecordset-class.md#open) Memberfunktion möglicherweise eine Ausnahme ausgelöst (des Typs [CDBException](../mfc/reference/cdbexception-class.md) für die ODBC-Klassen), also das code Klammern die `Open` rufen Sie mit einer **versuchen Sie es** Block. Die nachfolgenden **catch** Block fängt eine `CDBException`. Sie können überprüfen, das Ausnahmeobjekt selbst aufgerufen `e`, aber in diesem Fall ist es ausreichend zu wissen, dass beim Versuch, ein Recordset fehlgeschlagen ist. Die **catch** Block zeigt ein Meldungsfeld an, und bereinigen, indem Sie beim Löschen des Recordsetobjekts.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Beispiel für DAO-Ausnahme

Die DAO-Beispiel ist ähnlich wie im Beispiel für ODBC, aber Sie können weitere Arten von Informationen in der Regel abrufen. Der folgende Code versucht auch, ein Recordset zu öffnen. Wenn die, die versuchen, eine Ausnahme auslöst, können Sie ein Mitglied von Daten für das Ausnahmeobjekt für Fehlerinformationen überprüfen. Wie im vorherigen Beispiel für ODBC es wahrscheinlich ist ausreichend zu wissen, dass Fehler beim Erstellen einer Datensatzgruppe.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Dieser Code ruft folgender Fehlermeldungszeichenfolge aus der [M_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) Mitglied über das Ausnahmeobjekt. MFC füllt diesen Member an, beim Auslösen der Ausnahme.

Informationen zu den Fehlerinformationen von einem `CDaoException` Objekt, finden Sie in Klassen [CDaoException](../mfc/reference/cdaoexception-class.md) und [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).

Bei der Arbeit mit Datenbanken der Microsoft Jet (.mdb), und klicken Sie in den meisten Fällen, wenn Sie mit dem ODBC-arbeiten, werden nur ein Fehlerobjekt. In dem seltenen Fall, wenn Sie eine ODBC-Datenquelle verwenden und es mehrere Fehler auftreten gibt, können Sie eine Schleife über DAO Errors-Auflistung, die basierend auf der Anzahl von Fehlern, die vom [CDaoException:: GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Rufen Sie jedes Mal beim Durchlaufen der Schleife [CDaoException:: GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) zum Auffüllen der `m_pErrorInfo` -Datenmember.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

