---
title: MFC-Assistent zum Hinzufügen von Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
ms.openlocfilehash: 245963d4222188f16fd334d6950e04584ac1e978
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520841"
---
# <a name="mfc-add-class-wizard"></a>MFC-Assistent zum Hinzufügen von Klassen

Verwenden Sie diesen Code-Assistenten aus, um eine Klasse zu einem vorhandenen MFC-Projekt hinzuzufügen, oder ein ATL-Projekt eine Klasse hinzu, der MFC unterstützt. Sie können auch eine MFC-Klassen für Win32-Projekte hinzufügen, die MFC-Unterstützung verfügen. Die Features, die Sie beim Erstellen des Projekts angegeben bestimmen, die in diesem Dialogfeld verfügbaren Optionen.

## <a name="names"></a>Namen

Geben Sie auf dieser Seite den Namen der Klasse, die Basisklasse und Dateinamen für die neue Klasse.

- **Klassenname**

  Gibt den Namen der neuen Klasse und bildet die Grundlage für die Standardeinstellung für die Namen von IDs und Dateien auf dieser Seite. C++-Klassen werden in der Regel mit "C" beginnen, z. B. "CMyClass" "MeineKlasse.h", und so weiter.

- **Basisklasse**

  Gibt den Namen der Basisklasse für die neue Klasse. Standardmäßig ist die Basisklasse [CWnd](../../mfc/reference/cwnd-class.md). Die Basisklasse, die Sie auswählen, bestimmt, ob die anderen Felder auf dieser Seite aktiv sind.

  Der Typ der Klasse, die Sie festlegen, wie die Basisklasse bestimmt, ob die Klasse eine Dialogfeld-ID oder eine Ressourcen-ID verfügt. Die allgemeinen Arten von Klassen lauten wie folgt aus:

  - Klassen wie z. B. [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), oder [CDocument](../../mfc/reference/cdocument-class.md), die aber kein Dialogfeld oder Ressourcen-ID Diese Klassen verwenden Sie keine Dialogfeld oder Ressourcen-ID an. Bei Auswahl einer dieser Klassen als Basisklasse, die **Dialogfeld-ID** Feld und die **DHTML-Ressourcen-ID** Feld sind abgeblendet.

  - Klassen wie z. B. [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), oder [CPropertyPage](../../mfc/reference/cpropertypage-class.md), die erfordern, dass einer Dialogfeld-ID

  - Die Klasse [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), wofür eine Dialogfeld-ID, eine DHTML-Ressourcen-ID und den Namen einer HTML-Datei.

  Für Klassen, die eine Dialogfeld-ID erfordern, Sie finden es möglicherweise effizienter, mithilfe der [Ressourcen-Editor-](../../windows/resource-editors.md) weisen Sie zum Erstellen der Dialogfeldressource ihre ID in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), und klicken Sie dann eine Klasse verknüpft ist mit dieser Ressource-ID Finden Sie unter [Erstellen eines neuen Dialogfelds](../../windows/creating-a-new-dialog-box.md) für Weitere Informationen zum Erstellen einer Windows-Standarddialogfeld.

  > [!NOTE]
  > Wenn Sie eine Ressource zuerst erstellen, und leiten Sie die neue Klasse von `CDHtmlDialog`, löschen Sie die standardmäßigen Windows **OK** und **Abbrechen** Schaltflächen, die auf das standardmäßige Dialogfeld angezeigt werden. Das Windows-Standarddialogfeld hostet die DHTML-Formular, das eine eigene enthält **OK** und **Abbrechen** Schaltflächen.

  Während das Dialogfeld sowohl Windows-Steuerelemente und DHTML-Steuerelemente enthalten kann, ist es nicht empfohlen.

- **Dialogfeld-ID**

  Gibt die ID des Dialogfelds an, wenn Sie ausgewählt haben `CDialog`, `CFormView`, `CPropertyPage`, oder `CDHtmlDialog` als die **Basisklasse**.

- **H-Datei**

  Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

  Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **CPP-Datei**

  Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

  Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Active accessibility**

  Können Sie durch Aufrufen von MFC Unterstützung für Active Accessibility [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) im Konstruktor. Diese Option ist verfügbar, für die abgeleitete Klassen von [CWnd](../../mfc/reference/cwnd-class.md).

- **DHTML-Ressourcen-ID**

  Gilt für Klassen, die von `CDHtmlDialog` nur. Gibt an, die Ressourcen-ID des DHTML-Dialogfelds. Die Ressourcen-ID wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit der Datei den Namen des HTML-Dialogfeld angezeigt. Klicken Sie im Dialogfeld die DHTML-Ressource, die diese ID identifizierte gehostet wird, identifizierte **Dialogfeld-ID**.

- **. HTM-Datei**

  Gilt für Klassen, die von `CDHtmlDialog` nur. Legt den Namen der HTML-Datei für die DHTML-Dialogfeld. Der Dateiname basiert standardmäßig auf den Namen der Klasse verwendet wird. Der Dateiname wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit der DHTML Dialogfeld klicken Sie im Ressourcen-ID angezeigt.

- **Automatisierung**

  Legt die Klasse Grad der Unterstützung für [Automation](../../mfc/automation.md). Automatisierung auf Klassenebene ist für alle Klassen, die Unterstützung der Automatisierung verfügbar. Es ist auch verfügbar für Projekte mit Automatisierungsunterstützung erstellt wurden. Also entweder eine MFC zu projizieren, [ATL unterstützt](../../atl/reference/mfc-support-in-atl-projects.md), oder einem MFC-Projekt, das für die Sie ausgewählt der **Automation** Kontrollkästchen in der [erweiterte Features](../../mfc/reference/advanced-features-mfc-application-wizard.md) auf der Seite die MFC-Bibliothek Anwendungsassistenten.

  |Option|Beschreibung|
  |------------|-----------------|
  |**Keine**|Gibt an, dass die Klasse keine Automatisierung unterstützt.|
  |**Automatisierung**|Gibt an, dass die Klasse Automatisierung unterstützt. Wenn Sie diese Option auswählen, ist die neu erstellte Klasse als programmierbares Objekt von Automation-Clientanwendungen, z. B. Microsoft Visual Basic und Microsoft Excel verfügbar. Diese Option ist nicht verfügbar, für die Basisklassen, die nach dieser Tabelle aufgeführt.|
  |**Erstellbares Objekt nach Typ-ID**|Gibt an, dass sowohl die Klasse als auch das Projekt unterstützt andere Anwendungen, die Objekte dieser Klasse, die mithilfe von Automation erstellen. Mit dieser Option können Benutzeroberflächenautomatisierungs-Clients direkt auf ein Automatisierungsobjekt erstellen. Die Typ-ID in das Textfeld wird von der Clientanwendung zum Angeben des Objekts erstellt werden; Dabei handelt es sich systemweiten muss eindeutig sein. Diese Option ist nicht verfügbar, für die Basisklassen, die nach dieser Tabelle aufgeführt.|

  -Unterstützung ist nicht für den folgenden Basisklassen zur Verfügung:

  - `CAsyncMonitorFile`

  - `CAsyncSocket`

  - `CCachedDataPathProperty`

  - `CConnectionPoint`

  - `CDatabase`

  - `CDataPathProperty`

  - `CHttpFilter`

  - `CHttpServer`

  - `CInternetSession`

  - `CObject`

  - `CSocket`

- **Typ-ID**

  Legt die Typ-ID der Klasse fest. Die **Typ-ID** Feld verkettet den Projektnamen und den neuen Klassennamen wie folgt: *MFCProj.MFCClass*. Diese ID kann geändert werden, nur bei Auswahl der **Automation** Option **Creatable vom Typ ID**.

- **Erstellte DocTemplate-Ressourcen**

  Gibt an, dass die Dokumente, die von der Anwendung erstellten Ressourcen für Dokumentvorlagen. Um dieses Kontrollkästchen aktivieren, muss das Projekt der MFC Dokument-/Ansichtarchitektur unterstützen, und die Basisklasse dieser Klasse muss [CFormView](../../mfc/reference/cformview-class.md).

  Finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../../mfc/document-templates-and-the-document-view-creation-process.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
