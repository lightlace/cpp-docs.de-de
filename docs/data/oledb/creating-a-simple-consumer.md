---
title: "Erstellen eines einfachen Consumers | Microsoft Docs"
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
  - "OLE DB-Consumer, Erstellen"
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erstellen eines einfachen Consumers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie den ATL\-Projekt\-Assistenten und den ATL\-OLE DB\-Consumer\-Assistenten, um einen OLE DB\-Vorlagenconsumer zu erstellen.  
  
#### So erstellen Sie eine Konsolenanwendung für einen OLE DB\-Consumer  
  
1.  Klicken Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Klicken Sie im Bereich Projekttypen auf den Ordner **Visual C\+\+\-Projekte**, und klicken Sie im Bereich Vorlagen auf das Symbol **Win32\-Projekt**.  Geben Sie im Feld **Name** den Namen des Projekts ein, z. B. **MyCons**.  
  
3.  Klicken Sie auf **OK**.  
  
     Der Win32\-Anwendungs\-Assistent wird angezeigt.  
  
4.  Wählen Sie auf der Seite **Anwendungseinstellungen** die Option **Konsolenanwendung** aus, und wählen Sie anschließend **ATL\-Unterstützung hinzufügen** aus.  
  
5.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das Projekt zu erstellen.  
  
 Verwenden Sie als nächstes den ATL OLE DB\-Consumer\-Assistenten, um ein OLE DB\-Consumerobjekt hinzuzufügen.  
  
#### So erstellen Sie einen Consumer mit dem ATL\-OLE DB\-Consumer\-Assistenten  
  
1.  Klicken Sie in der Klassenansicht auf das `MyCons` \- Projekt mit der rechten Maustaste.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
     Das Dialogfeld **Klasse hinzufügen** wird angezeigt.  
  
3.  Klicken Sie im Bereich Kategorien auf **Visual C\+\+** und im Bereich Vorlagen auf das Symbol **ATL\-OLE DB\-Consumer**. Klicken Sie dann auf **Öffnen**.  
  
     Der ATL\-OLE DB\-Consumer\-Assistent wird angezeigt.  
  
4.  Klicken Sie auf die Schaltfläche **Datenquelle**.  
  
     Das Dialogfeld **Datenverbindungseigenschaften** wird angezeigt.  
  
5.  Führen Sie im Dialogfeld **Datenverknüpfungseigenschaften** die folgenden Schritte aus:  
  
    -   Geben Sie auf der Registerkarte **Anbieter** einen OLE DB\-Anbieter an.  
  
    -   Geben Sie auf der Registerkarte **Verbindung** den Servernamen, die Anmelde\-ID und das Kennwort für die Datenquelle sowie die Datenbank auf dem Server an.  
  
    > [!NOTE]
    >  Das Feature **Speichern des Kennworts zulassen** im Dialogfeld **Datenverknüpfungseigenschaften** kann ein Sicherheitsproblem verursachen.  In **Geben Sie Informationen zur Anmeldung beim Server ein** sind zwei Optionsfelder vorhanden: **Windows NT Integrated Security verwenden** und **Bestimmten Benutzernamen und ein Kennwort verwenden**.  
  
    > [!NOTE]
    >  Bei Auswahl von **Bestimmten Benutzernamen und ein Kennwort verwenden** können Sie das Kennwort zwar speichern \(mit dem Kontrollkästchen **Speichern des Kennworts zulassen**\), diese Option ist jedoch nicht sicher.  Daher wird empfohlen, **Windows NT Integrated Security verwenden** auszuwählen und auf diese Weise die Identität durch Windows NT zu überprüfen.  
  
    > [!NOTE]
    >  Wenn Sie nicht mit Windows NT Integrated Security arbeiten können, sollten Sie eine Anwendung mittlerer Ebene verwenden, damit der Benutzer zur Eingabe eines Kennworts aufgefordert oder das Kennwort an einem sicheren Ort \(und nicht im Quellcode\) gespeichert wird.  
  
     Klicken Sie nach dem Auswählen des Anbieters und der anderen Einstellungen auf **Testverbindung**, um die auf den vorherigen Dialogfeldseiten festgelegten Einstellungen zu überprüfen.  Wenn **Ergebnisse**  das Feld über `Test connection succeeded` gemeldet, klicken auf **OK**, um die Datenverknüpfung zu erstellen.  
  
     Das Dialogfeld **Datenbankobjekt auswählen** wird geöffnet.  
  
6.  Wählen Sie in der Strukturansicht eine Tabelle, eine Ansicht oder eine gespeicherte Prozedur aus.  Wählen Sie für diese Prozedur die Tabelle **Products** aus der Northwind\-Datenbank.  
  
7.  Klicken Sie auf **OK**.  Dadurch gelangen Sie wieder zurück zum ATL\-OLE DB\-Consumer\-Assistenten.  
  
8.  Der Assistent vervollständigt die Namen für `Class` und **.h file** anhand des Namens der Tabelle, Ansicht oder gespeicherten Prozedur ab, die Sie ausgewählt haben.  Sie können diese Namen nach Wunsch bearbeiten.  
  
9. Deaktivieren Sie das Kontrollkästchen **Attributiert**, damit der Assistent zur Erstellung des Consumercodes nicht die standardmäßigen [OLE DB\-Consumerattribute](../../windows/ole-db-consumer-attributes.md) sondern [OLE DB\-Vorlagenklassen](../../data/oledb/ole-db-consumer-templates-reference.md) verwendet.  
  
10. Wählen Sie unter **Typ** die Option **Befehl** aus.  
  
     Wenn Sie **Befehl** auswählen, erstellt der Assistent einen [CCommand](../../data/oledb/ccommand-class.md)\-basierten Consumer. Wenn Sie **Tabelle** auswählen, wird ein [CTable](../../data/oledb/ctable-class.md)\-basierter Consumer erstellt.  Die Tabellen\- oder Befehlsklasse wird nach dem ausgewählten Objekt benannt. Sie können den Namen jedoch bearbeiten.  
  
11. Aktivieren Sie unter **Unterstützung** die Kontrollkästchen **Ändern**, **Einfügen** und **Löschen** nicht.  
  
     Wählen Sie **Ändern**, **Einfügen** oder **Löschen** aus, um bei Bedarf das Ändern, Einfügen und Löschen von Datensätzen im Rowset zu unterstützen.  Weitere Informationen über das Schreiben von Daten in den Datenspeicher finden Sie unter [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).  
  
12. Klicken Sie auf **Fertig stellen**, um den Consumer zu erstellen.  
  
 Der Assistent erstellt eine Befehlsklasse und eine Benutzerdatensatz\-Klasse, wie unter [Vom Consumer\-Assistenten generierte Klassen](../../data/oledb/consumer-wizard-generated-classes.md) aufgezeigt.  Die Befehlsklasse trägt den Namen, den Sie im Assistenten im Feld `Class` \(in diesem Fall, `CProducts`\) eingeben, und die Benutzerdatensatz\-Klasse hat einen Namen des Formulars "*ClassNameAccessor*" \(in diesem Fall, `CProductsAccessor`\).  
  
> [!NOTE]
>  Der Assistent fügt in Products.h die folgende Zeile ein:  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Diese Zeile hindert die Consumeranwendung am Kompilieren, und erinnert Sie daran, die Verbindungszeichenfolgen für fest codierte Kennwörter zu überprüfen.  Sie können diese Codezeile entfernen, nachdem Sie die Verbindungszeichenfolge überprüft haben.  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)