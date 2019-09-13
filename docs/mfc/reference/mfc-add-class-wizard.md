---
title: MFC-Assistent zum Hinzufügen von Klassen
ms.date: 09/06/2019
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
ms.openlocfilehash: 2c82e084de2123c579299ca6490bdfcfdac5d255
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908032"
---
# <a name="mfc-add-class-wizard"></a>MFC-Assistent zum Hinzufügen von Klassen

Verwenden Sie diesen Code-Assistenten, um einem vorhandenen MFC-Projekt eine Klasse hinzuzufügen oder um eine Klasse zu einem ATL-Projekt hinzuzufügen, das MFC unterstützt. Sie können auch MFC-Klassen zu Win32-Projekten hinzufügen, die über MFC-Unterstützung verfügen. Die Funktionen, die Sie beim Erstellen des Projekts angegeben haben, bestimmen die in diesem Dialogfeld verfügbaren Optionen. Um auf den Assistenten zuzugreifen, klicken Sie im [Klassen-Assistenten](mfc-class-wizard.md)auf **Klasse hinzufügen** .

![MFC-Klassen-Assistenten hinzufügen](media/add-mfc-class-wizard.png "MFC-Klassen-Assistenten hinzufügen")

## <a name="names"></a>Namen

Geben Sie auf dieser Seite den Klassennamen, die Basisklasse und die Dateinamen für die neue Klasse an.

- **Klassenname**

  Gibt den Namen der neuen Klasse an und gibt die Standardbasis für die Namen von IDs und Dateien auf dieser Seite an. C++Klassen beginnen in der Regel mit "C", sodass z. b. "CMyClass" zu "MyClass. h" wird usw.

- **Basisklasse**

  Gibt den Namen der Basisklasse für die neue Klasse an. Standardmäßig ist die Basisklasse [CWnd](../../mfc/reference/cwnd-class.md). Die von Ihnen ausgewählte Basisklasse bestimmt, ob andere Felder auf dieser Seite aktiv sind.

  Der Typ der Klasse, die Sie als Basisklasse festlegen, bestimmt, ob die Klasse über eine Dialog-ID oder eine Ressourcen-ID verfügt. Die allgemeinen Klassentypen lauten wie folgt:

  - Klassen wie [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md)oder [CDocument](../../mfc/reference/cdocument-class.md), für die keine Dialog-ID oder Ressourcen-ID erforderlich ist. Diese Klassen verwenden keine Dialogfeld-oder Ressourcen-ID. Wenn Sie eine dieser Klassen für die Basisklasse auswählen, sind das Feld Dialog Feld- **ID** und das Feld **DHTML-Ressourcen-ID** abdimmt.

  - Klassen wie [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md)oder [CPropertyPage](../../mfc/reference/cpropertypage-class.md), die eine Dialog-ID erfordern.

  - Die Klasse [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), die eine Dialog-ID, eine DHTML-Ressourcen-ID und einen HTML-Dateinamen erfordert.

  Bei Klassen, die eine Dialog-ID erfordern, ist es möglicherweise effizienter, den [Ressourcen-Editor](../../windows/resource-editors.md) zum Erstellen der Dialogfeld Ressource zu verwenden, die ID im Klassen- [Assistenten](mfc-class-wizard.md)zuzuweisen und dann eine Klasse zu erstellen, die dieser Ressourcen-ID zugeordnet ist. Weitere Informationen zum Erstellen eines Standard Dialogfelds für Windows finden Sie unter [Erstellen eines neuen Dialog](../../windows/creating-a-new-dialog-box.md) Felds.

  > [!NOTE]
  > Wenn Sie zuerst eine Dialog Ressource erstellen und deren neue Klasse von `CDHtmlDialog`ableiten, löschen Sie die standardmäßigen Windows-Schaltflächen **OK** und **Abbrechen** , die im Standard Dialogfeld angezeigt werden. Das Standard Dialogfeld von Windows hostet das DHTML-Formular, das die eigenen Schaltflächen **OK** und **Abbrechen** enthält.

  Das Dialogfeld kann zwar sowohl Windows-Steuerelemente als auch DHTML-Steuerelemente enthalten, wird jedoch nicht empfohlen.

- **Dialog-ID**

  Gibt die ID des Dialog Felds an, wenn Sie `CDialog`, `CFormView`, `CPropertyPage`oder `CDHtmlDialog` als **Basisklasse**ausgewählt haben.

- **H-Datei**

  Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

  Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **CPP-Datei**

  Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

  Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Aktive Barrierefreiheit**

  Aktiviert die MFC-Unterstützung für Active Accessibility durch Aufrufen von [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) im Konstruktor. Diese Option ist für von [CWnd](../../mfc/reference/cwnd-class.md)abgeleitete Klassen verfügbar.

- **Automatisierung**

  Legt die Klassenebene der Unterstützung für [Automation](../../mfc/automation.md)fest. Automation auf Klassenebene ist für alle Klassen verfügbar, die Automation unterstützen. Sie steht auch für Projekte zur Verfügung, die mit Unterstützung für Automation erstellt wurden. Dies ist entweder ein MFC-Projekt, das [ATL unterstützt](../../atl/reference/mfc-support-in-atl-projects.md), oder ein MFC-Projekt, für das Sie im MFC-Anwendungs-Assistenten auf der Seite [Erweiterte Features](../../mfc/reference/advanced-features-mfc-application-wizard.md) das Kontrollkästchen **Automatisierung** ausgewählt haben.

   Automation-Unterstützung ist für die folgenden Basisklassen nicht verfügbar:

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

## <a name="see-also"></a>Siehe auch

[MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
