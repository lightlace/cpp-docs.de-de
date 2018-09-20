---
title: Dynamisches Layout | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08fc6f6a5b93851468d412e34b3ee0a85ab534e5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413249"
---
# <a name="dynamic-layout"></a>Dynamisches Layout

Mit MFC in Visual Studio 2015 können Sie Dialogfelder erstellen, die der Benutzer ändern kann, und Sie können steuern, wie das Layout zum Ändern der Größe angepasst wird. Beispielsweise können Sie Schaltflächen am unteren Rand eines Dialogfelds anfügen, sodass sie sich immer am unteren Rand befinden. Sie können auch bestimmte Steuerelemente einrichten, wie z. B. Textfelder, Listenfelder und Bearbeitungsfelder, die erweitert werden, wenn der Benutzer das Dialogfeld erweitert.

## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>Angeben dynamischer Layouteinstellungen für ein MFC-Dialogfeld

Wenn der Benutzer die Größe eines Dialogfelds ändert, können die Steuerelemente im Dialogfeld in der Größe verändert oder in X- und Y-Richtung verschoben werden. Die Änderung in der Größe oder Position eines Steuerelements, wenn der Benutzer die Größe eines Dialogfelds ändert, wird als dynamisches Layout bezeichnet. Folgendes ist z. B. ein Dialogfeld vor dem Ändern der Größe:

![Dialogfeld vor dem Ändern der Größe. ](../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")

Nach dem Ändern der Größe ist der Listenfeldbereich vergrößert, um weitere Elemente anzuzeigen, und die Schaltflächen wurden entlang der rechten unteren Ecke verschoben:

![Dialogfeld nach dem Ändern der Größe. ](../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")

Sie können dynamisches Layout steuern, durch Angeben der Details für jedes Steuerelement im Ressourcen-Editor in der IDE, oder Sie können es programmgesteuert durch Zugriff auf die `CMFCDynamicLayout` -Objekt für ein bestimmtes Steuerelement und Festlegen der Eigenschaften.

### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>Festlegen der Eigenschaften für das dynamische Layout im Ressourcen-Editor

Sie können das dynamische Layoutverhalten für ein Dialogfeld festlegen, ohne Code schreiben zu müssen, nämlich mit dem Ressourcen-Editor.

#### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>So legen Sie Eigenschaften für das dynamische Layout im Ressourcen-Editor fest

1. Öffnen Sie bei einem geöffneten MFC-Projekt das Dialogfeld, das Sie im Dialog-Editor bearbeiten möchten.

     ![Öffnen Sie das Dialogfeld, in dem Ressourcen-Editor. ](../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")

2. Wählen Sie ein Steuerelement aus, und legen Sie im Eigenschaftenfenster seine Eigenschaften für das dynamische Layout fest. Die **dynamisches Layout** Abschnitt in das Fenster "Eigenschaften" enthält die Eigenschaften **Verschiebungstyp**, **Größentyp**, und, je nach den Werten für diese Eigenschaften, ausgewählt bestimmte Eigenschaften, die definieren, wie viele Steuerelemente verschieben oder Ändern der Größe. **Verschiebungstyp** bestimmt, wie ein Steuerelement verschoben wird, wenn die Größe des Dialogfelds geändert wird; **Größentyp** bestimmt, wie ein Steuerelement skaliert wird, wenn die Größe des Dialogfelds geändert wird. **Verschiebungstyp** und **Größentyp** möglicherweise **horizontale**, **vertikale**, **sowohl**, oder **keine**abhängig von den Dimensionen, die Sie dynamisch ändern möchten. Horizontal ist die X-Dimension. Vertikal ist die Y-Richtung.

3. Wenn Sie möchten ein Steuerelement, z. B. eine Schaltfläche auf eine feste Größe und Position unten rechts bleibt, wird wie üblich, dass die **OK** oder **Abbrechen** legen Sie die Schaltflächen, die **Größentyp** zu  **Keine**, und legen Sie die **Verschiebungstyp** zu **sowohl**. Für die **Verschiebung X** und **Verschiebung Y** Werte unter **Verschiebungstyp**, legen Sie 100 %, die dazu führen, dass das Steuerelement in einem festen Abstand vom unteren rechten Ecke beibehält.

     ![Dynamisches Layout](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")

4. Angenommen, Sie haben auch ein Steuerelement, das erweitert werden soll, wenn das Dialogfeld erweitert wird. In der Regel kann ein Benutzer ein Dialogfeld erweitern, um ein mehrzeiliges Bearbeitungsfeld zu erweitern und die Größe des Textbereichs zu erhöhen, oder er erweitert möglicherweise ein Listensteuerelement, um mehr Daten anzuzeigen. Legen Sie für diesen Fall die **Größentyp** auf "beide" und legen Sie die **Verschiebungstyp** auf "None". Legen Sie dann die **Größe X** und **Größe Y** Werte und 100.

     ![Dynamische Layouteinstellungen](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")

5. Experimentieren Sie mit anderen Werten, die möglicherweise für Ihre Steuerelemente sinnvoll sind. Ein Dialogfeld mit einem einzeiligen Textfeld möglicherweise die **Größentyp** festgelegt **horizontale** , z. B.

### <a name="setting-dynamic-layout-properties-programmatically"></a>Programmgesteuertes Festlegen von Eigenschaften für das dynamische Layout

Das vorherige Verfahren eignet sich für das Angeben der Einstellungen für das dynamische Layout für einen Dialog zur Entwurfszeit, aber wenn Sie das dynamische Layout zur Laufzeit steuern möchten, können Sie Eigenschaften für das dynamische Layout programmgesteuert festlegen.

#### <a name="to-set-dynamic-layout-properties-programmatically"></a>So legen Sie Eigenschaften für das dynamische Layout programmgesteuert fest

1. Suchen oder erstellen Sie eine Position im Implementierungscode der Dialogfeldklasse, an dem Sie das dynamische Layout für den Dialog angeben möchten. Sie können z. B. eine Methode wie `AdjustLayout` im Dialogfeld hinzufügen und von Positionen aus aufrufen, an denen das Layout geändert werden muss. Sie können dies zuerst vom Konstruktor aus oder nach dem Vornehmen von Änderungen am Dialog aufrufen.

2. Rufen Sie für den Dialog [GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout), eine Methode der `CWnd` Klasse. `GetDynamicLayout` Gibt einen Zeiger auf eine `CMFCDynamicLayout` Objekt.

    ```cpp
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();
    ```

3. Für das erste Steuerelement, zu dem Sie dynamisches Verhalten hinzufügen möchten, verwenden Sie die statischen Methoden in der dynamischen Layoutklasse zum Erstellen der [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) -Struktur, die die Art und Weise codiert das Steuerelement angepasst werden soll. Zu diesem Zweck zuerst die entsprechende statische Methode auswählen: [CMFCDynamicLayout::MoveHorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), [CMFCDynamicLayout::MoveNone](../mfc/reference/cmfcdynamiclayout-class.md#movenone), oder [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical). Sie übergeben eine Prozentzahl für die horizontalen bzw. vertikalen Aspekte der Verschiebung. Diese statischen Methoden geben alle ein neu erstelltes „MoveSettings“-Objekt zurück, mit dem Sie das Verschiebeverhalten eines Steuerelements angeben können.

   Beachten Sie, dass 100 eine exakte Verschiebung gemäß der Größenänderung des Dialogs bedeutet, wodurch der Rand eines Steuerelement in einem festen Abstand zum neuen Rahmen bleibt.

    ```cpp
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);
    ```

4. Führen Sie dieselben Schritte für das Verhalten für Größe, die verwendet die [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) Typ. Um beispielsweise anzugeben, dass die Größe eines Steuerelements nicht geändert wird, wenn sich die Größe des Dialogfelds ändert, verwenden Sie folgenden Code:

    ```cpp
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();
    ```

5. Fügen Sie das Steuerelement zum dynamischen Layout-Manager mit der [cmfcdynamiclayout:: AddItem](../mfc/reference/cmfcdynamiclayout-class.md#additem) Methode. Es gibt zwei Überladungen für verschiedene Möglichkeiten zum Angeben des gewünschten Steuerelements. Eine verwendet den Fensterhandle (HWND) des Steuerelements, und die andere die Steuerelement-ID.

    ```cpp
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);
    ```

6. Wiederholen Sie den Vorgang für jedes Steuerelement, das verschoben oder dessen Größe geändert werden muss.

7. Wenn nötig, können die [cmfcdynamiclayout:: Hasitem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) Methode, um zu bestimmen, ob ein Steuerelement bereits in der Liste der Steuerelemente layoutänderungen unterliegen vorhanden, oder die [cmfcdynamiclayout:: IsEmpty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) Methode, die bestimmen, ob alle Steuerelemente, die Änderungen unterliegen.

8. Um Layout des Dialogfelds zu aktivieren, rufen die [CWnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) Methode.

    ```cpp
    pDialog->EnableDynamicLayout(TRUE);
    ```

9. Das nächste Mal, die der Benutzer ändert die Größe im Dialogfeld die [cmfcdynamiclayout:: Adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust) Methode wird aufgerufen, die die Einstellungen tatsächlich übernimmt.

10. Wenn Sie das dynamische Layout deaktivieren möchten, rufen Sie [CWnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) mit **"false"** wie für die *bAktiviert* Parameter.

    ```cpp
    pDialog->EnableDynamicLayout(FALSE);
    ```

#### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>So legen Sie das dynamische Layout programmgesteuert aus einer Ressourcendatei fest

1. Verwenden der [CMFCDynamicLayout::MoveHorizontalAndVertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) Methode, um einen Ressourcennamen in der entsprechenden Ressourcenskriptdatei (RC-Datei) anzugeben, der angibt, Informationen zum dynamischen Layout wie im folgenden Beispiel:

    ```cpp
    dynamicLayout->LoadResource("IDD_DIALOG1");
    ```

     Die benannte Ressource muss einen Dialog, der Layoutinformationen in Form von enthält verweisen eine **AFX_DIALOG_LAYOUT** Eintrag in der Ressourcendatei, wie im folgenden Beispiel gezeigt:

    ```RC
    /////////////////////////////////////////////////////////////////////////////
    //
    // AFX_DIALOG_LAYOUT
    //

    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6400,
    0x0028,
    0x643c,
    0x0028
    END

    IDD_DIALOG1 AFX_DIALOG_LAYOUT
    BEGIN
    0x0000,
    0x6464,
    0x0000,
    0x6464,
    0x0000,
    0x0000,
    0x6464,
    0x0000,
    0x0000

    END
    ```

## <a name="see-also"></a>Siehe auch

[CMFCDynamicLayout-Klasse](../mfc/reference/cmfcdynamiclayout-class.md)<br/>
[Steuerelementklassen](../mfc/control-classes.md)<br/>
[Dialogfeldklassen](../mfc/dialog-box-classes.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)<br/>
[Dialogfeld für dynamischen Layout für MFC in Visual C++ 2015](https://mariusbancila.ro/blog/2015/07/27/dynamic-dialog-layout-for-mfc-in-visual-c-2015/)
