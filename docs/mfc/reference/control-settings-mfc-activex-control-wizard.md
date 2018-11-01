---
title: Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.settings
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
ms.openlocfilehash: 3eedf24fa4b0bb527b374dbc9f538408f20de953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548238"
---
# <a name="control-settings-mfc-activex-control-wizard"></a>Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent

Verwenden Sie diese Seite des Assistenten, um anzugeben, wie das Steuerelement, das sich Verhalten soll. Beispielsweise können Sie das Steuerelement auf der Grundlage standard Windows-Steuerelementtypen, dessen Verhalten und die Darstellung zu optimieren oder anzugeben, dass das Steuerelement als Container für andere Steuerelemente agieren kann.

Weitere Informationen zum Auswählen der Optionen auf dieser Seite, um die Effizienz des Steuerelements zu maximieren, finden Sie unter [MFC-ActiveX-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Erstellen Sie auf der Grundlage-Steuerelement**

   In dieser Liste können Sie die Art von Steuerelement auswählen, von denen das Steuerelement erben soll. Die Liste ist eine Teilmenge der Klassen für Steuerelemente, die zur `CreateWindowEx` und zusätzlicher gemeinsamer Steuerelemente, die in commctrl.h angegeben werden. Ihre Auswahl bestimmt den Stil des Steuerelements in der `PreCreateWindow` Funktion in der *ProjName*Datei Ctrl.cpp fest. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente: Erstellen von Unterklassen für ein Windows-Steuerelement](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

   |Steuerelement|Beschreibung|
   |-------------|-----------------|
   |**SCHALTFLÄCHE "**|Ein Windows-Schaltflächen-Steuerelement|
   |**KOMBINATIONSFELD-STEUERELEMENT**|Ein Kombinationsfeld-Steuerelement von Windows|
   |**BEARBEITEN**|Ein Windows-Bearbeitungssteuerelement|
   |**LISTBOX-ELEMENT**|Ein Listenfeld-Steuerelement von Windows|
   |**BILDLAUFLEISTE**|Ein Windows Schiebeleisten-Steuerelement|
   |**STATIC**|Ein statisches Steuerelement von Windows|
   |**msctls_hotkey32**|Ein "Hot" Allgemeines Steuerelement|
   |**msctls_progress32**|Eine Statusanzeige Standardsteuerelements|
   |**msctls_statusbar32**|Eine Statusleiste Standardsteuerelements|
   |**msctls_trackbar32**|Eine Trackleiste-Standardsteuerelements|
   |**msctls_updown32**|Ein Drehfeld-Schaltfläche (oder nach oben und unten) Standardsteuerelements|
   |**SysAnimate32**|Ein allgemeines Animationssteuerelement|
   |**SysHeader32**|Eine allgemeine Kopfzeilen-Steuerelement|
   |**SysListView32**|Eine allgemeine Listenansicht-Steuerelement|
   |**SysTabControl32**|Ein häufig Registerkarten-Steuerelement|
   |**SysTreeView32**|Eine allgemeine Ansicht Strukturansicht|

- **Aktiviert, wenn sichtbar**

   Gibt an, dass ein Fenster für das Steuerelement erstellt wird, wenn darauf zugegriffen wird. In der Standardeinstellung die **aktiviert, wenn sichtbar** ausgewählt ist. Wenn Sie die Aktivierung des Steuerelements verzögern, bis der Container ist es, (z. B. erforderlich, wenn ein Benutzer mit die Maus klickt) möchten, deaktivieren Sie diese Option aus. Wenn dieses Feature deaktiviert ist, wird das Steuerelement nicht entstehen die Kosten für die Erstellung erst, wenn dies erforderlich ist. Weitere Informationen finden Sie unter [durch das Deaktivieren der Option "aktiviert wenn sichtbar"](../../mfc/turning-off-the-activate-when-visible-option.md).

- **Zur Laufzeit nicht sichtbar.**

   Gibt an, dass das Steuerelement zur Laufzeit über keine Benutzeroberfläche verfügt. Ein Zeitgeber ist eine Art von Steuerelement, das möglicherweise nicht sichtbar sein soll.

- **Verfügt über ein Info-Dialogfeld**

   Gibt an, dass das Steuerelement das standardmäßige Windows **zu** Dialogfeld zeigt die Versionsnummer und Copyrightinformationen an.

   > [!NOTE]
   > Wie der Benutzer die Hilfe für das Steuerelement zugreift, hängt davon ab, wie Sie die Hilfe implementiert haben und gibt an, ob Sie die benutzerführung mit Hilfe Container integriert haben. Weitere Informationen zur Integration von Hilfe, auf die [MSDN-Bibliothek](http://go.microsoft.com/fwlink/p/?linkid=150542) -Website, suchen Sie nach "Hinzufügen von kontextbezogene Hilfe, ein MFC-ActiveX-Steuerelement".

   Wenn Sie diese Option auswählen, fügt es der `AboutBox` -Methode in der die Klasse des Steuerelements zu steuern (C*ProjName*Ctrl.cpp fest) und die Projekt-Dispatchzuordnung AboutBox hinzugefügt. Diese Option ist standardmäßig ausgewählt.

- **Optimierter Code zum Zeichnen**

   Gibt an, dass der Container die ursprünglichen GDI-Objekte automatisch, nachdem alle Steuerelemente des Containers, der auf den gleichen Gerätekontext gezeichnet werden wiederhergestellt, wurden. Weitere Informationen zu diesem Feature finden Sie unter [Optimieren der Steuerelementdarstellung](../../mfc/optimizing-control-drawing.md).

- **Fensterlose Aktivierung**

   Gibt an, dass es sich bei das Steuerelement kein Fenster erstellt, wenn es aktiviert ist. Fensterloser Aktivierung ermöglicht für nicht rechteckige oder transparent Steuerelemente und ein fensterloses Steuerelement erfordert, dass weniger Systemaufwand als ein Steuerelement, das ein Fenster ist erforderlich. Ein fensterloses Steuerelement lässt sich nicht für eine ungeschnittener Gerätekontext oder flimmerfreier Aktivierung. Container, die vor 1996 erstellt wurden, unterstützen keine fensterlosen Aktivierung. Weitere Informationen dazu, wie Sie diese Option verwenden, finden Sie unter [bereitstellen Fensterloser Aktivierung](../../mfc/providing-windowless-activation.md).

- **Ungeschnittener Gerätekontext**

   Überschreibt [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) im Control-Header (*Projname*ctrl.h) deaktivieren Sie den Aufruf von `IntersectClipRect` vom `COleControl`. Wenn Sie diese Option auswählen, wird eine kleine Geschwindigkeitsvorteil angegeben. Bei Auswahl von **Fensterloser Aktivierung**, dieses Feature ist nicht verfügbar. Weitere Informationen finden Sie unter [mithilfe einer Ungeschnittener Gerätekontext](../../mfc/using-an-unclipped-device-context.md).

- **Flimmerfreier Aktivierung**

   Eliminiert die Zeichenoperationen und die damit verbundene Flimmern, die zwischen der aktive und inaktive Zustände des Steuerelements auftreten. Bei Auswahl von **Fensterloser Aktivierung**, dieses Feature ist nicht verfügbar. Beim Festlegen dieser Option die `noFlickerActivate` Flag ist eines der Flags, die von zurückgegeben werden [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen finden Sie unter [bereitstellen flimmerfreier Aktivierung](../../mfc/providing-flicker-free-activation.md).

- **Im Dialogfeld "Objekt einfügen" zur Verfügung.**

   Gibt an, dass das Steuerelement verfügbar sein, wird die **Objekt einfügen** im Dialogfeld für aktivierte Container. Bei Auswahl dieser Option die `afxRegInsertable` Flag ist eines der Flags, die von zurückgegeben werden `AfxOleRegisterControlClass`. Mithilfe der **Objekt einfügen** im Dialogfeld ein Benutzer kann neu erstellten einfügen oder vorhandene Objekte in einem Verbunddokument.

- **Maus-Benachrichtigungen, wenn inaktiv.**

   Können das Steuerelement, das mausbenachrichtigungen Zeiger Prozess, ob das Steuerelement aktiv ist oder nicht. Bei Auswahl dieser Option die `pointerInactive` Flag ist eines der Flags, die von zurückgegeben werden [COleControl:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Weitere Informationen dazu, wie Sie diese Option verwenden, finden Sie unter [Bereitstellen der Interaktion während der Inaktivität](../../mfc/providing-mouse-interaction-while-inactive.md).

- **Fungiert als ein einfacher Frame-Steuerelement**

   Gibt an, dass das Steuerelement ist ein Container für andere Steuerelemente OLEMISC_SIMPLEFRAME-Bit für das Steuerelement. Weitere Informationen auf der [MSDN-Bibliothek](http://go.microsoft.com/fwlink/p/?linkid=150542) -Website, suchen Sie nach "Simple Frame Site Containment".

- **Eigenschaften asynchron geladen**

   Aktiviert das Zurücksetzen von früheren asynchrone Daten und initiiert die asynchrone Eigenschaft des Steuerelements ein erneutes Laden.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

