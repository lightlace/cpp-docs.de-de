---
title: 'MFC-ActiveX-Steuerelemente: Einer Fenstersteuerelement | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs: C++
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5532a5ea76bbdde619829548c01c2d057f3cbc28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC-ActiveX-Steuerelemente: Erstellen einer Fenstersteuerelement-Unterklasse
Dieser Artikel beschreibt den Prozess für eine allgemeine Fenstersteuerelement um ein ActiveX-Steuerelement zu erstellen. Erstellen von Unterklassen für eine vorhandene Windows ist Steuerelement eine schnelle Möglichkeit, ein ActiveX-Steuerelement entwickeln. Das neue Steuerelement haben die Möglichkeit des untergeordnetes Windows-Steuerelements, wie z. B. Zeichnen und Mausklicks reagiert. Die MFC-ActiveX-Steuerelemente Beispiel [Schaltfläche](../visual-cpp-samples.md) ist ein Beispiel einer Fenstersteuerelement.  
  
 Unterklasse eines Windows-Steuerelements führen Sie die folgenden Aufgaben aus:  
  
-   [Überschreiben Sie die Memberfunktionen IsSubclassedControl und PreCreateWindow COleControl](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [Ändern Sie die OnDraw Member-Funktion](#_core_modifying_the_ondraw_member_function)  
  
-   [Behandeln Sie alle ActiveX-Steuerelement-Nachrichten (OCM) reflektiert, um das Steuerelement](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  Großteil der Arbeit für Sie ausgeführt vom ActiveX-Steuerelement-Assistenten bei Auswahl des Steuerelements, das als Unterklasse werden mithilfe der **wählen übergeordnete Fensterklasse** Dropdown-Liste auf die **Steuerelementeinstellungen** Seite.  
  
 Finden Sie für das Erstellen von Unterklassen für ein Steuerelement in der Knowledge Base-Artikel Q243454 für Weitere Informationen.  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>Überschreiben von IsSubclassedControl und PreCreateWindow  
 Überschreiben `PreCreateWindow` und `IsSubclassedControl`, fügen Sie die folgenden Codezeilen die `protected` Teil der Deklaration der Steuerelement-Klasse:  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 In der Implementierungsdatei des Steuerelements (. CPP), fügen Sie die folgenden Codezeilen die zwei überschriebenen Funktionen implementiert:  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 Beachten Sie, dass in diesem Beispiel wird die Windows Steuerelement Schaltfläche wird angegeben, `PreCreateWindow`. Allerdings können Windows-Standardsteuerelemente Unterklassen erstellt werden. Weitere Informationen zu Windows-Standardsteuerelemente, finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).  
  
 Beim Erstellen von Unterklassen für ein Windows-Steuerelement, möchten Sie möglicherweise bestimmte Fensterstil angeben (**WS_**) oder eine erweiterte Fensterstil (**WS_EX_**) Flags an, erstellen das Fenster des Steuerelements verwendet werden. Einstellbaren Werte für diese Parameter in der `PreCreateWindow` Memberfunktion durch Ändern der **cs.style** und **cs.dwExStyle** Struktur Felder. Dieser Felder sollten Änderungen mit einer `OR` Vorgang, um die Standardflags beizubehalten, die von der Klasse festgelegt werden `COleControl`. Z. B., wenn das Steuerelement erstellen von für das Schaltflächen-Steuerelement Unterklassen ist, und das Steuerelement als Kontrollkästchen angezeigt werden sollen, legen Sie die folgende Codezeile in der Implementierung der `CSampleCtrl::PreCreateWindow`, bevor Sie die return-Anweisung:  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 Dieser Vorgang fügt die **BS_CHECKBOX** formatflag, lassen Sie das standardmäßige Format-Flag (**WS_CHILD**) der Klasse `COleControl` intakt.  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a>Ändern die OnDraw Member-Funktion  
 Gegebenenfalls ein untergeordnete Steuerelement behalten Sie die gleiche Darstellung als das entsprechende Windows-Steuerelement die `OnDraw` Memberfunktion für das Steuerelement dürfen nur einen Aufruf der `DoSuperclassPaint` Memberfunktion ist, wie im folgenden Beispiel:  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 Die `DoSuperclassPaint` Memberfunktion von implementiert `COleControl`, die Fensterprozedur des Windows-Steuerelements verwendet, um das Steuerelement in den angegebenen Gerätekontext, innerhalb des umschließenden Rechtecks zeichnen. Dadurch wird das Steuerelement sichtbar, selbst wenn er nicht aktiv ist.  
  
> [!NOTE]
>  Die `DoSuperclassPaint` Memberfunktion funktionieren nur mit Steuerelementtypen, die ermöglichen, einen Gerätekontext als übergeben werden die **wParam** von einer `WM_PAINT` Nachricht. Dies enthält einige der standardmäßigen Windows-Steuerelemente, z. B. **BILDLAUFLEISTE** und **Schaltfläche**, und die Standardsteuerelemente. Sie müssen für Steuerelemente, die dieses Verhalten nicht unterstützen, geben Sie Ihren eigenen Code aus, um ein Inaktives Steuerelement ordnungsgemäß angezeigt.  
  
##  <a name="_core_handling_reflected_window_messages"></a>Behandeln von reflektierten Fenstermeldungen im  
 Windows-Steuerelemente in der Regel Nachrichten bestimmte Fenster an ihre übergeordnete Fenster. Einige dieser Meldungen, z. B. **WM_COMMAND**, geben Sie die Benachrichtigung über eine Aktion vom Benutzer. Andere, z. B. `WM_CTLCOLOR`, dienen zum Abrufen von Informationen über das übergeordnete Fenster. Ein ActiveX-Steuerelement kommuniziert mit anderen Mitteln in der Regel mit dem übergeordneten Fenster. Benachrichtigungen werden durch das Auslösen von Ereignissen (ereignisbenachrichtigungen senden) übermittelt, und Informationen zu dem Steuerelementcontainer durch Zugreifen auf Umgebungseigenschaften für den Container abgerufen wird. Da diese Kommunikation Techniken vorhanden sind, sind ActiveX-Steuerelementcontainer fenstermeldungen gesendet, die vom Steuerelement verarbeitet nicht erwartet.  
  
 Um zu verhindern, dass den Container den Nachrichtenempfang Fenster gesendet werden, indem Sie ein untergeordnetes Steuerelement von Windows `COleControl` erstellt eine zusätzliche Fenster, die als übergeordnete Element des Steuerelements dient. Diese zusätzliche Fenster, mit der Bezeichnung "Reflector" wird nur für ein ActiveX-Steuerelement erstellt, dass Unterklassen eines Windows steuern und dies die gleiche Größe und Position im Fenster Steuerelements hat. Das Fenster Reflector fängt bestimmte Windows-Meldungen ab und sendet sie zurück an das Steuerelement. Steuerelements in dessen Fensterprozedur auf, können Sie diese reflektierten Meldungen verarbeiten, durch die Aktionen, die für ein ActiveX-Steuerelement (z. B. das Auslösen eines Ereignisses) geeignet. Finden Sie unter [Fenstermeldungs-IDs reflektiert](../mfc/reflected-window-message-ids.md) eine Liste von abgefangenen Windows Nachrichten und ihre entsprechenden reflektierten Meldungen.  
  
 Ein ActiveX-Steuerelementcontainer auszuführenden Meldungsreflektion selbst, wodurch die Notwendigkeit entfällt entworfen werden möglicherweise `COleControl` Fenster Reflector und verringern die Laufzeit-overhead für ein untergeordnetes Steuerelement in Windows zu erstellen. `COleControl`erkennt, ob der Container diese Funktion unterstützt, mit der Überprüfung einer MessageReflect ambient-Eigenschaft mit einem Wert von **"true"**.  
  
 Um eine reflektierte Meldung Verarbeiten der Nachricht steuerelementzuordnung einen Eintrag hinzu, und implementieren Sie eine Handlerfunktion. Da reflektierte Meldungen, die nicht Teil der Standardsatz von Nachrichten, die von Windows definiert sind, unterstützt Klassenansicht keine solche Meldungshandler hinzufügen. Allerdings ist es nicht schwer, einen Handler manuell hinzufügen.  
  
 Zum Hinzufügen ein meldungshandlers für eine reflektierte Meldung manuell folgendermaßen vor:  
  
-   In der Control-Klasse. H-Datei, eine Ereignishandlerfunktion deklarieren. Die Funktion müssen Rückgabetyp **LRESULT** und zwei Parameter, mit Typen **WPARAM** und **LPARAM**zugeordnet. Zum Beispiel:  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   In der Control-Klasse. CPP-Datei, fügen Sie eine `ON_MESSAGE` Eintrag in der meldungszuordnung. Die Parameter dieses Eintrags sollte die Nachrichten-ID und den Namen der Handlerfunktion sein. Zum Beispiel:  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   Auch in der. CPP-Datei, implementieren die **OnOcmCommand** Memberfunktion reflektierte Meldung verarbeiten. Die **wParam** und **lParam** Parameter sind identisch mit denen der ursprünglichen Fensternachricht.  
  
 Für ein Beispiel dafür, wie Nachrichten verarbeitet werden reflektiert, finden Sie in dem Beispiel für die MFC-ActiveX-Steuerelemente [Schaltfläche](../visual-cpp-samples.md). Es zeigt eine **OnOcmCommand** Handler, der erkennt die **BN_CLICKED** Benachrichtigungscode und reagiert, ausgelöst Click-Ereignis (senden).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

