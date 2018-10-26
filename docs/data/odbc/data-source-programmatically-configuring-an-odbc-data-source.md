---
title: 'Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
f1_keywords:
- SQLConfigDataSource
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a06cefdd9df96cd228d2d8814eaafea7eab18930
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080259"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle

In diesem Thema wird erläutert, wie ODBC-Datenquellennamen programmgesteuert konfiguriert werden können. Dies ermöglicht es, auf Daten zuzugreifen, ohne den Benutzer dazu zu zwingen, die Namen der Datenquellen explizit mit ODBC-Administrator oder einem anderen Programm anzugeben.

Normalerweise führt ein Benutzer den ODBC-Administrator aus, um eine Datenquelle zu erstellen, wenn das betreffende Datenbankmanagementsystem (DBMS) diese Operation unterstützt.

Beim Anlegen einer Microsoft Access-ODBC-Datenquelle mit ODBC-Administrator haben Sie zwei Möglichkeiten: Sie können entweder eine vorhandene MDB-Datei auswählen oder eine neue MDB-Datei erstellen. Es gibt keine Möglichkeit, eine MDB-Datei von einer MFC-ODBC-Anwendung aus programmgesteuert anzulegen. Wenn es daher für die Anwendung erforderlich ist, Daten in einer Microsoft Access-Datenquelle (.mdb-Datei) zu speichern, benötigen Sie wahrscheinlich eine leere MDB-Datei, auf die Sie bei Bedarf zugreifen oder die Sie kopieren können.

Viele Datenbankmanagementsysteme ermöglichen jedoch das programmgesteuerte Erstellen einer Datenquelle. Einige Datenquellen verwenden eine Verzeichnisangabe für Datenbanken. Als Datenquelle wird also ein Verzeichnis verwendet. Jede Tabelle dieser Datenquelle ist in einer eigenen Datei gespeichert. Im Fall von dBASE ist jede Tabelle in einer eigenen DBF-Datei enthalten. Treiber für andere ODBC-Datenbanken, z. B. Microsoft Access und SQL Server, erfordern, dass bestimmte Kriterien erfüllt werden, bevor Sie eine Datenquelle hergestellt werden kann. Beispielsweise müssen bei Verwendung den SQL Server-ODBC-Treiber einen SQL Server-Computer eingerichtet haben.

##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource-Beispiel

Im folgenden Beispiel wird die `::SQLConfigDataSource` ODBC API-Funktion zum Erstellen einer neuen Excel-Datenquelle wird aufgerufen, neue Excel-Datenquelle:

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

Beachten Sie, dass es sich bei der Datenquelle um ein Verzeichnis handelt (C:\EXCELDIR), dessen Vorhandensein sichergestellt sein muss. Der Excel-Treiber verwendet Verzeichnisse als Datenquellen und Dateien als einzelne Tabellen, und zwar eine Tabelle pro XLS-Datei.

Weitere Informationen zum Erstellen von Tabellen finden Sie unter [Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).

Die folgende Informationen wird erläutert, die Parameter, die übergeben werden müssen, die `::SQLConfigDataSource` ODBC API-Funktion. Verwendung von `::SQLConfigDataSource`, müssen Sie die Headerdatei Odbcinst.h eingebunden und die Importbibliothek Odbcinst.lib verwendet werden. Außerdem muss die Datei Odbccp32.dll zur Laufzeit im Ausführungspfad gespeichert sein, bzw. für 16 Bits die Datei Odbcinst.dll.

Sie können einen ODBC-Datenquellennamen mit ODBC-Administrator oder einem ähnlichen Dienstprogramm erstellen. Manchmal ist es jedoch besser, einen Datenquellennamen direkt aus einer Anwendung heraus anzulegen. So wird der Zugriff ermöglicht, ohne dass der Benutzer ein separates Hilfsprogramm ausführen muss.

ODBC-Administrator, der normalerweise in der Windows-Systemsteuerung installiert ist, erstellt eine neue Datenquelle, indem er Einträge in die Windows-Registrierung schreibt, bzw. bei 16 Bits in die Datei Odbc.ini. Der ODBC-Treiber-Manager verwendet diese Datei, um die benötigten Informationen über die Datenquelle zu ermitteln. Es ist wichtig zu wissen, welche Informationen muss in der Registrierung platziert werden, da Sie ihn durch den Aufruf von müssen `::SQLConfigDataSource`.

Obwohl diese Informationen direkt in der Registrierung ohne geschrieben werden konnte `::SQLConfigDataSource`, jede Anwendung, die tut es setzt voraus, dass das aktuelle Verfahren, die der Treiber-Manager zum Verwalten der Daten verwendet. Sollte eine spätere Version von ODBC-Treiber-Manager die Datensatzverwaltung für Datenquellen in einer anderen Weise implementieren, wäre eine solche Anwendung nicht mehr funktionsfähig. Soweit möglich, sollte immer eine API-Funktion verwendet werden. Der Code ist z. B. aus 16-Bit mit 32 Bits portiert, wenn Sie verwenden die `::SQLConfigDataSource` Funktion, da die Funktion in der Datei Odbc.ini oder in die Registrierung schreibt.

##  <a name="_core_sqlconfigdatasource_parameters"></a> Parameter von SQLConfigDataSource

Das folgende Beispiel erläutert die Parameter der `::SQLConfigDataSource` Funktion. Der Großteil dieser Informationen stammt aus der ODBC-API *Programmer's Reference* mit Visual C++, Version 1.5 und höher angegeben.

###  <a name="_core_function_prototype"></a> Funktionsprototyp

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>Hinweise

####  <a name="_core_parameters_and_usage"></a> Parameter und Ihre Verwendung

*hwndParent*<br/>
Das Besitzerfenster für alle Dialogfelder, das der ODBC-Treiber-Manager oder der spezifische ODBC-Treiber erstellt, um vom Benutzer zusätzliche Informationen über die neue Datenquelle anzufordern. Wenn die *LpszAttributes* -Parameter nicht genügend Informationen bereitstellt, wird ein Dialogfeld angezeigt. Die *HwndParent* Parameter kann NULL sein.

*lpszDriver*<br/>
Hierbei handelt es sich um die Treiberbeschreibung. Dies ist der Name, der dem Benutzer an Stelle des physischen Treibernamens, also der DLL, angezeigt wird.

*lpszAttributes*<br/>
Die Liste der Attribute in der Form "Schlüsselname=Wert". Diese Zeichenfolgen werden durch NULL-Zeichen getrennt. Zwei aufeinander folgende NULL-Zeichen kennzeichnen das Ende der Liste. Diese Attribute sind in erster Linie treiberspezifische Standardeinträge, die für die neue Datenquelle in die Registrierung geschrieben werden. Ein wichtiger Schlüssel, der in der ODBC-API-Referenz zu dieser Funktion nicht erwähnt wird, ist "DSN" (Data Source Name, Datenquellenname). Hierdurch wird der Name der neuen Datenquelle angegeben. Die übrigen Einträge betreffen den Treiber für die neue Datenquelle. Meist ist es nicht erforderlich, alle Einträge zur Verfügung zu stellen, da der Benutzer durch den Treiber in Dialogfeldern zur Eingabe der neuen Werte aufgefordert werden kann. (Legen Sie *HwndParent* auf NULL, um dies zu verursachen.) Es können auch explizit Standardwerte bereitgestellt werden, damit der Benutzer nicht zu einer Eingabe aufgefordert wird.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>So ermitteln Sie mit ODBC-Administrator die Beschreibung eines Treibers für den lpszDriver-Parameter

1. Starten Sie den ODBC-Administrator.

1. Klicken Sie auf **Hinzufügen**.

Hierdurch wird eine Liste der installierten Treiber mit der entsprechenden Beschreibung angezeigt. Verwenden Sie diese Beschreibung der *LpszDriver* Parameter. Verwenden Sie hierbei die vollständige Beschreibung, z. B. "Excel-Dateien (*.xls)", einschließlich der Dateierweiterung und der Klammern, sofern diese in der Beschreibung vorhanden sind.

Wahlweise kann auch die Registrierung oder, bei 16 Bit-Systemen, die Datei Odbcinst.ini durchsucht werden, die eine Liste aller Treibereinträge und Beschreibungen unter dem Registrierungsschlüssel "ODBC Drivers" enthält bzw. der Abschnitt [ODBC Drivers] in der Datei Odbcinst.ini.

Eine Möglichkeit zum Suchen von Schlüsselnamen und Werte für die *LpszAttributes* Parameter ist die Untersuchung der Datei Odbc.ini einer bereits konfigurierten Datenquelle (z. B. eins, die vom ODBC-Administrator konfiguriert wurde).

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>So suchen Sie Schlüsselnamen und Werte für den Parameter lpszAttributes

1. Führen Sie den Registrierungs-Editor von Windows aus, oder öffnen Sie bei einem 16-Bit-System die Datei Odbc.ini.

1. Suchen Sie nach den Informationen zu ODBC-Datenquellen mit einer der folgenden Methoden:

   - Suchen Sie den Schlüssel für die 32-Bit **HKEY_CURRENT_USER\Software\ODBC\ODBC. Datenquellen INI\ODBC** im linken Bereich.

      Im rechten Fenster werden die Einträge der Form: "Pub: REG_SZ:*<data source name>*", wobei *<data source name>* ist eine Datenquelle, die bereits mit den gewünschten Einstellungen für den Treiber konfiguriert wurde werden sollen zu verwenden. Wählen Sie die Datenquelle, die Sie möchten, die z. b. SQL Server. Die Elemente, die nach der Zeichenfolge "Pub:" sind, die Reihenfolge der Schlüsselname und Wert für die Verwendung in Ihrem *LpszAttributes* Parameter.

   - Suchen Sie den Abschnitt für 16-Bit in der Datei Odbc.ini nach [*\<Datenquellenname >*].

      Die Zeilen im Anschluss an diese Zeile haben die Form "Schlüsselname=Wert". Hierbei handelt es sich um genau die Einträge für die Verwendung in Ihrem *LpszAttributes* Parameter.

Sie können auch die Dokumentation des Treibers durchsuchen, den Sie verwenden möchten. Sie finden nützliche Informationen in der Onlinehilfe zu diesem Treiber, auf die Sie mit ODBC-Administrator zugreifen können. Diese Hilfedateien werden in der Regel im Verzeichnis WINDOWS\SYSTEM von Windows NT, Windows 3.1 oder Windows 95 platziert.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>So greifen Sie auf die Onlinehilfe des ODBC-Treibers zu

1. Starten Sie den ODBC-Administrator.

1. Klicken Sie auf **Hinzufügen**.

1. Wählen Sie den Namen des Treibers aus.

1. Klicken Sie auf **OK**.

Wenn ODBC-Administrator die Informationen zum Erstellen einer neuen Datenquelle für diesen speziellen Treiber anzeigt, klicken Sie auf **Hilfe**. Hierdurch wird die Hilfedatei für diesen Treiber geöffnet, die in der Regel wichtige Informationen zu dessen Verwendung enthält.

## <a name="see-also"></a>Siehe auch

[Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)
