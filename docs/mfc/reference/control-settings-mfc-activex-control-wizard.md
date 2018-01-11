---
title: Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.ctl.settings
dev_langs: C++
helpviewer_keywords: MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60828b7f40009a5fd88c7f0a7f820ede3de4aa93
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="control-settings-mfc-activex-control-wizard"></a>Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent
Verwenden Sie diese Seite des Assistenten, um anzugeben, wie das Steuerelement Verhalten soll. Sie können z. B. das Steuerelement auf standardmäßige Windows-Steuerelementtypen, optimieren das Verhalten und Aussehen oder anzugeben, dass das Steuerelement als Container für andere Steuerelemente fungieren kann.  
  
 Weitere Informationen zum Auswählen von Optionen auf dieser Seite, um die Effizienz des Steuerelements zu maximieren, finden Sie unter [MFC-ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Erstellen des Steuerelements basierend auf**  
 In dieser Liste können Sie die Art von Steuerelement auswählen, von denen das Steuerelement erben soll. Die Liste ist eine Teilmenge der Steuerelementklassen, die für die verfügbaren `CreateWindowEx` und weitere allgemeine Steuerelemente, die in commctrl.h angegeben sind. Ihre Auswahl bestimmt den Stil des Steuerelements in der `PreCreateWindow` -Funktion in der *ProjName*Datei Ctrl.cpp fest. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente: einer Fenstersteuerelement](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
|Steuerelement|Beschreibung|  
|-------------|-----------------|  
|**SCHALTFLÄCHE**|Ein Windows-Schaltflächen-Steuerelement|  
|**KOMBINATIONSFELD-STEUERELEMENT**|Ein Kombinationsfeld-Steuerelement von Windows|  
|**BEARBEITEN**|Windows-Bearbeitungssteuerelements Feld|  
|**LISTBOX**|Ein Listenfeld-Steuerelement von Windows|  
|**BILDLAUFLEISTE**|Eine Windows Bildlaufleisten-Steuerelement|  
|**STATISCHE**|Ein statisches Steuerelement von Windows|  
|**msctls_hotkey32**|Ein allgemeines Abkürzungstaste-Steuerelement|  
|**msctls_progress32**|Eine Statusanzeige Standardsteuerelements|  
|**msctls_statusbar32**|Eine Statusleiste Standardsteuerelements|  
|**msctls_trackbar32**|Eine Trackleiste Standardsteuerelements|  
|**msctls_updown32**|Drehfeld-Taste (oder nach oben und unten) gemeinsamen-Steuerelement|  
|**SysAnimate32**|Ein allgemeines Animationssteuerelement|  
|**SysHeader32**|Ein allgemeines Headersteuerelement|  
|**SysListView32**|Eine allgemeine Listenansicht-Steuerelement|  
|**SysTabControl32**|Eine allgemeine Registerkarten-Steuerelement|  
|**SysTreeView32**|Eine allgemeine Ansicht Strukturansicht|  
  
 **Aktiviert, wenn sichtbar**  
 Gibt an, dass ein Fenster für das Steuerelement erstellt wird, wenn darauf zugegriffen wird. Wird standardmäßig die **aktiviert, wenn sichtbar** ausgewählt ist. Wenn Sie die Steuerelement-Aktivierung zu verzögern, bis der Container muss (z. B., wenn ein Benutzer die Maus klickt) möchten, deaktivieren Sie diese Option. Wenn diese Funktion deaktiviert ist, ist das Steuerelement nicht bis zur Löschung der Ausgaben einer fenstererstellung dies erforderlich ist. Weitere Informationen finden Sie unter [durch das Deaktivieren der Option "aktiviert wenn sichtbar"](../../mfc/turning-off-the-activate-when-visible-option.md).  
  
 **Zur Laufzeit nicht sichtbar.**  
 Gibt an, dass das Steuerelement zur Laufzeit keine Benutzeroberfläche verfügt. Ein Zeitgeber ist eine Art von Steuerelement, das nicht sichtbar sein sollen.  
  
 **Verfügt über ein Dialogfeld Info**  
 Gibt an, dass das Steuerelement das Windows-Standarddialogfeld **zu** (Dialogfeld), der Versionsnummer und copyright-Informationen angezeigt.  
  
> [!NOTE]
>  Wie der Benutzer die Hilfe für das Steuerelement zugreift, hängt davon ab, wie Sie die Hilfe implementiert haben und gibt an, ob Sie die benutzerführung mit Hilfe Container integriert wurden. Weitere Informationen zur Integration von Hilfe zu erhalten, auf die [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542) -Website, suchen Sie nach "Hinzufügen kontextbezogene Hilfe zu einem MFC-ActiveX-Steuerelement".  
  
 Wenn Sie diese Option auswählen, fügt die `AboutBox` steuern Sie die Methode in der Projekt-Steuerelementklasse (C*ProjName*Ctrl.cpp fest) und die Dispatchzuordnung Projekt AboutBox hinzugefügt. Diese Option ist standardmäßig ausgewählt.  
  
 **Optimierter Code zum Zeichnen**  
 Gibt an, dass der Container die ursprünglichen GDI-Objekte automatisch, nachdem alle Containersteuerelementen werden auf den gleichen Gerätekontext wiederherstellt, gezeichnet wurde. Weitere Informationen zu diesem Feature finden Sie unter [Optimieren der Steuerelementdarstellung](../../mfc/optimizing-control-drawing.md).  
  
 **Fensterlose Aktivierung**  
 Gibt an, dass das Steuerelement kein Fenster erstellt, wenn sie aktiviert wird. Fensterlose Aktivierung ermöglicht nicht rechteckige oder transparente Steuerelemente, und ein fensterloses Steuerelement erfordert weniger Systemaufwand als ein Steuerelement, das ein Fenster ist erforderlich. Ein fensterloses Steuerelement lässt sich nicht für eine Gerätekontexts ohne clippingbereichsanpassung oder flimmerfreier Aktivierung. Fensterlosen Aktivierung unterstützt Container, die vor 1996 erstellt wurden, nicht. Weitere Informationen zur Verwendung dieser Option finden Sie unter [bereitstellen Fensterloser Aktivierung](../../mfc/providing-windowless-activation.md).  
  
 **Gerätekontexts ohne clippingbereichsanpassung**  
 Überschreibt [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) in der Control-Header (*Projname*ctrl.h) deaktivieren Sie den Aufruf von `IntersectClipRect` von vorgenommenen `COleControl`. Wenn Sie diese Option auswählen, stellt es einen geringen Leistungsvorteil. Bei Auswahl des **fensterlose Aktivierung**, diese Funktion ist nicht verfügbar. Weitere Informationen finden Sie unter [Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../../mfc/using-an-unclipped-device-context.md).  
  
 **Flimmerfreier Aktivierung**  
 Eliminiert die Zeichenoperationen und die begleitende visual Flimmern, die zwischen den aktiven und inaktiven Status des Steuerelements auftreten. Bei Auswahl des **fensterlose Aktivierung**, diese Funktion ist nicht verfügbar. Bei Festlegung dieser Option die `noFlickerActivate` Flag ist eines der Flags, die von zurückgegeben werden [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen finden Sie unter [bereitstellen flimmerfreier Aktivierung](../../mfc/providing-flicker-free-activation.md).  
  
 **Im Dialogfeld "Objekt einfügen" verfügbar.**  
 Gibt an, dass das Steuerelement in zur Verfügung stehen die **Objekt einfügen** Dialogfeld für aktivierte Container. Bei Auswahl dieser Option die `afxRegInsertable` Flag ist eines der Flags, die von zurückgegeben werden `AfxOleRegisterControlClass`. Mithilfe der **Objekt einfügen** (Dialogfeld), kann ein Benutzer neu erstellte einzufügen oder vorhandenen Objekte in ein Verbunddokument.  
  
 **Mauszeiger-Benachrichtigung inaktiven Zustand.**  
 Können das Steuerelement in den Prozess Mauszeiger Benachrichtigungen, ob das Steuerelement aktiv ist. Bei Auswahl dieser Option die `pointerInactive` Flag ist eines der Flags, die von zurückgegeben werden [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen zur Verwendung dieser Option finden Sie unter [Bereitstellen der Aktivität während der Inaktivität](../../mfc/providing-mouse-interaction-while-inactive.md).  
  
 **Fungiert als ein einfacher Frame-Steuerelement**  
 Gibt an, dass das Steuerelement ein Container für andere Steuerelemente durch Festlegen der `OLEMISC_SIMPLEFRAME` bit für das Steuerelement. Weitere Informationen auf der [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542) -Website, suchen Sie nach "Simple Frame Site Containment".  
  
 **Lädt Eigenschaften asynchron**  
 Ermöglicht ein Zurücksetzen der vorherige asynchrone Daten und initiiert eine neue Last der asynchronen-Eigenschaft des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

