---
title: 'ODBC: Direktes Aufrufen von ODBC-API-Funktionen'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
ms.openlocfilehash: e76ff4da090a00409465333f8cbc9816ab4c4de6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518345"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: Direktes Aufrufen von ODBC-API-Funktionen

Die Datenbankklassen bieten eine einfachere Schnittstelle zu einem [Datenquelle](../../data/odbc/data-source-odbc.md) als ODBC ist. Daher sind die Klassen nicht alle ODBC-API kapseln. Für alle Funktionen, die außerhalb der Fähigkeiten der Klassen liegt, müssen Sie ODBC API-Funktionen direkt aufrufen. Sie müssen z. B. den ODBC-Katalogfunktionen aufrufen (`::SQLColumns`, `::SQLProcedures`, `::SQLTables`, usw.) direkt.

> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).

Zum Aufrufen von einer ODBC-API-Funktion müssen Sie direkt die gleichen Schritte ausführen, die Sie ergreifen würden, wenn Sie die Aufrufe ohne das Framework erzielt wurde. Diese Schritte sind:

- Zuordnen von Speicher für Ergebnisse, die Rückgabe des Aufrufs.

- Übergeben Sie einen ODBC `HDBC` oder `HSTMT` zu behandeln, abhängig von der Parametersignatur der Funktion. Verwenden der [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) Makro, um das ODBC-Handle abzurufen.

   Membervariablen `CDatabase::m_hdbc` und `CRecordset::m_hstmt` sind verfügbar, sodass Sie nicht benötigen, reservieren und diese selbst zu initialisieren.

- Rufen Sie bei Bedarf zusätzliche ODBC-Funktionen, um vorzubereiten, oder folgen der main-Aufruf.

- Wenn Sie fertig sind, heben Sie die Zuordnung "Storage".

Weitere Informationen zu diesen Schritten finden Sie unter den [Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) -SDK in der MSDN-Dokumentation.

Zusätzlich zu diesen Schritten müssen Sie auch zusätzliche Schritte zum Überprüfen von Rückgabewerten der Funktion, stellen Sie sicher, dass das Programm nicht wartet, für einen asynchronen Aufruf abzuschließen, und so weiter. Sie können diese letzten Schritte vereinfachen, mit der AFX_SQL_ASYNC und AFX_SQL_SYNC-Makros. Weitere Informationen finden Sie unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in die *MFC-Referenz*.

## <a name="see-also"></a>Siehe auch

[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)
