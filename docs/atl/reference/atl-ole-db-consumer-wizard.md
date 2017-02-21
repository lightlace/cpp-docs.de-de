---
title: "ATL-OLE DB-Consumer-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-OLE DB-Consumer-Assistent"
  - "ATL-Projekte, Hinzufügen von ATL-OLE DB-Consumern"
  - "Verbindungszeichenfolgen [C++], OLE DB-Consumer"
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL-OLE DB-Consumer-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten wird eine OLE DB\-Consumerklasse mit den Datenbindungen eingerichtet, die erforderlich sind, um über den jeweiligen OLE DB\-Anbieter auf die angegebene Datenquelle zuzugreifen.  
  
> [!NOTE]
>  Bevor Sie Namen in die Felder `Class` und **.h\-Datei** eingeben können, müssen Sie in diesem Assistenten auf die Schaltfläche **Datenquelle** klicken, um eine Datenquelle auszuwählen.  
  
## UIElement-Liste  
 **Datenquelle**  
 Über die Schaltfläche **Datenquelle** können Sie die angegebene Datenquelle unter Verwendung des jeweiligen OLE DB\-Anbieters einrichten.  Durch Klicken auf diese Schaltfläche wird das Dialogfeld **Datenverknüpfungseigenschaften** geöffnet.  Weitere Informationen zum Erstellen von Verbindungszeichenfolgen sowie zum Dialogfeld **Datenverknüpfungseigenschaften** finden Sie unter [Data Link API Overview](https://msdn.microsoft.com/en-us/library/ms718102.aspx) in der [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\-Dokumentation.  
  
> [!NOTE]
>  In früheren Versionen wurde durch Drücken der UMSCHALTTASTE und gleichzeitiges Klicken auf die Schaltfläche **Datenquelle** ein Dialogfeld zum Öffnen von Dateien geöffnet, in dem eine Datenverknüpfungsdatei \(.udl\) ausgewählt werden konnte.  Diese Funktion wird nicht mehr unterstützt.  
  
 Das Dialogfeld verfügt über vier Registerkarten:  
  
-   Registerkarte **Anbieter**  
  
-   Registerkarte **Verbindung**  
  
-   Registerkarte **Erweitert**  
  
-   Registerkarte **Alle**  
  
     Die folgenden zusätzlichen Informationen beschreiben die Registerkarten im Dialogfeld **Datenlink\-Eigenschaften**.  
  
     Klicken Sie zum Fertigstellen auf **OK**.  Das Dialogfeld **Datenbankobjekt auswählen** wird geöffnet.  In diesem Dialogfeld wählen Sie die Tabelle, Ansicht oder gespeicherte Prozedur aus, die vom Consumer verwendet wird.  
  
     **Anbieter**  
     Wählen Sie einen entsprechenden Anbieter aus, um die Verbindung zur Datenquelle zu verwalten.  Der Typ des Anbieters wird in der Regel vom Typ der Datenbank bestimmt, mit der Sie eine Verbindung herstellen.  Klicken Sie auf die Schaltfläche `Next` oder klicken Sie auf die Registerkarte **Verbindung**.  
  
     **Verbindung**  
     Der Inhalt dieser Registerkarte hängt vom ausgewählten Anbieter ab.  Obwohl es viele Anbietertypen gibt, werden in diesem Abschnitt Verbindungen für die beiden gebräuchlichsten beschrieben: SQL\- und ODBC\-Daten.  Die anderen sind ähnliche Variationen der hier beschriebenen Felder.  
  
     Für SQL\-Daten:  
  
    1.  **Wählen Sie einen Servernamen aus, oder geben Sie ihn ein:** Klicken Sie auf das Dropdownlistenmenü, um alle registrierten Datenserver im Netzwerk anzuzeigen, und wählen Sie einen aus.  
  
    2.  **Geben Sie Informationen zum Anmelden am Server ein:** Geben Sie einen Benutzername und ein Kennwort zum Anmelden am Datenserver ein.  
  
    3.  **Wählen Sie die Datenbank auf dem Server aus:** Klicken Sie auf das Dropdownlistenmenü, um alle registrierten Datenbanken auf dem Datenserver anzuzeigen, und wählen Sie eine aus.  
  
         \- oder \-  
  
         **Datenbankdatei als Datenbanknamen anfügen:** Geben Sie eine als Datenbank zu verwendende Datei ein; geben Sie den expliziten Pfadnamen ein.  
  
        > [!NOTE]
        >  Das Feature "Speichern des Kennworts zulassen" im Dialogfeld "Datenverknüpfungseigenschaften" kann ein Sicherheitsproblem verursachen.  Unter "Geben Sie Informationen zur Anmeldung beim Server ein" gibt es zwei Optionsfelder:  
  
         **Integrierte Sicherheit von Windows NT verwenden**  
  
         **Spezifischen Benutzernamen und Kennwort verwenden**  
  
         Bei Auswahl von **Bestimmten Benutzernamen und ein Kennwort verwenden** können Sie das Kennwort zwar speichern \(mit dem Kontrollkästchen "Speichern des Kennworts zulassen"\), diese Option ist jedoch nicht sicher.  Es wird empfohlen, **Windows NT Integrated Security verwenden** auszuwählen. Diese Option ist sicher, da sie das Kennwort verschlüsselt.  
  
         Möglicherweise gibt es Situationen, in denen Sie "Speichern des Kennworts zulassen" auswählen möchten. Wenn Sie beispielsweise eine Bibliothek mit einer privaten Datenbanklösung freigeben, sollten Sie nicht direkt auf die Datenbank zugreifen, sondern stattdessen mithilfe einer Anwendung der mittleren Ebene den Benutzer überprüfen \(mit einem beliebigen Authentifizierungsschema\), und dann die Art der Daten einschränken, die dem Benutzer zur Verfügung stehen.  
  
         Für ODBC\-Daten:  
  
         1.  **Geben Sie die Datenquelle Daten an:** Sie können Sie einen Datenquellennamen oder eine Verbindungszeichenfolge verwenden.  
  
         **Datenquellennamen verwenden:** Diese Dropdownliste zeigt die Datenquellen an, die in Ihrem Computer registriert sind.  Sie können Datenquellen mithilfe [ODBC Data Source Administrator](!Alink("dasdkODBCDataSourceAdmin")) vorzeitig installieren. \- oder \- **Verwenden Sie eine Verbindungszeichenfolge:** Geben Sie entweder eine Verbindungszeichenfolge ein, die Sie bereits abgerufen haben, oder klicken Sie auf die Schaltfläche **Erstellen**. Das Dialogfeld **Datenquelle auswählen** wird angezeigt.  Wählen Sie eine Datei\- oder Computerdatenquelle aus, und klicken Sie auf **OK**.  
  
        > [!NOTE]
        >  Sie erhalten eine Verbindungszeichenfolge, indem Sie die Eigenschaften einer vorhandenen Verbindung im Server\-Explorer anzeigen, oder Sie können eine Verbindung erstellen, indem Sie auf **Verbindung hinzufügen** im Server\-Explorer doppelklicken.  
  
         2.  **Geben Sie Informationen zum Anmelden am Server ein:** Geben Sie einen Benutzername und ein Kennwort zum Anmelden am Datenserver ein.  
  
         3.  Geben Sie den zu verwendenden Anfangskatalog ein.  
  
         4.  Klicken Sie auf **Testverbindung**; wenn der Test erfolgreich ist, klicken Sie auf **OK**.  Wenn dies nicht der Fall ist, überprüfen Sie die Anmeldeinformationen, versuchen Sie eine andere Datenbank oder einen anderen Datenserver.  
  
     **Erweitert**  
     **Netzwerkeinstellungen:** Geben Sie [Impersonation level](!Alink("_com_Impersonation_Levels")) an \(die Ebene des Identitätswechsels, die mit dem Server zulässig ist, wenn der Client die Identität annimmt, entspricht direkt den RPC\-Identitätswechselebenen\) und **Schutzgrad** \(die Schutzebene von gesendeten Daten zwischen Client und Server, entspricht direkt den RPC\-Schutzebenen\).  
  
     **Andere:** Geben Sie unter **Verbindungstimeout** die zulässige Anzahl der Sekunden der Leerlaufzeit ein, bevor ein Timeout eintritt.  Geben Sie unter **Zugriffsberechtigungen** die Zugriffsberechtigungen für die Datenverbindung an.  
  
     Weitere Informationen über erweiterte Initialisierungseigenschaften finden Sie in der jeweiligen Dokumentation der einzelnen OLE DB\-Anbieter.  
  
     **Alle**  
     Diese Registerkarte zeigt eine Zusammenfassung der Initialisierungseigenschaften für die Datenquelle und die Verbindung an, die Sie angegeben haben.  Diese Werte können bearbeitet werden.  
  
     Klicken Sie zum Fertigstellen auf **OK**.  Das Dialogfeld **Datenbankobjekt auswählen** wird geöffnet.  In diesem Dialogfeld wählen Sie die Tabelle, Ansicht oder gespeicherte Prozedur aus, die vom Consumer verwendet wird.  
  
 `Class`  
 Nach der Auswahl einer Datenquelle wird in dieses Feld ein Standardklassenname eingefügt, der auf der ausgewählten Tabelle oder gespeicherten Prozedur basiert \(siehe **Datenquelle auswählen** weiter unten\).  Der Klassenname kann bearbeitet werden.  
  
 **.h\-Datei**  
 Nach der Auswahl einer Datenquelle wird in dieses Feld ein Name für die Standardheaderdatei eingefügt, der auf der ausgewählten Tabelle oder der ausgewählten gespeicherten Prozedur basiert \(siehe **Datenquelle auswählen** weiter unten\).  Sie können den Namen der Headerdatei ändern oder eine bestehende Headerdatei auswählen.  
  
 **Attributiert**  
 Durch diese Option wird festgelegt, ob der Assistent Consumerklassen unter Verwendung von Attributen oder von Vorlagendeklarationen erstellt.  Bei Auswahl dieser Option verwendet der Assistent Attribute anstelle von Vorlagendeklarationen \(Standardoption\).  Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstatt von Attributen.  
  
-   Wenn Sie für Consumer den **Typ** Tabelle auswählen, verwendet der Assistent das `db_source`\-Attribut und das **db\_table**\-Attribut, um die Deklarationen für die Tabellen\- und Tabellenaccessorklasse zu erstellen, und verwendet **db\_column** zum Erstellen der Spaltenzuordnung. Beispiel:  
  
    ```  
    // Inject table class and table accessor class declarations  
    [  
        db_source("<initialization_string>"),  
        db_table("dbo.Orders")  
    ]  
    ...  
    // Column map  
        [ db_column(1, status=m_dwOrderIDStatus,         length=m_dwOrderIDLength) ] LONG m_OrderID;  
        [ db_column(2, status=m_dwCustomerIDStatus,         length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
        ...  
    ```  
  
     anstatt die `CTable`\-Vorlagenklasse zum Deklarieren der Tabellen\- und Tabellenaccessorklasse und das BEGIN\_COLUMN\_MAP\-Makro und das END\_COLUMN\_MAP\-Makro zum Erstellen der Spaltenzuordnung zu verwenden. Beispiel:  
  
    ```  
    // Table accessor class  
    class COrdersAccessor;  
    // Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor> >;  
    ...  
    // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor)  
        COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID,         m_dwOrderIDLength, m_dwOrderIDStatus)  
        COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID,         m_dwCustomerIDLength, m_dwCustomerIDStatus)  
        ...  
    END_COLUMN_MAP()  
    ```  
  
-   Wenn Sie für Consumer den **Typ** Befehl auswählen, verwendet der Assistent das `db_source`\-Attribut und das **db\_command**\-Attribut sowie **db\_column** zum Erstellen der Spaltenzuordnung. Beispiel:  
  
    ```  
    [  
        db_source("<initialization_string>"),  
        db_command("SQL_command")  
    ]  
    ...  
    // Column map using db_column is the same as for consumer type of 'table'  
    ```  
  
     anstatt die Deklarationen für die Befehls\- und Befehlsaccessorklasse in der H\-Datei der Befehlsklasse zu verwenden. Beispiel:  
  
    ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor> >;  
    ...  
    // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as  
    // for consumer type of 'table'  
    ```  
  
 Weitere Informationen finden Sie unter [Basic Mechanics of Attributes](../../windows/basic-mechanics-of-attributes.md).  
  
 **Text \[Type\]**  
 Aktivieren Sie eine dieser Optionsschaltflächen, um anzugeben, ob die Consumerklasse von `CTable` oder `CCommand` \(Standard\) abgeleitet wird.  
  
 **Tabelle**  
 Wählen Sie diese Option, wenn `CTable` oder **db\_table** verwendet werden soll, um die Deklarationen für die Tabellen\- und Tabellenaccessorklasse zu erstellen.  
  
 **Befehl**  
 Wählen Sie diese Option, wenn `CCommand` oder **db\_command** verwendet werden soll, um die Deklarationen für die Befehls\- und Befehlsaccessorklasse zu erstellen.  Dies ist die Standardauswahl.  
  
 **Unterstützung**  
 Aktivieren Sie die entsprechenden Kontrollkästchen, um die Aktualisierungsarten festzulegen, die im Consumer unterstützt werden sollen \(standardmäßig wird keine Unterstützung aktiviert\).  Durch jede der folgenden Optionen werden [DBPROP\_IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715892.aspx) und die geeigneten Einträge für [DBPROP\_UPDATABILITY](https://msdn.microsoft.com/en-us/library/ms722676.aspx) in der Eigenschaftenset\-Zuordnung festgelegt.  
  
 **Änderung**  
 Gibt an, dass der Consumer Aktualisierungen von Zeilendaten im Rowset unterstützt.  
  
 **Insert**  
 Gibt an, dass der Consumer das Einfügen von Zeilen in das Rowset unterstützt.  
  
 **Delete**  
 Gibt an, dass der Consumer das Löschen von Zeilen aus dem Rowset unterstützt.  
  
## Siehe auch  
 [ATL OLE DB Consumer](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Verbindungszeichenfolgen und Datenverknüpfungen \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms718376.aspx)