---
title: "Exemplarische Vorgehensweise: Erstellen einer Menübandanwendung mithilfe von MFC | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfad78b64f72b9ee9a896832e008039aa241e2ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>Exemplarische Vorgehensweise: Erstellen einer Menübandanwendung mithilfe von MFC
Diese exemplarische Vorgehensweise zeigt, wie die **MFC-Anwendung-Assistent** zum Erstellen einer Anwendung, die ein Menüband in der Standardeinstellung verfügt. Sie können das Menüband anschließend erweitern, indem Sie Hinzufügen einer **benutzerdefinierte** Menübandkategorie, die verfügt über eine **Favoriten** Bereich, und fügen einige häufig verwendete Befehle in den Bereich des Menübands.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie festgelegt haben [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verwenden **allgemeine Entwicklungseinstellungen**. Wenn Sie andere Einstellungen verwenden, werden möglicherweise einige Elemente der Benutzeroberfläche, auf die in den folgenden Anweisungen verwiesen wird, nicht angezeigt. Informationen zum Ändern der Einstellungen finden Sie unter [Vorgehensweise: Reset Your Settings](http://msdn.microsoft.com/en-us/c95c51be-e609-4769-abba-65e6beedec76).  
  
### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>So erstellen Sie eine MFC-Anwendung mit einem Menüband  
  
1.  Verwenden der **MFC-Anwendung-Assistent** zum Erstellen einer MFC_Anwendung, die ein Menüband verfügt. Zum Ausführen des Assistenten die **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten unter **installierte Vorlagen**Option **MFC**, und wählen Sie dann  **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. `MFCRibbonApp`, und klicken Sie dann auf **OK**.  
  
3.  Auf der ersten Seite des der **MFC-Anwendung-Assistent**, klicken Sie auf **Weiter**.  
  
4.  Auf der **Anwendungstyp** Seite **visueller Stil und Farben**Option **Office 2007 (blaues Design)**. Übernehmen Sie die übrigen Einstellungen unverändert. Klicken Sie auf **Weiter**.  
  
5.  Auf der **Verbunddokumente** Seite, stellen Sie sicher, dass **keine** ausgewählt ist, und klicken Sie dann auf **Weiter**.  
  
6.  Auf der **Eigenschaften für Dokumentvorlagen** Seite in der **Dateierweiterung** geben eine Dateinamenerweiterung für Dokumente, die diese Anwendung erstellt werden, z. B. `mfcrbnapp`. Klicken Sie auf **Weiter**.  
  
7.  Auf der **Datenbankunterstützung** Seite, stellen Sie sicher, dass **keine** ausgewählt ist, und klicken Sie dann auf **Weiter**.  
  
8.  Auf der **Benutzeroberflächenfunktionen** Seite, stellen Sie sicher, dass **verwenden ein Menübands** ausgewählt ist. Klicken Sie auf **Weiter**.  
  
9. Wird standardmäßig die **MFC-Anwendung-Assistent** fügt Unterstützung für einige andockbare Bereiche hinzu. Da in dieser exemplarischen Vorgehensweise nur das Menüband erläutert wird, können Sie diese Optionen aus der Anwendung entfernen. Auf der **erweiterte Funktionen** Seite, deaktivieren Sie alle Optionen. Klicken Sie auf **Weiter**.  
  
10. Auf der **generierte Klassen** auf **Fertig stellen** die MFC-Anwendung zu erstellen.  
  
11. Um zu überprüfen, ob die Anwendung erfolgreich erstellt wurde, erstellen Sie sie und führen sie aus. Um die Anwendung zu erstellen. die **erstellen** Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie es, indem Sie auf **Debuggen** auf die **Debuggen** Menü.  
  
     Der Assistent erstellt automatisch ein Menüband verwenden, das einer Menübandkategorie mit dem Namen **Home**. Dieses Menüband enthält drei menübandbereiche, die heißen **Zwischenablage**, **Ansicht**, und **Fenster**.  
  
### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>So fügen Sie dem Menüband eine Kategorie und einen Bereich hinzu  
  
1.  Um die menübandressource zu öffnen, die der Assistent erstellt werden, auf die **Ansicht** Sie im Menü **Weitere Fenster** , und klicken Sie dann auf **Ressourcenansicht**. In **Ressourcenansicht**, klicken Sie auf **Menüband** und doppelklicken Sie dann auf **IDR_RIBBON**.  
  
2.  Fügen Sie zunächst eine benutzerdefinierte Kategorie auf dem Menüband durch Doppelklicken auf **Kategorie** in der **Toolbox**.  
  
     Eine Kategorie aus, die die Beschriftung besitzt **Category1** wird erstellt. Standardmäßig enthält die Kategorie einen Bereich.  
  
     Mit der rechten Maustaste **Category1** , und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaften** ändern **Beschriftung** auf `Custom`.  
  
     Die **große Bilder** und **kleine Bilder** Eigenschaften geben Sie die Bitmaps, die als Symbole für die Menübandelemente in dieser Kategorie verwendet werden. Da die Erläuterungen zum Erstellen von benutzerdefinierten Bitmaps über den Rahmen dieser exemplarischen Vorgehensweise hinausgehen, verwenden Sie einfach die vom Assistenten erstellten Bitmaps erneut. Kleine Bitmaps sind 16 Pixel x 16 Pixel. Für kleine Bilder verwenden Sie die Bitmaps, auf die über die Ressourcen-ID IDB_FILESMALL zugegriffen wird. Große Bitmaps sind 32 Pixel x 32 Pixel. Für große Bilder verwenden Sie die Bitmaps, auf die über die Ressourcen-ID IDB_FILELARGE zugegriffen wird.  
  
    > [!NOTE]
    >  In HDPI-Anzeigen, die mehr Pixel pro Zoll enthalten, werden automatisch die HDPI-Versionen der Bilder verwendet.  
  
3.  Passen Sie danach den Bereich an. Bereiche werden zum Gruppieren von Elementen verwendet, die sich logisch aufeinander beziehen. Z. B. auf die **Home** Registerkarte dieser Anwendung die **Ausschneiden**, **Kopie**, und **einfügen** Befehle alle befinden sich auf die  **Zwischenablage** Bereich. Um den Bereich anzupassen, Maustaste **Panel1** , und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaften** ändern **Beschriftung** auf `Favorites`.  
  
     Sie können angeben, die **Abbildindex** des Panels. Diese Zahl gibt an, das Symbol, das angezeigt wird, wenn der Menübandbereich hinzugefügt wird die **Symbolleiste für den Schnellzugriff**. Das Symbol wird nicht im Menübandbereich selbst angezeigt.  
  
4.  Um sicherzustellen, dass die Menübandkategorie und der entsprechende Bereich erfolgreich erstellt wurden, rufen Sie eine Vorschau des Menüband-Steuerelements auf. Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf die **Ribbon testen** Schaltfläche. Ein **benutzerdefinierte** Registerkarte und **Favoriten** Bereich im Menüband angezeigt werden soll.  
  
### <a name="to-add-elements-to-the-ribbon-panels"></a>So fügen Sie den Menübandbereichen Elemente hinzu  
  
1.  Elemente in den Bereich hinzufügen, die Sie im vorherigen Verfahren erstellt haben, ziehen Sie Steuerelemente aus der **Ribbon-Editor** Teil der **Toolbox** in den Bereich in der Entwurfsansicht.  
  
2.  Fügen Sie zunächst eine **Drucken** Schaltfläche. Die **Drucken** Schaltfläche müssen ein Untermenü, das enthält eine **Schnelldruck** -Befehl, der mit dem Standarddrucker gedruckt. Beide Befehle sind bereits für diese Anwendung definiert. Sie befinden sich auf dem Anwendungsmenü.  
  
     Zum Erstellen der **Drucken** Schaltfläche, ziehen Sie ein schaltflächentool in den Bereich.  
  
     In der **Eigenschaften** Ändern der **ID** Eigenschaft **ID_FILE_PRINT**, die sollte bereits definiert. Änderung **Beschriftung** auf `Print`. Änderung **Image Index** auf `4`.  
  
     Zum Erstellen der **Schnelldruck** Schaltfläche, klicken Sie auf Spalte mit den Eigenschaftswerten neben **Menüelemente**, und klicken Sie dann auf die Auslassungspunkte (**...** ). In der **Elemente-Editor**, klicken Sie auf die unbeschriftete **hinzufügen** um ein Menüelement zu erstellen. In der **Eigenschaften** ändern **Beschriftung** auf `Quick Print`, **ID** auf `ID_FILE_PRINT_DIRECT`, und **Image** auf `5` . Die Bildeigenschaft gibt das Symbol für Schnelldruck in der IDB_FILESMALL-Bitmapressource an.  
  
3.  Um zu überprüfen, ob die Schaltflächen zum Menübandbereich hinzugefügt wurden, erstellen Sie die Anwendung, und führen Sie sie aus. Um die Anwendung zu erstellen. die **erstellen** Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung, indem Sie auf **Debuggen** auf die **Debuggen** Menü. Die **Drucken** Schaltfläche und das Kombinationsfeld Feld der **Favoriten** Bereich auf die **benutzerdefinierte** Menüband auf der Registerkarte angezeigt werden soll.  
  
## <a name="next-steps"></a>Nächste Schritte  
 [Vorgehensweise: Anpassen der Symbolleiste für den Schnellzugriff](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [Vorgehensweise: Anpassen der Anwendungsschaltfläche](../mfc/how-to-customize-the-application-button.md)  
  
 End-to-End-Beispiele finden Sie unter [Beispiele (MFC Feature Pack)](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)   
 [Beispiele (MFC Feature Pack)](../visual-cpp-samples.md)

