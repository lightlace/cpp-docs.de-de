---
title: Hinzufügen einer Klasse
ms.date: 11/08/2018
f1_keywords:
- vc.codewiz.classes.adding
- vc.addclass
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
- Add Class dialog box
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
ms.openlocfilehash: 21dd4b1936eda201df8283146ba9f41fa81e11de
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693578"
---
# <a name="add-a-class"></a>Hinzufügen einer Klasse

Klicken Sie zum Hinzufügen einer Klasse in ein Visual C++-Projekt erst im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt und anschließend mit der linken auf **Hinzufügen** > **Klasse**. Daraufhin wird das [Dialogfeld „Klasse hinzufügen“](#add-class-dialog-box) geöffnet.

Wenn Sie eine Klasse hinzufügen, müssen Sie einen Namen angeben, der sich von Klassen unterscheidet, die bereits in MFC oder ATL vorhanden sind. Wenn Sie einen Namen festlegen, der bereits in einer Bibliothek vorhanden ist, zeigt die IDE eine Fehlermeldung an.

Wenn Ihre Namenskonvention für das Projekt erfordert, dass Sie einen vorhandenen Namen verwenden, können Sie auch einfach die Groß-/Kleinschreibung von mindestens einem Buchstaben im Namen ändern, da C++ die Groß-/Kleinschreibung beachtet. Wenn Sie eine Klasse beispielsweise nicht `CDocument` nennen können, können Sie sie dennoch `cdocument` nennen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Welche Art von Klasse möchten Sie hinzufügen?](#what-kind-of-class-do-you-want-to-add)
- [Dialogfeld „Klasse hinzufügen“](#add-class-dialog-box)

## <a name="what-kind-of-class-do-you-want-to-add"></a>Welche Art von Klasse möchten Sie hinzufügen?

Wenn Sie im Dialogfeld **Klasse hinzufügen** den Knoten **Visual C++** erweitern, werden mehrere Gruppierungen von installierten Vorlagen im linken Bereich angezeigt. Zu diesen Gruppen gehören **CLR**, **ATL**, **MFC** und **C++**. Wenn Sie eine Gruppe auswählen, wird eine Liste der verfügbaren Vorlagen dieser Gruppe im mittleren Bereich angezeigt. Jede Vorlage enthält die Dateien und den Quellcode, die für eine Klasse erforderlich sind.

Wählen Sie zum Erstellen einer neuen Klasse eine Vorlage im mittleren Bereich aus, geben Sie in das Feld **Name** einen Namen für die Klasse ein, und klicken Sie auf **Hinzufügen**. Daraufhin wird der **Assistent zum Hinzufügen von Klassen** geöffnet, damit Sie die Optionen für die Klasse festlegen können.

- Weitere Informationen zum Erstellen von MFC-Klassen finden Sie unter [MFC Class (MFC-Klasse)](../mfc/reference/adding-an-mfc-class.md).

- Weitere Informationen zum Erstellen von ATL-Klassen finden Sie unter [ATL Simple Object (Einfaches ATL-Objekt)](../atl/reference/adding-an-atl-simple-object.md).

> [!NOTE]
> Die Vorlage **ATL-Unterstützung zu MFC hinzufügen** erstellt keine Klasse. Stattdessen konfiguriert sie für das Projekt die Verwendung von ATL. Weitere Informationen finden Sie unter [ATL Support in an MFC Project (ATL-Unterstützung in einem MFC-Projekt)](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

Verwenden Sie die Vorlage **C++-Klasse** in der **C++**-Gruppe installierter Vorlagen, um eine C++-Klasse zu erstellen, die MFC, ATL und CLR nicht verwendet. Weitere Informationen finden Sie unter [Adding a Generic C++ Class (Hinzufügen einer generischen C++-Klasse)](../ide/adding-a-generic-cpp-class.md).

Es stehen zwei Arten von formularbasierten C++-Klassen zur Verfügung. Die erste Klasse, die [CFormView-Klasse](../mfc/reference/cformview-class.md), erstellt eine MFC-Klasse. Die zweite Klasse erstellt eine CLR-Windows Forms-Klasse.

## <a name="add-class-dialog-box"></a>Klasse hinzufügen (Dialogfeld)

Das Dialogfeld **Klasse hinzufügen** enthält Vorlagen, die Ihnen folgende Möglichkeiten bieten:

- Öffnen Sie einen entsprechenden Code-Assistenten, falls verfügbar. Weitere Informationen finden Sie unter [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- oder –

- Erstellen Sie die neue Klasse automatisch durch Hinzufügen der entsprechenden Dateien und des Quellcodes zum Projekt.

Sie können auf das Dialogfeld **Klasse hinzufügen** über das Menü **Projekt** , den **Projektmappen-Explorer**oder die [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)zugreifen.

> [!NOTE]
> Wenn Sie versuchen, eine Klasse hinzuzufügen, die für das aktuelle Projekt nicht geeignet ist, erhalten Sie eine Fehlermeldung. Klicken Sie auf **OK**, um zum Dialogfeld **Klasse hinzufügen** zurückzukehren.

### <a name="add-class-templates"></a>Hinzufügen von Klassenvorlagen

Es gibt vier Kategorien von **Klasse hinzufügen** -Vorlagen: „.NET“, „ATL“, „MFC“ und „Generisch“. Bei der Auswahl einer Vorlage im Bereich **Vorlagen** wird ein Ihre Auswahl beschreibender Text unter den Bereichen **Kategorien** und **Vorlagen** angezeigt.

#### <a name="net"></a>.NET

|Vorlage|Assistent|
|--------------|------------|
|ASP.NET-Webdienst|Nicht verfügbar|
|Komponentenklasse (.NET)|Nicht verfügbar|
|Installerklasse (.NET)|Nicht verfügbar|
|Benutzersteuerelement (.NET)|Nicht verfügbar|
|Windows Form (.NET)|Nicht verfügbar|

#### <a name="atl"></a>ATL

|Vorlage|Assistent|
|--------------|------------|
|ATL-Unterstützung zu MFC hinzufügen|Nicht verfügbar|
|ATL Active Server Page-Komponente|[ATL active server page component wizard (ATL-Assistent für Active Server Page-Komponenten)](../atl/reference/atl-active-server-page-component-wizard.md)|
|ATL-Steuerelement|[ATL control wizard (ATL-Steuerelement-Assistent)](../atl/reference/atl-control-wizard.md)|
|ATL-Dialogfeld|[ATL dialog wizard (ATL-Dialogfeld-Assistent)](../atl/reference/atl-dialog-wizard.md)|
|ATL COM+ 1.0-Komponente|[ATL COM+ 1.0 component wizard (ATL COM+ 1.0 Komponenten-Assistent)](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|ATL-OLEDB-Consumer|[ATL OLE DB consumer wizard (ATL-OLE DB-Consumer-Assistent)](../atl/reference/atl-ole-db-consumer-wizard.md)|
|ATL-OLEDB-Provider|[ATL OLE DB provider wizard (ATL-OLE DB-Anbieter-Assistent)](../atl/reference/atl-ole-db-provider-wizard.md)|
|ATL-Eigenschaftenseite|[ATL property page wizard (ATL-Eigenschaftenseiten-Assistent)](../atl/reference/atl-property-page-wizard.md)|
|Einfaches ATL-Objekt|[ATL simple object wizard (ATL-Assistent für einfache Objekte)](../atl/reference/atl-simple-object-wizard.md)|
|WMI-Ereignisanbieter|WMI event provider wizard (WMI-Ereignisanbieter-Assistent)|
|WMI-Instanzenanbieter|WMI instance provider wizard (WMI-Instanzanbieter-Assistent)|

#### <a name="mfc"></a>MFC

|Vorlage|Assistent|
|--------------|------------|
|MFC-Klasse|[MFC add class wizard (MFC-Assistent zum Hinzufügen von Klassen)](../mfc/reference/mfc-add-class-wizard.md)|
|MFC-Klasse von ActiveX-Steuerelement|[Add class from ActiveX control wizard (Hinzufügen einer Klasse mit dem ActiveX-Steuerelement-Assistenten)](../ide/add-class-from-activex-control-wizard.md)|
|MFC-Klasse aus der Typbibliothek (typelib)|[Add Class From Typelib Wizard (Hinzufügen einer Klasse über den Typelib-Assistenten)](../mfc/reference/add-class-from-typelib-wizard.md)|
|MFC-ODBC-Consumer|[MFC ODBC consumer wizard (MFC-ODBC-Consumer-Assistent)](../mfc/reference/mfc-odbc-consumer-wizard.md)|

#### <a name="generic-classes"></a>Generische Klassen

|Vorlage|Assistent|
|--------------|------------|
|Generische C++-Klasse|[Generic C++ class wizard (Generischer C++-Klassen-Assistent)](../ide/generic-cpp-class-wizard.md)|
