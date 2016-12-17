---
title: "Implementing Property Pages"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage class"
  - "IPropertyPage2 class"
  - "Eigenschaftenseiten, Implementieren"
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eigenschaftenseiten sind COM\-Objekte, die `IPropertyPage` oder die **IPropertyPage2**\-Schnittstelle implementieren.  ATL bietet Unterstützung für das Implementieren von Eigenschaftenseiten von [ATL\-Eigenschaftenseiten\-Assistent](../atl/reference/atl-property-page-wizard.md) in [Fügen Sie Klassendialogfeld hinzu](../ide/add-class-dialog-box.md).  
  
 So fügen Sie eine Eigenschaftenseite mit ATL erstellen:  
  
-   Erstellen oder öffnen Sie ein Serverprojekt ATL\-DynamicLink Library \(DLL\).  
  
-   Öffnen Sie [Fügen Sie Klassendialogfeld hinzu](../ide/add-class-dialog-box.md) und wählen Sie **ATL\-Eigenschaftenseite** aus.  
  
-   Stellen Sie sicher, dass die Eigenschaftenseite das verlegte Apartment befindet \(da sie eine Benutzeroberfläche besitzt\).  
  
-   Legen Sie den Namen, die Beschreibung \(Doc. Zeichenfolgen\-\) und die der Seite zugeordnet werden Hilfedatei, fest.  
  
-   Fügen Sie Steuerelemente der generierten Dialogfeldressource hinzu, die als Benutzeroberfläche der Eigenschaftenseite fungiert.  
  
-   Reagieren auf Änderungen in der Benutzeroberfläche der Seite, um die Validierung auszuführen, die Seitensite zu aktualisieren, oder die Objekte zu aktualisieren, die der Seite zugeordnet werden.  Insbesondere Aufruf [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md), wenn ein Benutzer Änderungen an der Eigenschaftenseite vornimmt.  
  
-   Überschreiben Sie optional die `IPropertyPageImpl`\-Methoden mithilfe der Richtlinien unten.  
  
    |IPropertyPageImpl\-Methode|Überschreiben Sie, wenn Sie möchten...|Hinweise|  
    |--------------------------------|--------------------------------------------|--------------|  
    |[SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|Ausführen grundlegender Plausibilitätsprüfungen auf der Anzahl von Objekten aus, die der Seite und auf Schnittstellen, die sie unterstützen, übergeben werden.|Ausführen von eigenem Code, bevor Sie die Basisklassenimplementierung aufrufen.  Wenn die Objekte, die festgelegt werden, nicht an Ihren Erwartungen anpassen, sollten Sie den Aufruf so schnell wie möglich beibehalten.|  
    |[Aktivieren Sie](../Topic/IPropertyPageImpl::Activate.md)|Initialisieren Sie die Benutzeroberfläche der Seite \(beispielsweise, legen Sie Dialogfeld\-Steuerelemente mit aktuellen Eigenschaftswerten von Objekten fest, erstellen Sie Steuerelemente dynamisch oder führen Sie andere Initialisierungen aus\).|Rufen Sie die Basisklassenimplementierung vor dem Code auf, sodass die Basisklasse eine Möglichkeit haben, das Dialogfeld zu erstellen und alle Steuerelemente, bevor Sie versuchen, diese zu aktualisieren.|  
    |[Übernehmen](../Topic/IPropertyPageImpl::Apply.md)|Überprüfen Sie die Eigenschafteneinstellungen und aktualisieren Sie die Objekte.|Es ist nicht erforderlich, die Basisklassenimplementierung aufzurufen, da sie keine abgesehen von der Ablaufverfolgung Aufruf geschieht.|  
    |[Deaktivieren Sie](../Topic/IPropertyPageImpl::Deactivate.md)|Löschen Sie fensterbezogene Elemente auf.|Die Basisklassenimplementierung zerstört das Dialogfeld, das die Eigenschaftenseite darstellt.  Wenn Sie bereinigen müssen, bevor das Dialogfeld zerstört wird, sollten Sie den Code hinzufügen, bevor Sie die Basisklasse aufrufen.|  
  
 Ein Beispiel finden Eigenschaftenseitenimplementierung, [Beispiel: Implementieren einer Eigenschaftenseite](../atl/example-implementing-a-property-page.md).  
  
> [!NOTE]
>  Wenn Sie ActiveX\-Steuerelemente in der Eigenschaftenseite hosten möchten, müssen Sie die Ableitung der vom Assistenten generierte Klasse ändern.  Ersetzen Sie **CDialogImpl\<CYourClass\>** durch **CAxDialogImpl\<CYourClass\>** in der Liste der Basisklassen.  
  
## Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages\-Beispiel](../top/visual-cpp-samples.md)