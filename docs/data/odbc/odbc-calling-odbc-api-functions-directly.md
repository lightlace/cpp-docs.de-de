---
title: 'ODBC: Aufrufen von ODBC-API-Funktionen direkt | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b7304d83eca004952eb65ed6c5d16e4ce816bb56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: Direktes Aufrufen von ODBC-API-Funktionen
Die Datenbankklassen stellen eine einfachere Schnittstelle zu einer [Datenquelle](../../data/odbc/data-source-odbc.md) als ODBC verfügt. Daher werden die Klassen nicht alle ODBC-API kapseln. Für alle Funktionen, die die Fähigkeiten der Klassen verlassen hat, müssen Sie ODBC-API-Funktionen direkt aufrufen. Beispielsweise müssen Sie die ODBC-Katalogfunktionen aufrufen (**:: SQLColumns**, **:: SQLProcedures**, **:: SQLTables**, usw.) direkt.  
  
> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).  
  
 Zum Aufrufen einer ODBC-API-Funktion müssen Sie direkt die gleichen Schritte nutzen, die Sie dauern würde, wenn Sie die Aufrufe ohne das Framework wurden. Diese Schritte sind:  
  
-   Zuordnen von Speicher für alle Ergebnisse dar, die der Aufruf zurückgegeben.  
  
-   Übergeben Sie einen ODBC **HDBC** oder **Befehls beschäftigt** zu behandeln, abhängig von der Parametersignatur der Funktion. Verwenden der [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) Makro, um das ODBC-Handle abzurufen.  
  
     Membervariablen **CDatabase:: M_hdbc** und **M_hstmt** sind verfügbar, sodass Sie nicht benötigen, reservieren und diese selbst zu initialisieren.  
  
-   Rufen Sie bei Bedarf zusätzliche ODBC-Funktionen, um vorzubereiten, oder führen die main-Aufruf.  
  
-   Freigeben Sie Speicher, wenn Sie fertig sind.  
  
 Weitere Informationen zu diesen Schritten finden Sie unter der [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK in der MSDN-Dokumentation.  
  
 Zusätzlich zu diesen Schritten müssen Sie zusätzliche Schritte zum Überprüfen von Rückgabewerten der Funktion stellen Sie sicher, dass das Programm nicht für einen asynchronen Aufruf, usw. wartet. Sie können diese letzten Schritte zu vereinfachen, indem die `AFX_SQL_ASYNC` und `AFX_SQL_SYNC` Makros. Weitere Informationen finden Sie unter [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in der *MFC-Referenz*.  

  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)
