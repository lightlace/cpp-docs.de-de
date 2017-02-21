---
title: "Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell-Steuerelemente | Microsoft Docs"
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
helpviewer_keywords: 
  - "Shell-Steuerelemente (MFC)"
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell-Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise erstellen Sie eine Anwendung, die Datei\-Explorer ähnelt.  Sie erstellen ein Fenster, das zwei Bereiche enthält.  Der linke Bereich enthält ein [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md)\-Objekt, das den Desktop in einer hierarchischen Ansicht anzeigt.  Der rechte Bereich enthält einen [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md), der die Dateien in dem Ordner anzeigt, der im linken Bereich ausgewählt wurde.  
  
## Vorbereitungsmaßnahmen  
 In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installiert haben, um **Allgemeine Entwicklungseinstellungen** zu verwenden.  Wenn Sie eine andere Entwicklungseinstellung verwenden, werden einige [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Fenster, die Sie in dieser exemplarischen Vorgehensweise verwenden, nicht standardmäßig angezeigt.  
  
### So erstellen Sie eine MFC\-Anwendung mit dem MFC\-Anwendungs\-Assistenten  
  
1.  Verwenden Sie den **MFC\-Anwendungs\-Assistenten**, um eine neue MFC\-Anwendung zu erstellen.  Um den Assistenten auszuführen, wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.  Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C\+\+** im Bereich **Projekttypen**, und wählen Sie **MFC** aus.  Wählen Sie dann im Bereich **Vorlagen** den Eintrag **MFC\-Anwendung** aus.  Geben Sie einen Namen für das Projekt ein, z. B. `MFCShellControls`, und klicken Sie auf **OK**.  Der **MFC\-Anwendungs\-Assistent** wird angezeigt.  
  
3.  Klicken Sie im Dialogfeld **MFC\-Anwendungs\-Assistent** auf **Weiter**.  Der Bereich **Anwendungstyp** wird angezeigt.  
  
4.  Deaktivieren Sie im Bereich **Anwendungstyp** unter **Anwendungstyp** die Option **Dokumente im Registerkartenformat**.  Wählen Sie als Nächstes **Einfaches Dokument** und anschließend **Unterstützung für die Dokument\-\/Ansichtarchitektur** aus.  Wählen Sie unter **Projektstil** die Option **Visual Studio** aus, und wählen Sie dann in der Dropdownliste **Visueller Stil und Farben** den Eintrag **Office 2007 \(Blaues Design\)** aus.  Lassen Sie alle anderen Optionen unverändert.  Klicken Sie auf **Weiter**, um den Bereich **Verbunddokumente** anzuzeigen.  
  
5.  Wählen Sie im Bereich **Verbunddokumente** die Option **Kein** aus.  Klicken Sie auf **Weiter**, um den Bereich **Zeichenfolgen für Dokumentvorlagen** anzuzeigen.  
  
6.  Nehmen Sie keine Änderungen am Bereich **Zeichenfolgen für Dokumentvorlagen** vor.  Klicken Sie auf **Weiter**, um den Bereich **Datenbankunterstützung** anzuzeigen.  
  
7.  Wählen Sie im Bereich **Datenbankunterstützung** die Option **Kein** aus, da diese Anwendung keine Datenbank verwendet.  Klicken Sie auf **Weiter**, um den Bereich **Benutzeroberflächenfunktionen** anzuzeigen.  
  
8.  Überprüfen Sie im Bereich **Benutzeroberflächenfunktionen**, ob die Option **Menü\- und Symbolleiste verwenden** aktiviert ist.  Lassen Sie alle anderen Optionen unverändert.  Klicken Sie auf **Weiter**, um den Bereich **Erweiterte Funktionen** anzuzeigen.  
  
9. Wählen Sie im Bereich **Erweiterte Funktionen** unter **Erweiterte Funktionen** nur **ActiveX\-Steuerelemente** und **Allgemeines Steuerelementmanifest** aus.  Wählen Sie unter **Erweiterte Framebereiche** nur die Option **Navigationsbereich** aus.  Dies bewirkt, dass der Assistent den Bereich auf der linken Seite des Fensters mit bereits eingebetteten `CMFCShellTreeCtrl` erstellt.  Klicken Sie auf **Weiter**, um den Bereich **Generierte Klassen** anzuzeigen.  
  
10. Es werden keine Änderungen am Bereich **Generierte Klassen** vorgenommen.  Klicken Sie daher auf **Fertig stellen**, um das neue MFC\-Projekt zu erstellen.  
  
11. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen.  Wählen Sie **Projektmappe erstellen** im Menü **Erstellen** aus, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debug** auf **Debugging starten** klicken.  
  
     Der Assistent erstellt automatisch eine Anwendung, die eine Standardmenüleiste, eine Standardsymbolleiste, eine Standardstatusleiste und eine Outlook\-Leiste auf der linken Seite des Fensters mit einer Ansicht **Ordner** und einer Ansicht **Kalender** enthält.  
  
### So fügen Sie das Shell\-Listensteuerelement der Dokumentenansicht hin  
  
1.  In diesem Abschnitt fügen Sie der Ansicht eine vom Assistenten erstellte Instanz von `CMFCShellListCtrl` hinzu.  Öffnen Sie die Ansichtsheaderdatei, indem Sie auf MFCShellControlsView.h im **Projektmappen\-Explorer** doppelklicken.  
  
     Suchen Sie die `#pragma once`\-Direktive am oberen Rand der Headerdatei.  Fügen Sie direkt darunter den folgenden Code hinzu, mit dem die Headerdatei für `CMFCShellListCtrl` eingeschlossen wird:  
  
    ```  
    #include <afxShellListCtrl.h>  
    ```  
  
     Fügen Sie nun eine Membervariable des Typs `CMFCShellListCtrl` hinzu.  Suchen Sie zunächst den folgenden Kommentar in der Headerdatei:  
  
    ```  
    // Generated message map functions  
    ```  
  
     Fügen Sie direkt über diesem Kommentar den folgenden Code hinzu:  
  
    ```  
    private:  
        CMFCShellListCtrl m_wndList;  
    ```  
  
2.  Vom **MFC\-Anwendungs\-Assistent** wurde bereits ein `CMFCShellTreeCtrl`\-Objekt in der `CMainFrame`\-Klasse erstellt. Es handelt sich aber um einen geschützten Member.  Wir werden zu einem späteren Zeitpunkt auf dieses Objekt zugreifen.  Erstellen Sie daher nun einen Accessor für das Objekt.  Öffnen Sie die Headerdatei MainFrm.h, indem Sie im **Projektmappen\-Explorer** darauf doppelklicken.  Suchen Sie den folgenden Kommentar:  
  
    ```  
    // Attributes  
    ```  
  
     Fügen Sie direkt darunter die folgende Methodendeklaration hinzu:  
  
    ```  
    public:  
        CMFCShellTreeCtrl& GetShellTreeCtrl();  
    ```  
  
     Als Nächstes öffnen Sie die Quelldatei MainFrm.cpp, indem Sie im **Projektmappen\-Explorer** darauf doppelklicken.  Fügen Sie am unteren Rand dieser Datei die folgende Methodendefinition hinzu:  
  
    ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
    {  
        return m_wndTree;  
    }  
    ```  
  
3.  Jetzt aktualisieren wir die `CMFCShellControlsView`\-Klasse, um die **WM\_CREATE**\-Fenstermeldung zu bearbeiten.  Öffnen Sie die Headerdatei MFCShellControlsView.h, und klicken Sie auf diese Codezeile:  
  
    ```  
    class CMFCShellControlsView : public CView  
    ```  
  
     Klicken Sie als Nächstes im Fenster **Eigenschaften** auf die Schaltfläche **Meldungen**.  Führen Sie einen Bildlauf nach unten bis zur **WM\_CREATE**\-Meldung durch.  Wählen Sie aus Dropdownliste neben **WM\_CREATE** den Eintrag **\<Hinzufügen\> OnCreate** aus.  Damit wird ein Meldungshandler erstellt, und die MFC\-Meldungszuordnung wird automatisch aktualisiert.  
  
     In der `OnCreate`\-Methode erstellen Sie jetzt das `CMFCShellListCtrl`\-Objekt.  Suchen Sie die `OnCreate`\-Methodendefinition in der Quelldatei MFCShellControlsView.cpp, und ersetzen Sie die entsprechende Implementierung durch folgenden Code:  
  
    ```  
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
  
4.  Wiederholen Sie den vorherigen Schritt nun für die **WM\_SIZE**\-Meldung.  Dadurch wird die Anwendungsansicht neu gezeichnet, wenn ein Benutzer die Größe des Anwendungsfensters ändert.  Ersetzen Sie die Definition für die `OnSize`\-Methode durch den folgenden Code:  
  
    ```  
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,  
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);  
    }  
    ```  
  
5.  Der letzte Schritt besteht darin, mit der [CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)\-Methode eine Verbindung der Objekte `CMFCShellTreeCtrl` und `CMFCShellListCtrl` herzustellen.  Nachdem Sie diese Methode aufgerufen haben, zeigt `CMFCShellListCtrl` automatisch den Inhalt des Elements an, das in `CMFCShellTreeCtrl` ausgewählt ist.  Dazu wird die `OnActivateView`\-Methode verwendet, die durch [CView::OnActivateView](../Topic/CView::OnActivateView.md) überschrieben wird.  
  
     Fügen Sie in der Headerdatei MFCShellControlsView.h innerhalb der `CMFCShellControlsView`\-Klassendeklaration die folgende Methodendeklaration hinzu:  
  
    ```  
    protected:  
        virtual void OnActivateView(BOOL bActivate,  
            CView* pActivateView,  
            CView* pDeactiveView);  
    ```  
  
     Als Nächstes fügen Sie die Definition für diese Methode der Quelldatei MFCShellControlsView.cpp hinzu:  
  
    ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,  
        CView* pActivateView,  
        CView* pDeactiveView)   
    {  
        if (bActivate && AfxGetMainWnd() != NULL)  
        {  
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);  
        }  
  
        CView::OnActivateView(bActivate, pActivateView, pDeactiveView);  
    }  
    ```  
  
     Da die Methoden aus der Klasse `CMainFrame` aufgerufen werden, muss eine `#include`\-Direktive am Anfang der Quelldatei MFCShellControlsView.cpp hinzugefügt werden:  
  
    ```  
    #include "MainFrm.h"  
    ```  
  
6.  Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen.  Wählen Sie **Projektmappe erstellen** im Menü **Erstellen** aus, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debug** auf **Debugging starten** klicken.  
  
     Sie sollten nun die Details zum Element sehen, die im Ansichtsbereich `CMFCShellTreeCtrl` ausgewählt sind.  Wenn Sie auf einen Knoten in `CMFCShellTreeCtrl` klicken, wird `CMFCShellListCtrl` automatisch aktualisiert.  Wenn Sie auf einen Ordner in `CMFCShellListCtrl` doppelklicken, sollte `CMFCShellTreeCtrl` automatisch aktualisiert werden.  
  
     Klicken Sie mit der rechten Maustaste auf ein beliebiges Element in der Strukturansicht oder im Listensteuerelement.  Beachten Sie, dass Sie das gleiche Kontextmenü wie im richtigen Datei\-Explorer abrufen.  
  
## Nächste Schritte  
  
-   Der Assistent hat eine Outlook\-Leiste mit einem Bereich **Ordner** und einem Bereich **Kalender** erstellt.  Es ist wahrscheinlich nicht sinnvoll, einen Bereich **Kalender** in einem Explorer\-Fenster zu haben.  Daher entfernen Sie diesen Bereich jetzt.  
  
-   `CMFCShellListCtrl` unterstützt die Anzeige von Dateien in unterschiedlichen Modi, z. B. **Große Symbole**, **Kleine Symbole**, **Liste** und **Details**.  Aktualisieren Sie die Anwendung, um diese Funktionalität zu implementieren.  Hinweis: siehe [Visual C\+\+\-Beispiele](../top/visual-cpp-samples.md).  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)