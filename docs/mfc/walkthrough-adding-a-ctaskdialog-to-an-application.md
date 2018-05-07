---
title: 'Exemplarische Vorgehensweise: Hinzufügen ein CTaskDialog zu einer Anwendung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b2c10583a4c3fc2b988e50c15b6c1dcf206af65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>Exemplarische Vorgehensweise: Hinzufügen eines CTaskDialog zu einer Anwendung
In dieser exemplarische Vorgehensweise wird [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) vorgestellt, und Sie erfahren, wie Sie eine Ihrer Anwendung hinzufügen können.  
  
 Die `CTaskDialog` ist ein Aufgabendialogfeld, das die Windows-Meldungsfeld in Windows Vista und höheren Versionen ersetzt. Der `CTaskDialog` verbessert das ursprüngliche Meldungsfeld und fügt Funktionen hinzu. Das Windows-Meldungsfeld wird weiterhin in Visual Studio unterstützt.  
  
> [!NOTE]
> Windows-Versionen vor Windows Vista unterstützen nicht die `CTaskDialog`. Sie müssen eine alternative Dialogfeldoption programmieren, wenn Sie einem Benutzer eine Meldung anzeigen möchten, der Ihre Anwendung unter einer früheren Version von Windows ausführt. Sie können die statische Methode [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) verwenden, um zur Laufzeit zu bestimmen, ob der Computer eines Benutzers ein `CTaskDialog`ersetzt. Darüber hinaus ist der `CTaskDialog` nur verfügbar, wenn Ihre Anwendung mit der Unicode-Bibliothek erstellt wird.  
  
 Der `CTaskDialog` unterstützt mehrere optionale Elemente zum Sammeln und Anzeigen von Informationen. Ein `CTaskDialog` kann beispielsweise Befehlslinks, benutzerdefinierte Schaltflächen, benutzerdefinierte Symbole und eine Fußzeile anzeigen. Der `CTaskDialog` verfügt auch über mehrere Methoden, mit denen Sie den Status des Aufgabendialogfelds abfragen können, um festzustellen, welche optionalen Elemente der Benutzer ausgewählt hat.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
- Visual Studio 2010 oder höher  
  
- Windows Vista oder höher  
  
## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Ersetzen eines Windows-Meldungsfeld mit einem CTaskDialog  
 Das folgende Verfahren veranschaulicht die grundlegende Verwendung des `CTaskDialog`, sprich die Ersetzung des Windows-Meldungsfelds. In diesem Beispiel wird auch das Symbol geändert, das dem Aufgabendialogfeld zugeordnet ist. Durch Ändern des Symbols wird das Erscheinungsbild des `CTaskDialog` mit dem des Windows-Meldungsfelds identisch.  
  
#### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>So ersetzen Sie ein Windows-Meldungsfeld durch einen CTaskDialog  
  
1.  Erstellen Sie ein neues MFC-Anwendungsprojekt mit den Standardeinstellungen. Geben Sie ihm den Namen `MyProject`.  
  
2.  Verwenden Sie den **Projektmappen-Explorer** , die Datei „MyProject.cpp“ zu öffnen.  
  
3.  Fügen Sie nach der include-Liste `#include "afxtaskdialog.h"` ein.  
  
4.  Suchen Sie die Methode `CMyProjectApp::InitInstance`. Fügen Sie die folgenden Codezeilen vor der `return TRUE;` -Anweisung ein. Dieser Code erstellt die Zeichenfolgen, die wir im Windows-Meldungsfeld oder im `CTaskDialog`verwenden.  
  
 ```  
    CString message("My message to the user");

    CString dialogTitle("My Task Dialog title");

    CString emptyString;  
 ```  
  
5.  Fügen Sie den folgenden Code nach dem Code aus Schritt 4 ein. Dieser Code stellt sicher, dass der Computer des Benutzers den `CTaskDialog`unterstützt. Wenn das Dialogfeld nicht unterstützt wird, zeigt die Anwendung stattdessen ein Windows-Meldungsfeld an.  
  
 ```  
    if (CTaskDialog::IsSupported())  
 {  
 
 }  
    else 
 {  
    AfxMessageBox(message);

 }  
 ```  
  
6.  Fügen Sie folgenden Code zwischen den Klammern hinter der `if` -Anweisung aus Schritt 5 ein. Dieser Code erstellt den `CTaskDialog`.  
  
 ```  
    CTaskDialog taskDialog(message,
    emptyString,
    dialogTitle,
    TDCBF_OK_BUTTON);

 ```  
  
7.  Fügen Sie in der nächsten Zeile den folgenden Code ein. Dieser Code legt das Warnsymbol fest.  
  
 ```  
    taskDialog.SetMainIcon(TD_WARNING_ICON);

 ```  
  
8.  Fügen Sie in der nächsten Zeile den folgenden Code ein. Dieser Code zeigt das Aufgabendialogfeld an.  
  
 ```  
    taskDialog.DoModal();

 ```  
  
 Sie können Schritt 7 weglassen, wenn Sie im `CTaskDialog` nicht das gleiche Symbol wie im Windows-Meldungsfeld angezeigt werden soll. Wenn Sie diesen Schritt auslassen, hat der `CTaskDialog` kein Symbol, wenn er von der Anwendung angezeigt wird.  
  
 Kompilieren Sie die Anwendung, und führen Sie sie aus. Die Anwendung zeigt das Aufgabendialogfeld nach dem Start an.  
  
## <a name="adding-functionality-to-the-ctaskdialog"></a>Hinzufügen von Funktionen zum CTaskDialog  
 Das folgende Verfahren zeigt, wie Sie dem `CTaskDialog` Funktionen hinzufügen können, die Sie im vorherigen Verfahren erstellt haben. Der Beispielcode zeigt Ihnen, wie Sie bestimmte Anweisungen basierend auf der Auswahl des Benutzers ausführen.  
  
#### <a name="to-add-functionality-to-the-ctaskdialog"></a>So fügen Sie Funktionen zum CTaskDialog hinzu  
  
1.  Navigieren Sie zur **Ressourcenansicht**. Wenn Sie die **Ressourcenansicht**nicht sehen, können Sie sie über das Menü **Ansicht** öffnen.  
  
2.  Erweitern Sie die **Ressourcenansicht** , bis Sie den Ordner **Zeichenfolgentabelle** auswählen können. Erweitern Sie ihn, und doppelklicken Sie auf den Eintrag **Zeichenfolgentabelle** .  
  
3.  Führen Sie einen Bildlauf zum unteren Rand der Tabelle durch, und fügen Sie einen neuen Eintrag hinzu. Ändern Sie die ID in `TEMP_LINE1`. Legen Sie **Befehlszeile 1**als Beschriftung fest.  
  
4.  Fügen Sie einen weiteren neuen Eintrag hinzu. Ändern Sie die ID in `TEMP_LINE2`. Legen Sie **Befehlszeile 2**als Beschriftung fest.  
  
5.  Navigieren Sie zurück zu „MyProject.cpp“.  
  
6.  Fügen Sie nach `CString emptyString;`den folgenden Code hinzu:  
  
 ```  
    CString expandedLabel("Hide extra information");

    CString collapsedLabel("Show extra information");

    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");

 ```  
  
7.  Suchen Sie die `taskDialog.DoModal()` -Anweisung, und ersetzen Sie sie durch den folgenden Code. Dieser Code aktualisiert das Aufgabendialogfeld und fügt neue Steuerelemente hinzu:  
  
 ```  
    taskDialog.SetMainInstruction(L"Warning");

 taskDialog.SetCommonButtons(TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);

    taskDialog.LoadCommandControls(TEMP_LINE1,
    TEMP_LINE2);

    taskDialog.SetExpansionArea(expansionInfo,
    collapsedLabel,
    expandedLabel);

    taskDialog.SetFooterText(L"This is the a small footnote to the user");

    taskDialog.SetVerificationCheckboxText(L"Remember your selection");

 ```  
  
8.  Fügen Sie die folgende Codezeile hinzu, die das Aufgabendialogfeld für den Benutzer anzeigt und die Auswahl des Benutzers abruft:  
  
 ```  
    INT_PTR result = taskDialog.DoModal();

 ```  
  
9. Fügen Sie nach dem Aufruf von `taskDialog.DoModal()`den folgenden Code ein. Mit diesem Codeabschnitt wird die Eingabe des Benutzers verarbeitet:  
  
 ```  
    if (taskDialog.GetVerificationCheckboxState())  
 { *// PROCESS IF the user selects the verification checkbox   
 }  
 
    switch (result)  
 {  
    case TEMP_LINE1: *// PROCESS IF the first command line  
    break; 
    case TEMP_LINE2: *// PROCESS IF the second command line  
    break; 
    case IDYES: *// PROCESS IF the user clicks yes  
    break; 
    case IDNO: *// PROCESS IF the user clicks no  
    break; 
    case IDCANCEL: *// PROCESS IF the user clicks cancel  
    break; 
    default: *// This case should not be hit because closing the dialog box results in IDCANCEL  
    break; 
 }  
 ```  
  
 Ersetzen Sie im Code in Schritt 9 die Kommentare, die mit PROCESS IF beginnen, durch den Code, den Sie unter den angegebenen Bedingungen ausführen möchten.  
  
 Kompilieren Sie die Anwendung, und führen Sie sie aus. Die Anwendung zeigt das Aufgabendialogfeld an, das die neuen Steuerelemente und zusätzliche Informationen verwendet.  
  
## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Anzeigen eines CTaskDialog, ohne ein CTaskDialog-Objekt zu erstellen  
 Das folgende Verfahren veranschaulicht, wie Sie ein `CTaskDialog` anzeigen, ohne zuvor ein `CTaskDialog` -Objekt erstellen zu müssen. Mit diesem Beispiel werden die vorherigen Prozeduren fortgesetzt.  
  
#### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>So zeigen Sie einen CTaskDialog an, ohne ein CTaskDialog-Objekt zu erstellen  
  
1.  Öffnen Sie die Datei „MyProject.cpp“, sofern noch nicht geöffnet.  
  
2.  Navigieren Sie zur schließenden Klammer für die `if (CTaskDialog::IsSupported())` -Anweisung.  
  
3.  Fügen Sie den folgenden Code direkt vor der schließenden Klammer der `if` -Anweisung (vor dem `else` -Block) ein:  
  
 ```  
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
    L"Error",
    L"New Title",
    TEMP_LINE1,
    TEMP_LINE2);

 ```  
  
 Kompilieren Sie die Anwendung, und führen Sie sie aus. Die Anwendung zeigt zwei Aufgabendialogfelder an. Das erste Dialogfeld stammt aus der Prozedur „So fügen Sie Funktionen zum CTaskDialog hinzu“. Das zweite Dialogfeld stammt aus der vorherigen Prozedur.  
  
 Diese Beispiele zeigen nicht alle verfügbaren Optionen für ein `CTaskDialog`, sind jedoch ein guter Anfangspunkt. Eine vollständige Beschreibung der Klasse finden Sie unter [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) .  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [CTaskDialog-Klasse](../mfc/reference/ctaskdialog-class.md)   
 [CTaskDialog::CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)

