---
title: ATL-OLE DB-Consumer-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/31/2018
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
ms.openlocfilehash: 163949c4421cca8e4d5e414a18bda4ed98f32d3d
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861641"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL-OLE DB-Consumer-Assistent

Dieser Assistent richtet eine OLE DB-Consumer-Klasse mit datenbindungen, die zum Zugriff auf die angegebene Datenquelle über den angegebenen OLE DB-Anbieter.

> [!NOTE]
> Mit diesem Assistenten müssen Sie auf die **Datenquelle** klicken, um eine Datenquelle auszuwählen, bevor Sie eingeben der Namen in der `Class` und **.h-Datei** Felder.

## <a name="uielement-list"></a>UIElement-Liste

- **Datenquelle**

   Die **Datenquelle** Schaltfläche können Sie die angegebene Datenquelle, die mit dem angegebenen OLE DB-Anbieter einrichten. Wenn Sie auf diese Schaltfläche, klicken Sie auf die **Datenlinkeigenschaften** Dialogfeld wird angezeigt. Weitere Informationen zum Erstellen von Verbindungszeichenfolgen und die **Datenlinkeigenschaften** im Dialogfeld finden Sie unter [Data Link-API – Übersicht](/previous-versions/windows/desktop/ms718102\(v=vs.85\)) in der Windows SDK-Dokumentation.

   Die folgende zusätzliche Informationen beschreibt die Registerkarten in der **Datenlinkeigenschaften** Dialogfeld.

   - **Anbieter** Registerkarte

      Wählen Sie einen entsprechenden-Anbieter für die Verbindung mit der Datenquelle zu verwalten. Der Typ des Anbieters wird normalerweise durch den Typ der Datenbank bestimmt, der Sie eine Verbindung herstellen. Klicken Sie auf die **Weiter** Schaltfläche aus, oder klicken Sie auf die **Verbindung** Registerkarte.

   - **Verbindung** Registerkarte

      Der Inhalt dieser Registerkarte hängt von der gewählten Anbieter ab. Es gibt, zwar viele Arten von Anbietern handelt es sich bei dieser Abschnitt behandelt die Verbindungen für die beiden am häufigsten verwendeten: SQL- und ODBC-Daten. Die anderen sind ähnlich wie Variationen der hier beschriebenen Felder.

      Für SQL-Daten:

      1. **Wählen Sie aus, oder geben Sie einen Servernamen:** klicken Sie auf das Dropdown-Listenfeld-Menü, um alle registrierten Daten-Server im Netzwerk angezeigt, und wählen Sie eine.

      1. **Geben Sie Informationen zum Anmelden an den Server:** Geben Sie einen Benutzernamen und Kennwort, mit dem Datenserver anzumelden.

         > [!NOTE]
         > Es gibt ein Sicherheitsproblem mit der Funktion "Speichern des Kennworts zulassen" des Dialogfelds Eigenschaften für Datenlinks. Es gibt zwei Optionsfelder, in "Geben Sie Informationen zum Anmelden an den Server":
         >
         > - **Windows NT integrated Security verwenden**
         > - **Bestimmten Benutzernamen und bestimmtes Kennwort**
         >
         > Bei Auswahl von **bestimmten Benutzernamen und bestimmtes Kennwort**, Sie haben die Möglichkeit, speichern Sie das Kennwort (mit der Sie das Kontrollkästchen für "Speichern des Kennworts zulassen"); diese Option ist jedoch nicht sicher. Es wird empfohlen, die Sie auswählen, **Windows NT integrated Security verwenden**; diese Option ist sicherer, da das Kennwort verschlüsselt.
         > Es kann jedoch Situationen, in denen gewünschten "Speichern von Kennwort zulassen". Z. B. Wenn Sie eine Bibliothek mit einer privaten datenbanklösung freigeben, sollten Sie nicht greifen direkt auf die Datenbank jedoch stattdessen eine Anwendung der mittleren Ebene verwenden, überprüfen den Benutzer (über den Authentifizierungsschema, das Sie auswählen), und klicken Sie dann die Art der Daten zu beschränken für den Benutzer verfügbar.

      1. **Wählen Sie die Datenbank auf dem Server:** klicken Sie auf das Dropdown-Listenfeld-Menü, um alle registrierten Datenbanken auf dem Datenserver angezeigt, und wählen Sie eine.

         \- oder –

         **Anfügen einer Datenbankdatei als Datenbanknamen:** Geben Sie eine Datei als die Datenbank verwendet werden soll, geben Sie den expliziten Pfadnamen.

      Für ODBC-Daten:

      1. **Geben Sie die Quelle der Daten:** können Sie einen Data Source Name oder eine Verbindungszeichenfolge verwenden.

         **Name der Datenquelle verwenden:** dieses Dropdown-Liste zeigt Datenquellen, die auf Ihrem Computer registriert. Sie können Datenquellen voraus mithilfe von ODBC-Datenquellen-Administrator einrichten

         \- oder –

         **Verwenden Sie die Verbindungszeichenfolge:** Geben Sie eine Verbindungszeichenfolge, die Sie bereits erworben haben, oder klicken Sie auf die **erstellen** Schaltfläche der **Auswählen einer Datenquelle** Dialogfeld wird angezeigt. Vybrat zdroj DAT-Datei oder der Computer, und klicken Sie auf **OK**.

         > [!NOTE]
         > Sie erhalten eine Verbindungszeichenfolge durch Anzeigen der Eigenschaften einer vorhandenen Verbindung in **Server-Explorer**, oder Sie können eine Verbindung erstellen, durch Doppelklicken auf **Verbindung hinzufügen** in **Server Explorer**.

      1. **Geben Sie Informationen zum Anmelden an den Server:** Geben Sie einen Benutzernamen und Kennwort, mit dem Datenserver anzumelden.

      1. Geben Sie den ersten Katalog verwenden.

      1. Klicken Sie auf **Verbindung testen**; Wenn der Test erfolgreich ist, klicken Sie auf **OK**. Wenn dies nicht der Fall ist, überprüfen Sie Ihre Anmeldeinformationen, versuchen Sie es einer anderen Datenbank oder einen anderen Datenserver.

   - **Erweiterte** Registerkarte

      **Netzwerkeinstellungen:** geben die **Ebene des Identitätswechsels** (die Ebene des Identitätswechsels, die der Server zu verwenden, wenn der Identitätswechsel für den Client zulässig ist, entspricht direkt den RPC-Ebenen des Identitätswechsels) und  **Schutzebene** (das Maß an Schutz von Daten zwischen Client und Server gesendeten entspricht direkt den RPC-Schutzebenen).

      **Sonstiges:** In **Verbindungstimeout**, geben Sie die Anzahl von Sekunden Zeit im Leerlauf, die zulässig sind, bevor ein Timeout auftritt. In **Zugriffsberechtigungen**, geben Sie die Zugriffsberechtigungen auf die Datenverbindung.

       Weitere Informationen zu erweiterten Eigenschaften finden Sie in der Begleitdokumentation für jeden bestimmten OLE DB-Anbieter.

   - **Alle** Registerkarte

      Diese Registerkarte zeigt eine Zusammenfassung der Initialisierungseigenschaften für die Datenquelle und die Verbindung, die Sie angegeben haben. Sie können diese Werte bearbeiten.

   Klicken Sie auf **OK** um den Vorgang abzuschließen. Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt. Wählen Sie in diesem Dialogfeld die Tabelle, Sicht oder gespeicherte Prozedur, den vom Consumer verwendet wird.

- **Klasse**

   Nachdem Sie eine Datenquelle ausgewählt haben, dieses Feld wird gefüllt mit einem Standardnamen-Klasse anhand der Tabelle oder eine gespeicherte Prozedur, die Sie ausgewählt haben (finden Sie unter **Vybrat zdroj DAT** unten). Sie können den Namen der Klasse bearbeiten.

- **H-Datei**

   Nachdem Sie eine Datenquelle ausgewählt haben, dieses Feld wird gefüllt mit einem Standard-Header-Klassennamen basierend auf der Tabelle oder eine gespeicherte Prozedur, die Sie ausgewählt haben (finden Sie unter **Vybrat zdroj DAT** unten). Sie können die Namen für die Header-Datei bearbeiten oder eine vorhanden Headerdatei auswählen.

- **Zugeordnet sind**

   Diese Option gibt an, ob der Assistent vom Consumer-Klassen, die mithilfe von Attributen oder Vorlagendeklarationen erstellt. Wenn Sie diese Option auswählen, verwendet der Assistent Attribute anstatt von Vorlagendeklarationen (Dies ist die Standardoption) aus. Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attributen.

   - Bei Auswahl von einem Consumer **Typ** von **Tabelle**, verwendet der Assistent die `db_source` und `db_table` Attribute, um die Tabelle und die Tabellenaccessor Klassendeklarationen erstellen, und verwendet `db_column` auf die spaltenzuordnung zu erstellen. Beispielsweise wird diese Zuordnung erstellt:

        ```cpp
        // Inject table class and table accessor class declarations
        [db_source("<initialization_string>"), db_table("dbo.Orders")]
        ...
        // Column map
        [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;
        [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];
        ...
        ```

      anstatt die `CTable` Vorlagenklasse, die in der Tabelle und Tabelle Accessor-Klasse und die BEGIN_COLUMN_MAP und END_COLUMN_MAP Makros zum Erstellen der Spalte-Karte, wie im folgenden Beispiel deklarieren:

        ```cpp
        // Table accessor class
            class COrdersAccessor; // Table class
            class COrders : public CTable<CAccessor<COrdersAccessor>>;
        // ...
        // Column map
            BEGIN_COLUMN_MAP(COrderDetailsAccessor)
                COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)
                COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)
                // ...
            END_COLUMN_MAP()
        ```

   - Bei Auswahl von einem Consumer **Typ** von **Befehl**, verwendet der Assistent die `db_source` und `db_command` Attribute aus, und verwendet `db_column` die spaltenzuordnung zu erstellen. Beispielsweise wird diese Zuordnung erstellt:

        ```cpp
        [db_source("<initialization_string>"), db_command("SQL_command")]
        ...
        // Column map using db_column is the same as for consumer type of 'table'
        ```

      anstatt den Befehl und den Befehl Accessor Klassendeklarationen in die Befehlsklasse .h-Datei, z. B.:

        ```cpp
        // Command accessor class:
            class CListOrdersAccessor;
        // Command class:
            class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;
        // ...
        // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
        // for consumer type of 'table'
        ```

      Finden Sie unter [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.

- **Type**

   Wählen Sie eine der folgenden Optionsfelder an, ob die Consumerklasse abgeleitet wird `CTable` oder `CCommand` (Standard).

   - **Table**

      Wählen Sie diese Option aus, wenn Sie verwenden möchten `CTable` oder `db_table` die Tabellen- und Klassendeklarationen erstellen.

   - **Befehl**

      Wählen Sie diese Option aus, wenn Sie verwenden möchten `CCommand` oder `db_command` der Befehls- und Klassendeklarationen erstellen. Dies ist die Standardauswahl.

- **Unterstützung**

   Wählen Sie die Kontrollkästchen, um die Art der Updates, die im Consumer unterstützt werden (der Standardwert ist "None") anzugeben. Folgendes wird festgelegt, [DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892\(v=vs.85\)) und die entsprechenden Einträge für [DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676\(v=vs.85\)) -Zuordnung in der Eigenschaft festgelegt.

   - **Änderung**

      Gibt an, dass die Consumer Updates der Daten der Zeile im Rowset unterstützt.

   - **Einfügen**

      Gibt an, dass der Consumer das Einfügen von Zeilen in das Rowset unterstützt.

   - **Löschen**

      Gibt an, dass der Consumer das Löschen von Zeilen aus dem Rowset unterstützt.

## <a name="see-also"></a>Siehe auch

[ATL-OLE DB-Consumers](../../atl/reference/adding-an-atl-ole-db-consumer.md)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Verbindungszeichenfolgen und Datenverknüpfungen (OLE DB)](/previous-versions/windows/desktop/ms718376\(v=vs.85\))
