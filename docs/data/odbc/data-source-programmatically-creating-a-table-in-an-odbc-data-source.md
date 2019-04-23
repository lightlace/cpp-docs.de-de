---
title: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 61d3f3e39362db27d1e3abc00fa3cb9ea82b86e2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028398"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle

In diesem Thema wird erläutert, wie zum Erstellen einer Tabelle für Ihre Daten für die Datenquelle, das mithilfe der `ExecuteSQL` Memberfunktion der Klasse `CDatabase`, übergeben der Funktion eine Zeichenfolge, enthält eine **CREATE TABLE** SQL-Anweisung.

Allgemeine Informationen zu ODBC-Datenquellen in MFC, finden Sie unter [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md). Das Thema [Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) wird die Erstellung von Datenquellen beschrieben.

Wenn Sie die Datenquelle eingerichtet haben, können Sie ganz einfach erstellen, auf Tabellen mit den `ExecuteSQL` Member-Funktion und die **CREATE TABLE** SQL-Anweisung. Angenommen, Sie haben eine `CDatabase` Objekt mit dem Namen `myDB`, können Sie die folgenden MFC-Code zum Erstellen einer Tabelle verwenden:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Dieses Codebeispiel erstellt eine Tabelle namens "NIEDERLASSUNGEN" in der Microsoft Access-Verbindung vom verwaltet `myDB`; die Tabelle enthält zwei Felder "OfficeID" und "OfficeName."

> [!NOTE]
>  Die Feldtypen, angegeben der **CREATE TABLE** SQL-Anweisung unterscheiden sich entsprechend den ODBC-Treiber, die Sie verwenden. Das Microsoft Query-Programm (zusammen mit Visual C++-1,5) ist eine Möglichkeit zum erkennen, welche Feldtypen für eine Datenquelle verfügbar sind. Klicken Sie im Microsoft-Query, auf **Datei**, klicken Sie auf **Table_Definition**, wählen Sie eine Tabelle aus einer Datenquelle, und sehen Sie sich die Art, die der **Typ** im Kombinationsfeld. SQL-Syntax ist auch zum Erstellen von Indizes vorhanden.

## <a name="see-also"></a>Siehe auch

[Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)