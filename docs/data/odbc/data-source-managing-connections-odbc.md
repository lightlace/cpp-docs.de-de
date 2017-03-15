---
title: "Datenquelle: Verwalten von Verbindungen (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verbindungszeichenfolgen [C++], Verallgemeinern"
  - "Verbindungen [C++], Datenquelle"
  - "Datenquellen [C++], Verbinden mit"
  - "Datenbankverbindungen [C++], Erstellen"
  - "Datenbankverbindungen [C++], MFC-ODBC-Klassen"
  - "Datenbanken [C++], Verbinden mit"
  - "Trennen von Datenquellen"
  - "Verallgemeinern von Verbindungszeichenfolgen"
  - "GetDefaultConnect-Methode"
  - "ODBC [C++], Trennen von Datenquellen"
  - "ODBC-Verbindungen [C++], Konfigurieren"
  - "ODBC-Verbindungen [C++], Verbinden mit Datenquelle"
  - "ODBC-Verbindungen [C++], Trennen der Verbindung"
  - "ODBC-Datenquellen [C++], Verbindungen"
  - "ODBC-Datenquellen [C++], Mehrbenutzerumgebungen"
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Datenquelle: Verwalten von Verbindungen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wie Sie eine Datenquelle konfigurieren](#_core_configuring_a_data_source).  
  
-   [Wie sich eine Mehrbenutzerumgebung auf eine Datenquelle und ihre Recordsets auswirkt](#_core_working_in_a_multiuser_environment).  
  
-   [Warum Sie die Verbindungszeichenfolge für eine Datenquelle allgemein formulieren](#_core_generalizing_the_connection_string).  
  
-   [Wie Sie die Verbindung zu einer Datenquelle aufbauen](#_core_connecting_to_a_specific_data_source).  
  
-   [Wie Sie die Verbindung zu einer Datenquelle trennen](#_core_disconnecting_from_a_data_source).  
  
-   [Wie Sie ein CDatabase\-Objekt wiederverwenden](#_core_reusing_a_cdatabase_object).  
  
 Der Verbindungsaufbau mit einer Datenquelle umfasst das Herstellen der Kommunikation mit einem DBMS, um auf die Daten zugreifen zu können.  Wenn Sie von der Anwendung aus über einen ODBC\-Treiber die Verbindung zu einer Datenquelle aufbauen, stellt der Treiber die Verbindung entweder lokal oder über ein Netzwerk her.  
  
 Sie können die Verbindung mit jeder beliebigen Datenquelle herstellen, für die Sie einen ODBC\-Treiber besitzen.  Die Benutzer der Anwendung müssen für ihre Datenquelle denselben ODBC\-Treiber verwenden.  Weitere Informationen über die Weitergabe von ODBC\-Treibern finden Sie unter [Weitervertrieb von ODBC\-Komponenten an Kunden](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a> Konfigurieren einer Datenquelle  
 Datenquellen werden mit dem ODBC\-Administrator konfiguriert.  Sie können mit dem ODBC\-Administrator nach der Installation Datenquellen hinzufügen oder entfernen.  Beim Erstellen von Anwendungen können Sie entweder Benutzer anleiten, wie Sie mit dem ODBC\-Administrator Datenquellen hinzufügen, oder Sie können diese Funktionalität in die Anwendung integrieren, indem Sie direkte ODBC\-Installationsaufrufe durchführen.  Weitere Informationen finden Sie unter [ODBC\-Administrator](../../data/odbc/odbc-administrator.md).  
  
 Als Datenquelle kann eine Excel\-Datei verwendet werden, die zur Registrierung und zur Anzeige im Dialogfeld **Datenquelle auswählen** konfiguriert werden muss.  
  
#### So verwenden Sie eine Excel\-Datei als Datenquelle  
  
1.  Konfigurieren Sie die Datei mit dem ODBC\-Datenquellen\-Administrator.  
  
2.  Klicken Sie auf der Registerkarte **Datei\-DSN** auf **Hinzufügen**.  
  
3.  Wählen Sie im Dialogfeld **Neue Datenquelle erstellen** einen Excel\-Treiber aus, und klicken Sie auf **Weiter**.  
  
4.  Klicken Sie auf **Durchsuchen**, und wählen Sie den Namen der Datei aus, die als Datenquelle verwendet werden soll.  
  
> [!NOTE]
>  Wählen Sie ggf. im Dropdownmenü **Alle Dateien** aus, um XLS\-Dateien anzuzeigen.  
  
1.  Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.  
  
2.  Wählen Sie im Dialogfeld **ODBC Microsoft Excel Setup** die Datenbankversion und die Arbeitsmappe aus.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> Arbeiten in einer Mehrbenutzerumgebung  
 Falls mehrere Benutzer mit derselben Datenquelle verbunden sind, können sie Daten verändern, während Sie dieselben Daten in Ihren Recordsets bearbeiten.  Ebenso könnten die von Ihnen durchgeführten Änderungen die Recordsets anderer Benutzer betreffen.  Weitere Informationen finden Sie unter [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) und [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a> Verallgemeinern der Verbindungszeichenfolge  
 Die Assistenten verwenden für den Verbindungsaufbau mit einer Datenquelle eine Standard\-Verbindungszeichenfolge.  Mit dieser Verbindung werden während der Entwicklung einer Anwendung Tabellen und Spalten angezeigt.  Diese Standard\-Verbindungszeichenfolge eignet sich jedoch möglicherweise nicht für die Verbindungen, die Benutzer über die Anwendung mit der Datenquelle aufbauen.  Beispielsweise könnten sich die Datenquelle und der Pfad zum Speicherort dieser Datenquelle von denen unterscheiden, die Sie beim Entwickeln der Anwendung verwendet hatten.  Für diesen Fall sollten Sie die [CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md)\-Memberfunktion allgemeiner implementieren und die Implementierung des Assistenten verwerfen.  Sie können z. B. eine der folgenden Lösungsmöglichkeiten verwenden:  
  
-   Registrieren und verwalten Sie die Verbindungszeichenfolgen mithilfe des ODBC\-Administrators.  
  
-   Bearbeiten Sie die Verbindungszeichenfolge, und entfernen Sie den Namen der Datenquelle.  Das Framework verwendet ODBC als Datenquelle. In ODBC wird zur Laufzeit ein Dialogfeld angezeigt, in dem der Name der Datenquelle und alle anderen erforderlichen Verbindungsinformationen angefordert werden.  
  
-   Geben Sie ausschließlich den Namen der Datenquelle an.  ODBC fordert ggf. zur Eingabe der Benutzer\-ID und des Kennworts auf.  Vor der Verallgemeinerung könnte die Verbindungszeichenfolge z. B. folgendermaßen aussehen:  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     In dieser Verbindungszeichenfolge ist angegeben, dass eine vertrauenswürdige Verbindung mit integrierten Sicherheitsfeatures von Windows NT verwendet wird.  Die Angabe eines fest codierten bzw. keines Kennworts sollte vermieden werden, da dies zu erheblichen Sicherheitsmängeln führen kann.  Sie können stattdessen eine neue Verbindungszeichenfolge für `GetDefaultConnect` festlegen, sodass Benutzer\-ID und Kennwort abgefragt werden.  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> Aufbauen der Verbindung zu einer bestimmten Datenquelle  
 Bevor die Anwendung eine Verbindung zu einer bestimmten Datenquelle aufbauen kann, muss diese Datenquelle mit dem [ODBC\-Administrator](../../data/odbc/odbc-administrator.md) konfiguriert worden sein.  
  
#### So bauen Sie die Verbindung zu einer bestimmten Datenquelle auf  
  
1.  Konstruieren Sie ein `CDatabase`\-Objekt.  
  
2.  Rufen Sie dessen `OpenEx`\-Memberfunktion oder **Open**\-Memberfunktion auf.  
  
 Falls Sie eine andere Datenquelle angeben möchten als die, die Sie im Assistenten angegeben hatten, finden Sie weitere Informationen unter [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) oder [CDatabase::Open](../Topic/CDatabase::Open.md) in der *MFC\-Referenz*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> Trennen der Verbindung zu einer Datenquelle  
 Sie müssen alle geöffneten Recordsets schließen, bevor Sie die **Close**\-Memberfunktion von `CDatabase` aufrufen.  In Recordsets, die mit dem `CDatabase`\-Objekt verknüpft sind, das Sie schließen möchten, werden alle anstehenden `AddNew`\-Anweisungen und **Edit**\-Anweisungen abgebrochen und alle anstehenden Transaktionen zurückgesetzt.  
  
#### So trennen Sie die Verbindung mit einer Datenquelle  
  
1.  Rufen Sie die [Close](../Topic/CDatabase::Close.md)\-Memberfunktion des `CDatabase`\-Objekts auf.  
  
2.  Zerstören Sie das Objekt, sofern Sie es nicht wiederverwenden möchten.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> Wiederverwenden eines CDatabase\-Objekts  
 Nachdem Sie die Verbindung zu einem `CDatabase`\-Objekt getrennt haben, können Sie dieses wiederverwenden. Hierbei kann entweder eine neue Verbindung zu derselben oder zu einer anderen Datenquelle aufgebaut werden.  
  
#### So verwenden Sie ein CDatabase\-Objekt wieder  
  
1.  Trennen Sie die ursprüngliche Verbindung des Objekts.  
  
2.  Rufen Sie erneut die `OpenEx`\-Memberfunktion oder die **Open**\-Memberfunktion auf, statt das Objekt zu zerstören.  
  
## Siehe auch  
 [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md)   
 [Datenquelle: Bestimmen des Schemas der Datenquelle \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)