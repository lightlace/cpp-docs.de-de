---
title: "Verwenden von Eigenschaftenseiten in einer Anwendung"
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
  - "AddPage-Methode"
  - "CPropertyPage-Klasse, Stile"
  - "Create-Methode [C++], Eigenschaftenblätter"
  - "Dialogressourcen"
  - "Dialogvorlagen, Eigenschaftenblätter"
  - "DoModal-Methodeneigenschaftenblätter"
  - "Eigenschaftenseiten, Eigenschaftenblätter"
  - "Eigenschaftenblätter, Informationen über Eigenschaftenblätter"
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Eigenschaftenseiten in einer Anwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein Eigenschaftenblatt in der Anwendung zu verwenden, führen Sie die folgenden Schritte aus:  
  
1.  Erstellen einer Dialogfeldvorlagen\-Ressource für jede Seite.  Beachten Sie, dass der Benutzer von einer Seite zur anderen wechseln, sodass für jede Seite so konsistent, wie möglich.  
  
     Die Dialogfeldvorlagen für alle Seiten müssen nicht die gleiche Größe sein.  Das Framework verwendet die Größe der längsten Seite, um zu bestimmen, welche im Eigenschaftenblatt die Eigenschaftenseiten für Leerzeichen, zuzuordnen.  
  
     Wenn Sie die Dialogfeldvorlagen\-Ressource für eine Eigenschaftenseite erstellen, müssen Sie folgenden Stile im Dialogfeld\-Eigenschafteneigenschaftenblatt angeben:  
  
    -   Legen Sie das **Beschriftung**  Eingabefeld **Allgemein**  auf der Seite auf den Text fest, den Sie auf der Registerkarte für die Seite angezeigt werden sollen.  
  
    -   Legen Sie das **Formatvorlage**  Listenfeld auf der Seite **Stile**  auf **Untergeordnet** fest.  
  
    -   Legen Sie das **Rahmen**  Listenfeld auf der Seite **Stile**  auf **Dünn** fest.  
  
    -   Stellen Sie sicher, dass das Kontrollkästchen **Titlebar**  auf der Seite **Stile**  ausgewählt ist.  
  
    -   Stellen Sie sicher, dass das Kontrollkästchen **Deaktiviert**  auf der Seite **Weitere Formate** ausgewählt ist.  
  
2.  Erstellen Sie [CPropertyPage](../mfc/reference/cpropertypage-class.md) abgeleitete Klasse entsprechend jeder Eigenschaftenseitendialogfeldvorlage.  Siehe [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).  Wählen Sie `CPropertyPage` als Basisklasse aus.  
  
3.  Erstellen Sie die Membervariablen, um die Werte für diese Eigenschaftenseite aufzunehmen.  Das Hinzufügen von Membervariablen in eine Eigenschaftenseite ist identisch mit dem, Membervariablen zu einem Dialogfeld hinzuzufügen, da eine Eigenschaftenseite ein spezialisiertes Dialogfeld ist.  Weitere Informationen finden Sie unter [Definieren von Membervariablen für Dialogfeld\-Kontrollen](../mfc/defining-member-variables-for-dialog-controls.md).  
  
4.  [CPropertySheet](../mfc/reference/cpropertysheet-class.md) Erstellen Sie ein Objekt im Quellcode.  Normalerweise erstellen Sie das Objekt `CPropertySheet` im Handler für den Befehl das Eigenschaftenblatt, der anzeigt.  Dieses Objekt stellt das gesamte Eigenschaftenblatt dar.  Wenn Sie ein modales Eigenschaftenblatt mit der Funktion [DoModal](../Topic/CPropertySheet::DoModal.md) erstellen, gibt das Framework drei Befehlsschaltflächen standardmäßig an: OK, Löschen und gelten.  Das Framework stellt keine Befehlsschaltflächen für das nicht modale Eigenschaftenblätter erstellt, die mit der Funktion [Erstellen](../Topic/CPropertySheet::Create.md) erstellt werden.  Sie müssen nicht, um eine Klasse von `CPropertySheet` abgeleitet werden, es sei denn, dass Sie entweder hinzufügen andere Steuerelemente \(wie ein Aktualisierung\) anzeigen oder ein nicht modales Eigenschaftenblatt soll.  Dieser Schritt ist für nicht modale Eigenschaftenblätter erforderlich, da sie keine Standardsteuerelemente enthalten, die verwendet werden können, um das Eigenschaftenblatt zu schließen.  
  
5.  Für jede Seite zum Eigenschaftenblatt hinzugefügt werden kann, sind folgende:  
  
    -   Erstellen Sie ein Objekt für jedes von `CPropertyPage` abgeleitete Klasse, die vorher in diesem Prozess erstellt haben.  
  
    -   Aufruf [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) für jede Seite.  
  
     In der Regel erstellt das Objekt, das `CPropertySheet` erstellt, die `CPropertyPage`\-Objekte in diesem Schritt.  Wenn Sie jedoch `CPropertySheet` abgeleitete Klasse, die `CPropertyPage`\-Objekte im `CPropertySheet`\-Objekt einbetten und `AddPage` für jede Seite einer `CPropertySheet` aufrufen können \- Konstruktor der abgeleiteten Klasse implementieren.  `AddPage` fügt hinzu, dem `CPropertyPage`\-Objekt der Liste des Eigenschaftenblatts vonseiten aber eigentlich nicht enthält das Fenster für diese Seite.  Daher ist es nicht erforderlich, wenn Erstellung des Eigenschaftenblattfensters warten, um `AddPage` aufzurufen; Sie können `AddPage` vom Konstruktor des Eigenschaftenblatts aufrufen.  
  
     Standardmäßig wird ein Eigenschaftenblatt weitere Registerkarten hat, als in einer einzelnen Zeile des Eigenschaftenblatts passt, stapeln die Registerkarten in mehreren Zeilen.  Um das Stapeln zu deaktivieren, rufen Sie die [CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md) mit dem Parameter, der auf **FALSE** festgelegt wird.  Sie müssen `EnableStackedTabs` aufrufen, wenn Sie das Eigenschaftenblatt erstellen.  
  
6.  Rufen Sie [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) oder [Erstellen](../Topic/CPropertySheet::Create.md) auf, um das Eigenschaftenblatt anzuzeigen.  Rufen Sie `DoModal` auf, um ein Eigenschaftenblatt als modales Dialogfeld zu erstellen.  Rufen Sie **Erstellen** auf, um das Eigenschaftenblatt als nicht modales Dialogfeld zu erstellen.  
  
7.  Austauschen von Daten zwischen Eigenschaftenseiten und den Besitzer des Eigenschaftenblatts.  Dies wird im Artikel [Austausch\-Daten](../mfc/exchanging-data.md) erläutert.  
  
 Ein Beispiel, wie Eigenschaftenblätter, finden Sie das Beispiel [Darüber](../top/visual-cpp-samples.md) allgemeine MFC verwendet.  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)