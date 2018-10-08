---
title: Erstellen eines einfachen Consumers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 120829b08ab65c10cca7ab922fc4f9be732ccc53
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860809"
---
# <a name="creating-a-simple-consumer"></a>Erstellen eines einfachen Consumers

Verwenden Sie die ATL-Projektassistenten und ATL-OLE DB-Consumer-Assistenten, um einen OLE DB-Vorlagen-Consumer zu generieren.

### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Zum Erstellen einer Konsolenanwendung für einen OLE DB-consumer

1. Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.

   Das Dialogfeld **Neues Projekt** wird angezeigt.

1. Klicken Sie im Bereich Projekttypen auf der **Visual C++-Projekte** Ordner, und klicken Sie dann auf die **Win32-Projekt** Symbol im Bereich Vorlagen. In der **Namen** Geben Sie den Namen des Projekts, z. B. **MyCons**.

1. Klicken Sie auf **OK**.

   Die Win32-Projekt-Assistent wird angezeigt.

1. Auf der **Anwendungseinstellungen** Seite **Konsolenanwendung**, und wählen Sie dann **ATL-Unterstützung hinzufügen**.

1. Klicken Sie auf **Fertig stellen** den Assistenten zu schließen und das Projekt zu erstellen.

Verwenden Sie anschließend die ATL-OLE DB-Consumer-Assistenten zum Hinzufügen eines OLE DB-Consumer-Objekts.

#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>Um einen Consumer mit dem ATL-OLE DB-Consumer-Assistenten erstellen

1. In der Klassenansicht, Maustaste den `MyCons` Projekt.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.

   Die **Klasse hinzufügen** Dialogfeld wird angezeigt.

1. Klicken Sie in den Bereich "Kategorien" auf **Visual C++**, klicken Sie auf die **ATL-OLE DB-Consumer** in den Vorlagen (Bereich), und klicken Sie dann auf **öffnen**.

   Der ATL-OLE DB-Consumer-Assistent wird angezeigt.

1. Klicken Sie auf die **Datenquelle** Schaltfläche.

   Die **Datenlinkeigenschaften** Dialogfeld wird angezeigt.

1. In der **Datenlinkeigenschaften** Dialogfeld Feld, gehen Sie folgendermaßen vor:

   - Auf der **Anbieter** Registerkarte, geben Sie einen OLE DB-Anbieter.

   - Auf der **Verbindung** an, der Servernamen, Anmelde-ID und das Kennwort für die Datenquelle und die Datenbank auf dem Server.

   > [!NOTE]
   > Es wurde ein Sicherheitsproblem mit der **Speichern des Kennworts zulassen** Feature von der **Datenlinkeigenschaften** im Dialogfeld. In **Geben Sie Informationen zum Anmelden an den Server**, es gibt zwei Optionsfelder: **Windows NT integrated Security verwenden** und **bestimmten Benutzernamen und bestimmtes Kennwort**.

   > [!NOTE]
   > Bei Auswahl von **bestimmten Benutzernamen und bestimmtes Kennwort**, Sie haben die Möglichkeit, speichern Sie das Kennwort (mit der **Speichern von Kennwort zulassen** Kontrollkästchen), aber diese Option ist nicht sicher. Es wird empfohlen, die Sie auswählen, **Windows NT integrated Security verwenden**; diese Option verwendet die Windows NT zur Überprüfung Ihrer Identität.

   > [!NOTE]
   > Wenn Sie Windows NT integrated Security verwenden können, sollten Sie eine Anwendung der mittleren Ebene verwenden, um den Benutzer für das Kennwort aufzufordern oder das Kennwort an einem Ort mit Sicherheitsmechanismen, um dessen Schutz zu speichern (nicht im Quellcode).

   Nachdem Sie Ihren Anbieter und andere Einstellungen auswählen, klicken Sie auf **Testverbindung** um zu überprüfen, ob die Auswahl auf der vorherigen dialogfeldseiten. Wenn die **Ergebnisse** Feld Berichte `Test connection succeeded`, klicken Sie auf **OK** zum Erstellen der datenverknüpfung.

   Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt.

1. Verwenden Sie die Strukturansicht-Steuerelement, um eine Tabelle, Sicht oder gespeicherte Prozedur auszuwählen. Wählen Sie für diese Prozedur die Products-Tabelle aus der Northwind-Datenbank.

1. Klicken Sie auf **OK**. Dies gibt Sie an der ATL-OLE DB-Consumer-Assistenten zurück.

1. Der Assistent abgeschlossen ist, die Namen für `Class` und **.h-Datei** basierend auf den Namen der Tabelle, Sicht oder gespeicherte Prozedur, die Sie ausgewählt haben. Sie können diese Namen bearbeiten, wenn Sie möchten.

1. Deaktivieren der **attributiert** Kontrollkästchen, damit der Assistent erstellt der Consumer-Code mit [OLE DB-Vorlagenklassen](../../data/oledb/ole-db-consumer-templates-reference.md) anstelle des standardmäßigen [OLE DB-Consumerattribute](../../windows/ole-db-consumer-attributes.md).

1. Klicken Sie unter **Typ**Option **Befehl**.

   Der Assistent erstellt eine [CCommand](../../data/oledb/ccommand-class.md)--basierten Consumer, wenn Sie die Option **Befehl** oder ein [CTable](../../data/oledb/ctable-class.md)--basierten Consumer, wenn Sie die Option **Tabelle**. Die Tabelle oder Befehlsklasse wird nach dem ausgewählten Objekt mit dem Namen, aber Sie können den Namen bearbeiten.

1. Unter **Unterstützung**, lassen Sie die **Änderung**, **einfügen**, und **löschen** Kontrollkästchen deaktiviert.

   Wählen Sie die **Änderung**, **einfügen**, und **löschen** Kontrollkästchen, um die ändern, einfügen und Löschen von Datensätzen in das Rowset unterstützt werden, wenn erforderlich. Weitere Informationen zum Schreiben von Daten an den Daten zu speichern, finden Sie unter [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).

1. Klicken Sie auf **Fertig stellen** an den Consumer zu erstellen.

Der Assistent generiert eine Befehlsklasse und eine Benutzerdatensatz-Klasse, siehe [vom Klassen](../../data/oledb/consumer-wizard-generated-classes.md). Die Befehlsklasse müssen den Namen, den Sie im eingegeben haben die `Class` Feld im Assistenten (in diesem Fall `CProducts`), und die Benutzerdatensatz-Klasse hat einen Namen im Format "*ClassName*Accessor" (in diesem Fall `CProductsAccessor`).

> [!NOTE]
> Der Assistent setzt die folgende Zeile in Products.h:

```cpp
#error Security Issue: The connection string may contain a password
```

> [!NOTE]
> Diese Zeile wird verhindert, dass die Consumer-Anwendung zu kompilieren und erinnert Sie daran, Ihre Verbindungszeichenfolge auf der fest programmierte Kennwörter zu überprüfen. Nach dem Überprüfen Ihre Verbindungszeichenfolge enthält, können Sie diese Codezeile entfernen.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
