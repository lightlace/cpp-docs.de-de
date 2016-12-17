---
title: "Exemplarische Vorgehensweise: Erstellen einer Men&#252;bandanwendung mithilfe von MFC"
ms.custom: na
ms.date: "12/15/2016"
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
  - "Erstellen einer Menübandanwendung (MFC)"
  - "Menübandanwendung, Erstellen (MFC)"
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
caps.latest.revision: 21
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen einer Men&#252;bandanwendung mithilfe von MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mithilfe des **MFC\-Anwendungs\-Assistenten** eine Anwendung erstellen, die standardmäßig über ein Menüband verfügt.  Sie können das Menüband anschließend erweitern, indem Sie eine Menübandkategorie vom Typ **Benutzerdefiniert** mit einem Menübandbereich **Favoriten** hinzufügen und dem Band dann einige häufig verwendete Befehle hinzufügen.  
  
## Vorbereitungsmaßnahmen  
 In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] für die Verwendung der **Allgemeinen Entwicklungseinstellungen** eingerichtet haben.  Wenn Sie andere Einstellungen verwenden, werden möglicherweise einige Elemente der Benutzeroberfläche, auf die in den folgenden Anweisungen verwiesen wird, nicht angezeigt.  Informationen zum Ändern der Einstellungen finden Sie unter [How to: Reset Your Settings](assetId:///c95c51be-e609-4769-abba-65e6beedec76).  
  
### So erstellen Sie eine MFC\-Anwendung mit einem Menüband  
  
1.  Verwenden Sie den **MFC\-Anwendungs\-Assistenten**, um eine MFC\-Anwendung mit einem Menüband zu erstellen.  Um den Assistenten auszuführen, wählen Sie im Menü **Datei** die Option **Neu** aus, und klicken Sie und anschließend auf **Projekt**.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C\+\+** unter **Installierte Vorlagen**, wählen Sie **MFC** und anschließend **MFC\-Anwendung** aus.  Geben Sie einen Namen für das Projekt ein, z. B. `MFCRibbonApp` ein, und klicken Sie dann auf **OK**.  
  
3.  Klicken Sie auf der ersten Seite des **MFC\-Anwendungs\-Assistenten** auf **Weiter**.  
  
4.  Wählen Sie auf der Seite **Anwendungstyp** unter **Visueller Stil und Farben** den Eintrag **Office 2007 \(Blaues Design\)** aus.  Übernehmen Sie die übrigen Einstellungen unverändert.  Klicken Sie auf **Weiter**.  
  
5.  Überprüfen Sie auf der Seite **Verbunddokumente**, ob **Kein** ausgewählt ist, und klicken Sie dann auf **Weiter**.  
  
6.  Geben Sie auf der Seite **Eigenschaften für Dokumentvorlagen** im Feld **Dateierweiterung** eine Dateinamenerweiterung für Dokumente ein, die von dieser Anwendung erstellt werden, z. B. `mfcrbnapp`.  Klicken Sie auf **Weiter**.  
  
7.  Überprüfen Sie auf der Seite **Datenbankunterstützung**, ob **Kein** ausgewählt ist, und klicken Sie dann auf **Weiter**.  
  
8.  Überprüfen Sie auf der Seite **Benutzeroberflächenfunktionen**, ob **Menüband verwenden** ausgewählt ist.  Klicken Sie auf **Weiter**.  
  
9. Standardmäßig fügt der **MFC\-Anwendungs\-Assistent** Unterstützung für einige andockbare Bereiche hinzu.  Da in dieser exemplarischen Vorgehensweise nur das Menüband erläutert wird, können Sie diese Optionen aus der Anwendung entfernen.  Deaktivieren Sie auf der Seite **Erweiterte Funktionen** alle Optionen.  Klicken Sie auf **Weiter**.  
  
10. Klicken Sie auf der Seite **Generierte Klassen** auf **Fertig stellen**, um die MFC\-Anwendung zu erstellen.  
  
11. Um zu überprüfen, ob die Anwendung erfolgreich erstellt wurde, erstellen Sie sie und führen sie aus.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debug** auf **Debugging starten** darauf klicken.  
  
     Der Assistent erstellt automatisch ein Menüband mit einer Menübandkategorie, die **Startseite** genannt wird.  Dieses Menüband enthält drei Menübandbereiche, die **Zwischenablage**, **Ansicht** und **Fenster** heißen.  
  
### So fügen Sie dem Menüband eine Kategorie und einen Bereich hinzu  
  
1.  Um die Menübandressource zu öffnen, die im Menü **Anzeigen** erstellt wurde, zeigen auf **Weitere Fenster**, und klicken Sie dann auf **Ressourcenansicht**.  Doppelklicken Sie in **Ressourcenansicht** auf **Menüband** und dann auf **IDR\_RIBBON**.  
  
2.  Fügen Sie zunächst dem Menüband eine benutzerdefinierte Kategorie hinzu, indem Sie auf **Kategorie** in **Werkzeugkasten** doppelklicken.  
  
     Eine Kategorie mit der Beschriftung **Category1** wird erstellt.  Standardmäßig enthält die Kategorie einen Bereich.  
  
     Klicken Sie mit der rechten Maustaste auf **Category1**, und klicken Sie dann auf **Eigenschaften**.  Ändern Sie im **Eigenschaftenfenster** die **Beschriftung** in`Benutzerdefiniert`.  
  
     In den Eigenschaften **Große Bilder** und **Kleine Bilder** werden die Bitmaps angegeben, die als Symbole für die Menübandelemente in dieser Kategorie verwendet werden.  Da die Erläuterungen zum Erstellen von benutzerdefinierten Bitmaps über den Rahmen dieser exemplarischen Vorgehensweise hinausgehen, verwenden Sie einfach die vom Assistenten erstellten Bitmaps erneut.  Kleine Bitmaps sind 16 Pixel x 16 Pixel.  Für kleine Bilder verwenden Sie die Bitmaps, auf die über die Ressourcen\-ID IDB\_FILESMALL zugegriffen wird.  Große Bitmaps sind 32 Pixel x 32 Pixel.  Für große Bilder verwenden Sie die Bitmaps, auf die über die Ressourcen\-ID IDB\_FILELARGE zugegriffen wird.  
  
    > [!NOTE]
    >  In HDPI\-Anzeigen, die mehr Pixel pro Zoll enthalten, werden automatisch die HDPI\-Versionen der Bilder verwendet.  
  
3.  Passen Sie danach den Bereich an.  Bereiche werden zum Gruppieren von Elementen verwendet, die sich logisch aufeinander beziehen.  Beispielsweise befinden sich auf der Registerkarte **Startseite** dieser Anwendung die Befehle **Ausschneiden**, **Kopieren** und **Einfügen** alle im Bereich **Zwischenablage**.  Klicken Sie mit der rechten Maustaste Sie auf **Panel1**, und klicken Sie dann auf **Eigenschaften**, um den Bereich anzupassen.  Ändern Sie im Fenster **Eigenschaften** die **Beschriftung** in `Favoriten`.  
  
     Sie können den **Bildindex** für den Bereich angeben.  Diese Zahl gibt das Symbol an, das angezeigt wird, wenn der Menübandbereich zu **Symbolleiste für den Schnellzugriff** hinzugefügt wird.  Das Symbol wird nicht im Menübandbereich selbst angezeigt.  
  
4.  Um sicherzustellen, dass die Menübandkategorie und der entsprechende Bereich erfolgreich erstellt wurden, rufen Sie eine Vorschau des Menüband\-Steuerelements auf.  Klicken Sie auf der **Ribbon\-Editor\-Symbolleiste** Sie auf die Schaltfläche **Ribbon testen**.  Auf dem Menüband sollten eine Registerkarte **Benutzerdefiniert** und ein Bereich **Favoriten** angezeigt werden.  
  
### So fügen Sie den Menübandbereichen Elemente hinzu  
  
1.  Um dem Bereich, den Sie im vorherigen Verfahren erstellt haben, Elemente hinzuzufügen, ziehen Sie Steuerelemente auf dem Bereich **Ribbon\-Editor** des **Werkzeugkastens** in den Bereich in der Entwurfsansicht.  
  
2.  Fügen Sie zuerst eine Schaltfläche **Drucken** hinzu.  Die Schaltfläche **Drucken** verfügt über ein Untermenü, das einen Befehl **Schnelldruck** enthält, mit dem auf dem Standarddrucker gedruckt wird.  Beide Befehle sind bereits für diese Anwendung definiert.  Sie befinden sich auf dem Anwendungsmenü.  
  
     Um die Schaltfläche **Drucken** zu erstellen, ziehen Sie ein Schaltflächentool in den Bereich.  
  
     Ändern Sie im Fenster **Eigenschaften** die Eigenschaft **ID** auf **ID\_FILE\_PRINT**, die bereits definiert sein sollte.  Ändern Sie **Beschriftung** in `Drucken`.  Ändern Sie **Bildindex** auf `4`.  
  
     Um die Schaltfläche **Schnelldruck** zu erstellen, klicken Sie auf die Spalte mit den Eigenschaftswerten neben **Menüoptionen**, und klicken Sie dann auf die Auslassungspunkte \(**...**\).  Klicken Sie im **Elemente\-Editor** auf die unbeschriftete Schaltfläche **Hinzufügen**, um ein Menüelement zu erstellen.  Ändern Sie im Fenster **Eigenschaften** die **Beschriftung** in `Schnelldruck`, die **ID** in `ID_FILE_PRINT_DIRECT` und die Eigenschaft **Bild** in `5`.  Die Bildeigenschaft gibt das Symbol für Schnelldruck in der IDB\_FILESMALL\-Bitmapressource an.  
  
3.  Um zu überprüfen, ob die Schaltflächen zum Menübandbereich hinzugefügt wurden, erstellen Sie die Anwendung, und führen Sie sie aus.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debuggen** auf **Debugging starten** klicken.  Die Schaltfläche **Drucken** und das Kombinationsfeld im Bereich **Favoriten** auf der Registerkarte **Benutzerdefiniert** auf dem Menüband sollten angezeigt werden.  
  
## Nächste Schritte  
 [Gewusst wie: Anpassen der Symbolleiste für den Schnellzugriff](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [Gewusst wie: Anpassen der Anwendungsschaltfläche](../mfc/how-to-customize-the-application-button.md)  
  
 End\-to\-End\-Beispiele finden Sie unter [Beispiele \(MFC\-Feature Pack\)](../top/visual-cpp-samples.md).  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)   
 [Beispiele \(MFC\-Feature Pack\)](../top/visual-cpp-samples.md)