---
title: 'Exemplarische Vorgehensweise: Verwenden die neue MFC-Bibliothek Shell-Steuerelemente | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: 81925cfa31c394a1b307a184388fb0d331d31fdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432489"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell-Steuerelemente

In dieser exemplarischen Vorgehensweise erstellen Sie eine Anwendung, die Datei-Explorer ähnelt. Sie erstellen ein Fenster, das zwei Bereiche enthält. Der linke Bereich enthält eine [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) Objekt, das Ihrem Desktop in einer hierarchischen Ansicht anzeigt. Der rechte Bereich enthält eine [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) , die Dateien angezeigt, in dem Ordner, der im linken Bereich ausgewählt ist.

## <a name="prerequisites"></a>Erforderliche Komponenten

In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie Visual Studio eingerichtet haben, verwenden **allgemeine Entwicklungseinstellungen**. Wenn Sie eine andere entwicklungseinstellung verwenden, können einige Visual Studio-Fenster, die in dieser exemplarischen Vorgehensweise wir verwenden nicht standardmäßig angezeigt.

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>So erstellen Sie eine MFC-Anwendung mit dem MFC-Anwendungs-Assistenten

1. Verwenden der **MFS-Anwendungsassistenten** eine MFC-Anwendung zu erstellen. Zum Ausführen des Assistenten aus den **Datei** Menü die Option **neu**, und wählen Sie dann **Projekt**. Die **neues Projekt** Dialogfeld wird angezeigt.

2. In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten in der **Projekttypen** Bereich, und wählen Sie **MFC**. Klicken Sie auf die **Vorlagen** wählen Sie im Bereich **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. `MFCShellControls` , und klicken Sie auf **OK**. Die **MFS-Anwendungsassistenten** wird angezeigt.

3. In der **MFS-Anwendungsassistenten** Dialogfeld klicken Sie auf **Weiter**. Die **Anwendungstyp** Bereich angezeigt wird.

4. Auf der **Anwendungstyp** Bereich unter **Anwendungstyp**Deaktivieren der **Dokumente im Registerformat** Option. Wählen Sie als Nächstes **einzelnes Dokument** , und wählen Sie **Unterstützung für die Dokument-/Ansicht**. Unter **Style Project**Option **Visual Studio**, und von der **visueller Stil und Farben** Dropdown-Liste den Eintrag **Office 2007 (blaues Design)**. Lassen Sie alle anderen Optionen unverändert. Klicken Sie auf **Weiter** zum Anzeigen der **Verbunddokumente** Bereich.

5. Auf der **Verbunddokumente** wählen Sie im Bereich **keine**. Klicken Sie auf **Weiter** zum Anzeigen der **Zeichenfolgen für Dokumentvorlagen** Bereich.

6. Nehmen Sie keine Änderungen an der **Zeichenfolgen für Dokumentvorlagen** Bereich. Klicken Sie auf **Weiter** zum Anzeigen der **Datenbankunterstützung** Bereich.

7. Auf der **Datenbankunterstützung** wählen Sie im Bereich **keine** da diese Anwendung keine Datenbank verwendet werden. Klicken Sie auf **Weiter** zum Anzeigen der **Benutzeroberflächenfunktionen** Bereich.

8. Auf der **Benutzeroberflächenfunktionen** Bereich Stellen Sie sicher, dass die **verwenden, ein Menü- und Symbolleiste** ausgewählt ist. Lassen Sie alle anderen Optionen unverändert. Klicken Sie auf **Weiter** zum Anzeigen der **erweiterte Features** Bereich.

9. Auf der **erweiterte Features** Bereich unter **erweiterte Features**, wählen Sie nur **ActiveX-Steuerelemente** und **Allgemeines Steuerelementmanifest**. Klicken Sie unter **erweiterte Framebereiche**, wählen Sie nur die **Navigationsbereich** Option. Dies bewirkt, dass der Assistent den Bereich auf der linken Seite des Fensters mit bereits eingebetteten `CMFCShellTreeCtrl` erstellt. Klicken Sie auf **Weiter** zum Anzeigen der **generierte Klassen** Bereich.

10. Wir werden keine Änderungen an der **generierte Klassen** Bereich. Klicken Sie daher auf **Fertig stellen** um das neue MFC-Projekt zu erstellen.

11. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Erstellen Sie die Anwendung, aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie die Anwendung dazu **Debuggen starten** aus der **Debuggen** Menü.

   Der Assistent erstellt automatisch eine Anwendung, die eine Standardmenüleiste, eine Standardsymbolleiste, eine Standardstatusleiste und eine Outlook-Leiste auf der linken Seite des Fensters mit hat eine **Ordner** anzeigen und eine **Kalender** anzeigen .

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>So fügen Sie das Shell-Listensteuerelement der Dokumentenansicht hin

1. In diesem Abschnitt fügen Sie der Ansicht eine vom Assistenten erstellte Instanz von `CMFCShellListCtrl` hinzu. Öffnen Sie die ansichtsheaderdatei, indem Sie durch Doppelklicken auf MFCShellControlsView.h im der **Projektmappen-Explorer**.

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

2. Die **MFS-Anwendungsassistenten** bereits erstellt eine `CMFCShellTreeCtrl` -Objekt in der `CMainFrame` -Klasse, aber es ist ein geschützter Member. Wir werden zu einem späteren Zeitpunkt auf dieses Objekt zugreifen. Erstellen Sie daher nun eine Zugriffsmethode für das Objekt. Öffnen Sie die Headerdatei MainFrm.h durch Doppelklick im der **Projektmappen-Explorer**. Suchen Sie den folgenden Kommentar:

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

3. Jetzt wir aktualisieren die `CMFCShellControlsView` -Klasse zur Verarbeitung der **WM_CREATE** Windows-Meldung. Öffnen Sie die Headerdatei MFCShellControlsView.h, und klicken Sie auf diese Codezeile:

    ```cpp
    class CMFCShellControlsView : public CView
    ```

   Als Nächstes wird in der **Eigenschaften** Fenster klicken Sie auf die **Nachrichten** Symbol. Scrollen Sie nach unten, bis Sie finden die **WM_CREATE** Nachricht. Aus der Dropdown-Liste neben **WM_CREATE**Option  **\<hinzufügen > OnCreate**. Damit wird ein Meldungshandler erstellt, und die MFC-Meldungszuordnung wird automatisch aktualisiert.

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

4. Wiederholen Sie den vorherigen Schritt, aber für die **WM_SIZE** Nachricht. Dadurch wird die Anwendungsansicht neu gezeichnet, wenn ein Benutzer die Größe des Anwendungsfensters ändert. Ersetzen Sie die Definition für die `OnSize`-Methode durch den folgenden Code:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

5. Der letzte Schritt ist die Verbindung der `CMFCShellTreeCtrl` und `CMFCShellListCtrl` Objekte mithilfe der [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) Methode. Nachdem Sie diese Methode aufgerufen haben, zeigt `CMFCShellListCtrl` automatisch den Inhalt des Elements an, das in `CMFCShellTreeCtrl` ausgewählt ist. Dazu wird der `OnActivateView` -Methode, die von außer Kraft gesetzt wird [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).

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

6. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Erstellen Sie die Anwendung, aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie es dazu **Debuggen starten** aus der **Debuggen** Menü.

   Sie sollten nun die Details zum Element sehen, die im Ansichtsbereich `CMFCShellTreeCtrl` ausgewählt sind. Wenn Sie auf einen Knoten in `CMFCShellTreeCtrl` klicken, wird `CMFCShellListCtrl` automatisch aktualisiert. Wenn Sie auf einen Ordner in `CMFCShellListCtrl` doppelklicken, sollte `CMFCShellTreeCtrl` automatisch aktualisiert werden.

   Klicken Sie mit der rechten Maustaste auf ein beliebiges Element in der Strukturansicht oder im Listensteuerelement. Beachten Sie, dass Sie das gleiche Kontextmenü wie im richtigen Datei-Explorer abrufen.

## <a name="next-steps"></a>Nächste Schritte

- Der Assistent erstellt eine Outlook-Leiste mit einem **Ordner** Bereich und eine **Kalender** Bereich. Es wahrscheinlich nicht sinnvoll, Sie haben eine **Kalender** Bereich in einem Explorer-Fenster. Daher entfernen Sie diesen Bereich jetzt.

- Die `CMFCShellListCtrl` unterstützt die Anzeige von Dateien in unterschiedlichen Modi, z. B. **große Symbole**, **kleine Symbole**, **Liste**, und **Details**. Aktualisieren Sie die Anwendung, um diese Funktionalität zu implementieren. Hinweis: Siehe [Visual C++-Beispiele](../visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
