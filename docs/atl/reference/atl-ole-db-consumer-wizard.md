---
title: ATL-OLE DB-Consumer-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f53d8273a708b7f84393290dd578933a5390313c
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121688"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL-OLE DB-Consumer-Assistent
Dieser Assistent richtet eine OLE DB-Consumer-Klasse mit datenbindungen, die zum Zugriff auf die angegebene Datenquelle über den angegebenen OLE DB-Anbieter.  
  
> [!NOTE]
>  Dieser Assistent erfordert, dass Sie auf die **Datenquelle** klicken, um eine Datenquelle auszuwählen, vor dem Eingeben der Namen in der `Class` und **.h-Datei** Felder.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Datenquelle**  
 Die **Datenquelle** Schaltfläche können Sie die angegebene Datenquelle mithilfe des angegebenen OLE DB-Anbieters eingerichtet. Wenn Sie auf diese Schaltfläche, klicken Sie auf die **Datenlinkeigenschaften** Dialogfeld wird angezeigt. Weitere Informationen zum Erstellen von Verbindungszeichenfolgen und die **Datenlinkeigenschaften** (Dialogfeld), finden Sie unter [Data Link API Overview](https://msdn.microsoft.com/library/ms718102.aspx) in das Windows SDK-Dokumentation.  
  
> [!NOTE]
>  In früheren Versionen, die UMSCHALT-Taste die **Datenquelle** Schaltfläche Öffnen ein Dialogfeld, öffnen Sie eine Datei Data Link (UDL) auswählen können. Diese Funktionalität wird nicht mehr unterstützt.  
  
 Das Dialogfeld enthält vier Registerkarten:  
  
- **Anbieter** Registerkarte  
  
- **Verbindung** Registerkarte  
  
- **Erweiterte** Registerkarte  
  
- **Alle** Registerkarte  
  
     Die folgende zusätzliche Informationen beschreibt die Registerkarten in der **Datenlinkeigenschaften** (Dialogfeld).  
  
     Klicken Sie auf **OK** um den Vorgang abzuschließen. Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt. Wählen Sie in diesem Dialogfeld die Tabelle, Sicht oder gespeicherte Prozedur, die vom Consumer verwendet wird.  
  
 **Anbieter**  
     Wählen Sie einen entsprechenden Anbieter auf die Verbindung mit der Datenquelle zu verwalten. Der Typ des Anbieters wird in der Regel durch den Typ der Datenbank bestimmt, zu dem Sie eine Verbindung herstellen. Klicken Sie auf die `Next` klicken, oder klicken Sie auf die **Verbindung** Registerkarte.  
  
 **Verbindung**  
     Der Inhalt dieser Registerkarte hängt von den ausgewählten Anbieter ab. Dieser Abschnitt behandelt zwar viele Arten von Anbietern, Verbindungen für die beiden am häufigsten verwendeten: SQL- und ODBC-Daten. Die anderen sind ähnliche Variationen der hier beschriebenen Felder.  
  
     Für SQL-Daten:  
  
    1. **Wählen Sie aus, oder geben Sie einen Servernamen:** klicken Sie auf das Dropdown-Liste-Menü, um alle registrierten Server im Netzwerk anzuzeigen, und wählen Sie eine.  
  
    2. **Geben Sie Informationen zum Melden Sie sich an den Server:** Geben Sie einen Benutzernamen und ein Kennwort ein, mit dem Datenserver anzumelden.  
  
    3. **Wählen Sie die Datenbank auf dem Server:** klicken Sie auf das Menü Dropdown-Liste, um alle registrierten Datenbanken auf dem Datenserver anzuzeigen, und wählen Sie eine.  
  
         - oder -   
  
 **Anfügen einer Datenbankdatei als Datenbanknamen:** Geben Sie eine Datei als die Datenbank verwendet werden soll, geben Sie den expliziten Pfadnamen.  
  
        > [!NOTE]
        >  There is a security problem with the "Allow saving of password" feature of the Data Link Properties dialog box. In "Enter information to log on to the server," there are two radio buttons:  
  
 **Windows NT integrated Security verwenden**  
  
 **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**  
  
         If you select **Use a specific user name and password**, you have the option of saving the password (using the check box for "Allow saving password"); however, this option is not secure. It is recommended that you select **Use Windows NT integrated security**; this option is secure because it encrypts the password.  
  
         There might be situations in which you want to select "Allow saving password." For example, if you are releasing a library with a private database solution, you should not access the database directly but instead use a middle-tier application to verify the user (through whatever authentication scheme you choose) and then limit the sort of data available to the user.  
  
         For ODBC data:  
  
         1. **Specify the source of data:** You can use a data source name or a connection string.  
  
 **Name der Datenquelle verwenden:** dieses Dropdown-Liste zeigt Datenquellen, die auf Ihrem Computer registriert. Können Sie Datenquellen mithilfe von ODBC-Datenquellen-Administrator voraus einrichten- oder -**Verbindungszeichenfolge verwenden:** Geben Sie eine Verbindungszeichenfolge, die Sie bereits abgerufen haben, oder klicken Sie auf die **erstellen** Schaltfläche; die **Auswählen einer Datenquelle** Dialogfeld wird angezeigt. Wählen Sie eine Datei oder der Computer-Datenquelle, und klicken Sie auf **OK**.  
  
        > [!NOTE]
        >  You can obtain a connection string by viewing the properties of an existing connection in Server Explorer, or you can create a connection by double-clicking **Add Connection** in Server Explorer.  
  
         2. **Enter information to log on to the server:** Enter a user name and password to log on to the data server.  
  
         3. Enter the initial catalog to use.  
  
         4. Click **Test Connection**; if the test succeeds, click **OK**. If not, check your logon information, try another database, or try another data server.  
  
 **Erweitert**  
 **Netzwerkeinstellungen:** geben die **Identitätswechselebene** (die Ebene des Identitätswechsels, die der Server beim Identitätswechsel für den Client zu verwendende zulässig ist, entspricht direkt den RPC-Identitätswechselebenen) und  **Schutzebene** (das Maß an Schutz von Daten zwischen Client und Server gesendeten entspricht direkt den RPC-Schutzebenen).  
  
 **Andere:** In **Verbindungstimeout**, geben Sie die Anzahl der Sekunden der Leerlaufzeit zulässig sind, bevor ein Timeout auftritt. In **Zugriffsberechtigungen**, geben Sie die Zugriffsberechtigungen auf die Datenverbindung.  
  
     Weitere Informationen über erweiterte Initialisierungseigenschaften finden Sie in der Dokumentation, die mit jeder bestimmte OLE DB-Anbieter bereitgestellt.  
  
 **All**  
     Diese Registerkarte zeigt eine Zusammenfassung der Initialisierungseigenschaften für die Datenquelle und die Verbindung, die Sie angegeben haben. Sie können diese Werte bearbeiten.  
  
     Klicken Sie auf **OK** um den Vorgang abzuschließen. Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt. Wählen Sie in diesem Dialogfeld die Tabelle, Sicht oder gespeicherte Prozedur, die vom Consumer verwendet wird.  
  
 `Class`  
 Nachdem Sie eine Datenquelle ausgewählt haben, wird dieses Feld mit einem Standardnamen-Klasse anhand der Tabelle oder gespeicherten Prozedur, die Sie ausgewählt aufgefüllt (finden Sie unter **wählen Sie eine Datenquelle** unten). Sie können den Klassennamen bearbeiten.  
  
 **H-Datei**  
 Nachdem Sie eine Datenquelle ausgewählt haben, dieses Feld wird aufgefüllt durch einen Klassennamen der Standard-Header basierend auf der Tabelle oder gespeicherten Prozedur, die Sie ausgewählt haben (finden Sie unter **wählen Sie eine Datenquelle** unten). Sie können Namen für die Header-Datei bearbeiten oder wählen Sie eine bestehende Headerdatei.  
  
 **Mit Attributen versehen**  
 Diese Option gibt an, ob der Assistent Consumerklassen unter Verwendung von Attributen oder Vorlagendeklarationen erstellt wird. Wenn Sie diese Option auswählen, verwendet der Assistent Attribute anstelle von Vorlagendeklarationen (Dies ist die Standardoption). Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attributen.  
  
-   Bei Auswahl von einem Consumer **Typ** der Tabelle, die der Assistent verwendet die `db_source` und **Db_table** Attribute, um die Tabelle und die Tabellenaccessor Klassendeklarationen erstellen und verwendet **Db_column**  , z. B. die spaltenzuordnung zu erstellen:  
  
 ``` 
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...  
 ```  
  
     anstatt die `CTable` Vorlagenklasse zum Deklarieren der Tabelle und Accessor Tabellenklasse und den BEGIN_COLUMN_MAP und END_COLUMN_MAP-Makros, um die spaltenzuordnung, z. B. erstellen:  
  
 ``` 
 // Table accessor class  
    class COrdersAccessor; // Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
 ```  
  
-   Bei Auswahl von einem Consumer **Typ** des Befehls, der Assistent verwendet die `db_source` und **Db_command** Attributen und verwendet **Db_column** spaltenzuordnung, z. B. erstellen :  
  
 ```  
 [db_source("<initialization_string>"), db_command("SQL_command")]  
 ... 
 // Column map using db_column is the same as for consumer type of 'table'  
 ```  
  
     anstatt den Befehl und den Befehl Accessor Klassendeklarationen in die Befehlsklasse .h-Datei, z. B.:  
  
 ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;  
 ... 
 // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
 // for consumer type of 'table'  
 ```  
  
 Finden Sie unter [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.  
  
 **Type**  
 Wählen Sie eine dieser Optionsfelder, um anzugeben, ob die Consumerklasse abgeleitet `CTable` oder `CCommand` (Standard).  
  
 **Table**  
 Wählen Sie diese Option aus, wenn Sie verwenden möchten `CTable` oder **Db_table** die Tabellen- und Klassendeklarationen erstellen.  
  
 **Befehl**  
 Wählen Sie diese Option aus, wenn Sie verwenden möchten `CCommand` oder **Db_command** die Befehls- und Klassendeklarationen erstellen. Dies ist die Standardauswahl.  
  
 **Unterstützung**  
 Wählen Sie die Kontrollkästchen, um die Art der Updates, die in der Consumer unterstützt werden (die Standardeinstellung ist "none") anzugeben. Jede der folgenden wird festgelegt, [DBPROP_IRowsetChange](https://msdn.microsoft.com/library/ms715892.aspx) und die entsprechenden Einträge für [DBPROP_UPDATABILITY](https://msdn.microsoft.com/library/ms722676.aspx) im Eigenschaftensatz Zuordnung.  
  
 **Ändern**  
 Gibt an, dass der Consumer Updates der Daten aus Zeile im Rowset unterstützt.  
  
 **Einfügen**  
 Gibt an, dass der Consumer das Einfügen von Zeilen in das Rowset unterstützt.  
  
 **Löschen**  
 Gibt an, dass der Consumer das Löschen von Zeilen aus dem Rowset unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-OLE DB-Consumers](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Verbindungszeichenfolgen und Datenverknüpfungen (OLE DB)](https://msdn.microsoft.com/library/ms718376.aspx)
