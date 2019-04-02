---
title: Implementieren der Eigenschaftenseiten
ms.date: 11/04/2016
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
ms.openlocfilehash: 8999f6469e420fa86cb1267675f10dc173d45ff0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776247"
---
# <a name="implementing-property-pages"></a>Implementieren der Eigenschaftenseiten

Eigenschaftenseiten sind COM-Objekte, implementieren die `IPropertyPage` oder `IPropertyPage2` Schnittstelle. ATL bietet Unterstützung für das Implementieren der Eigenschaftenseiten über die [ATL-Eigenschaftenseiten-Assistent](../atl/reference/atl-property-page-wizard.md) in die [Dialogfeld Klasse hinzufügen](../ide/add-class-dialog-box.md).

So erstellen Sie eine Eigenschaftenseite mit ATL

- Erstellen Sie oder öffnen Sie ein Serverprojekt für ATL-Dynamic Link Library (DLL).

- Öffnen der [Dialogfeld Klasse hinzufügen](../ide/add-class-dialog-box.md) , und wählen Sie **ATL-Eigenschaftenseite**.

- Stellen Sie sicher, dass Ihr Eigenschaftenseite apartmentthreadpaket (da es sich um eine Benutzeroberfläche besitzt).

- Legen Sie den Titel, Beschreibung (Doc-Zeichenfolge) und die Hilfedatei, um die Seite zugeordnet werden soll.

- Fügen Sie Steuerelemente auf die generierten Dialogressource, als die Benutzeroberfläche der Ihre Eigenschaftenseite zu fungieren.

- Reagieren Sie auf Änderungen in Ihrer Seite auf der Benutzeroberfläche für die eine Überprüfung durchführen, aktualisieren die Site der Seite oder die Objekte zugeordnet sind, mit der Seite zu aktualisieren. Rufen Sie vor allem [:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) Wenn der Benutzer Änderungen vornimmt, auf der Eigenschaftenseite.

- Überschreiben Sie optional die `IPropertyPageImpl` Methoden, die mithilfe des Leitfadens untenan.

   |IPropertyPageImpl-Methode|Außer Kraft setzen, wenn Sie möchten...|Hinweise|
   |------------------------------|----------------------------------|-----------|
   |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|Führen Sie grundlegende wurden die integritätsprüfungen für die Anzahl der Objekte übergeben werden, um die Seite und die Schnittstellen, die sie unterstützen.|Führen Sie Ihren eigenen Code vor der Implementierung der Basisklasse aufrufen. Wenn die Objekte, die festgelegt wird nicht Ihren Erwartungen entsprechen, sollten Sie so bald wie möglich der Aufruf fehl.|
   |[Aktivieren](../atl/reference/ipropertypageimpl-class.md#activate)|Initialisieren Sie Ihrer Seite Benutzeroberfläche (z. B. Festlegen der Dialogfeld-Steuerelemente mit aktuellen Eigenschaftswerten von Objekten, erstellen Sie dynamisch Steuerelemente oder andere Initialisierungen durchführen).|Rufen Sie die basisklassenimplementierung, bevor Sie Ihren Code, sodass die Basisklasse der Klasse hat die Möglichkeit, das Dialogfeld und alle Steuerelemente erstellen, bevor Sie versuchen, die sie aktualisieren.|
   |[Anwenden](../atl/reference/ipropertypageimpl-class.md#apply)|Überprüfen Sie die eigenschafteneinstellungen, und aktualisieren Sie die Objekte.|Es ist nicht erforderlich, die Implementierung der Basisklasse aufrufen, da nichts außer der Ablaufverfolgung des Aufrufs nicht möglich ist.|
   |[Deaktivieren](../atl/reference/ipropertypageimpl-class.md#deactivate)|Bereinigen Sie bezogenen Elemente.|Die basisklassenimplementierung zerstört das Dialogfeld, das die Eigenschaftenseite darstellt. Bei Bedarf bereinigt werden, bevor Sie das Dialogfeld zerstört wird, sollten Sie Ihren Code vor dem Aufruf der Basisklasse hinzufügen.|

Eine Implementierung der Beispiel-Eigenschaft-Seite, finden Sie unter [Beispiel: Implementieren einer Eigenschaftenseite](../atl/example-implementing-a-property-page.md).

> [!NOTE]
> Wenn Sie zum Hosten von ActiveX-Steuerelementen in Ihr Eigenschaftenseite möchten, müssen Sie die Ableitung der vom Assistenten generierten Klasse zu ändern. Ersetzen Sie dies **CDialogImpl\<CYourClass >** mit **CAxDialogImpl\<CYourClass >** in der Liste der Basisklassen.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../atl/atl-com-property-pages.md)<br/>
[ATLPages-Beispiel](../overview/visual-cpp-samples.md)
