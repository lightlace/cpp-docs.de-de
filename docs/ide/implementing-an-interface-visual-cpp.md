---
title: Implementieren einer Schnittstelle (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
ms.openlocfilehash: 5146a8ced1b8347ea724940a7419d8d2507b5b58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449646"
---
# <a name="implementing-an-interface-visual-c"></a>Implementieren einer Schnittstelle (Visual C++)

Zum Implementieren einer Schnittstelle müssen Sie ein Projekt als ATL COM-Anwendung oder MFC-Anwendung, die ATL-Unterstützung enthält, erstellt haben. Sie können den [ATL-Projekt-Assistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

Nachdem Sie das Projekt erstellt haben, müssen Sie zum Implementieren einer Schnittstelle zunächst ein ATL-Objekt hinzufügen. Eine Liste von Assistenten, die Ihrem ATL-Projekt Objekte hinzufügen, finden Sie unter [Adding Objects and Controls to an ATL Project (Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt)](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

> [!NOTE]
>  Der Assistent unterstützt keine ATL-Dialogfelder, XML-Webdienste mit ATL, Leistungsobjekte oder Leistungsindikatoren.

Wenn Sie [ein ATL-Steuerelement hinzufügen](../atl/reference/adding-an-atl-control.md), können Sie angeben, ob die Standardschnittstellen implementiert werden sollen, die auf der Seite [Schnittstellen](../atl/reference/interfaces-atl-control-wizard.md) des Assistenten aufgelistet und in „atlcom.h“ definiert sind.

Sobald Sie das Objekt oder Steuerelement hinzugefügt haben, können Sie weitere Schnittstellen implementieren, die sich in einer der verfügbaren Typbibliotheken befinden, indem Sie den Assistenten zum Implementieren von Schnittstellen verwenden.

Wenn Sie eine neue Schnittstelle hinzufügen, müssen Sie sie der IDL-Datei des Projekts manuell hinzufügen. Weitere Informationen finden Sie unter [Adding a New Interface in an ATL Project (Hinzufügen einer neuen Schnittstelle zu einem ATL-Projekt)](../atl/reference/adding-a-new-interface-in-an-atl-project.md).

### <a name="to-implement-an-interface"></a>So implementieren Sie eine Schnittstelle

1. Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen für das ATL-Objekt.

1. Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Schnittstelle implementieren**, um den [Assistenten zum Implementieren von Schnittstellen](../ide/implement-interface-wizard.md) anzuzeigen.

1. Wählen Sie die zu implementierenden Schnittstellen aus den entsprechenden Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.

1. Erweitern Sie in der Klassenansicht den Knoten „Basen und Schnittstellen“, um die implementierte Schnittstelle anzuzeigen, erweitern Sie dann den Knoten der Schnittstelle, um die verfügbaren Eigenschaften, Methoden und Ereignisse anzuzeigen.

   > [!NOTE]
   > Sie können auch den [Objektkatalog](/visualstudio/ide/viewing-the-structure-of-code) verwenden, um die Members der Schnittstelle zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Erstellen einer COM-Schnittstelle](../ide/creating-a-com-interface-visual-cpp.md)<br>
[Bearbeiten einer COM-Schnittstelle](../ide/editing-a-com-interface.md)