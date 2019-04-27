---
title: Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 99f262d420cd503c6ca385ed29bcaa2647c5f556
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249192"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt

Wenn Sie eine Schnittstelle zu Ihrem Objekt oder ein Steuerelement hinzufügen, erstellen Sie die Stub-Out-Funktionen für die einzelnen Methoden in dieser Schnittstelle. In dem Objekt oder ein Steuerelement können Sie nur Schnittstellen derzeit in einer vorhandenen Typbibliothek hinzufügen. Außerdem muss die Klasse, in dem Sie die Schnittstelle hinzufügen, implementieren die [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) Makro oder, bei das Projekt attributiert ist, muss die `coclass` Attribut.

Sie können eine neue Schnittstelle zu Ihrem Steuerelement auf zwei Arten hinzufügen: manuell oder mithilfe von Code-Assistenten in der Klassenansicht.

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Code-Assistenten in der Klassenansicht zu verwenden, um eine Schnittstelle zu einem vorhandenen Objekt oder ein Steuerelement hinzufügen

1. In [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code), mit der rechten Maustaste des Klassennamen eines Steuerelements. Z. B. eine Vollzugriff oder zusammengesetzten Steuerelement oder jede andere Control-Klasse, die in der Headerdatei ein-Makro implementiert.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Schnittstelle implementieren**.

1. Wählen Sie die Schnittstellen implementieren in der [Assistent zum Implementieren von Schnittstellen](../../ide/implement-interface-wizard.md). Wenn die Schnittstelle in keiner verfügbaren nicht vorhanden ist, müssen dann Sie die IDL-Datei manuell hinzufügen.

## <a name="to-add-a-new-interface-manually"></a>So fügen Sie eine neue Schnittstelle manuell hinzu

1. Fügen Sie die Definition der neuen Schnittstelle der IDL-Datei ein.

1. Leiten Sie Ihre Objekt oder ein Steuerelement die Schnittstelle an.

1. Erstellen Sie ein neues [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) für die Schnittstelle oder, wenn das Projekt attributiert ist, fügen Sie der `coclass` Attribut.

1. Implementieren Sie Methoden für die Schnittstelle.

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++-Projekttypen](../../build/reference/visual-cpp-project-types.md)<br/>
[Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)
