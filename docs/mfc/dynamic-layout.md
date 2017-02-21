---
title: "Dynamisches Layout | Microsoft Docs"
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
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Dynamisches Layout
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit MFC in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] können Sie Dialogfelder erstellen, die der Benutzer ändern kann, und Sie können steuern, wie das Layout auf die Änderung der Größe angepasst wird.  Beispielsweise können Sie Schaltflächen am unteren Rand eines Dialogfelds anfügen, sodass sie sich immer am unteren Rand befinden.  Sie können auch bestimmte Steuerelemente einrichten, wie z. B. Textfelder, Listenfelder und Bearbeitungsfelder, die erweitert werden, wenn der Benutzer das Dialogfeld erweitert.  
  
## Angeben dynamischer Layouteinstellungen für ein MFC\-Dialogfeld  
 Wenn der Benutzer die Größe eines Dialogfelds ändert, können die Steuerelemente im Dialogfeld in der Größe verändert oder in X\- und Y\-Richtung verschoben werden.  Die Änderung in der Größe oder Position eines Steuerelements, wenn der Benutzer die Größe eines Dialogfelds ändert, wird als dynamisches Layout bezeichnet.  Folgendes ist z. B. ein Dialogfeld vor dem Ändern der Größe:  
  
 ![Dialogfeld vor dem Ändern der Größe.](../mfc/media/mfcdynamiclayout4.png "MFCDynamicLayout4")  
  
 Nach dem Ändern der Größe ist der Listenfeldbereich vergrößert, um weitere Elemente anzuzeigen, und die Schaltflächen wurden entlang der rechten unteren Ecke verschoben:  
  
 ![Dialogfeld nach dem Ändern der Größe.](../mfc/media/mfcdynamiclayout5.png "MFCDynamicLayout5")  
  
 Sie können das dynamische Layout steuern, indem Sie die Details für jedes Steuerelement im Ressourcen\-Editor in der IDE angegeben, oder Sie können es programmgesteuert durch Zugriff auf das „CMFCDynamicLayout“\-Objekt für ein bestimmtes Steuerelement und Festlegen der Eigenschaften steuern.  
  
### Festlegen der Eigenschaften für das dynamische Layout im Ressourcen\-Editor  
 Sie können das dynamische Layoutverhalten für ein Dialogfeld festlegen, ohne Code schreiben zu müssen, nämlich mit dem Ressourcen\-Editor.  
  
##### So legen Sie Eigenschaften für das dynamische Layout im Ressourcen\-Editor fest  
  
1.  Öffnen Sie bei einem geöffneten MFC\-Projekt das Dialogfeld, das Sie im Dialog\-Editor bearbeiten möchten.  
  
     ![Öffnen Sie das Dialogfeld im Ressourcen&#45;Editor.](../mfc/media/mfcdynamiclayout3.png "MFCDynamicLayout3")  
  
2.  Wählen Sie ein Steuerelement aus, und legen Sie im Eigenschaftenfenster seine Eigenschaften für das dynamische Layout fest.  Der Abschnitt **Dynamisches Layout** im Eigenschaftenfenster enthält die Eigenschaften **Verschiebungstyp**, **Größentyp** und je nach den für diese Eigenschaften ausgewählten Werten bestimmte Eigenschaften, die definieren, wie viele Steuerelemente verschoben werden oder die Größe ändern.  **Verschiebungstyp** bestimmt, wie ein Steuerelement verschoben wird, wenn sich die Größe des Dialogfelds ändert. **Größentyp** bestimmt, wie die Größe eines Steuerelements geändert wird, wenn sich die Größe des Dialogfelds ändert.  **Verschiebungstyp** und **Größentyp** können **Horizontal**, **Vertikal**, **Beides** oder **Kein\(e\)** sein, je nach den Dimensionen, die Sie dynamisch ändern möchten.  Horizontal ist die X\-Dimension. Vertikal ist die Y\-Richtung.  
  
3.  Wenn ein Steuerelement, zum Beispiel eine Schaltfläche, eine feste Größe und die Position unten rechts beibehalten soll, was häufig für die Schaltflächen **OK** oder **Abbrechen** der Fall ist, legen Sie **Größentyp** auf **Kein\(e\)** und **Verschiebungstyp** auf **Beide** fest.  Für die Werte **Verschiebung X** und **Verschiebung Y** unter **Verschiebungstyp** legen Sie 100 % fest, damit das Steuerelement einen festen Abstand zur unteren rechten Ecke beibehält.  
  
     ![Dynamisches Layout](../mfc/media/mfcdynamiclayout1.png "MFCDynamicLayout1")  
  
4.  Angenommen, Sie haben auch ein Steuerelement, das erweitert werden soll, wenn das Dialogfeld erweitert wird.  In der Regel kann ein Benutzer ein Dialogfeld erweitern, um ein mehrzeiliges Bearbeitungsfeld zu erweitern und die Größe des Textbereichs zu erhöhen, oder er erweitert möglicherweise ein Listensteuerelement, um mehr Daten anzuzeigen.  Legen Sie für diesen Fall **Größentyp** auf „Beide“ und **Verschiebungstyp** auf „Kein\(e\)“ fest.  Legen Sie dann die Werte für **Größe X** und **Größe Y** auf 100 fest.  
  
     ![Dynamische Layouteinstellungen](../mfc/media/mfcdynamiclayout2.png "MFCDynamicLayout2")  
  
5.  Experimentieren Sie mit anderen Werten, die möglicherweise für Ihre Steuerelemente sinnvoll sind.  Beispielsweise kann für ein Dialogfeld mit einem einzeiligen Textfeld **Größentyp** auf **Horizontal** festgelegt werden.  
  
### Programmgesteuertes Festlegen von Eigenschaften für das dynamische Layout  
 Das vorherige Verfahren eignet sich für das Angeben der Einstellungen für das dynamische Layout für einen Dialog zur Entwurfszeit, aber wenn Sie das dynamische Layout zur Laufzeit steuern möchten, können Sie Eigenschaften für das dynamische Layout programmgesteuert festlegen.  
  
##### So legen Sie Eigenschaften für das dynamische Layout programmgesteuert fest  
  
1.  Suchen oder erstellen Sie eine Position im Implementierungscode der Dialogfeldklasse, an dem Sie das dynamische Layout für den Dialog angeben möchten.  Sie können z. B. eine Methode wie `AdjustLayout` im Dialogfeld hinzufügen und von Positionen aus aufrufen, an denen das Layout geändert werden muss.  Sie können dies zuerst vom Konstruktor aus oder nach dem Vornehmen von Änderungen am Dialog aufrufen.  
  
2.  Rufen Sie für den Dialog [GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md) auf, eine Methode der „CWnd“\-Klasse.  „GetDynamicLayout“ gibt einen Zeiger auf ein „CMFCDynamicLayout“\-Objekt zurück.  
  
    ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();  
    ```  
  
3.  Verwenden Sie für das erste Steuerelement, zu dem Sie dynamisches Verhalten hinzufügen möchten, die statischen Methoden der dynamischen Layoutklasse zum Erstellen der [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) \-Struktur, die die Art und Weise codiert, in der das Steuerelement angepasst werden soll.  Wählen Sie dazu zuerst die geeignete statische Methode aus: [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md), [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md), [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md) oder [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md).  Sie übergeben eine Prozentzahl für die horizontalen bzw. vertikalen Aspekte der Verschiebung.  Diese statischen Methoden geben alle ein neu erstelltes „MoveSettings“\-Objekt zurück, mit dem Sie das Verschiebeverhalten eines Steuerelements angeben können.  
  
     Beachten Sie, dass 100 eine exakte Verschiebung gemäß der Größenänderung des Dialogs bedeutet, wodurch der Rand eines Steuerelement in einem festen Abstand zum neuen Rahmen bleibt.  
  
    ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);  
    ```  
  
4.  Führen Sie dieselben Schritte für das Größenverhalten durch, das den [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)\-Typ verwendet.  Um beispielsweise anzugeben, dass die Größe eines Steuerelements nicht geändert wird, wenn sich die Größe des Dialogfelds ändert, verwenden Sie folgenden Code:  
  
    ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();  
    ```  
  
5.  Fügen Sie das Steuerelement dem dynamischen Layout\-Manager mithilfe der [CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)\-Methode zu.  Es gibt zwei Überladungen für verschiedene Möglichkeiten zum Angeben des gewünschten Steuerelements.  Eine verwendet den Fensterhandle \(HWND\) des Steuerelements, und die andere die Steuerelement\-ID.  
  
    ```  
    dynamicLayout->AddItem(hWndControl, moveSettings, sizeSettings);  
    ```  
  
6.  Wiederholen Sie den Vorgang für jedes Steuerelement, das verschoben oder dessen Größe geändert werden muss.  
  
7.  Wenn erforderlich, können Sie die [CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)\-Methode verwenden, um zu bestimmen, ob ein Steuerelement bereits in der Liste der Steuerelemente vorhanden ist, die dynamischen Layoutänderungen unterliegen, oder die [CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)\-Methode, um zu ermitteln, ob es Steuerelemente gibt, die Änderungen unterliegen.  
  
8.  Um das Layout des Dialogfelds zu aktivieren, rufen Sie die [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md)\-Methode auf.  
  
    ```  
    pDialog->EnableDynamicLayout(TRUE);  
    ```  
  
9. Wenn der Benutzer das nächste Mal die Größe des Dialogfelds ändert, wird die [CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)\-Methode aufgerufen, die die Einstellungen tatsächlich übernimmt.  
  
10. Wenn Sie das dynamische Layout deaktivieren möchten, rufen Sie [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md) mit `FALSE` wie für den `bEnabled`\-Parameter auf.  
  
    ```  
    pDialog->EnableDynamicLayout(FALSE);  
    ```  
  
##### So legen Sie das dynamische Layout programmgesteuert aus einer Ressourcendatei fest  
  
1.  Verwenden Sie die [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md)\-Methode, um einen Ressourcennamen in der entsprechenden Ressourcenskriptdatei \(RC\-Datei\) anzugeben, die Informationen zum dynamischen Layout wie im folgenden Beispiel angibt:  
  
    ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");  
    ```  
  
     Die benannte Ressource muss auf ein Dialogfeld verweisen, das Layoutinformationen in Form eines AFX\_DIALOG\_LAYOUT\-Eintrags in der Ressourcendatei enthält, wie im folgenden Beispiel gezeigt wird:  
  
    ```  
    /////////////////////////////////////////////////////////////////////////////  
    //  
    // AFX_DIALOG_LAYOUT  
    //  
  
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6400, 0x0028, 0x643c, 0x0028  
    END  
  
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6464, 0x0000, 0x6464, 0x0000, 0x0000, 0x6464, 0x0000, 0x0000  
  
    END  
    ```  
  
## Siehe auch  
 [CMFCDynamicLayout\-Klasse](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Steuerelementklassen](../mfc/control-classes.md)   
 [Dialogfeldklassen](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)