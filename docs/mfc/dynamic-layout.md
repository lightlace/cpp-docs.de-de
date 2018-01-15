---
title: Dynamisches Layout | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e309d8ef023346c0e37babeabe23f7e6e1762939
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dynamic-layout"></a>Dynamisches Layout
Mit MFC in Visual Studio 2015 können Sie Dialogfelder erstellen, die der Benutzer ändern kann, und Sie können steuern, wie, die das Layout auf die Änderung der Größe angepasst. Beispielsweise können Sie Schaltflächen am unteren Rand eines Dialogfelds anfügen, sodass sie sich immer am unteren Rand befinden. Sie können auch bestimmte Steuerelemente einrichten, wie z. B. Textfelder, Listenfelder und Bearbeitungsfelder, die erweitert werden, wenn der Benutzer das Dialogfeld erweitert.  
  
## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>Angeben dynamischer Layouteinstellungen für ein MFC-Dialogfeld  
 Wenn der Benutzer die Größe eines Dialogfelds ändert, können die Steuerelemente im Dialogfeld in der Größe verändert oder in X- und Y-Richtung verschoben werden. Die Änderung in der Größe oder Position eines Steuerelements, wenn der Benutzer die Größe eines Dialogfelds ändert, wird als dynamisches Layout bezeichnet. Folgendes ist z. B. ein Dialogfeld vor dem Ändern der Größe:  
  
 ![Dialogfeld vor dem Ändern der Größe. ] (../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")  
  
 Nach dem Ändern der Größe ist der Listenfeldbereich vergrößert, um weitere Elemente anzuzeigen, und die Schaltflächen wurden entlang der rechten unteren Ecke verschoben:  
  
 ![Dialogfeld nach dem Ändern der Größe. ] (../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")  
  
 Sie können das dynamische Layout steuern, indem Sie die Details für jedes Steuerelement im Ressourcen-Editor in der IDE angegeben, oder Sie können es programmgesteuert durch Zugriff auf das „CMFCDynamicLayout“-Objekt für ein bestimmtes Steuerelement und Festlegen der Eigenschaften steuern.  
  
### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>Festlegen der Eigenschaften für das dynamische Layout im Ressourcen-Editor  
 Sie können das dynamische Layoutverhalten für ein Dialogfeld festlegen, ohne Code schreiben zu müssen, nämlich mit dem Ressourcen-Editor.  
  
##### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>So legen Sie Eigenschaften für das dynamische Layout im Ressourcen-Editor fest  
  
1.  Öffnen Sie bei einem geöffneten MFC-Projekt das Dialogfeld, das Sie im Dialog-Editor bearbeiten möchten.  
  
     ![Öffnen Sie das Dialogfeld, in dem Ressourcen-Editor. ] (../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")  
  
2.  Wählen Sie ein Steuerelement aus, und legen Sie im Eigenschaftenfenster seine Eigenschaften für das dynamische Layout fest. Die **dynamisches Layout** Abschnitt im Eigenschaftenfenster die Eigenschaften enthält **Verschiebungstyp**, **Größentyp**, und abhängig von den für diese Eigenschaften ausgewählten Werten bestimmte Eigenschaften, die definieren, wie viele Steuerelemente verschieben oder Ändern der Größe. **Verschiebungstyp** bestimmt, wie ein Steuerelement verschoben wird wie die Größe des Dialogfelds geändert wird. **Größentyp** bestimmt, wie die Größe eines Steuerelements geändert wird, wie die Größe des Dialogfelds geändert wird. **Verschiebungstyp** und **Größentyp** möglicherweise **horizontale**, **vertikale**, **beide**, oder **keine** je nach den Dimensionen, die Sie dynamisch ändern möchten. Horizontal ist die X-Dimension. Vertikal ist die Y-Richtung.  
  
3.  Wenn Sie möchten ein Steuerelement, z. B. eine Schaltfläche an eine feste Größe und Position unten rechts bleibt, ist wie üblich, dass die **OK** oder **"Abbrechen"** legen Sie die Schaltflächen, die **Größentyp** zu  **Keine**, und legen Sie die **Verschiebungstyp** auf **beide**. Für die **Verschiebung X** und **Verschiebung Y** Werte unter **Verschiebungstyp**, legen Sie 100 %, dazu führen, dass das Steuerelement einen festen Abstand zur unteren rechten Ecke beibehält.  
  
     ![Dynamisches Layout](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")  
  
4.  Angenommen, Sie haben auch ein Steuerelement, das erweitert werden soll, wenn das Dialogfeld erweitert wird. In der Regel kann ein Benutzer ein Dialogfeld erweitern, um ein mehrzeiliges Bearbeitungsfeld zu erweitern und die Größe des Textbereichs zu erhöhen, oder er erweitert möglicherweise ein Listensteuerelement, um mehr Daten anzuzeigen. Legen Sie für diesen Fall die **Größentyp** auf "beide" und legen Sie die **Verschiebungstyp** auf none. Schalten Sie dann die **Größe X** und **Größe Y** Werte und 100.  
  
     ![Dynamische Layouteinstellungen](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")  
  
5.  Experimentieren Sie mit anderen Werten, die möglicherweise für Ihre Steuerelemente sinnvoll sind. Ein Dialogfeld mit einem einzeiligen Textfeld möglicherweise die **Größentyp** festgelegt **horizontale** nur, z. B.  
  
### <a name="setting-dynamic-layout-properties-programmatically"></a>Programmgesteuertes Festlegen von Eigenschaften für das dynamische Layout  
 Das vorherige Verfahren eignet sich für das Angeben der Einstellungen für das dynamische Layout für einen Dialog zur Entwurfszeit, aber wenn Sie das dynamische Layout zur Laufzeit steuern möchten, können Sie Eigenschaften für das dynamische Layout programmgesteuert festlegen.  
  
##### <a name="to-set-dynamic-layout-properties-programmatically"></a>So legen Sie Eigenschaften für das dynamische Layout programmgesteuert fest  
  
1.  Suchen oder erstellen Sie eine Position im Implementierungscode der Dialogfeldklasse, an dem Sie das dynamische Layout für den Dialog angeben möchten. Sie können z. B. eine Methode wie `AdjustLayout` im Dialogfeld hinzufügen und von Positionen aus aufrufen, an denen das Layout geändert werden muss. Sie können dies zuerst vom Konstruktor aus oder nach dem Vornehmen von Änderungen am Dialog aufrufen.  
  
2.  Rufen Sie für den Dialog [GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout), eine Methode der CWnd-Klasse. „GetDynamicLayout“ gibt einen Zeiger auf ein „CMFCDynamicLayout“-Objekt zurück.  
  
 ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();

 ```  
  
3.  Für das erste Steuerelement, das Sie dynamisches Verhalten hinzufügen möchten, verwenden Sie die statischen Methoden auf der dynamischen Layoutklasse zum Erstellen der [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) -Struktur, die die Art und Weise codiert das Steuerelement angepasst werden soll. Sie dazu zuerst die entsprechende statische Methode auswählen: [CMFCDynamicLayout::MoveHorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), [CMFCDynamicLayout::MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone), oder [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical). Sie übergeben eine Prozentzahl für die horizontalen bzw. vertikalen Aspekte der Verschiebung. Diese statischen Methoden geben alle ein neu erstelltes „MoveSettings“-Objekt zurück, mit dem Sie das Verschiebeverhalten eines Steuerelements angeben können.  
  
     Beachten Sie, dass 100 eine exakte Verschiebung gemäß der Größenänderung des Dialogs bedeutet, wodurch der Rand eines Steuerelement in einem festen Abstand zum neuen Rahmen bleibt.  
  
 ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);

 ```  
  
4.  Führen Sie dieselben Schritte für das Verhalten für Größe, verwendet der [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) Typ. Um beispielsweise anzugeben, dass die Größe eines Steuerelements nicht geändert wird, wenn sich die Größe des Dialogfelds ändert, verwenden Sie folgenden Code:  
  
 ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();

 ```  
  
5.  Fügen Sie das Steuerelement zum dynamischen Layout-Manager mit der [cmfcdynamiclayout:: AddItem](../mfc/reference/cmfcdynamiclayout-class.md#additem) Methode. Es gibt zwei Überladungen für verschiedene Möglichkeiten zum Angeben des gewünschten Steuerelements. Eine verwendet den Fensterhandle (HWND) des Steuerelements, und die andere die Steuerelement-ID.  
  
 ```  
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);

 ```  
  
6.  Wiederholen Sie den Vorgang für jedes Steuerelement, das verschoben oder dessen Größe geändert werden muss.  
  
7.  Wenn erforderlich, können die [cmfcdynamiclayout:: Hasitem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) Methode, um zu bestimmen, ob ein Steuerelement bereits in der Liste der Steuerelemente zum dynamischen layoutänderungen unterliegen, vorhanden ist oder die [cmfcdynamiclayout:: IsEmpty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) Methode, um festzustellen, ob alle Steuerelemente, die sich Änderungen enthalten sind.  
  
8.  Um das Layout des Dialogfelds zu aktivieren, rufen Sie die [CWnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) Methode.  
  
 ```  
    pDialog->EnableDynamicLayout(TRUE);

 ```  
  
9. Das nächste Mal mit dem Benutzer die Größe im Dialogfeld Ändern der [cmfcdynamiclayout:: Adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust) Methode wird aufgerufen, die die Einstellungen tatsächlich übernimmt.  
  
10. Wenn Sie das dynamische Layout deaktivieren möchten, rufen Sie [CWnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) mit `FALSE` wie für die `bEnabled` Parameter.  
  
 ```  
    pDialog->EnableDynamicLayout(FALSE);

 ```  
  
##### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>So legen Sie das dynamische Layout programmgesteuert aus einer Ressourcendatei fest  
  
1.  Verwenden der [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) Methode, um einen Ressourcennamen in der entsprechenden Ressourcenskriptdatei (RC-Datei) angeben, die Informationen zum dynamischen Layout wie im folgenden Beispiel gibt:  
  
 ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");

 ```  
  
     Die benannte Ressource muss auf ein Dialogfeld verweisen, das Layoutinformationen in Form eines AFX_DIALOG_LAYOUT-Eintrags in der Ressourcendatei enthält, wie im folgenden Beispiel gezeigt wird:  
  
 "" * / / / * / / * / / AFX_DIALOG_LAYOUT * / /  
 
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGINNEN SIE 0 X 0000, 0X6400, 0 X 0028, 0X643C, 0 X 0028  
    ENDE 
 
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGINNEN SIE 0 X 0000, 0X6464, 0 X 0000, 0X6464, 0 X 0000, 0 X 0000, 0X6464, 0 X 0000, 0 X 0000  
 
    ENDE 
 ```  
  
## See Also  
 [CMFCDynamicLayout Class](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Control Classes](../mfc/control-classes.md)   
 [Dialog Box Classes](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../windows/dialog-editor.md)

