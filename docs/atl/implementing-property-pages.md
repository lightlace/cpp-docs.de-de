---
title: Implementieren von Eigenschaftenseiten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1db6ca4ea374cd76d5b0e1df8e6c0cd03474fdf2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-property-pages"></a>Implementieren von Eigenschaftenseiten
Eigenschaftenseiten sind COM-Objekte implementiert, die `IPropertyPage` oder **IPropertyPage2** Schnittstelle. ATL stellt Unterstützung für das Implementieren von Eigenschaftenseiten über die [ATL-Eigenschaftenseiten-Assistent](../atl/reference/atl-property-page-wizard.md) in der [Klasse hinzufügen (Dialogfeld)](../ide/add-class-dialog-box.md).  
  
 So erstellen Sie eine Eigenschaftenseite mit ATL  
  
-   Erstellen Sie oder öffnen Sie eine ATL-Dynamic Link Library (DLL)-Server-Projekt.  
  
-   Öffnen der [Klasse hinzufügen (Dialogfeld)](../ide/add-class-dialog-box.md) , und wählen Sie **ATL-Eigenschaftenseite**.  
  
-   Stellen Sie sicher, dass die Eigenschaftenseite apartmentthreadpaket (da sie über eine Benutzeroberfläche verfügt).  
  
-   Legen Sie Titel, Beschreibung (Doc String) und Hilfe-Datei mit der Seite zugeordnet werden soll.  
  
-   Fügen Sie Steuerelemente auf die generierten Dialogressource, als die Benutzeroberfläche der Eigenschaftenseiten zu fungieren.  
  
-   Reagieren Sie auf Änderungen in der Seite der Benutzeroberfläche für die Validierung ausführen, aktualisieren Sie die Seite Standort oder aktualisieren die Objekte zugeordnet sind, mit der Seite. Rufen Sie insbesondere [:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) Wenn der Benutzer mit der Änderungen an der Eigenschaftenseite.  
  
-   Überschreiben Sie optional die `IPropertyPageImpl` Methoden, die über die folgenden Richtlinien.  
  
    |IPropertyPageImpl-Methode|Überschreiben Sie, wenn Sie möchten...|Hinweise|  
    |------------------------------|----------------------------------|-----------|  
    |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|Führen Sie grundlegende Rückfragen auf die Anzahl der Objekte, die auf der Seite und die Schnittstellen, die sie unterstützen übergeben werden.|Führen Sie Ihren eigenen Code vor der Implementierung der Basisklasse aufrufen. Wenn die Objekte, die festgelegt wird nicht Ihren Erwartungen entspricht, sollten Sie so bald wie möglich der Aufruf fehl.|  
    |[Aktivieren](../atl/reference/ipropertypageimpl-class.md#activate)|Initialisieren Sie die Seite-Benutzeroberfläche (z. B. Festlegen der Dialogfeld-Steuerelemente mit aktuellen Eigenschaftswerten von Objekten, erstellen Sie dynamisch Steuerelemente oder andere Initialisierungen durchzuführen).|Rufen Sie die Implementierung der Basisklasse vor dem Code die Basisklasse verfügt über eine Möglichkeit, im Dialogfenster und alle Steuerelemente erstellen, bevor Sie versuchen, diese zu aktualisieren.|  
    |[Anwenden](../atl/reference/ipropertypageimpl-class.md#apply)|Überprüfen Sie die eigenschafteneinstellungen und aktualisieren Sie die Objekte zu.|Es ist nicht erforderlich, die Implementierung der Basisklasse aufgerufen werden, da alles außer Trace den Aufruf nicht möglich ist.|  
    |[Deaktivieren](../atl/reference/ipropertypageimpl-class.md#deactivate)|Bereinigen Sie fensterbezogene Elemente.|Die basisklassenimplementierung zerstört das Dialogfeld, das die Eigenschaftenseite darstellt. Wenn Sie müssen zum Bereinigen, bevor Sie das Dialogfeld zerstört wird, sollten Sie den Code vor dem Aufruf der Basisklasse hinzufügen.|  
  
 Eigenschaftenimplementierung Seite ein Beispiel finden Sie unter [Beispiel: Implementieren einer Eigenschaftenseite](../atl/example-implementing-a-property-page.md).  
  
> [!NOTE]
>  Sie nach Bedarf Host ActiveX-Steuerelemente auf der Eigenschaftenseite, müssen Sie die Ableitung der vom Assistenten generierten Klasse ändern. Ersetzen Sie **CDialogImpl\<CYourClass >** mit **CAxDialogImpl\<CYourClass >** in der Liste der Basisklassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages-Beispiel](../visual-cpp-samples.md)

