---
title: "Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "SQLConfigDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konfigurieren von ODBC-Datenquellen"
  - "ODBC-Verbindungen, Konfigurieren"
  - "ODBC-Datenquellen, Konfigurieren"
  - "SQLConfigDataSource-Methode (Beispiel)"
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie ODBC\-Datenquellennamen programmgesteuert konfiguriert werden können.  Dies ermöglicht es, auf Daten zuzugreifen, ohne den Benutzer dazu zu zwingen, die Namen der Datenquellen explizit mit ODBC\-Administrator oder einem anderen Programm anzugeben.  
  
 Normalerweise führt ein Benutzer den ODBC\-Administrator aus, um eine Datenquelle zu erstellen, wenn das betreffende Datenbankmanagementsystem \(DBMS\) diese Operation unterstützt.  
  
 Beim Anlegen einer Microsoft Access\-ODBC\-Datenquelle mit ODBC\-Administrator haben Sie zwei Möglichkeiten: Sie können entweder eine vorhandene MDB\-Datei auswählen oder eine neue MDB\-Datei erstellen.  Es gibt keine Möglichkeit, eine MDB\-Datei von einer MFC\-ODBC\-Anwendung aus programmgesteuert anzulegen.  Wenn es daher für die Anwendung erforderlich ist, Daten in einer Microsoft Access\-Datenquelle \(.mdb\-Datei\) zu speichern, benötigen Sie wahrscheinlich eine leere MDB\-Datei, auf die Sie bei Bedarf zugreifen oder die Sie kopieren können.  
  
 Viele Datenbankmanagementsysteme ermöglichen jedoch das programmgesteuerte Erstellen einer Datenquelle.  Einige Datenquellen verwenden eine Verzeichnisangabe für Datenbanken.  Als Datenquelle wird also ein Verzeichnis verwendet. Jede Tabelle dieser Datenquelle ist in einer eigenen Datei gespeichert. Im Fall von dBASE ist jede Tabelle in einer eigenen DBF\-Datei enthalten.  Treiber für andere ODBC\-Datenbanken, z. B. Microsoft Access und SQL Server, setzen voraus, dass bestimmte Kriterien erfüllt sind, bevor eine Datenquelle eingerichtet werden kann.  Wenn z. B. der SQL Server\-ODBC\-Treiber verwendet wird, muss ein Computer mit SQL Server eingerichtet sein.  
  
##  <a name="_core_sqlconfigdatasource_example"></a> Beispiel für die Verwendung von SQLConfigDataSource  
 Im folgenden Beispiel wird mithilfe der **::SQLConfigDataSource**\-ODBC\-API\-Funktion eine neue Excel\-Datenquelle mit dem Namen New Excel Data Source angelegt:  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 Beachten Sie, dass es sich bei der Datenquelle um ein Verzeichnis handelt \(C:\\EXCELDIR\), dessen Vorhandensein sichergestellt sein muss.  Der Excel\-Treiber verwendet Verzeichnisse als Datenquellen und Dateien als einzelne Tabellen, und zwar eine Tabelle pro XLS\-Datei.  
  
 Weitere Informationen zur Tabellenerstellung finden Sie unter [Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC\-Datenquelle](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).  
  
 In den folgenden Abschnitten werden die Parameter der ODBC\-API\-Funktion **::SQLConfigDataSource** beschrieben.  Bevor **::SQLConfigDataSource** verwendet werden kann, muss die Headerdatei Odbcinst.h eingebunden und die Importbibliothek Odbcinst.lib verwendet werden.  Außerdem muss die Datei Odbccp32.dll zur Laufzeit im Ausführungspfad gespeichert sein, bzw. für 16 Bits die Datei Odbcinst.dll.  
  
 Sie können einen ODBC\-Datenquellennamen mit ODBC\-Administrator oder einem ähnlichen Dienstprogramm erstellen.  Manchmal ist es jedoch besser, einen Datenquellennamen direkt aus einer Anwendung heraus anzulegen. So wird der Zugriff ermöglicht, ohne dass der Benutzer ein separates Hilfsprogramm ausführen muss.  
  
 ODBC\-Administrator, der normalerweise in der Windows\-Systemsteuerung installiert ist, erstellt eine neue Datenquelle, indem er Einträge in die Windows\-Registrierung schreibt, bzw. bei 16 Bits in die Datei Odbc.ini.  Der ODBC\-Treiber\-Manager verwendet diese Datei, um die benötigten Informationen über die Datenquelle zu ermitteln.  Es muss bekannt sein, welche Informationen in der Registrierung einzutragen sind, da diese beim Aufruf von **::SQLConfigDataSource** bereitgestellt werden sollen.  
  
 Diese Informationen könnten auch ohne Verwendung von **::SQLConfigDataSource** direkt in die Registrierung eingetragen werden. Anwendungen mit dieser Vorgehensweise verwenden jedoch die Methode, die für den Treiber\-Manager zur Datenverwaltung eingesetzt wird.  Sollte eine spätere Version von ODBC\-Treiber\-Manager die Datensatzverwaltung für Datenquellen in einer anderen Weise implementieren, wäre eine solche Anwendung nicht mehr funktionsfähig.  Soweit möglich, sollte immer eine API\-Funktion verwendet werden.  Der Code kann z. B. zwischen einem System mit 16 Bits und einem System mit 32 Bits portiert werden, wenn Sie die Funktion **::SQLConfigDataSource** verwenden, da diese Funktion je nach Plattform entweder in die Datei Odbc.ini oder in die Registrierung schreibt.  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a> Parameter von SQLConfigDataSource  
 Im folgenden Abschnitt werden die Parameter der **::SQLConfigDataSource**\-Funktion erläutert.  Der Großteil dieser Informationen stammt aus *Programmer's Reference* für ODBC\-API in Visual C\+\+, Version 1.5 oder höher.  
  
###  <a name="_core_function_prototype"></a> Funktionsprototyp  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### Hinweise  
  
####  <a name="_core_parameters_and_usage"></a> Parameter und ihre Verwendung  
 *hwndParent*  
 Das Besitzerfenster für alle Dialogfelder, das der ODBC\-Treiber\-Manager oder der spezifische ODBC\-Treiber erstellt, um vom Benutzer zusätzliche Informationen über die neue Datenquelle anzufordern.  Falls durch den `lpszAttributes`\-Parameter nicht genügend Informationen bereitstellt werden, wird ein Dialogfeld angezeigt.  Der *hwndParent*\-Parameter könnte **NULL** sein.  
  
 `lpszDriver`  
 Hierbei handelt es sich um die Treiberbeschreibung.  Dies ist der Name, der dem Benutzer an Stelle des physischen Treibernamens, also der DLL, angezeigt wird.  
  
 `lpszAttributes`  
 Die Liste der Attribute in der Form "Schlüsselname\=Wert".  Diese Zeichenfolgen werden durch NULL\-Zeichen getrennt. Zwei aufeinander folgende NULL\-Zeichen kennzeichnen das Ende der Liste.  Diese Attribute sind in erster Linie treiberspezifische Standardeinträge, die für die neue Datenquelle in die Registrierung geschrieben werden.  Ein wichtiger Schlüssel, der in der ODBC\-API\-Referenz zu dieser Funktion nicht erwähnt wird, ist "DSN" \(Data Source Name, Datenquellenname\). Hierdurch wird der Name der neuen Datenquelle angegeben.  Die übrigen Einträge betreffen den Treiber für die neue Datenquelle.  Meist ist es nicht erforderlich, alle Einträge zur Verfügung zu stellen, da der Benutzer durch den Treiber in Dialogfeldern zur Eingabe der neuen Werte aufgefordert werden kann. \(Legen Sie hierzu *hwndParent* auf **NULL** fest.\) Es können auch explizit Standardwerte bereitgestellt werden, damit der Benutzer nicht zu einer Eingabe aufgefordert wird.  
  
###### So ermitteln Sie mit ODBC\-Administrator die Beschreibung eines Treibers für den lpszDriver\-Parameter  
  
1.  Starten Sie den ODBC\-Administrator.  
  
2.  Klicken Sie auf **Hinzufügen**.  
  
 Hierdurch wird eine Liste der installierten Treiber mit der entsprechenden Beschreibung angezeigt.  Verwenden Sie diese Beschreibung für den `lpszDriver`\-Parameter.  Verwenden Sie hierbei die vollständige Beschreibung, z. B. "Excel\-Dateien \(\*.xls\)", einschließlich der Dateinamenerweiterung und der Klammern, sofern diese in der Beschreibung vorhanden sind.  
  
 Wahlweise kann auch die Registrierung oder, bei 16 Bit\-Systemen, die Datei Odbcinst.ini durchsucht werden, die eine Liste aller Treibereinträge und Beschreibungen unter dem Registrierungsschlüssel "ODBC Drivers" enthält bzw. der Abschnitt \[ODBC Drivers\] in der Datei Odbcinst.ini.  
  
 Eine Möglichkeit, die Schlüsselnamen und Werte für den `lpszAttributes`\-Parameter zu ermitteln, ist die Untersuchung der Datei ODBC.ini einer bereits konfigurierten Datenquelle, die möglichst mit ODBC\-Administrator konfiguriert wurde.  
  
###### So suchen Sie Schlüsselnamen und Werte für den Parameter lpszAttributes  
  
1.  Führen Sie den Registrierungs\-Editor von Windows aus, oder öffnen Sie bei einem 16\-Bit\-System die Datei Odbc.ini.  
  
2.  Suchen Sie nach den Informationen zu ODBC\-Datenquellen mit einer der folgenden Methoden:  
  
    -   Suchen Sie bei einem 32\-Bit\-System im linken Fensterbereich den Schlüssel **HKEY\_CURRENT\_USER\\Software\\ODBC\\ODBC.INI\\ODBC Data Sources**.  
  
         Im rechten Bereich werden Einträge der Form "pub: REG\_SZ:*\<data source name\>*" aufgelistet, wobei *\<data source name\>* für eine Datenquelle steht, deren Konfiguration mit den erwünschten Einstellungen für den zu verwendenden Treiber bereits durchgeführt wurde.  Wählen Sie die gewünschte Datenquelle aus, also z. B. SQL Server.  Die Elemente nach der Zeichenfolge "pub:" enthalten in der erforderlichen Reihenfolge den zu verwendenden Schlüsselnamen und den Wert für den `lpszAttributes`\-Parameter.  
  
    -   Für 16\-Bit suchen in der Datei Odbc.ini nach dem mit \[*\<data source name\>*\] bezeichneten Abschnitt.  
  
         Die Zeilen im Anschluss an diese Zeile haben die Form "Schlüsselname\=Wert".  Exakt diese Einträge müssen im `lpszAttributes`\-Parameter verwendet werden.  
  
 Sie können auch die Dokumentation des Treibers durchsuchen, den Sie verwenden möchten.  Sie finden nützliche Informationen in der Onlinehilfe zu diesem Treiber, auf die Sie mit ODBC\-Administrator zugreifen können.  Diese Hilfedateien sind normalerweise im Verzeichnis WINDOWS\\SYSTEM von Windows NT, Windows 3.1 oder Windows 95 gespeichert.  
  
###### So greifen Sie auf die Onlinehilfe des ODBC\-Treibers zu  
  
1.  Starten Sie den ODBC\-Administrator.  
  
2.  Klicken Sie auf **Hinzufügen**.  
  
3.  Wählen Sie den Namen des Treibers aus.  
  
4.  Klicken Sie auf **OK**.  
  
 Wenn ODBC\-Administrator Informationen zur Erstellung einer neuen Datenquelle für diesen speziellen Treiber anzeigt, klicken Sie auf **Hilfe**.  Hierdurch wird die Hilfedatei für diesen Treiber geöffnet, die in der Regel wichtige Informationen zu dessen Verwendung enthält.  
  
## Siehe auch  
 [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md)