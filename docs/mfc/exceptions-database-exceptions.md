---
title: "Ausnahmen: Datenbankausnahmen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], Ausnahmen"
  - "Datenbankausnahmen [C++]"
  - "Datenbanken [C++], Ausnahmebehandlung"
  - "Fehlercodes [C++], Datenbankausnahmebehandlung"
  - "Ausnahmebehandlung [C++], Datenbanken"
  - "Ausnahmen [C++], Datenbank"
  - "ODBC [C++], Ausnahmen"
  - "ODBC-Ausnahmen [C++]"
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmen: Datenbankausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie Datenbankausnahmen behandelt.  Die Großteil des Materials in diesem Artikel gilt, dass Sie mit MFC\-Klassen für ODBC \(Open Database Connectivity\) oder MFC\-Klassen für Datenzugriffsobjekte \(DAO\) arbeiten.  Material Spezielle um einen oder anderen Modell wird explizit markiert.  Folgende Themen werden behandelt:  
  
-   [Herangehensweisen für die Ausnahmebehandlung](#_core_approaches_to_exception_handling)  
  
-   [Ein Datenbankausnahmebehandlungsbeispiel](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Herangehensweisen für die Ausnahmebehandlung  
 Der Ansatz ist gleich, ob Sie mit DAO oder ODBC arbeiten.  
  
 Sie sollten zu den Ausnahmehandler außergewöhnlichen Zuständen des Handles immer schreiben.  
  
 Der pragmatischste Ansatz zu von Datenbankausnahmen ist, die Anwendung mit Ausnahmeszenarien zu testen.  Bestimmen der wahrscheinlichen Ausnahmen, die möglicherweise für eine Operation im Code auftreten, und erzwingen Sie die Ausnahme, um zu fungieren.  Untersuchen Sie dann die Ablaufverfolgungsausgabe, um anzuzeigen, welche Ausnahme ausgelöst wird, oder die Fehlerinformationen zurückgegebenen im Debugger zu überprüfen.  Dieses informiert Sie, welche Rückgabecodes Sie für die Ausnahmeszenarien finden, die Sie verwenden.  
  
### Fehlercodes verwendet für ODBC\-Ausnahmen  
 Neben den Rückgabecodes, die vom Framework, Namen des Formulars **AFX\_SQL\_ERROR\_XXX** definiert sind, sind entweder [CDBExceptions](../mfc/reference/cdbexception-class.md) auf [ODBC](../data/odbc/odbc-basics.md) Rückgabecodes.  Die Rückgabecodes für solche Ausnahmen über Namen des Formulars **SQL\_ERROR\_XXX**.  
  
 Die Rückgabecodes \- vom Framework definiert und ODBC\-definiert \- dem die Datenbankklassen zurückgeben können, werden im [m\_nRetCode](../Topic/CDBException::m_nRetCode.md) \- Datenmember der Klasse `CDBException` dokumentiert.  Zusätzliche Informationen zur Rückgabecodes, die mit ODBC definiert sind, ist in ODBC SDK Programmer's Reference in der MSDN Library verfügbar.  
  
### Fehlercodes verwendet für DAO\-Ausnahmen  
 Für DAO\-Ausnahmen sind weitere Informationen normalerweise verfügbar.  Sie können Fehlerinformationen auf durch drei Datenmember eines abgefangenen [CDaoException](../mfc/reference/cdaoexception-class.md)\-Objekts zugreifen:  
  
-   [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) enthält einen Zeiger auf ein [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md), das in Fehlerobjekten Fehlerinformationen Auflistung DAO kapselt, die der Datenbank zugeordnet werden.  
  
-   [m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md) enthält einen erweiterten Fehlercode aus den MFC\-DAO\-Klassen.  Diese Fehlercodes, Namen des Formulars **AFX\_DAO\_ERROR\_XXX** haben, werden unter dem Datenmember in `CDaoException` dokumentiert.  
  
-   [m\_scode](../Topic/CDaoException::m_scode.md) enthält ein OLE `SCODE` von DAO, sofern zutreffend.  Sie müssen selten mit diesem Fehlercode, funktionieren jedoch.  Normalerweise sind weitere Informationen in den anderen zwei Datenmember verfügbar.  Siehe den Datenmember für mehr über `SCODE`\-Werte.  
  
 Zusätzliche Informationen über DAO\-Fehler, den DAO\-Fehlerobjekttyp und die DAO\-Fehlerauflistung unterliegt Klasse [CDaoException](../mfc/reference/cdaoexception-class.md) verfügbar.  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> Ein Datenbank\-Ausnahmebehandlungs\-Beispiel  
 Im folgenden Beispiel versucht, Erstellen [CRecordset](../mfc/reference/crecordset-class.md) abgeleitetes Objekt auf dem Heap mit dem Operator **neu**, und Recordset dann zu öffnen \(für eine ODBC\-Datenquelle.\)  Ein Ähnliches Beispiel für die DAO\-Klassen, finden Sie unter "DAO\-Ausnahme\-Beispiel" unten.  
  
### ODBC\-Ausnahme\-Beispiel  
 Die Memberfunktion [Öffnen](../Topic/CRecordset::Open.md) kann eine Ausnahme des Typs [CDBException](../mfc/reference/cdbexception-class.md) \(für die ODBC\-Klassen\), d Klammern diesem Code auslösen der **Öffnen** Aufruf mit einem **try**\-Block.  Der folgenden **catch**\-Block fängt `CDBException` ab.  Sie könnten das Ausnahmeobjekt selbst überprüfen, `e`, jedoch ist es in diesem Fall ausreichend, zu wissen, dass der Test, ein Recordset erstellen fehlgeschlagen ist.  Der **catch**\-Block wird ein Meldungsfeld angezeigt und bereinigt, indem das Recordset\-Objekt löscht.  
  
 [!CODE [NVC_MFCDatabase#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDatabase#36)]  
  
### DAO\-Ausnahme\-Beispiel  
 Das DAO\-Beispiel ist beispielsweise für ODBC vergleichbar, jedoch können Sie weitere Arten von Informationen in der Regel ab.  Der folgenden Code versucht auch, ein Recordset öffnen.  Wenn dieser Versuch eine Ausnahme auslöst, einen Datenmember des Ausnahmeobjekts für Fehlerinformationen überprüfen.  Wie im vorherigen ODBC\-Beispiel, ist es wahrscheinlich genug, zu wissen, dass der Test, ein Recordset erstellen konnte.  
  
 [!CODE [NVC_MFCDatabase#37](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDatabase#37)]  
  
 Dieser Code ruft eine Fehlermeldungszeichenfolge vom [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)\-Member des Ausnahmeobjekts ab.  MFC füllt diesen Member aus, wenn die Ausnahme auslöst.  
  
 Eine Erörterung die Fehlerinformationen, die durch ein `CDaoException`\-Objekt zurückgegeben werden, finden Sie Klassen [CDaoException](../mfc/reference/cdaoexception-class.md) und [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).  
  
 Wenn Sie mit Microsoft Jet\-Datenbanken \(.mdb\) arbeiten und den meisten Fällen, wenn Sie mit ODBC arbeiten, ist nur ein Fehlerobjekts.  Im seltenen Fall, wenn Sie eine ODBC\-Datenquelle verwenden und mehrere Fehler auftreten, können Sie durch Fehlerauflistung DAO auf Grundlage der Anzahl von Fehlern durchlaufen, die von [CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md) zurückgegeben werden.  Jedes Mal wenn von der Schleife, rufen Sie [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md), um den `m_pErrorInfo` Datenmembers erneut zu füllen.  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)