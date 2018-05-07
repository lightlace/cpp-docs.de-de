---
title: Hinzufügen mehrerer Ansichten zu einem einzelnen Dokument | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb40b356b5601e19c33083c7b731a1dc411de3c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-multiple-views-to-a-single-document"></a>Hinzufügen mehrerer Ansichten zu einem Dokument
In einer Single Document Interface (SDI)-Anwendung mit der Microsoft Foundation Class (MFC)-Bibliothek erstellt ist eine einzelne Ansichtstyp zugeordnet jeder Dokumenttyp. In einigen Fällen ist es wünschenswert sein, Sie haben die Möglichkeit, die aktuelle Ansicht eines Dokuments mit einer neuen Ansicht wechseln.  
  
> [!TIP]
>  Zusätzliche Verfahren zum Implementieren mehrerer Ansichten für ein einzelnes Dokument finden Sie unter [CDocument:: AddView](../mfc/reference/cdocument-class.md#addview) und [sammeln](../visual-cpp-samples.md) MFC-Beispiel.  
  
 Sie können diese Funktionalität implementieren, indem er ein neues `CView`-abgeleitete Klasse sowie zusätzlichen Code für die Ansicht dynamisch zu einer vorhandenen MFC-Anwendung zu wechseln.  
  
 Die Schritte sind wie folgt aus:  
  
-   [Ändern Sie die vorhandene Anwendungsklasse](#vcconmodifyexistingapplicationa1)  
  
-   [Erstellen Sie und ändern Sie die neue Ansichtsklasse](#vcconnewviewclassa2)  
  
-   [Erstellen und Anfügen der neuen Ansicht](#vcconattachnewviewa3)  
  
-   [Implementieren der Funktion zum Wechseln](#vcconswitchingfunctiona4)  
  
-   [Fügen Sie Unterstützung für das Wechseln der Ansicht hinzu](#vcconswitchingtheviewa5)  
  
 Im weiteren Verlauf dieses Themas wird Folgendes vorausgesetzt:  
  
-   Der Name des der `CWinApp`-abgeleitete Objekt `CMyWinApp`, und `CMyWinApp` deklariert und in MYWINAPP definiert ist. H und MYWINAPP. CPP.  
  
-   `CNewView` Der Name der neuen `CView`-abgeleitetes Objekt, und `CNewView` deklariert und in NEWVIEW definiert ist. H und NEWVIEW. CPP.  
  
##  <a name="vcconmodifyexistingapplicationa1"></a> Ändern Sie die vorhandene Anwendungsklasse  
 Für die Anwendung zwischen Ansichten wechseln müssen Sie die Anwendungsklasse durch Hinzufügen von Membervariablen zum Speichern von Ansichten und eine Methode zum Wechseln zu ändern.  
  
 Fügen Sie den folgenden Code zur Deklaration von `CMyWinApp` in MYWINAPP. H  
  
 [!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]  
  
 Die neue Membervariablen `m_pOldView` und `m_pNewView`, zeigen Sie auf der aktuellen Ansicht und der neu erstellte. Die neue Methode (`SwitchView`) wechselt die Ansichten aus, wenn vom Benutzer angefordert. Der Text der Methode wird weiter unten in diesem Thema im [implementieren die wechseln-Funktion](#vcconswitchingfunctiona4).  
  
 Die letzte Änderung an der Anwendungsklasse erfordert z. B. eine neue Headerdatei, die eine Windows-Meldung definiert (**WM_INITIALUPDATE**), die in der wechseln-Funktion verwendet wird.  
  
 Fügen Sie die folgende Zeile im Includeabschnitt "MYWINAPP. CPP:  
  
 [!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]  
  
 Die Änderungen zu speichern und mit dem nächsten Schritt fortfahren.  
  
##  <a name="vcconnewviewclassa2"></a> Erstellen Sie und ändern Sie die neue Ansichtsklasse  
 Erstellen neue Ansichtsklasse erfolgt einfach mithilfe der **neue Klasse** Befehl in der Klassenansicht. Die einzige Anforderung für diese Klasse ist, dass es abgeleitet `CView`. Fügen Sie diese neue Art der Anwendung. Spezifische Informationen über das Projekt eine neue Klasse hinzufügen, finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).  
  
 Nachdem Sie die Klasse dem Projekt hinzugefügt haben, müssen Sie den Zugriff auf einige Klassenmember Ansicht ändern.  
  
 Ändern Sie NEWVIEW. H durch Ändern der Zugriffsspezifizierer aus `protected` auf **öffentlichen** für den Konstruktor und Destruktor. Dadurch wird die Klasse erstellt und zerstört dynamisch sein und das Erscheinungsbild der Ansicht zu ändern, bevor es angezeigt wird.  
  
 Die Änderungen zu speichern und mit dem nächsten Schritt fortfahren.  
  
##  <a name="vcconattachnewviewa3"></a> Erstellen und Anfügen der neuen Ansicht  
 Zum Erstellen, und fügen Sie die neue Sicht, müssen Sie ändern die `InitInstance` Funktion Ihrer Anwendung-Klasse. Die Änderung fügt neue Code, der ein neues Objekt, und klicken Sie dann initialisiert beide erstellt `m_pOldView` und `m_pNewView` mit den zwei vorhandene Ansicht-Objekten.  
  
 Da die neue Ansicht, innerhalb erstellt wird der `InitInstance` -Funktion, die neuen und vorhandenen Ansichten gelten, für die Lebensdauer der Anwendung. Allerdings kann die Anwendung die neue Ansicht genauso einfach dynamisch erstellen.  
  
 Fügen Sie diesen Code nach dem Aufruf von `ProcessShellCommand`:  
  
 [!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]  
  
 Die Änderungen zu speichern und mit dem nächsten Schritt fortfahren.  
  
##  <a name="vcconswitchingfunctiona4"></a> Implementieren der Funktion zum Wechseln  
 Im vorherigen Schritt haben Sie Code, der erstellt und initialisiert ein neues Ansichtsobjekt hinzugefügt. Die letzte Aufgabe wird zur Implementierung der switching Methode `SwitchView`.  
  
 Am Ende der Implementierungsdatei für die Anwendungsklasse (MYWINAPP. CPP), fügen Sie die folgende Methodendefinition hinzu:  
  
 [!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]  
  
 Die Änderungen zu speichern und mit dem nächsten Schritt fortfahren.  
  
##  <a name="vcconswitchingtheviewa5"></a> Fügen Sie Unterstützung für das Wechseln der Ansicht hinzu  
 Der letzte Schritt umfasst das Hinzufügen von Code, der Aufrufe der `SwitchView` Methode, wenn die Anwendung zwischen Ansichten wechseln muss. Dies kann auf unterschiedliche Weise ausgeführt werden: durch Hinzufügen eines neuen Menüelements für die Benutzer auswählen oder intern die Ansicht wechseln, wenn bestimmte Bedingungen erfüllt sind.  
  
 Weitere Informationen zum Hinzufügen von neuen Menüelemente und befehlshandlerfunktionen finden Sie unter [Handler für Befehle und Steuerelementbenachrichtigungen](../mfc/handlers-for-commands-and-control-notifications.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

