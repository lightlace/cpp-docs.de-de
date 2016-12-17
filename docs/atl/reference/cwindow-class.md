---
title: "CWindow Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWindow"
  - "ATL::CWindow"
  - "CWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindow class"
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Bearbeiten eines Fensters.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CWindow  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindow::CWindow](../Topic/CWindow::CWindow.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindow::ArrangeIconicWindows](../Topic/CWindow::ArrangeIconicWindows.md)|Ordnet alle minimierten untergeordneten Fenster an.|  
|[CWindow::Attach](../Topic/CWindow::Attach.md)|Fügt ein Fenster mit dem `CWindow`\-Objekt.|  
|[CWindow::BeginPaint](../Topic/CWindow::BeginPaint.md)|Bereitet das Fenster zum Zeichnen vor.|  
|[CWindow::BringWindowToTop](../Topic/CWindow::BringWindowToTop.md)|Setzt das Fenster zum Anfang der z\-Ordnung.|  
|[CWindow::CenterWindow](../Topic/CWindow::CenterWindow.md)|Zentriert das Fenster mit einem angegebenen Fenster.|  
|[CWindow::ChangeClipboardChain](../Topic/CWindow::ChangeClipboardChain.md)|Entfernt das Fenster in der Kette von Zwischenablagen\-Viewern.|  
|[CWindow::CheckDlgButton](../Topic/CWindow::CheckDlgButton.md)|Ändert den Aktivierungszustand der angegebenen Schaltfläche.|  
|[CWindow::CheckRadioButton](../Topic/CWindow::CheckRadioButton.md)|Überprüft das angegebene Optionsfeld.|  
|[CWindow::ChildWindowFromPoint](../Topic/CWindow::ChildWindowFromPoint.md)|Ruft das untergeordnete Fenster ab, das den angegebenen Punkt enthält.|  
|[CWindow::ChildWindowFromPointEx](../Topic/CWindow::ChildWindowFromPointEx.md)|Ruft einen bestimmten Typ untergeordnetes Fenster den angegebenen Punkt enthalten.|  
|[CWindow::ClientToScreen](../Topic/CWindow::ClientToScreen.md)|Konvertiert Clientkoordinaten zu Bildschirmkoordinaten.|  
|[CWindow::Create](../Topic/CWindow::Create.md)|Stellt ein Fenster erstellt.|  
|[CWindow::CreateCaret](../Topic/CWindow::CreateCaret.md)|Erstellt eine neue Form für das Caretzeichen.|  
|[CWindow::CreateGrayCaret](../Topic/CWindow::CreateGrayCaret.md)|Erstellt ein graues Rechteck für das Caretzeichen.|  
|[CWindow::CreateSolidCaret](../Topic/CWindow::CreateSolidCaret.md)|Erstellt ein ausgefülltes Rechteck für das Caretzeichen.|  
|[CWindow::DeferWindowPos](../Topic/CWindow::DeferWindowPos.md)|Aktualisiert die angegebene Mehrfachverbindungsstelle\-FensterPosition Struktur für das angegebene Fenster.|  
|[CWindow::DestroyWindow](../Topic/CWindow::DestroyWindow.md)|Zerstört das Fenster, das mit dem `CWindow`\-Objekt zugeordnet ist.|  
|[CWindow::Detach](../Topic/CWindow::Detach.md)|Trennt das Fenster im `CWindow`\-Objekt.|  
|[CWindow::DlgDirList](../Topic/CWindow::DlgDirList.md)|Füllt ein Listenfeld mit den Namen aller Dateien aus, die einen angegebenen Pfad oder einen Dateinamen übereinstimmen.|  
|[CWindow::DlgDirListComboBox](../Topic/CWindow::DlgDirListComboBox.md)|Füllt ein Kombinationsfeld mit den Namen aller Dateien aus, die einen angegebenen Pfad oder einen Dateinamen übereinstimmen.|  
|[CWindow::DlgDirSelect](../Topic/CWindow::DlgDirSelect.md)|Ruft die aktuelle Auswahl von einem Listenfeld ab.|  
|[CWindow::DlgDirSelectComboBox](../Topic/CWindow::DlgDirSelectComboBox.md)|Ruft die aktuelle Auswahl in einem Kombinationsfeld ab.|  
|[CWindow::DragAcceptFiles](../Topic/CWindow::DragAcceptFiles.md)|Registriert, dass das Fenster gezogene Dateien akzeptiert.|  
|[CWindow::DrawMenuBar](../Topic/CWindow::DrawMenuBar.md)|Aktualisiert die Menüleiste des Fensters neu.|  
|[CWindow::EnableScrollBar](../Topic/CWindow::EnableScrollBar.md)|Aktiviert oder deaktiviert die Pfeile der Bildlaufleiste.|  
|[CWindow::EnableWindow](../Topic/CWindow::EnableWindow.md)|Aktiviert oder deaktiviert Eingabe.|  
|[CWindow::EndPaint](../Topic/CWindow::EndPaint.md)|Markiert das Ende des Zeichnens.|  
|[CWindow::FlashWindow](../Topic/CWindow::FlashWindow.md)|Blinkt das Fenster erneut.|  
|[CWindow::GetClientRect](../Topic/CWindow::GetClientRect.md)|Ruft die Koordinaten des Clientbereichs ab.|  
|[CWindow::GetDC](../Topic/CWindow::GetDC.md)|Ruft einen Gerätekontext für den Clientbereich ab.|  
|[CWindow::GetDCEx](../Topic/CWindow::GetDCEx.md)|Ruft einen Gerätekontext für den Clientbereich ab und ermöglicht Clippingoptionen.|  
|[CWindow::GetDescendantWindow](../Topic/CWindow::GetDescendantWindow.md)|Ruft das angegebene untergeordnete Fenster ab.|  
|[CWindow::GetDlgControl](../Topic/CWindow::GetDlgControl.md)|Ruft eine Schnittstelle für das angegebene Steuerelement ab.|  
|[CWindow::GetDlgCtrlID](../Topic/CWindow::GetDlgCtrlID.md)|Ruft den Bezeichner des Fensters ab \(nur für untergeordnete Fenster\).|  
|[CWindow::GetDlgHost](../Topic/CWindow::GetDlgHost.md)|Ruft einen Zeiger auf eine Schnittstelle zum ATL\-Steuerhostingcontainer ab.|  
|[CWindow::GetDlgItem](../Topic/CWindow::GetDlgItem.md)|Ruft das angegebene untergeordnete Fenster ab.|  
|[CWindow::GetDlgItemInt](../Topic/CWindow::GetDlgItemInt.md)|Übersetzt den Text eines Steuerelements in eine ganze Zahl.|  
|[CWindow::GetDlgItemText](../Topic/CWindow::GetDlgItemText.md)|Ruft den Text eines Steuerelements ab.|  
|[CWindow::GetExStyle](../Topic/CWindow::GetExStyle.md)|Ruft die erweiterten Fensterstile ab.|  
|[CWindow::GetFont](../Topic/CWindow::GetFont.md)|Ruft die aktuelle Schriftart des Fensters ab.|  
|[CWindow::GetHotKey](../Topic/CWindow::GetHotKey.md)|Bestimmt die Zugriffstaste, die mit dem Fenster zugeordnet ist.|  
|[CWindow::GetIcon](../Topic/CWindow::GetIcon.md)|Ruft das große oder kleine Symbol des Fensters ab.|  
|[CWindow::GetLastActivePopup](../Topic/CWindow::GetLastActivePopup.md)|Ruft das zuletzt aktive Popupfenster ab.|  
|[CWindow::GetMenu](../Topic/CWindow::GetMenu.md)|Ruft das Menü des Fensters ab.|  
|[CWindow::GetNextDlgGroupItem](../Topic/CWindow::GetNextDlgGroupItem.md)|Ruft das vorherige oder nächste Steuerelement innerhalb einer Gruppe Steuerelemente ab.|  
|[CWindow::GetNextDlgTabItem](../Topic/CWindow::GetNextDlgTabItem.md)|Ruft das vorherige oder nächste Steuerelement ab, das das **WS\_TABSTOP**\-Format hat.|  
|[CWindow::GetParent](../Topic/CWindow::GetParent.md)|Ruft das unmittelbar übergeordnete Fenster ab.|  
|[CWindow::GetScrollInfo](../Topic/CWindow::GetScrollInfo.md)|Ruft die Parameter einer Bildlaufleiste ab.|  
|[CWindow::GetScrollPos](../Topic/CWindow::GetScrollPos.md)|Ruft die Position des Bildlauffelds ab.|  
|[CWindow::GetScrollRange](../Topic/CWindow::GetScrollRange.md)|Ruft den Bildlaufleistenbereich ab.|  
|[CWindow::GetStyle](../Topic/CWindow::GetStyle.md)|Ruft die Fensterstile ab.|  
|[CWindow::GetSystemMenu](../Topic/CWindow::GetSystemMenu.md)|Erstellt eine Kopie des Systemmenüs für Änderung.|  
|[CWindow::GetTopLevelParent](../Topic/CWindow::GetTopLevelParent.md)|Ruft das übergeordnete Element oder das Besitzerfenster der obersten Ebene ab.|  
|[CWindow::GetTopLevelWindow](../Topic/CWindow::GetTopLevelWindow.md)|Ruft das Besitzerfenster der obersten Ebene ab.|  
|[CWindow::GetTopWindow](../Topic/CWindow::GetTopWindow.md)|Ruft das untergeordnete Fenster der obersten Ebene ab.|  
|[CWindow::GetUpdateRect](../Topic/CWindow::GetUpdateRect.md)|Ruft die Koordinaten des kleinsten Rechtecks ab, das vollständig das UpdatePanel einschließt.|  
|[CWindow::GetUpdateRgn](../Topic/CWindow::GetUpdateRgn.md)|Ruft den UpdatePanel ab und kopiert sie in einen angegebenen Bereich.|  
|[CWindow::GetWindow](../Topic/CWindow::GetWindow.md)|Ruft das angegebene Fenster ab.|  
|[CWindow::GetWindowContextHelpId](../Topic/CWindow::GetWindowContextHelpId.md)|Ruft den Hilfekontextbezeichner des Fensters ab.|  
|[CWindow::GetWindowDC](../Topic/CWindow::GetWindowDC.md)|Ruft einen Gerätekontext für das gesamte Fenster ab.|  
|[CWindow::GetWindowLong](../Topic/CWindow::GetWindowLong.md)|Ruft einen 32\-Bit\-Wert an einem angegebenen Offset in zusätzlichen Fensterarbeitsspeicher ab.|  
|[CWindow::GetWindowLongPtr](../Topic/CWindow::GetWindowLongPtr.md)|Ruft Informationen über das angegebene Fenster, einschließlich einen Wert an einem angegebenen Offset in zusätzlichen Fensterarbeitsspeicher ab.|  
|[CWindow::GetWindowPlacement](../Topic/CWindow::GetWindowPlacement.md)|Ruft den Ansichtszustand und Positionen ab.|  
|[CWindow::GetWindowProcessID](../Topic/CWindow::GetWindowProcessID.md)|Ruft den Bezeichner des Prozesses ab, der das Fenster erstellt wurde.|  
|[CWindow::GetWindowRect](../Topic/CWindow::GetWindowRect.md)|Ruft die springenden Dimensionen des Fensters ab.|  
|[CWindow::GetWindowRgn](../Topic/CWindow::GetWindowRgn.md)|Ruft eine Kopie des Fensterbereichs eines Fensters.|  
|[CWindow::GetWindowText](../Topic/CWindow::GetWindowText.md)|Ruft den Text des Fensters ab.|  
|[CWindow::GetWindowTextLength](../Topic/CWindow::GetWindowTextLength.md)|Ruft die Länge des Texts des Fensters ab.|  
|[CWindow::GetWindowThreadID](../Topic/CWindow::GetWindowThreadID.md)|Ruft den Bezeichner des Threads ab, der das angegebene Fenster erstellt wurde.|  
|[CWindow::GetWindowWord](../Topic/CWindow::GetWindowWord.md)|Ruft einen 16\-Bit\-Wert in einem angegebenen Offset in zusätzlichen Fensterarbeitsspeicher ab.|  
|[CWindow::GotoDlgCtrl](../Topic/CWindow::GotoDlgCtrl.md)|Legt den Tastaturfokus zu einem Steuerelement im Dialogfeld fest.|  
|[CWindow::HideCaret](../Topic/CWindow::HideCaret.md)|Blendet das Caretzeichen aus.|  
|[CWindow::HiliteMenuItem](../Topic/CWindow::HiliteMenuItem.md)|Hervorhebungen oder entfernt die Hervorhebung von einem Menüelement der obersten Ebene.|  
|[CWindow::Invalidate](../Topic/CWindow::Invalidate.md)|Löscht den gesamten Clientbereich ungültig.|  
|[CWindow::InvalidateRect](../Topic/CWindow::InvalidateRect.md)|Löscht den Clientbereich innerhalb des angegebenen Rechtecks ungültig.|  
|[CWindow::InvalidateRgn](../Topic/CWindow::InvalidateRgn.md)|Löscht den Clientbereich innerhalb des angegebenen Bereichs ungültig.|  
|[CWindow::IsChild](../Topic/CWindow::IsChild.md)|Bestimmt, ob das angegebene Fenster ein untergeordnetes Fenster ist.|  
|[CWindow::IsDialogMessage](../Topic/CWindow::IsDialogMessage.md)|Bestimmt, ob eine Meldung für das angegebene Dialogfeld vorgesehen.|  
|[CWindow::IsDlgButtonChecked](../Topic/CWindow::IsDlgButtonChecked.md)|Bestimmt den Aktivierungszustand der Schaltfläche.|  
|[CWindow::IsIconic](../Topic/CWindow::IsIconic.md)|Bestimmt, ob das Fenster minimiert wird.|  
|[CWindow::IsParentDialog](../Topic/CWindow::IsParentDialog.md)|Bestimmt, ob das übergeordnete Fenster eines Steuerelements ein Dialogfeld ist.|  
|[CWindow::IsWindow](../Topic/CWindow::IsWindow.md)|Bestimmt, ob das angegebene Fensterhandle ein vorhandenes Fenster identifiziert.|  
|[CWindow::IsWindowEnabled](../Topic/CWindow::IsWindowEnabled.md)|Bestimmt, ob das Fenster für Eingabe aktiviert ist.|  
|[CWindow::IsWindowUnicode](../Topic/CWindow::IsWindowUnicode.md)|Bestimmt, ob das angegebene Fenster ein systemeigenes Unicode\-Fenster ist.|  
|[CWindow::IsWindowVisible](../Topic/CWindow::IsWindowVisible.md)|Bestimmt den Sichtbarkeitszustand des Fensters.|  
|[CWindow::IsZoomed](../Topic/CWindow::IsZoomed.md)|Bestimmt, ob das Fenster maximiert wird.|  
|[CWindow::KillTimer](../Topic/CWindow::KillTimer.md)|Zerstört ein Zeitgeberereignis.|  
|[CWindow::LockWindowUpdate](../Topic/CWindow::LockWindowUpdate.md)|Deaktiviert oder aktiviert Zeichnung im Fenster.|  
|[CWindow::MapWindowPoints](../Topic/CWindow::MapWindowPoints.md)|Konvertiert einen von Punkten im Koordinatenraum des Fensters zum Koordinatenraum eines anderen Fensters.|  
|[CWindow::MessageBox](../Topic/CWindow::MessageBox.md)|Zeigt ein Meldungsfeld an.|  
|[CWindow::ModifyStyle](../Topic/CWindow::ModifyStyle.md)|Ändert die Fensterstile.|  
|[CWindow::ModifyStyleEx](../Topic/CWindow::ModifyStyleEx.md)|Ändert die erweiterten Fensterstile.|  
|[CWindow::MoveWindow](../Topic/CWindow::MoveWindow.md)|Ändert die Größe des Fensters und Position.|  
|[CWindow::NextDlgCtrl](../Topic/CWindow::NextDlgCtrl.md)|Legt den Tastaturfokus zum nächsten Steuerelement im Dialogfeld fest.|  
|[CWindow::OpenClipboard](../Topic/CWindow::OpenClipboard.md)|Öffnet die Zwischenablage.|  
|[CWindow::PostMessage](../Topic/CWindow::PostMessage.md)|Setzt eine Meldung in der Meldungswarteschlange, die mit dem Thread zugeordnet ist, der das Fenster erstellt wurde.  EINGABETASTE, ohne auf den Thread zu warten, bis die Nachricht zu verarbeiten.|  
|[CWindow::PrevDlgCtrl](../Topic/CWindow::PrevDlgCtrl.md)|Legt den Tastaturfokus zum vorherigen Steuerelement im Dialogfeld fest.|  
|[CWindow::Print](../Topic/CWindow::Print.md)|Die diese Anforderungen das Fenster werden in einem angegebenen Gerätekontext gezeichnet.|  
|[CWindow::PrintClient](../Topic/CWindow::PrintClient.md)|Die diese Anforderungen der Clientbereich des Fensters werden in einem angegebenen Gerätekontext gezeichnet.|  
|[CWindow::RedrawWindow](../Topic/CWindow::RedrawWindow.md)|Aktualisiert ein bestimmtes Rechteck oder einen Bereich im Clientbereich.|  
|[CWindow::ReleaseDC](../Topic/CWindow::ReleaseDC.md)|Gibt einen Gerätekontext frei.|  
|[CWindow::ResizeClient](../Topic/CWindow::ResizeClient.md)|Ändert die Größe des Fensters.|  
|[CWindow::ScreenToClient](../Topic/CWindow::ScreenToClient.md)|Konvertiert Bildschirmkoordinaten in Clientkoordinaten.|  
|[CWindow::ScrollWindow](../Topic/CWindow::ScrollWindow.md)|Führt den angegebenen Clientbereich aus.|  
|[CWindow::ScrollWindowEx](../Topic/CWindow::ScrollWindowEx.md)|Führt den angegebenen Clientbereich mit zusätzlichen Funktionen aus.|  
|[CWindow::SendDlgItemMessage](../Topic/CWindow::SendDlgItemMessage.md)|Sendet eine Nachricht an ein Steuerelement.|  
|[CWindow::SendMessage](../Topic/CWindow::SendMessage.md)|Sendet eine Meldung in die Fenster und wird erst zurückgegeben, wenn die Fensterprozedur die Meldung verarbeitet hat.|  
|[CWindow::SendMessageToDescendants](../Topic/CWindow::SendMessageToDescendants.md)|Sendet eine Nachricht an den angegebenen Nachfolgerelemente Fenstern.|  
|[CWindow::SendNotifyMessage](../Topic/CWindow::SendNotifyMessage.md)|Sendet eine Meldung in das Fenster.  Wenn das Fenster durch den aufrufenden Thread erstellt wurde, gibt `SendNotifyMessage` nicht zurück, bis die Fensterprozedur die Meldung verarbeitet hat.  Andernfalls wird sie sofort zurück.|  
|[CWindow::SetActiveWindow](../Topic/CWindow::SetActiveWindow.md)|Ermöglicht das Fenster.|  
|[CWindow::SetCapture](../Topic/CWindow::SetCapture.md)|Sendet alle folgenden Maus, die an das Fenster eingegeben wird.|  
|[CWindow::SetClipboardViewer](../Topic/CWindow::SetClipboardViewer.md)|Fügt das Fenster der Zwischenablagen\-Viewer\-Kette hinzu.|  
|[CWindow::SetDlgCtrlID](../Topic/CWindow::SetDlgCtrlID.md)|Ändert den Bezeichner des Fensters.|  
|[CWindow::SetDlgItemInt](../Topic/CWindow::SetDlgItemInt.md)|Ändert den Text eines Steuerelements an die Zeichenfolgendarstellung eines ganzzahligen Werts.|  
|[CWindow::SetDlgItemText](../Topic/CWindow::SetDlgItemText.md)|Ändert den Text eines Steuerelements.|  
|[CWindow::SetFocus](../Topic/CWindow::SetFocus.md)|Legt den Eingabefokus auf fest.|  
|[CWindow::SetFont](../Topic/CWindow::SetFont.md)|Ändert die aktuelle Schriftart des Fensters.|  
|[CWindow::SetHotKey](../Topic/CWindow::SetHotKey.md)|Ordnet eine Zugriffstaste mit dem Fenster zu.|  
|[CWindow::SetIcon](../Topic/CWindow::SetIcon.md)|Ändert das große oder kleine Symbol des Fensters.|  
|[CWindow::SetMenu](../Topic/CWindow::SetMenu.md)|Ändert das aktuelle Menü des Fensters.|  
|[CWindow::SetParent](../Topic/CWindow::SetParent.md)|Ändert das übergeordnete Fenster.|  
|[CWindow::SetRedraw](../Topic/CWindow::SetRedraw.md)|Setzt oder freie Räume das Aktualisierungsflag.|  
|[CWindow::SetScrollInfo](../Topic/CWindow::SetScrollInfo.md)|Legt die Parameter einer Bildlaufleiste fest.|  
|[CWindow::SetScrollPos](../Topic/CWindow::SetScrollPos.md)|Ändert die Position des Bildlauffelds.|  
|[CWindow::SetScrollRange](../Topic/CWindow::SetScrollRange.md)|Ändert den Bildlaufleistenbereich.|  
|[CWindow::SetTimer](../Topic/CWindow::SetTimer.md)|Erstellt ein Timer\-Ereignis.|  
|[CWindow::SetWindowContextHelpId](../Topic/CWindow::SetWindowContextHelpId.md)|Legt den Hilfekontextbezeichner des Fensters fest.|  
|[CWindow::SetWindowLong](../Topic/CWindow::SetWindowLong.md)|Legt einen 32\-Bit\-Wert an einem angegebenen Offset in zusätzlichen Fensterarbeitsspeicher fest.|  
|[CWindow::SetWindowLongPtr](../Topic/CWindow::SetWindowLongPtr.md)|Ändert ein Attribut des angegebenen Fensters und legt auch einen Wert am angegebenen Offset im zusätzlichen Fensterarbeitsspeicher fest.|  
|[CWindow::SetWindowPlacement](../Topic/CWindow::SetWindowPlacement.md)|Legt den Ansichtszustand und Positionen fest.|  
|[CWindow::SetWindowPos](../Topic/CWindow::SetWindowPos.md)|Legt die Größe, Position und die z\-Ordnung fest.|  
|[CWindow::SetWindowRgn](../Topic/CWindow::SetWindowRgn.md)|Legt den Fensterbereich eines Fensters fest.|  
|[CWindow::SetWindowText](../Topic/CWindow::SetWindowText.md)|Ändert den Text des Fensters.|  
|[CWindow::SetWindowWord](../Topic/CWindow::SetWindowWord.md)|Legt einen 16\-Bit\-Wert in einem angegebenen Offset in zusätzlichen Fensterarbeitsspeicher fest.|  
|[CWindow::ShowCaret](../Topic/CWindow::ShowCaret.md)|Zeigt das Caretzeichen an.|  
|[CWindow::ShowOwnedPopups](../Topic/CWindow::ShowOwnedPopups.md)|In oder aus die Popupfenster im Besitz das Fenster.|  
|[CWindow::ShowScrollBar](../Topic/CWindow::ShowScrollBar.md)|In oder aus ein Bildlaufleiste.|  
|[CWindow::ShowWindow](../Topic/CWindow::ShowWindow.md)|Legt den Anzeigezustand des Fensters fest.|  
|[CWindow::ShowWindowAsync](../Topic/CWindow::ShowWindowAsync.md)|Legt den Ansichtszustand eines Fensters fest, das von einem anderen Thread erstellt wird.|  
|[CWindow::UpdateWindow](../Topic/CWindow::UpdateWindow.md)|Aktualisiert den Clientbereich.|  
|[CWindow::ValidateRect](../Topic/CWindow::ValidateRect.md)|Überprüft den angegebenen Clientbereich innerhalb des Rechtecks.|  
|[CWindow::ValidateRgn](../Topic/CWindow::ValidateRgn.md)|Überprüft den Clientbereich innerhalb des angegebenen Bereichs.|  
|[CWindow::WinHelp](../Topic/CWindow::WinHelp.md)|Anfangs\-Windows\-Hilfe.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindow::operator HWND](../Topic/CWindow::operator%20HWND.md)|Konvertiert das `CWindow`\-Objekt zu `HWND`.|  
|[CWindow::operator \=](../Topic/CWindow::operator%20=.md)|Weist `HWND` zum `CWindow`\-Objekt zu.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindow::m\_hWnd](../Topic/CWindow::m_hWnd.md)|Das Handle für das Fenster, das dem `CWindow`\-Objekt zugeordnet ist.|  
|[CWindow::rcDefault](../Topic/CWindow::rcDefault.md)|Enthält Standard Fensterdimensionen.|  
  
## Hinweise  
 `CWindow` stellt Basisfunktionen zum Bearbeiten eines Fensters in ATL bereit.  Viele der `CWindow`\-Methoden binden einfach eine der Win32\-API\-Funktionen ein.  Beispielsweise vergleichen Sie die Prototypen für `CWindow::ShowWindow` und `ShowWindow`:  
  
|CWindow\-Methode|Win32\-Funktion|  
|----------------------|---------------------|  
|**BOOL ShowWindow\( int**  `nCmdShow` **\);**|**BOOL ShowWindow\( HWND**  `hWnd` **, int**  `nCmdShow` **\);**|  
  
 `CWindow::ShowWindow` ruft die Win32\-Funktion `ShowWindow` auf, indem sie `CWindow::m_hWnd` als erster Parameter übergeben.  Jede `CWindow`\-Methode, die direkt eine Win32\-Funktion umschließt, führt den `m_hWnd`\-Member, daher verweist viel der `CWindow` Dokumentation Sie zu [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Nicht jede fensterbezogene Win32\-Funktion wird durch `CWindow` und umschließt nicht jeder `CWindow`\-Methode eine Win32\-Funktion umschlossen.  
  
 `CWindow::m_hWnd` speichert `HWND`, das ein Fenster identifiziert.  `HWND` wird dem Objekt angefügt, wenn Sie:  
  
-   Geben Sie `HWND` im Konstruktor von `CWindow` an.  
  
-   Rufen Sie `CWindow::Attach` auf.  
  
-   Verwenden Sie **operator \=** von `CWindow`.  
  
-   Herstellen oder ordnen Sie ein Fenster mit einer der folgenden Klassen unter, die von `CWindow` abgeleitet werden:  
  
     [CWindowImpl](../../atl/reference/cwindowimpl-class.md) ermöglicht es Ihnen, ein neues Fenster zu erstellen oder ein vorhandenes Fenster unterzuordnen.  
  
     [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) implementiert ein Fenster, das innerhalb eines anderen Objekts enthalten ist.  Sie können ein neues Fenster erstellen oder ein vorhandenes Fenster unterordnen.  
  
     [CDialogImpl](../../atl/reference/cdialogimpl-class.md) ermöglicht es Ihnen, ein modales oder ein nicht modales Dialogfeld zu erstellen.  
  
 Weitere Informationen zum Fenster, finden Sie unter [Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) und folgende Themen in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Weitere Informationen zur Verwendung von Fenstern in ATL, finden Sie im Artikel [ATL\-Fensterklassen](../../atl/atl-window-classes.md).  
  
## Anforderungen  
 **Header:** atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)