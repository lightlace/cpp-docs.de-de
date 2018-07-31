---
title: 'Datenquelle: Verwalten von Verbindungen (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e60a7b03c34106a51ed87269521524ef5889f9cf
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339479"
---
# <a name="data-source-managing-connections-odbc"></a>Datenquelle: Verwalten von Verbindungen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Vorgehensweise: konfigurieren eine Datenquelle](#_core_configuring_a_data_source).  
  
-   [Wie sich eine mehrbenutzerumgebung auf eine Datenquelle und ihre Recordsets auswirkt](#_core_working_in_a_multiuser_environment).  
  
-   [Warum Sie eine Verbindungszeichenfolge für eine Datenquelle Allgemein formulieren](#_core_generalizing_the_connection_string).  
  
-   [Herstellen einer Verbindung mit einer Datenquelle](#_core_connecting_to_a_specific_data_source).  
  
-   [Aus einer Datenquelle trennen der Verbindung](#_core_disconnecting_from_a_data_source).  
  
-   [Wie Sie ein CDatabase-Objekt wiederverwenden](#_core_reusing_a_cdatabase_object).  
  
 Der Verbindungsaufbau mit einer Datenquelle umfasst das Herstellen der Kommunikation mit einem DBMS, um auf die Daten zugreifen zu können. Wenn Sie von der Anwendung aus über einen ODBC-Treiber die Verbindung zu einer Datenquelle aufbauen, stellt der Treiber die Verbindung entweder lokal oder über ein Netzwerk her.  
  
 Sie können die Verbindung mit jeder beliebigen Datenquelle herstellen, für die Sie einen ODBC-Treiber besitzen. Die Benutzer der Anwendung müssen für ihre Datenquelle denselben ODBC-Treiber verwenden. Weitere Informationen über die Weitergabe von ODBC-Treiber finden Sie unter [Weitervertrieb von ODBC-Komponenten an Kunden](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a> Konfigurieren einer Datenquelle  
 Datenquellen werden mit dem ODBC-Administrator konfiguriert. Sie können mit dem ODBC-Administrator nach der Installation Datenquellen hinzufügen oder entfernen. Beim Erstellen von Anwendungen können Sie entweder Benutzer anleiten, wie Sie mit dem ODBC-Administrator Datenquellen hinzufügen, oder Sie können diese Funktionalität in die Anwendung integrieren, indem Sie direkte ODBC-Installationsaufrufe durchführen. Weitere Informationen finden Sie unter [ODBC-Administrator](../../data/odbc/odbc-administrator.md).  
  
 Sie können eine Excel-Datei als Datenquelle verwenden und müssen Sie die Datei so konfigurieren, dass er registriert ist, und wird in der **Auswählen einer Datenquelle** Dialogfeld.  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>So verwenden Sie eine Excel-Datei als Datenquelle  
  
1.  Konfigurieren Sie die Datei mit dem ODBC-Datenquellen-Administrator.  
  
2.  Auf der **Datei-DSN** auf **hinzufügen**.  
  
3.  In der **neue Datenquelle erstellen** im Dialogfeld Wählen Sie ein Excel-Treiber aus, und klicken Sie dann auf **Weiter**.  
  
4.  Klicken Sie auf **Durchsuchen**, und wählen Sie den Namen der Datei, die als Datenquelle verwendet werden.  
  
> [!NOTE]
>  Sie müssen ggf. auf **alle Dateien** im Dropdown-Menü, XLS-Dateien anzuzeigen.  
  
1.  Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.  
  
2.  In der **ODBC Microsoft Excel Setup** Dialogfeld wählen die Datenbankversion und der Arbeitsmappe.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> Arbeiten in einer Mehrbenutzerumgebung  
 Falls mehrere Benutzer mit derselben Datenquelle verbunden sind, können sie Daten verändern, während Sie dieselben Daten in Ihren Recordsets bearbeiten. Ebenso könnten die von Ihnen durchgeführten Änderungen die Recordsets anderer Benutzer betreffen. Weitere Informationen finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) und [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a> Verallgemeinern der Verbindungszeichenfolge  
 Die Assistenten verwenden für den Verbindungsaufbau mit einer Datenquelle eine Standard-Verbindungszeichenfolge. Mit dieser Verbindung werden während der Entwicklung einer Anwendung Tabellen und Spalten angezeigt. Diese Standard-Verbindungszeichenfolge eignet sich jedoch möglicherweise nicht für die Verbindungen, die Benutzer über die Anwendung mit der Datenquelle aufbauen. Beispielsweise könnten sich die Datenquelle und der Pfad zum Speicherort dieser Datenquelle von denen unterscheiden, die Sie beim Entwickeln der Anwendung verwendet hatten. In diesem Fall sollten Sie erneut die [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) Member-Funktion in einer allgemeineren Form und Implementierung des Assistenten verwerfen. Sie können z. B. eine der folgenden Lösungsmöglichkeiten verwenden:  
  
-   Registrieren und verwalten Sie die Verbindungszeichenfolgen mithilfe des ODBC-Administrators.  
  
-   Bearbeiten Sie die Verbindungszeichenfolge, und entfernen Sie den Namen der Datenquelle. Das Framework verwendet ODBC als Datenquelle. In ODBC wird zur Laufzeit ein Dialogfeld angezeigt, in dem der Name der Datenquelle und alle anderen erforderlichen Verbindungsinformationen angefordert werden.  
  
-   Geben Sie ausschließlich den Namen der Datenquelle an. ODBC fordert ggf. zur Eingabe der Benutzer-ID und des Kennworts auf. Vor der Verallgemeinerung könnte die Verbindungszeichenfolge z. B. folgendermaßen aussehen:  
  
    ```cpp  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     Diese Verbindungszeichenfolge gibt eine vertrauenswürdige Verbindung mit Windows NT, die integrierte Sicherheit verwendet. Die Angabe eines fest codierten bzw. keines Kennworts sollte vermieden werden, da dies zu erheblichen Sicherheitsmängeln führen kann. Sie können stattdessen eine neue Verbindungszeichenfolge für `GetDefaultConnect` festlegen, sodass Benutzer-ID und Kennwort abgefragt werden.  
  
    ```cpp  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> Herstellen einer Verbindung mit einer bestimmten Datenquelle  
 Zum Verbinden mit einer bestimmten Datenquelle Ihrer Datenquelle muss bereits konfiguriert sein [ODBC-Administrator](../../data/odbc/odbc-administrator.md).  
  
#### <a name="to-connect-to-a-specific-data-source"></a>So bauen Sie die Verbindung zu einer bestimmten Datenquelle auf  
  
1.  Konstruieren Sie ein `CDatabase`-Objekt.  
  
2.  Rufen Sie die `OpenEx` oder `Open` Member-Funktion.  
  
 Weitere Informationen dazu, wie Sie die Datenquelle angeben, wenn es etwas anderes als das ist Sie im Assistenten angegeben werden, finden Sie unter [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) oder [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) in die *MFC Verweis*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> Trennen von einer Datenquelle  
 Sie müssen vor dem Aufruf alle geöffneten Recordsets schließen die `Close` Memberfunktion `CDatabase`. In Recordsets im Zusammenhang mit der `CDatabase` Objekt Sie schließen möchten, alle ausstehenden `AddNew` oder `Edit` -Anweisungen abgebrochen und alle ausstehenden Transaktionen ein Rollback.  
  
#### <a name="to-disconnect-from-a-data-source"></a>So trennen Sie die Verbindung mit einer Datenquelle  
  
1.  Rufen Sie die `CDatabase` des Objekts [schließen](../../mfc/reference/cdatabase-class.md#close) Member-Funktion.  
  
2.  Zerstören Sie das Objekt, sofern Sie es nicht wiederverwenden möchten.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> Wiederverwenden von ein CDatabase-Objekt  
 Nachdem Sie die Verbindung zu einem `CDatabase`-Objekt getrennt haben, können Sie dieses wiederverwenden. Hierbei kann entweder eine neue Verbindung zu derselben oder zu einer anderen Datenquelle aufgebaut werden.  
  
#### <a name="to-reuse-a-cdatabase-object"></a>So verwenden Sie ein CDatabase-Objekt wieder  
  
1.  Trennen Sie die ursprüngliche Verbindung des Objekts.  
  
2.  Anstatt die Zerstörung des Objekts aufrufen seiner `OpenEx` oder `Open` Member-Funktion erneut aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Datenquelle: Bestimmen des Schemas der Datenquelle (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)