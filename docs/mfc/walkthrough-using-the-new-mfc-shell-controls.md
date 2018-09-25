---
title: 'Exemplarische Vorgehensweise: Verwenden die neue MFC-Bibliothek Shell-Steuerelemente | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/20/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e1cffc9d1231cd9e8e91b445f05eb7dbbbc4ce4
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169618"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell-Steuerelemente

In dieser exemplarischen Vorgehensweise erstellen Sie eine Anwendung, die Datei-Explorer ähnelt. Sie erstellen ein Fenster, das zwei Bereiche enthält. Der linke Bereich enthält eine [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) Objekt, das Ihrem Desktop in einer hierarchischen Ansicht anzeigt. Der rechte Bereich enthält eine [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) , die Dateien angezeigt, in dem Ordner, der im linken Bereich ausgewählt ist.

## <a name="prerequisites"></a>Erforderliche Komponenten

In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie Visual Studio eingerichtet haben, verwenden **allgemeine Entwicklungseinstellungen**. Wenn Sie eine andere entwicklungseinstellung verwenden, können einige Visual Studio-Fenster, die in dieser exemplarischen Vorgehensweise wir verwenden nicht standardmäßig angezeigt.

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>So erstellen Sie eine MFC-Anwendung mit dem MFC-Anwendungs-Assistenten

1. Verwenden der **MFS-Anwendungsassistenten** eine MFC-Anwendung zu erstellen. Zum Ausführen des Assistenten aus den **Datei** Menü die Option **neu**, und wählen Sie dann **Projekt**. Die **neues Projekt** Dialogfeld wird angezeigt.

1. In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten in der **Projekttypen** Bereich, und wählen Sie **MFC**. Klicken Sie auf die **Vorlagen** wählen Sie im Bereich **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. `MFCShellControls` , und klicken Sie auf **OK**. Nach dem **MFS-Anwendungsassistenten** angezeigt, und verwenden Sie die folgenden Optionen:

    1. Auf der **Anwendungstyp** Bereich unter **Anwendungstyp**Deaktivieren der **Dokumente im Registerformat** Option. Wählen Sie als Nächstes **einzelnes Dokument** , und wählen Sie **Unterstützung für die Dokument-/Ansicht**. Unter **Style Project**Option **Visual Studio**, und von der **visueller Stil und Farben** Dropdown-Liste den Eintrag **Office 2007 (blaues Design)**. 

    1. Auf der **Verbunddokumente** wählen Sie im Bereich **keine**.

    1. Nehmen Sie keine Änderungen an der **Zeichenfolgen für Dokumentvorlagen** Bereich.

    1. Auf der **Datenbankunterstützung** wählen Sie im Bereich (Visual Studio 2015 und früher), **keine** da diese Anwendung keine Datenbank verwendet werden. 

    1. Auf der **Benutzeroberflächenfunktionen** Bereich Stellen Sie sicher, dass die **verwenden, ein Menü- und Symbolleiste** ausgewählt ist. Lassen Sie alle anderen Optionen unverändert. 

    1. Auf der **erweiterte Features** Bereich unter **erweiterte Features**, wählen Sie nur **ActiveX-Steuerelemente** und **Allgemeines Steuerelementmanifest**. Klicken Sie unter **erweiterte Framebereiche**, wählen Sie nur die **Navigationsbereich** Option. Dies bewirkt, dass der Assistent den Bereich auf der linken Seite des Fensters mit bereits eingebetteten `CMFCShellTreeCtrl` erstellt. 

    1. Wir werden keine Änderungen an der **generierte Klassen** Bereich. Klicken Sie daher auf **Fertig stellen** um das neue MFC-Projekt zu erstellen.

1. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Erstellen Sie die Anwendung, aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie die Anwendung dazu **Debuggen starten** aus der **Debuggen** Menü.

   Der Assistent erstellt automatisch eine Anwendung, die eine Standardmenüleiste, eine Standardsymbolleiste, eine Standardstatusleiste und eine Outlook-Leiste auf der linken Seite des Fensters mit hat eine **Ordner** anzeigen und eine **Kalender** anzeigen .

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>So fügen Sie das Shell-Listensteuerelement der Dokumentenansicht hin

1. In diesem Abschnitt fügen Sie der Ansicht eine vom Assistenten erstellte Instanz von `CMFCShellListCtrl` hinzu. Öffnen Sie die ansichtsheaderdatei, indem Sie durch Doppelklicken auf **MFCShellControlsView.h** in die **Projektmappen-Explorer**.

   Suchen Sie die `#pragma once`-Direktive am oberen Rand der Headerdatei. Fügen Sie direkt darunter den folgenden Code hinzu, mit dem die Headerdatei für `CMFCShellListCtrl` eingeschlossen wird:

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   Fügen Sie nun eine Membervariable des Typs `CMFCShellListCtrl` hinzu. Suchen Sie zunächst den folgenden Kommentar in der Headerdatei:

   ```cpp
   // Generated message map functions
   ```

   Fügen Sie direkt über diesem Kommentar den folgenden Code hinzu:

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. Die **MFS-Anwendungsassistenten** bereits erstellt eine `CMFCShellTreeCtrl` -Objekt in der `CMainFrame` -Klasse, aber es ist ein geschützter Member. Wir werden zu einem späteren Zeitpunkt auf dieses Objekt zugreifen. Erstellen Sie daher nun eine Zugriffsmethode für das Objekt. Öffnen Sie die Headerdatei MainFrm.h durch Doppelklick im der **Projektmappen-Explorer**. Suchen Sie den folgenden Kommentar:

   ```cpp
   // Attributes
   ```

   Fügen Sie direkt darunter die folgende Methodendeklaration hinzu:

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   Öffnen Sie als Nächstes die Quelldatei MainFrm.cpp durch Doppelklick im der **Projektmappen-Explorer**. Fügen Sie am unteren Rand dieser Datei die folgende Methodendefinition hinzu:

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. Jetzt aktualisieren wir die `CMFCShellControlsView`-Klasse, um die `WM_CREATE`-Fenstermeldung zu bearbeiten. Öffnen der **Klassenansicht** Fenster, und wählen die `CMFCShellControlsView` Klasse. Mit der rechten Maustaste, und wählen Sie **Eigenschaften**.

    Als Nächstes wird in der **Eigenschaften** Fenster klicken Sie auf die **Nachrichten** Symbol. Führen Sie einen Bildlauf nach unten bis zur `WM_CREATE`-Meldung durch. Aus der Dropdown-Liste neben `WM_CREATE`Option  **\<hinzufügen > OnCreate**. Damit wird ein Meldungshandler erstellt, und die MFC-Meldungszuordnung wird automatisch aktualisiert.

   In der `OnCreate`-Methode erstellen Sie jetzt das `CMFCShellListCtrl`-Objekt. Suchen Sie die `OnCreate`-Methodendefinition in der Quelldatei MFCShellControlsView.cpp, und ersetzen Sie die entsprechende Implementierung durch folgenden Code:

    ```cpp
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)
    {
        if (CView::OnCreate(lpCreateStruct) == -1)
            return -1;

        CRect rectDummy (0, 0, 0, 0);

        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,
            rectDummy, this, 1);

        return 0;
    }
    ```

1. Wiederholen Sie den vorherigen Schritt nun für die `WM_SIZE`-Meldung. Dadurch wird die Anwendungsansicht neu gezeichnet, wenn ein Benutzer die Größe des Anwendungsfensters ändert. Ersetzen Sie die Definition für die `OnSize`-Methode durch den folgenden Code:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. Der letzte Schritt ist die Verbindung der `CMFCShellTreeCtrl` und `CMFCShellListCtrl` Objekte mithilfe der [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) Methode. Nachdem Sie diese Methode aufgerufen haben, zeigt `CMFCShellListCtrl` automatisch den Inhalt des Elements an, das in `CMFCShellTreeCtrl` ausgewählt ist. Dazu wird der `OnActivateView` -Methode, die von außer Kraft gesetzt wird [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).

   Fügen Sie in der Headerdatei MFCShellControlsView.h innerhalb der `CMFCShellControlsView`-Klassendeklaration die folgende Methodendeklaration hinzu:

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   Als Nächstes fügen Sie die Definition für diese Methode der Quelldatei MFCShellControlsView.cpp hinzu:

    ```cpp
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView)
    {
        if (bActivate&& AfxGetMainWnd() != NULL)
        {
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }

        CView::OnActivateView(bActivate,
            pActivateView,
            pDeactiveView);
    }
    ```

   Da die Methoden aus der Klasse `CMainFrame` aufgerufen werden, muss eine `#include`-Direktive am Anfang der Quelldatei MFCShellControlsView.cpp hinzugefügt werden:

    ```cpp
    #include "MainFrm.h"
    ```

1. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Erstellen Sie die Anwendung, aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie es dazu **Debuggen starten** aus der **Debuggen** Menü.

   Sie sollten nun die Details zum Element sehen, die im Ansichtsbereich `CMFCShellTreeCtrl` ausgewählt sind. Wenn Sie auf einen Knoten in `CMFCShellTreeCtrl` klicken, wird `CMFCShellListCtrl` automatisch aktualisiert. Wenn Sie auf einen Ordner in `CMFCShellListCtrl` doppelklicken, sollte `CMFCShellTreeCtrl` automatisch aktualisiert werden.

   Klicken Sie mit der rechten Maustaste auf ein beliebiges Element in der Strukturansicht oder im Listensteuerelement. Beachten Sie, dass Sie das gleiche Kontextmenü erhalten, als würden Sie den tatsächlichen verwenden **Datei-Explorer**.

## <a name="next-steps"></a>Nächste Schritte

- Der Assistent erstellt eine Outlook-Leiste mit einem **Ordner** Bereich und eine **Kalender** Bereich. Es wahrscheinlich nicht sinnvoll, Sie haben eine **Kalender** im Bereich einer **Explorer** Fenster. Daher entfernen Sie diesen Bereich jetzt.

- Die `CMFCShellListCtrl` unterstützt die Anzeige von Dateien in unterschiedlichen Modi, z. B. **große Symbole**, **kleine Symbole**, **Liste**, und **Details**. Aktualisieren Sie die Anwendung, um diese Funktionalität zu implementieren. Hinweis: Siehe [Visual C++-Beispiele](../visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
