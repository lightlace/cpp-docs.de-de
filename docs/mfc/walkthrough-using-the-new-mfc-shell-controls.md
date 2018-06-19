---
title: 'Exemplarische Vorgehensweise: Verwenden von neuen MFC Shell-Steuerelemente | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f19939a50b5bdbf98d087450b6301a923651a433
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385095"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell-Steuerelemente
In dieser exemplarischen Vorgehensweise erstellen Sie eine Anwendung, die Datei-Explorer ähnelt. Sie erstellen ein Fenster, das zwei Bereiche enthält. Der linke Bereich enthält eine [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) Objekt, das den Desktop in einer hierarchischen Ansicht anzeigt. Der rechte Bereich enthält eine [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) , die Dateien anzeigt, in dem Ordner, der im linken Bereich ausgewählt ist.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie eingerichtet haben, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verwenden **allgemeine Entwicklungseinstellungen**. Wenn Sie eine andere Entwicklungseinstellung verwenden, werden einige [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Fenster, die Sie in dieser exemplarischen Vorgehensweise verwenden, nicht standardmäßig angezeigt.  
  
### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>So erstellen Sie eine MFC-Anwendung mit dem MFC-Anwendungs-Assistenten  
  
1.  Verwenden der **MFC-Anwendung-Assistent** zum Erstellen einer neuen MFC-Anwendung. Zum Ausführen des Assistenten aus dem **Datei** Menü die Option **neu**, und wählen Sie dann **Projekt**. Die **neues Projekt** Dialogfeld wird angezeigt.  
  
2.  In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten in der **-Projekttypen** und wählen **MFC**. Klicken Sie auf die **Vorlagen** klicken Sie im Bereich **MFC-Anwendung**. Geben Sie einen Namen für das Projekt ein, z. B. `MFCShellControls` , und klicken Sie auf **OK**. Die **MFC-Anwendung-Assistent** wird angezeigt.  
  
3.  In der **MFC-Anwendung-Assistent** (Dialogfeld), klicken Sie auf **Weiter**. Die **Anwendungstyp** Bereich angezeigt.  
  
4.  Auf der **Anwendungstyp** Bereich unter **Anwendungstyp**Deaktivieren der **Dokumente im Registerformat** Option. Wählen Sie als Nächstes **einzelnes Dokument** , und wählen Sie **Unterstützung der Dokument-/Ansichtarchitektur-Architektur**. Unter **Projekt Stil**Option **Visual Studio**, und von der **visueller Stil und Farben** Dropdown-Liste auf **Office 2007 (blaues Design)**. Lassen Sie alle anderen Optionen unverändert. Klicken Sie auf **Weiter** zum Anzeigen der **Verbunddokumente** Bereich.  
  
5.  Auf der **Verbunddokumente** klicken Sie im Bereich **keine**. Klicken Sie auf **Weiter** zum Anzeigen der **Zeichenfolgen für Dokumentvorlagen** Bereich.  
  
6.  Nehmen Sie keine Änderungen an der **Zeichenfolgen für Dokumentvorlagen** Bereich. Klicken Sie auf **Weiter** zum Anzeigen der **Datenbankunterstützung** Bereich.  
  
7.  Auf der **Datenbankunterstützung** klicken Sie im Bereich **keine** da diese Anwendung keine Datenbank verwendet werden. Klicken Sie auf **Weiter** zum Anzeigen der **Benutzeroberflächenfunktionen** Bereich.  
  
8.  Auf der **Benutzeroberflächenfunktionen** Bereich, stellen Sie sicher, dass die **Menü- und Symbolleiste verwenden** ausgewählt ist. Lassen Sie alle anderen Optionen unverändert. Klicken Sie auf **Weiter** zum Anzeigen der **erweiterte Funktionen** Bereich.  
  
9. Auf der **erweiterte Funktionen** Bereich unter **erweiterte Funktionen**, wählen Sie nur **ActiveX-Steuerelemente** und **Allgemeines Steuerelementmanifest**. Klicken Sie unter **erweiterte Framebereiche**, wählen Sie nur die **Navigationsbereich** Option. Dies bewirkt, dass der Assistent den Bereich auf der linken Seite des Fensters mit bereits eingebetteten `CMFCShellTreeCtrl` erstellt. Klicken Sie auf **Weiter** zum Anzeigen der **generierte Klassen** Bereich.  
  
10. Wir werden keine Änderungen an der **generierte Klassen** Bereich. Klicken Sie daher auf **Fertig stellen** zu ein neue MFC-Projekt zu erstellen.  
  
11. Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Beim Erstellen der Anwendung aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung dazu **Debuggen** aus der **Debuggen** Menü.  
  
     Der Assistent erstellt automatisch eine Anwendung, die eine Standardmenüleiste, eine Standardsymbolleiste, eine Standardstatusleiste und eine Outlook-Leiste auf der linken Seite des Fensters mit hat eine **Ordner** anzeigen und eine **Kalender** anzeigen .  
  
### <a name="to-add-the-shell-list-control-to-the-document-view"></a>So fügen Sie das Shell-Listensteuerelement der Dokumentenansicht hin  
  
1.  In diesem Abschnitt fügen Sie der Ansicht eine vom Assistenten erstellte Instanz von `CMFCShellListCtrl` hinzu. Öffnen Sie die ansichtsheaderdatei durch Doppelklicken auf MFCShellControlsView.h im die **Projektmappen-Explorer**.  
  
     Suchen Sie die `#pragma once`-Direktive am oberen Rand der Headerdatei. Fügen Sie direkt darunter den folgenden Code hinzu, mit dem die Headerdatei für `CMFCShellListCtrl` eingeschlossen wird:  
  
 ```  
    #include <afxShellListCtrl.h>  
 ```  
  
     Fügen Sie nun eine Membervariable des Typs `CMFCShellListCtrl` hinzu. Suchen Sie zunächst den folgenden Kommentar in der Headerdatei:  
  
 "" * / / Generiert Message Map-Funktionen  
 ```  
  
     Immediately above that comment add this code:  
  
 ```  
    Private: CMFCShellListCtrl M_wndList;  
 ```  
  
2.  The **MFC Application Wizard** already created a `CMFCShellTreeCtrl` object in the `CMainFrame` class, but it is a protected member. We will access this object later. Therefore, create an accessor for it now. Open the MainFrm.h header file by double-clicking it in the **Solution Explorer**. Locate the following comment:  
  
 ``` *// Attributes  
 ```  
  
     Fügen Sie direkt darunter die folgende Methodendeklaration hinzu:  
  
 ```  
    public: 
    CMFCShellTreeCtrl& GetShellTreeCtrl();

 ```  
  
     Als Nächstes öffnen Sie die Datei "MainFrm.cpp" durch Doppelklick im die **Projektmappen-Explorer**. Fügen Sie am unteren Rand dieser Datei die folgende Methodendefinition hinzu:  
  
 ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
 {  
    return m_wndTree;  
 }  
 ```  
  
3.  Jetzt wir aktualisieren die `CMFCShellControlsView` Klasse zum Behandeln der **WM_CREATE** Windows-Meldung. Öffnen Sie die Headerdatei MFCShellControlsView.h, und klicken Sie auf diese Codezeile:  
  
 ```  
    class CMFCShellControlsView : public CView  
 ```  
  
     Im nächsten Schritt in der **Eigenschaften** Fenster, klicken Sie auf die **Nachrichten** Symbol. Führen Sie einen Bildlauf nach unten aus, bis Sie gefunden der **WM_CREATE** Nachricht. In der Dropdownliste neben **WM_CREATE**Option  **\<hinzufügen > OnCreate**. Damit wird ein Meldungshandler erstellt, und die MFC-Meldungszuordnung wird automatisch aktualisiert.  
  
     In der `OnCreate`-Methode erstellen Sie jetzt das `CMFCShellListCtrl`-Objekt. Suchen Sie die `OnCreate`-Methodendefinition in der Quelldatei MFCShellControlsView.cpp, und ersetzen Sie die entsprechende Implementierung durch folgenden Code:  
  
 ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
 {  
    if (CView::OnCreate(lpCreateStruct) == -1)  
    return -1;  
 
    CRect rectDummy (0,
    0,
    0,
    0);

    m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,  
    rectDummy,
    this,
    1);

 
    return 0;  
 }  
 ```  
  
4.  Wiederholen Sie den vorherigen Schritt, aber für die **WM_SIZE** Nachricht. Dadurch wird die Anwendungsansicht neu gezeichnet, wenn ein Benutzer die Größe des Anwendungsfensters ändert. Ersetzen Sie die Definition für die `OnSize`-Methode durch den folgenden Code:  
  
 ```  
    void CMFCShellControlsView::OnSize(UINT nType,
    int cx,
    int cy)  
 {  
    CView::OnSize(nType,
    cx,
    cy);

    m_wndList.SetWindowPos(NULL, -1, -1,
    cx,
    cy,  
    SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);

 }  
 ```  
  
5.  Im letzten Schritt wird die Verbindung der `CMFCShellTreeCtrl` und `CMFCShellListCtrl` Objekte mithilfe der [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) Methode. Nachdem Sie diese Methode aufgerufen haben, zeigt `CMFCShellListCtrl` automatisch den Inhalt des Elements an, das in `CMFCShellTreeCtrl` ausgewählt ist. Es führt dies der `OnActivateView` -Methode, die von außer Kraft gesetzt wird [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).  
  
     Fügen Sie in der Headerdatei MFCShellControlsView.h innerhalb der `CMFCShellControlsView`-Klassendeklaration die folgende Methodendeklaration hinzu:  
  
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
  
 ```  
    #include "MainFrm.h"  
 ```  
  
6.  Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Beim Erstellen der Anwendung aus der **erstellen** Menü die Option **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie es dazu **Debuggen** aus der **Debuggen** Menü.  
  
     Sie sollten nun die Details zum Element sehen, die im Ansichtsbereich `CMFCShellTreeCtrl` ausgewählt sind. Wenn Sie auf einen Knoten in `CMFCShellTreeCtrl` klicken, wird `CMFCShellListCtrl` automatisch aktualisiert. Wenn Sie auf einen Ordner in `CMFCShellListCtrl` doppelklicken, sollte `CMFCShellTreeCtrl` automatisch aktualisiert werden.  
  
     Klicken Sie mit der rechten Maustaste auf ein beliebiges Element in der Strukturansicht oder im Listensteuerelement. Beachten Sie, dass Sie das gleiche Kontextmenü wie im richtigen Datei-Explorer abrufen.  
  
## <a name="next-steps"></a>Nächste Schritte  
  
-   Der Assistent erstellt eine Outlook-Leiste mit einem **Ordner** Bereich und ein **Kalender** Bereich. Es wahrscheinlich ist nicht sinnvoll, eine **Kalender** Bereich in einem Explorer-Fenster. Daher entfernen Sie diesen Bereich jetzt.  
  
-   Die `CMFCShellListCtrl` unterstützt die Anzeige von Dateien in verschiedenen Modi, z. B. **große Symbole**, **kleine Symbole**, **Liste**, und **Details**. Aktualisieren Sie die Anwendung, um diese Funktionalität zu implementieren. Hinweis: Siehe [Visual C++-Beispiele](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)

