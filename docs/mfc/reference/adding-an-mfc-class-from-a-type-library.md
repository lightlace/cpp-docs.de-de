---
title: Hinzufügen einer MFC-Klasse aus einer Typbibliothek
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: e8264de2c717c874da157cb29ad5e336e3ecbd0f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301584"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Hinzufügen einer MFC-Klasse aus einer Typbibliothek

Verwenden Sie diesen Assistenten zum Erstellen einer MFC-Klasse von einer Schnittstelle in einer Bibliothek verfügbar. Sie können eine MFC-Klasse in eine [MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md), eine [MFC-DLL](../../mfc/reference/creating-an-mfc-dll-project.md) oder ein [MFC-ActiveX-Steuerelement](../../mfc/reference/creating-an-mfc-activex-control.md) einfügen.

> [!NOTE]
>  Sie müssen sich nicht zum Erstellen von eines MFC-Projekts mit der Automatisierung aktiviert, um eine Klasse aus einer Typbibliothek hinzufügen.

Eine Typbibliothek enthält eine binäre Beschreibung der Schnittstellen verfügbar gemacht, von einer Komponente, die Methoden zusammen mit ihren Parametern und Rückgabetypen definieren. Die Typbibliothek muss registriert werden, angezeigt in der **Verfügbare Typbibliotheken** Liste im Hinzufügen von Klassen aus Typelib-Assistent. Finden Sie unter "Inside Distributed COM: Geben Sie Bibliotheken und Sprachintegration"in der MSDN Library Weitere Informationen.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Hinzufügen eine MFC-Klasse aus einer Typbibliothek

1. In einem **Projektmappen-Explorer** oder [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code), mit der rechten Maustaste in des Namens des Projekts, dem Sie die Klasse hinzufügen möchten.

1. Klicken Sie im Kontextmenü auf die Option **Hinzufügen**, und klicken Sie danach auf **Klasse hinzufügen**.

1. In der [Klasse hinzufügen](../../ide/add-class-dialog-box.md) im Dialogfeld im Bereich "Vorlagen", klicken Sie auf **MFC-Klasse aus der Typbibliothek**, und klicken Sie dann auf **öffnen** zum Anzeigen der [Hinzufügen von Klassen aus Typelib-Assistent ](../../mfc/reference/add-class-from-typelib-wizard.md).

Im Assistenten können Sie mehr als eine Klasse in einer Typbibliothek hinzufügen. Ebenso können Sie Klassen aus mehr als eine Typbibliothek in einer einzelnen Assistenten-Sitzung hinzufügen.

Der Assistent erstellt eine MFC-Klasse, die von abgeleiteten [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), für jede Schnittstelle, die Sie aus der gewählten Typbibliothek hinzufügen. `COleDispatchDriver` implementiert die Clientseite der OLE-Automatisierung.

## <a name="see-also"></a>Siehe auch

[Automatisierungsclients](../../mfc/automation-clients.md)<br/>
[Benutzeroberflächenautomatisierungs-Clients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)
