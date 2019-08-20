---
title: Implementieren einer Schnittstelle
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.impl.interface.overview
helpviewer_keywords:
- interfaces, implementing
- implement interface wizard [C++]
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
ms.openlocfilehash: bb1db35e269ef884f3ebdf4564d8f0a3e579db50
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509514"
---
# <a name="implement-an-interface"></a>Implementieren einer Schnittstelle

Zum Implementieren einer Schnittstelle müssen Sie ein Projekt als ATL COM-Anwendung oder MFC-Anwendung, die ATL-Unterstützung enthält, erstellt haben. Sie können den [ATL-Projekt-Assistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

Nachdem Sie das Projekt erstellt haben, müssen Sie zum Implementieren einer Schnittstelle zunächst ein ATL-Objekt hinzufügen. Eine Liste von Assistenten, die Ihrem ATL-Projekt Objekte hinzufügen, finden Sie unter [Adding Objects and Controls to an ATL Project (Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt)](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

> [!NOTE]
> Der Assistent unterstützt keine ATL-Dialogfelder, XML-Webdienste mit ATL, Leistungsobjekte oder Leistungsindikatoren.

Wenn Sie ein [ATL-Steuerelement](../atl/reference/adding-an-atl-control.md) hinzufügen, können Sie festlegen, ob Standardschnittstellen implementiert werden sollen. Die Standardschnittstellen werden auf der Seite [Schnittstellen](../atl/reference/interfaces-atl-control-wizard.md) des Assistenten aufgelistet und in „atlcom.h“ definiert.

Sobald Sie das Objekt oder Steuerelement hinzugefügt haben, können Sie weitere Schnittstellen implementieren, die sich in einer der verfügbaren Typbibliotheken befinden, indem Sie den Assistenten zum Implementieren von Schnittstellen verwenden.

Wenn Sie eine neue Schnittstelle hinzufügen, müssen Sie sie der IDL-Datei des Projekts manuell hinzufügen. Weitere Informationen finden Sie unter [Adding a New Interface in an ATL Project (Hinzufügen einer neuen Schnittstelle zu einem ATL-Projekt)](../atl/reference/adding-a-new-interface-in-an-atl-project.md).

**So implementieren Sie eine Schnittstelle:**

1. Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen für das ATL-Objekt.

1. Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Schnittstelle implementieren**, um den [Assistenten zum Implementieren von Schnittstellen](#implement-interface-wizard) anzuzeigen.

1. Wählen Sie die zu implementierenden Schnittstellen aus den entsprechenden Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.

1. Erweitern Sie in der Klassenansicht den Objektknoten „Bases and Interfaces“ (Basen und Schnittstellen), um die von Ihnen implementierte Schnittstelle anzuzeigen. Erweitern Sie dann den Schnittstellenknoten, um die verfügbaren Eigenschaften, Methoden und Ereignisse anzuzeigen.

   > [!NOTE]
   > Sie können auch den [Objektkatalog](/visualstudio/ide/viewing-the-structure-of-code) verwenden, um die Members der Schnittstelle zu überprüfen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Assistent zum Implementieren von Schnittstellen](#implement-interface-wizard)

## <a name="implement-interface-wizard"></a>Assistent zum Implementieren von Schnittstellen

Dieser Assistent implementiert eine Schnittstelle für ein COM-Projekt. Implementierungen vieler Schnittstellen sind in den COM-Bibliotheken enthalten, die in Visual Studio und Windows verfügbar sind. Eine Schnittstellenimplementierung wird einem Objekt zugeordnet, wenn eine Schnittstelle dieses Objekts erstellt wird. Diese stellt die Dienste bereit, die das Objekt anbietet.

Eine Erläuterung der Schnittstellen und Implementierungen finden Sie im Windows SDK unter [Interfaces and Interface Implementations (Schnittstellen und Schnittstellenimplementierungen)](/windows/win32/com/interfaces-and-interface-implementations).

- **Implement interface from** (Schnittstelle implementieren aus)

  Gibt den Speicherort der Typbibliothek an, aus der die Schnittstelle erstellt wird.

  |Option|BESCHREIBUNG|
  |------------|-----------------|
  |**Projekt**|Die Typbibliothek ist ein Teil des Projekts.|
  |**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken werden unter **Verfügbare Typbibliotheken** aufgeführt.|
  |**Datei**|Die Typbibliothek wird nicht unbedingt im System registriert, sondern in einer Datei gespeichert. Geben Sie den Dateispeicherort unter **Speicherort** an.|

- **Verfügbare Typbibliotheken**

  Zeigt die verfügbaren Typbibliotheken an, die die Schnittstellendefinitionen enthalten, die Sie implementieren können. Wenn Sie unter **Implement interface from** (Schnittstelle implementieren aus) auf **Datei** klicken, kann dieses Feld nicht geändert werden.

- **Position**

  Zeigt den Speicherort der Typbibliothek an, die in der Liste **Verfügbare Typbibliotheken** aktuell ausgewählt ist. Wenn Sie unter **Implement interface from** (Schnittstelle implementieren aus) auf **Datei** geklickt haben, klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei zu suchen, die die zu verwendende Typbibliothek enthält.

- **Schnittstellen**

  Zeigt die Schnittstellen an, deren Definitionen in der aktuell im Feld **Verfügbare Typbibliotheken** ausgewählten Typbibliothek enthalten sind.

  > [!NOTE]
  > Schnittstellen mit dem gleichen Namen wie die, die bereits vom ausgewählten Objekt implementiert wurden, werden nicht im Feld **Schnittstellen** angezeigt.

  |Schaltfläche „Übertragen“|BESCHREIBUNG|
  |---------------------|-----------------|
  |**>**|Fügt den Namen der aktuell in der Liste **Schnittstellen** ausgewählten Schnittstelle der Liste **Schnittstellen implementieren** hinzu.|
  |**>>**|Fügt alle Namen der in der Liste **Schnittstellen** verfügbaren Schnittstellen der Liste **Schnittstellen implementieren** hinzu.|
  |**\<**|Entfernt den Namen der Schnittstelle, die aktuell in der Liste **Schnittstellen implementieren** ausgewählt ist.|
  |**\<\<**|Entfernt alle Namen der Schnittstellen, die aktuell in der Liste **Schnittstellen implementieren** aufgelistet sind.|

- **Schnittstellen implementieren**

  Zeigt die Namen der Schnittstellen an, die Sie zum Implementieren in Ihr Objekt ausgewählt haben.

  > [!NOTE]
  > Wenn Sie mehr als eine Schnittstelle einfügen, die von `IDispatch` abgeleitet wird, oder wenn Sie versuchen, eine Schnittstelle zu implementieren, die von einer Schnittstelle abgeleitet wird, die sich bereits in der Klasse befindet, müssen Sie die COM_MAP-Einträge voneinander unterscheiden. Weitere Informationen finden Sie unter [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2).
