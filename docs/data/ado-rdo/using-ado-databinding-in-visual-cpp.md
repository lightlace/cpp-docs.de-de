---
title: "Verwenden der ADO-Datenbindung in Visual C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO [C++], Datenbindung"
  - "Gebundene Steuerelemente [C++], ADO"
  - "Gebundene Steuerelemente [C++], RDO"
  - "Datenbindung [C++], ADO"
  - "Datenbindung [C++], RDO"
ms.assetid: ad193919-3437-41ee-b41c-9d353f6274e5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden der ADO-Datenbindung in Visual C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Verwendung der ADO\-Datenbindung in Visual C\+\+ setzt die folgenden Schritte voraus:  
  
-   Hinzufügen eines ADO\-Datensteuerelements.  
  
-   Zeigen auf eine Datenquelle.  
  
-   Festlegen der Datensatzquelle \(SQL\-Abfrage oder Datenempfangssprache\).  
  
-   Hinzufügen eines datengebundenen ADO\-Steuerelements.  
  
-   Verbinden des datengebundenen Steuerelements mit einem ADO\-Datensteuerelement.  
  
-   Auswählen der Felder, die an die Datensatzquelle des ADO\-Datensteuerelements gebunden werden sollen.  
  
### So verwenden Sie die ADO\-Datenbindung in Visual C\+\+  
  
1.  Erstellen Sie mit dem MFC\-Anwendungs\-Assistenten eine auf Dialogfeldern oder auf einer Formularansicht basierende MFC\-Anwendung.  
  
2.  Fügen Sie dem Dialogfeld das Microsoft ADO\-Datensteuerelement hinzu. Siehe [Einfügen des Steuerelements in eine Visual C\+\+\-Anwendung](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md).  
  
3.  Lassen Sie das ADO\-Datensteuerelement auf die OLE DB\-Datenquelle zeigen.  
  
    1.  Klicken Sie mit der rechten Maustaste auf das ADO\-Datensteuerelement, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Klicken Sie auf der Registerkarte **Steuerelement** auf **Verbindungszeichenfolge verwenden**.  Sie können den vorgegebenen Anbieter verwenden oder aber löschen.  
  
    3.  Klicken Sie auf **Erstellen**.  Wenn Sie den Anbieter unter **Verbindungszeichenfolge verwenden** gelöscht haben, können Sie jetzt einen Anbieter definieren.  Nachdem Sie den Anbieter definiert haben, rufen Sie die Eigenschaften des ADO\-Datensteuerelements erneut auf und wählen zum Fortfahren wieder **Erstellen** aus.  
  
         Wenn vor dem Klicken auf **Erstellen** unter **Verbindungszeichenfolge verwenden** bereits ein Anbieter definiert war, können Sie nun die Datenverknüpfungseigenschaften definieren.  Der DataLink\-Assistent wird geöffnet.  
  
    4.  Ändern Sie ggf. die Angabe unter **Anbieter**, und definieren Sie je nach Anbieter die entsprechenden Werte für **Speicherort** und **Datenquelle**.  Wenn Sie beispielsweise einen SQL Server\-Anbieter verwenden, wird unter **Speicherort** der Datenbankserver und unter **Datenquelle** die Datenbank angegeben.  Verwenden Sie hingegen einen ODBC\-Anbieter, entspricht **Datenquelle** dem ODBC\-DSN.  
  
    5.  Klicken Sie auf die Registerkarte **Authentifizierung**, und geben Sie unter **Benutzername** und **Kennwort** Werte ein, falls diese von der Datenquelle benötigt werden.  
  
    6.  Klicken Sie auf die Registerkarte **Verbindung**, und klicken Sie auf **Testverbindung**, um die Datenquelle zu testen.  Führen Sie den Bildlauf bis zum Ende des Fensters **Ergebnisse** durch, um festzustellen, ob der Test erfolgreich war.  Falls er fehlschlägt, überprüfen Sie die Konfiguration der Datenquelle.  Häufig werden Fehler durch ungültige Kennwörter und falsche Werte in den Feldern **Speicherort** und **Datenquelle** verursacht.  
  
    7.  Beenden Sie den DataLink\-Assistenten, und kehren Sie zum Eigenschaftenblatt des ADO\-Datensteuerelements zurück.  
  
4.  Geben Sie auf der Registerkarte `RecordSource` unter **Befehlstext \(SQL\)** eine Abfrage ein.  Die datengebundenen Steuerelemente sind in der Lage, eine Bindung mit den Ergebnissen der Abfrage herzustellen.  Die Abfrage ist normalerweise eine SQL\-Anweisung.  Einige OLE DB\-Anbieter verwenden jedoch kein SQL.  
  
5.  Legen Sie ggf. weitere Eigenschaften des ADO\-Datensteuerelements fest, und schließen Sie das Eigenschaftenblatt des ADO\-Datensteuerelements.  
  
6.  Fügen Sie ein datengebundenes Steuerelement hinzu.  \(Verwenden Sie beispielsweise das Datentabellen\-Steuerelement, das sich vom RDO\-DBTabelle\-Steuerelement unterscheidet.\)  
  
7.  Legen Sie die Eigenschaften des Datentabellen\-Steuerelements fest.  
  
    1.  Klicken Sie mit der rechten Maustaste auf die Datentabelle, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Klicken Sie auf die Registerkarte **Alle**, und legen Sie als **DataSource**\-Eigenschaft das ADO\-Datensteuerelement fest.  Klicken Sie auf die Dropdownliste **DataSource**, und suchen Sie nach der ID des ADO\-Datensteuerelements.  Die Standard\-ID lautet IDC\_ADODC1.  
  
8.  Starten Sie den Testmodus durch Drücken von STRG\+T.  Sie können dann einen Bildlauf durch die Daten durchführen.  Sie beenden den Testmodus mit ESC oder durch Schließen des Dialogfelds.  
  
 Wenn Sie das Programm kompilieren und ausführen, sind Sie ebenfalls in der Lage, einen Bildlauf durch die Daten durchzuführen.  
  
## Siehe auch  
 [ADO\-Datenbindung](../../data/ado-rdo/ado-databinding.md)   
 [Datenbindung mit ActiveX\-Steuerelementen in Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)