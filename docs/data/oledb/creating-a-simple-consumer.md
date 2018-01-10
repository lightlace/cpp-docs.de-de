---
title: Erstellen eines einfachen Consumers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5febdc019f5e575f685e4e93c892b7f5e777b776
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-simple-consumer"></a>Erstellen eines einfachen Consumers
Verwenden Sie die ATL-Projekt-Assistent und die ATL-OLE DB-Consumer-Assistenten, um einen OLE DB-Vorlagen-Consumer zu generieren.  
  
#### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>So erstellen eine Konsolenanwendung für einen OLE DB-consumer  
  
1.  Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Klicken Sie im Bereich Projekttypen auf die **Visual C++-Projekte** Ordner, und klicken Sie dann auf die **Win32-Projekt** Symbol ", klicken Sie im Bereich" Vorlagen ". In der **Namen** Geben Sie den Namen des Projekts, z. B. **MyCons**.  
  
3.  Klicken Sie auf **OK**.  
  
     Die Win32-Projekt-Assistent wird angezeigt.  
  
4.  Auf der **Anwendungseinstellungen** Seite **Konsolenanwendung**, und wählen Sie dann **ATL-Unterstützung hinzufügen**.  
  
5.  Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen und das Projekt zu erstellen.  
  
 Als Nächstes verwenden Sie den ATL OLE DB-Consumer-Assistenten zum Hinzufügen eines OLE DB-Consumer-Objekts.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>So erstellen Sie einen Consumer mit ATL-OLE DB-Consumer-Assistenten  
  
1.  In der Klassenansicht Maustaste die `MyCons` Projekt.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.  
  
     Die **Klasse hinzufügen** Dialogfeld wird angezeigt.  
  
3.  Klicken Sie in den Bereich "Kategorien" auf **Visual C++**, klicken Sie auf die **ATL-OLE DB-Consumer** in der Vorlagen (Bereich), und klicken Sie dann auf **öffnen**.  
  
     ATL-OLE DB-Consumer-Assistent wird angezeigt.  
  
4.  Klicken Sie auf die **Datenquelle** Schaltfläche.  
  
     Die **Datenlinkeigenschaften** Dialogfeld wird angezeigt.  
  
5.  In der **Datenlinkeigenschaften** Dialogfeld Feld, gehen Sie folgendermaßen vor:  
  
    -   Auf der **Anbieter** Registerkarte geben Sie einen OLE DB-Anbieter.  
  
    -   Auf der **Verbindung** Registerkarte, geben Sie den Servernamen, Anmelde-ID und Kennwort für die Datenquelle und die Datenbank auf dem Server.  
  
    > [!NOTE]
    >  Es ist ein Sicherheitsproblem mit den **Speichern des Kennworts zulassen** Feature von der **Datenlinkeigenschaften** (Dialogfeld). In **Geben Sie Informationen zur Anmeldung beim Server**, es gibt zwei Optionsfelder: **integrierte Sicherheit von Windows NT verwenden** und **bestimmten Benutzernamen und bestimmtes Kennwort verwenden**.  
  
    > [!NOTE]
    >  Bei Auswahl des **bestimmten Benutzernamen und bestimmtes Kennwort verwenden**, stehen Ihnen die Möglichkeit, speichern das Kennwort (mithilfe der **Speichern von Kennwort zulassen** Kontrollkästchen), aber diese Option ist nicht sicher. Es wird empfohlen, Sie wählen **integrierte Sicherheit von Windows NT verwenden**; diese Option wird Windows NT verwendet, um Ihre Identität zu überprüfen.  
  
    > [!NOTE]
    >  Wenn Sie Windows NT integrated Security verwenden können, sollten Sie eine Middle-Tier Application verwenden, um den Benutzer für das Kennwort aufzufordern oder das Kennwort an einem Ort mit Sicherheitsmechanismen, um dessen Schutz zu speichern (nicht im Quellcode).  
  
     Nach der Auswahl von Ihrem Anbieter und andere Einstellungen, klicken Sie auf **Testverbindung** der Auswahl auf der vorherigen dialogfeldseiten überprüfen. Wenn die **Ergebnisse** Feld Berichte `Test connection succeeded`, klicken Sie auf **OK** zum Erstellen der datenverknüpfung.  
  
     Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt.  
  
6.  Verwenden Sie die Strukturansicht, um eine Tabelle, Sicht oder gespeicherte Prozedur auszuwählen. Wählen Sie für dieses Verfahren der Products-Tabelle aus der Northwind-Datenbank.  
  
7.  Klicken Sie auf **OK**. Sie kehren zu den ATL OLE DB-Consumer-Assistenten zurück.  
  
8.  Der Assistent abgeschlossen ist, die Namen für `Class` und **.h-Datei** basierend auf den Namen der Tabelle, Sicht oder gespeicherte Prozedur, die Sie ausgewählt haben. Sie können diese Namen bearbeiten, wenn Sie möchten.  
  
9. Deaktivieren der **attributiert** Kontrollkästchen, damit der Assistent erstellt der Consumer Code mit [OLE DB-Vorlagenklassen](../../data/oledb/ole-db-consumer-templates-reference.md) anstelle des standardmäßigen [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md).  
  
10. Klicken Sie unter **Typ**Option **Befehl**.  
  
     Der Assistent erstellt eine [CCommand](../../data/oledb/ccommand-class.md)--basierten Consumer, wenn Sie die Option **Befehl** oder ein [CTable](../../data/oledb/ctable-class.md)--basierten Consumer, wenn Sie die Option **Tabelle**. Die Tabelle oder Befehlsklasse wird nach dem ausgewählten Objekt mit dem Namen, aber Sie können den Namen bearbeiten.  
  
11. Unter **Unterstützung**, lassen Sie die **Änderung**, **einfügen**, und **löschen** Kontrollkästchen deaktiviert.  
  
     Wählen Sie die **Änderung**, **einfügen**, und **löschen** Kontrollkästchen ändern, einfügen und Löschen von Datensätzen im Rowset zu unterstützen, wenn erforderlich. Weitere Informationen über das Schreiben von Daten an den Daten speichern, finden Sie unter [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).  
  
12. Klicken Sie auf **Fertig stellen** an den Consumer zu erstellen.  
  
 Der Assistent generiert eine Befehlsklasse und eine Benutzerdatensatz-Klasse, entsprechend [vom Klassen](../../data/oledb/consumer-wizard-generated-classes.md). Die Befehlsklasse weist des Namens, den Sie in eingegeben haben die `Class` Feld im Assistenten (in diesem Fall `CProducts`), und die Benutzerdatensatz-Klasse hat einen Namen im Format "*ClassName*Accessor" (in diesem Fall `CProductsAccessor`).  
  
> [!NOTE]
>  Der Assistent fügt die folgende Zeile in Products.h:  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Diese Zeile wird verhindert, dass der Consumer-Anwendung zu kompilieren und erinnert Sie daran, überprüfen Sie die Verbindungszeichenfolge für Kennwörter hartcodiert. Überprüfen Sie die Verbindungszeichenfolge, können Sie diese Codezeile entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)