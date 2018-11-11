---
title: Klasse hinzufügen (Dialogfeld)
ms.date: 11/04/2016
f1_keywords:
- vc.addclass
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
ms.openlocfilehash: 405f88f7f77ea75584ec3cfd76af1ea9a0457ed6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643195"
---
# <a name="add-class-dialog-box"></a>Klasse hinzufügen (Dialogfeld)

Das Dialogfeld **Klasse hinzufügen** enthält Vorlagen, die Ihnen folgende Möglichkeiten bieten:

- Öffnen Sie einen entsprechenden Code-Assistenten, falls verfügbar. Weitere Informationen finden Sie unter [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- oder –

- Erstellen Sie die neue Klasse automatisch durch Hinzufügen der entsprechenden Dateien und des Quellcodes zum Projekt.

Sie können auf das Dialogfeld **Klasse hinzufügen** über das Menü **Projekt** , den **Projektmappen-Explorer**oder die [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)zugreifen.

> [!NOTE]
>  Wenn Sie versuchen, eine Klasse hinzuzufügen, die für das aktuelle Projekt nicht geeignet ist, erhalten Sie eine Fehlermeldung. Klicken Sie auf **OK** , um zum Dialogfeld **Klasse hinzufügen** zurückzukehren.

## <a name="add-class-templates"></a>Hinzufügen von Klassenvorlagen

Es gibt vier Kategorien von **Klasse hinzufügen** -Vorlagen: „.NET“, „ATL“, „MFC“ und „Generisch“. Bei der Auswahl einer Vorlage im Bereich **Vorlagen** wird ein Ihre Auswahl beschreibender Text unter den Bereichen **Kategorien** und **Vorlagen** angezeigt.

### <a name="net"></a>.NET

|Vorlage|Assistent|
|--------------|------------|
|ASP.NET-Webdienst|Nicht verfügbar|
|Komponentenklasse (.NET)|Nicht verfügbar|
|Installerklasse (.NET)|Nicht verfügbar|
|Benutzersteuerelement (.NET)|Nicht verfügbar|
|Windows Form (.NET)|Nicht verfügbar|

### <a name="atl"></a>ATL

|Vorlage|Assistent|
|--------------|------------|
|ATL-Unterstützung zu MFC hinzufügen|Nicht verfügbar|
|ATL Active Server Page-Komponente|[ATL-Assistent für Active Server Page-Komponenten](../atl/reference/atl-active-server-page-component-wizard.md)|
|ATL-Steuerelement|[ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md)|
|ATL-Dialogfeld|[ATL-Dialogfeld-Assistent](../atl/reference/atl-dialog-wizard.md)|
|ATL COM+ 1.0-Komponente|[ATL COM+ 1.0 Komponenten-Assistent](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|ATL-OLEDB-Consumer|[ATL-OLE DB-Consumer-Assistent](../atl/reference/atl-ole-db-consumer-wizard.md)|
|ATL-OLEDB-Provider|[ATL-OLE DB-Anbieter-Assistent](../atl/reference/atl-ole-db-provider-wizard.md)|
|ATL-Eigenschaftenseite|[ATL-Eigenschaftenseiten-Assistent](../atl/reference/atl-property-page-wizard.md)|
|Einfaches ATL-Objekt|[ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md)|
|WMI-Ereignisanbieter|WMI-Ereignisanbieter-Assistent|
|WMI-Instanzenanbieter|WMI-Instanzanbieter-Assistent|

### <a name="mfc"></a>MFC

|Vorlage|Assistent|
|--------------|------------|
|MFC-Klasse|[MFC-Assistent zum Hinzufügen von Klassen](../mfc/reference/mfc-add-class-wizard.md)|
|MFC-Klasse von ActiveX-Steuerelement|[Hinzufügen einer Klasse mit dem ActiveX-Steuerelement-Assistenten](../ide/add-class-from-activex-control-wizard.md)|
|MFC-Klasse aus der Typbibliothek (typelib)|[Add Class From Typelib Wizard (Hinzufügen von Klassen über den Typelib-Assistenten)](../mfc/reference/add-class-from-typelib-wizard.md)|
|MFC-ODBC-Consumer|[MFC-ODBC-Consumer-Assistent](../mfc/reference/mfc-odbc-consumer-wizard.md)|

### <a name="generic-classes"></a>Generische Klassen

|Vorlage|Assistent|
|--------------|------------|
|Generische C++-Klasse|[Generischer C++-Klassen-Assistent](../ide/generic-cpp-class-wizard.md)|

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)<br>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../ide/navigating-the-class-structure-visual-cpp.md)