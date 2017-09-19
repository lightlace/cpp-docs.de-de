---
title: Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.settings
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 35ec579e6f777a3dffd87adc5a86af2ea38b30f4
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="control-settings-mfc-activex-control-wizard"></a>Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent
Verwenden Sie diese Seite des Assistenten, um anzugeben, wie das Steuerelement verhält. Sie können z. B. das Steuerelement auf standardmäßige Windows-Steuerelementtypen, dessen Verhalten und Darstellung optimieren oder darauf hinweisen, dass das Steuerelement als Container für andere Steuerelemente verwendet werden kann.  
  
 Weitere Informationen zum Auswählen von Optionen auf dieser Seite zur Maximierung der Effizienz des Steuerelements finden Sie unter [MFC-ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Erstellen des Steuerelements basierend auf**  
 In dieser Liste können Sie die Art von Steuerelement auswählen, von denen das Steuerelement erben soll. Die Liste ist eine Teilmenge der Steuerelementklassen, die für verfügbaren `CreateWindowEx` und weitere allgemeine Steuerelemente, die in commctrl.h angegeben sind. Ihre Auswahl bestimmt den Stil des Steuerelements in der `PreCreateWindow` -Funktion in der *Projektname*Datei Ctrl.cpp fest. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente: Erstellen von Unterklassen eines Windows-Steuerelements](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
|Steuerelement|Beschreibung|  
|-------------|-----------------|  
|**SCHALTFLÄCHE**|Ein Windows-Schaltflächen-Steuerelement|  
|**KOMBINATIONSFELD-STEUERELEMENT**|Ein Kombinationsfeld-Steuerelement von Windows|  
|**BEARBEITEN**|Ein Windows-Bearbeitungssteuerelement|  
|**LISTBOX-ELEMENT**|Ein Listenfeld-Steuerelement von Windows|  
|**BILDLAUFLEISTE**|Eine Windows-Bildlaufleiste|  
|**STATISCHE**|Ein statisches Windows-Steuerelement|  
|**msctls_hotkey32**|Ein allgemeines Abkürzungstaste-Steuerelement|  
|**msctls_progress32**|Eine Statusanzeige-Standardsteuerelement|  
|**msctls_statusbar32**|Eine Statusleiste Standardsteuerelement|  
|**msctls_trackbar32**|Eine Trackleiste-Standardsteuerelement|  
|**msctls_updown32**|Ein Drehfeld-Schaltfläche (oder nach oben und unten)-Standardsteuerelement|  
|**SysAnimate32**|Ein allgemeines Animationssteuerelement|  
|**SysHeader32**|Ein allgemeines Headersteuerelement|  
|**SysListView32**|Eine allgemeine Listenansicht-Steuerelement|  
|**SysTabControl32**|Ein allgemeines Registersteuerelement|  
|**SysTreeView32**|Ein allgemeines Strukturansichtsteuerelement|  
  
 **Aktiviert, wenn sichtbar**  
 Gibt an, dass ein Fenster für das Steuerelement erstellt wird, wenn darauf zugegriffen wird. In der Standardeinstellung die **aktiviert, wenn sichtbar** ausgewählt ist. Wenn Sie Steuerelement-Aktivierung zu verzögern, bis der Container muss (z. B., wenn ein Benutzer mit die Maus klickt) möchten, deaktivieren Sie diese Option. Wenn diese Funktion deaktiviert ist, spart das Steuerelement die Kosten der Erstellung bis es erforderlich ist. Weitere Informationen finden Sie unter [durch das Deaktivieren der Activate When Visible Option](../../mfc/turning-off-the-activate-when-visible-option.md).  
  
 **Zur Laufzeit nicht sichtbar.**  
 Gibt an, dass das Steuerelement zur Laufzeit keine Benutzeroberfläche hat. Ein Zeitgeber ist eine Art von Steuerelement, das nicht sichtbar sein sollen.  
  
 **Verfügt über ein Info-Dialogfeld**  
 Gibt an, dass das Steuerelement das Windows-Standarddialogfeld **zu** Dialogfeld, das Versionsnummer und copyright-Informationen angezeigt.  
  
> [!NOTE]
>  Wie der Benutzer die Hilfe für das Steuerelement zugreift, hängt davon ab wie Sie die Hilfe implementiert haben, und gibt an, ob Sie die Steuerelementhilfe in der Container-Hilfe integriert haben. Weitere Informationen dazu, wie Sie für die Integration von Hilfe, auf die [MSDN Library](http://go.microsoft.com/fwlink/linkid=150542) -Website, suchen Sie nach "Hinzufügen kontextbezogener Hilfe auf ein MFC-ActiveX-Steuerelement".  
  
 Wenn Sie diese Option auswählen, fügt der `AboutBox` -Methode in der Steuerelementklasse des Projekts zu steuern (C*Projektname*Ctrl.cpp fest) und AboutBox Dispatchzuordnung des Projekts. Diese Option ist standardmäßig ausgewählt.  
  
 **Optimierter Zeichencode**  
 Gibt an, dass der Container die ursprünglichen GDI-Objekte automatisch, nachdem alle Steuerelemente des Containers, die im selben Gerätekontext gezeichnet werden wiederherstellt, wurden. Weitere Informationen zu dieser Funktion finden Sie unter [Optimieren der Steuerelementdarstellung](../../mfc/optimizing-control-drawing.md).  
  
 **Fensterlose Aktivierung**  
 Gibt an, dass das Steuerelement kein Fenster erstellt, wenn es aktiviert ist. Fensterlose Aktivierung ermöglicht nicht rechteckige oder transparente Steuerelemente, und ein fensterloses Steuerelement erfordert weniger Systemaufwand als ein Steuerelement, das ein Fenster erfordert. Ein fensterloses Steuerelement lässt sich nicht für eine ungeschnittener Gerätekontext oder flimmerfreie Aktivierung. Container, die vor 1996 erstellt wurden, unterstützen keine fensterlosen Aktivierung. Weitere Informationen zum Verwenden dieser Option finden Sie unter [bereitstellen fensterlose Aktivierung](../../mfc/providing-windowless-activation.md).  
  
 **Ungeschnittener Gerätekontext**  
 Überschreibt [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) im Control-Header (*Projektname*ctrl.h) So deaktivieren Sie den Aufruf von `IntersectClipRect` vom `COleControl`. Wenn Sie diese Option auswählen, stellt es einen geringen Leistungsvorteil. Wenn Sie die Option **fensterlose Aktivierung**, dieses Feature ist nicht verfügbar. Weitere Informationen finden Sie unter [Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../../mfc/using-an-unclipped-device-context.md).  
  
 **Flimmerfreie Aktivierung**  
 Eliminiert die Zeichenoperationen und das damit verbundene Flimmern, die zwischen der aktive und inaktive Zustände des Steuerelements auftreten. Wenn Sie die Option **fensterlose Aktivierung**, dieses Feature ist nicht verfügbar. Wenn Sie diese Option Festlegen der `noFlickerActivate` Flag entspricht einem der Flags, die von zurückgegebenen [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen finden Sie unter [bereitstellen flimmerfreie Aktivierung](../../mfc/providing-flicker-free-activation.md).  
  
 **Verfügbar im Dialogfeld "Objekt einfügen"**  
 Gibt an, dass das Steuerelement verfügbar sein, wird die **Objekt einfügen** Dialogfeld für aktivierte Container. Bei Auswahl dieser Option die `afxRegInsertable` Flag entspricht einem der Flags, die von zurückgegebenen `AfxOleRegisterControlClass`. Mithilfe der **Objekt einfügen** Dialogfeld kann ein Benutzer neu erstellte einfügen oder vorhandene Objekte in ein Verbunddokument.  
  
 **Mauszeiger-Benachrichtigung wenn inaktiv**  
 Können das Steuerelement Prozess Mauszeiger-Benachrichtigung, ob das Steuerelement aktiv ist. Bei Auswahl dieser Option die `pointerInactive` Flag entspricht einem der Flags, die von zurückgegebenen [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen zum Verwenden dieser Option finden Sie unter [Bereitstellen der Mausinteraktion während der Inaktivität](../../mfc/providing-mouse-interaction-while-inactive.md).  
  
 **Fungiert als ein einfacher Frame-Steuerelement**  
 Gibt an, dass das Steuerelement ein Container für andere Steuerelemente durch Festlegen der `OLEMISC_SIMPLEFRAME` bit für das Steuerelement. Weitere Informationen auf der [MSDN Library](http://go.microsoft.com/fwlink/linkid=150542) -Website, suchen Sie nach "Simple Frame Site Containment".  
  
 **Lädt Eigenschaften asynchron**  
 Aktiviert das Zurücksetzen von vorherigen asynchronen Daten und initiiert ein neues Laden der asynchronen-Eigenschaft des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Steuerelementnamen Sie, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-names-mfc-activex-control-wizard.md)


