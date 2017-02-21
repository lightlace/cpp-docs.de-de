---
title: "Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.settings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelement-Assistent, Steuerelementeinstellungen"
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten, um anzugeben, wie sich das Steuerelement verhalten soll.  Beispielsweise können Sie standardmäßige Windows\-Steuerelementtypen als Grundlage für das Steuerelement verwenden, dessen Verhalten und Darstellung optimieren oder angeben, dass das Steuerelement als Container für andere Steuerelemente fungieren kann.  
  
 Weitere Informationen dazu, wie Sie ein Steuerelement mit den Optionen auf dieser Seite effizienter gestalten, finden Sie unter [MFC\-ActiveX\-Steuerelemente: Optimierung](../../mfc/mfc-activex-controls-optimization.md).  
  
## UIElement-Liste  
 **Steuerelement auf folgender Basis erstellen**  
 Aus der Liste können Sie den Typ des Steuerelements auswählen, von dem das Steuerelement erben soll.  Die Liste ist eine Teilmenge der Steuerelementklassen, die für `CreateWindowEx` verfügbar sind, und weitere allgemeine Steuerelemente, die in commctrl.h angegeben sind.  die Auswahl durch den Stil des Steuerelements in der `PreCreateWindow`\-Funktion in der Datei *ProjName* Ctrl.cpp.  Weitere Informationen finden Sie unter [MFC\-ActiveX\-Steuerelemente: Erstellen einer Fenstersteuerelement\-Unterklasse](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
|Steuerelement|**Beschreibung**|  
|-------------------|----------------------|  
|**BUTTON**|Ein Windows\-Schaltflächensteuerelement|  
|**COMBOBOX**|Ein Windows\-Kombinationsfeldsteuerelement|  
|**EDIT**|Ein Windows\-Eingabefeldsteuerelement|  
|**LISTBOX**|Ein Windows\-Listenfeldsteuerelement|  
|**SCROLLBAR**|Ein Windows\-Bildlaufleistensteuerelement|  
|**STATIC**|Ein statisches Windows\-Steuerelement|  
|**msctls\_hotkey32**|Ein allgemeines Steuerelement der Abkürzungstaste|  
|**msctls\_progress32**|Ein allgemeines Statusanzeigensteuerelement|  
|**msctls\_statusbar32**|Ein allgemeines Statusleistensteuerelement|  
|**msctls\_trackbar32**|Ein allgemeines Trackleistensteuerelement|  
|**msctls\_updown32**|Ein allgemeines Drehfeld\- \(oder Auf\/Ab\-\) Steuerelement|  
|**SysAnimate32**|Ein allgemeines Animationssteuerelement|  
|**SysHeader32**|Ein allgemeines Headersteuerelement|  
|**SysListView32**|Ein allgemeines Listenansichtsteuerelement|  
|**SysTabControl32**|Ein allgemeines Registersteuerelement|  
|**SysTreeView32**|Ein allgemeines Strukturansichtsteuerelement|  
  
 **Aktiviert, wenn sichtbar**  
 Gibt an, dass ein Fenster für das Steuerelement erstellt wird, wenn darauf zugegriffen wird.  Standardmäßig ist die Option **Aktiviert, wenn sichtbar** ausgewählt.  Wenn Sie die Steuerelementaktivierung verzögern möchten, bis der Container sie benötigt \(z. B. wenn ein Benutzer mit der Maus klickt\), deaktivieren Sie diese Option.  Wenn diese Funktion deaktiviert ist, unternimmt das Steuerelement nicht die Erstellung eines Fensters, bis es erforderlich ist.  Weitere Informationen finden Sie unter [Deaktivieren der Option „Aktiviert, wenn sichtbar“](../../mfc/turning-off-the-activate-when-visible-option.md).  
  
 **Unsichtbar bei Laufzeit**  
 Legt fest, dass das Steuerelement zur Laufzeit keine Benutzeroberfläche hat.  Ein Zeitgeber ist eine Art von Steuerelement, das sichtbar sein soll.  
  
 **Enthält ein "Info"\-Dialogfeld**  
 Legt fest, dass das Steuerelement über das Windows\-Standarddialogfeld **Info** verfügt, in dem die Versionsnummer und Urheberrechtsinformationen angezeigt werden.  
  
> [!NOTE]
>  Wie der Benutzer Hilfe zum Steuerelement aufruft, hängt von der Implementierung der Hilfe und davon ab, ob die jeweiligen Hilfefunktionen des Steuerelements und des Containers integriert sind.  Weitere Informationen dazu, wie Hilfe, auf der [MSDN Library](http://go.microsoft.com/fwlink/?linkID=150542) Website, nach "Hinzufügen von kontextbezogenen Hilfe zu einem MFC\-ActiveX\-Steuerelement" integriert.  
  
 Wenn Sie diese Option auswählen, fügt sie die `AboutBox` Steuerungsmethode zur Aktivierung in der Projektsteuerelementklasse \(*ProjName* Ctrl.cpp\) und fügt AboutBox der Projektdispatchzuordnung hinzu.  Diese Option ist standardmäßig ausgewählt.  
  
 **Optimierter Zeichencode**  
 Legt fest, dass der Container die ursprünglichen GDI\-Objekte automatisch wiederherstellt, nachdem alle Steuerelemente des Containers, die im selben Gerätekontext dargestellt werden, gezeichnet wurden.  Weitere Informationen über dieses Feature finden Sie unter [Optimieren der Steuerelementdarstellung](../../mfc/optimizing-control-drawing.md).  
  
 **Fensterlose Aktivierung**  
 Legt fest, dass vom Steuerelement kein Fenster erstellt wird, nachdem es aktiviert wurde.  Fensterlose Aktivierung ermöglicht nicht rechteckige oder transparente Steuerelemente, und ein fensterloses Steuerelement erfordert weniger Systemaufwand als ein Steuerelement, für das ein Fenster erforderlich ist.  Ein fensterloses Steuerelement unterstützt weder den nicht geschnittenen Gerätekontext noch die flimmerfreie Aktivierung.  Vor 1996 erstellte Container unterstützen keine fensterlose Aktivierung.  Weitere Informationen zum Verwenden dieser Option finden Sie unter [Bereitstellung von fensterloser Aktivierung](../../mfc/providing-windowless-activation.md).  
  
 **Nicht geschnittener Gerätekontext**  
 Überschreibungen [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) in der Steuerkopfzeile \(*projname* ctrl.h\) der Aufruf von `IntersectClipRect` zu deaktivieren haben durch `COleControl`.  Wenn Sie diese Option auswählen, erzielen Sie einen geringen Leistungsvorteil.  Wenn Sie **Fensterlose Aktivierung** auswählen, ist dieses Feature nicht verfügbar.  Weitere Informationen finden Sie unter [Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung](../../mfc/using-an-unclipped-device-context.md).  
  
 **Flimmerfreie Aktivierung**  
 Unterdrückt Neuzeichenoperationen mit dem typischen visuellen Flimmern, das zwischen den aktiven und nicht aktiven Zuständen des Steuerelements auftritt.  Wenn Sie **Fensterlose Aktivierung** auswählen, ist dieses Feature nicht verfügbar.  Bei Festlegen dieser Option ist das `noFlickerActivate`\-Flag eines der Flags, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden.  Weitere Informationen finden Sie unter [Bereitstellen flimmerfreier Aktivierung](../../mfc/providing-flicker-free-activation.md).  
  
 **Verfügbar im Dialogfeld "Objekt einfügen"**  
 Legt fest, dass das Steuerelement im Dialogfeld **Objekt einfügen** für aktivierte Container verfügbar ist.  Bei Auswahl dieser Option ist das `afxRegInsertable`\-Flag eines der Flags, die von `AfxOleRegisterControlClass` zurückgegeben werden.  Mithilfe des Dialogfelds **Objekt einfügen** kann ein Benutzer neu erstellte oder vorhandene Objekte in ein Verbunddokument einfügen.  
  
 **Mauszeiger\-Benachrichtigung wenn inaktiv**  
 Ermöglicht es dem Steuerelement, Mauszeiger\-Benachrichtigungen unabhängig davon zu verarbeiten, ob das Steuerelement aktiv ist.  Bei Auswahl dieser Option ist das `pointerInactive`\-Flag eines der Flags, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden.  Weitere Informationen zum Verwenden dieser Option finden Sie unter [Bereitstellen von Mausinteraktionen in inaktiven Steuerelementen](../../mfc/providing-mouse-interaction-while-inactive.md).  
  
 **Dient als einfaches Rahmensteuerelement**  
 Gibt an, dass das Steuerelement ein Container für andere Steuerelemente ist, indem das `OLEMISC_SIMPLEFRAME`\-Bit für das Steuerelement festgelegt wird.  Weitere Informationen über die [MSDN Library](http://go.microsoft.com/fwlink/?linkID=150542) Website, für einfache Suche "Feld\-Site\-Kapselung".  
  
 **Lädt Eigenschaften asynchron**  
 Aktiviert das Zurücksetzen vorheriger asynchroner Daten und initiiert das erneute Laden der asynchronen Eigenschaft des Steuerelements.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Anwendungseinstellungen, MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Steuerelementnamen, MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/control-names-mfc-activex-control-wizard.md)