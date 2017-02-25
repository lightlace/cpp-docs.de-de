---
title: "Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.names"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelement-Assistent, Steuerelementnamen"
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legen Sie für das Steuerelement die Namen der Steuerelement\- und Eigenschaftenseitenklassen, die Typnamen und Typenbezeichner fest.  Mit Ausnahme von **Kurzer Name** können alle anderen Felder unabhängig voneinander bearbeitet werden.  Wenn Sie den Text für **Kurzer Name** ändern, wirkt sich diese Änderung auch auf die Namen in allen anderen Feldern auf dieser Seite aus.  Das Namenssystem ist so ausgelegt, dass alle Namen während der Entwicklung des Steuerelements leicht identifizierbar sind.  
  
 **Kurzer Name**  
 Geben Sie einen abgekürzten Namen für das Steuerelement ein.  Dieser Name basiert standardmäßig auf dem Projektnamen, der im Dialogfeld **Neues Projekt** eingegeben wird.  Durch den angegebenen Namen werden die Namen von Klassen, Typen und Typenbezeichnern festgelegt, es sei denn, diese Felder werden nachträglich separat geändert.  
  
 **Steuerelementklassenname**  
 Der Name der Steuerelementklasse basiert standardmäßig auf dem kurzen Namen, wobei `C` als Präfix und `Ctrl` als Suffix verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Steuerelementklasse beispielsweise den Namen `CPriceCtrl`.  
  
 **Steuerelement .h\-Datei**  
 Der Name der Headerdatei basiert standardmäßig auf dem kurzen Namen, wobei `Ctrl` als Suffix und `.h` als Dateierweiterung verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Headerdatei beispielsweise den Namen `PriceCtrl.h`.  Der Name in diesem Feld sollte mit dem Namen der Steuerelementklasse übereinstimmen.  
  
 **Steuerelement .cpp\-Datei**  
 Der Name der Headerdatei basiert standardmäßig auf dem kurzen Namen, wobei `Ctrl` als Suffix und `.cpp` als Dateierweiterung verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Headerdatei beispielsweise den Namen `PriceCtrl.cpp`.  Der Name in diesem Feld sollte mit dem Headernamen übereinstimmen.  
  
 **Steuerelement Typname**  
 Der Name des Steuerelementtyps basiert standardmäßig auf dem kurzen Namen, gefolgt von `Control`.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Steuerelementklasse beispielsweise den Typnamen `Price Control`.  Wenn Sie den Wert in diesem Feld ändern, sollten Sie sicherstellen, dass der Name eine Vererbung erkennen lässt.  
  
 **Steuerelement Typ\-ID**  
 Legt die Steuerelementtyp\-ID der Steuerelementklasse fest.  Diese Zeichenfolge wird vom Steuerelement in die Registrierung geschrieben, sobald es einem Projekt hinzugefügt wird.  In Containeranwendungen wird diese Zeichenfolge verwendet, um eine Instanz des Steuerelements zu erstellen.  
  
 Die Steuerelementtyp\-ID basiert standardmäßig auf dem Projektnamen, den Sie im Dialogfeld **Neues Projekt** angegeben haben, sowie auf dem kurzen Namen.  Dieser Name sollte mit dem Typnamen übereinstimmen.  
  
 Die Steuerelementtyp\-ID wird standardmäßig wie folgt angezeigt:  
  
 *ProjectName*.*ShortName*Ctrl.1  
  
 Wenn Sie den kurzen Namen in diesem Dialogfeld ändern, wird die Steuerelementtyp\-ID wie folgt angezeigt:  
  
 *ProjectName*.*NewShortName*Ctrl.1  
  
 **PropPage\-Klassenname**  
 Der Name der Eigenschaftenseitenklasse basiert standardmäßig auf dem kurzen Namen, wobei `C` als Präfix und `PropPage` als Suffix verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Eigenschaftenseitenklasse beispielsweise den Namen `CPricePropPage`.  Dieser Name sollte mit dem Namen der Steuerelementklasse übereinstimmen, an den `PropPage` angefügt ist.  
  
 **PropPage .h\-Datei**  
 Der Name der Eigenschaftenseiten\-Headerdatei basiert standardmäßig auf dem kurzen Namen, wobei `PropPage` als Suffix und `.h` als Dateierweiterung verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Eigenschaftenseiten\-Headerdatei beispielsweise den Namen `PricePropPage.h`.  Dieser Name sollte mit dem Klassennamen übereinstimmen.  
  
 **PropPage .cpp\-Datei**  
 Der Name der Eigenschaftenseiten\-Implementierungsdatei basiert standardmäßig auf dem kurzen Namen, wobei `PropPage` als Suffix und `.cpp` als Dateierweiterung verwendet wird.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat die Eigenschaftenseiten\-Headerdatei beispielsweise den Namen `PricePropPage.cpp`.  Dieser Name sollte mit dem Headerdateinamen übereinstimmen.  
  
 **PropPage\-Typname**  
 Der Name für den Eigenschaftenseitentyp basiert standardmäßig auf dem kurzen Namen, gefolgt von `Property Page`.  Wenn der kurze Name des Steuerelements `Price` lautet, dann hat der Eigenschaftenseitentyp beispielsweise den Namen `Price Property Page`.  Wenn Sie den Wert in diesem Feld ändern, sollten Sie sicherstellen, dass der Name die Steuerelementklasse angibt.  
  
 **PropPage Typ\-ID**  
 Legt die ID der Eigenschaftenseitenklasse fest.  Diese Zeichenfolge wird vom Steuerelement in die Registrierung geschrieben, sobald es auf ein Projekt angewendet wird.  In Containeranwendungen wird diese Zeichenfolge verwendet, um eine Instanz der Eigenschaftenseite des Steuerelements zu erstellen.  
  
 Die Eigenschaftenseitentyp\-ID basiert auf dem Projektnamen, den Sie im Dialogfeld **Neues Projekt** angegeben haben, sowie auf dem kurzen Namen.  Dieser Name sollte mit dem Typnamen übereinstimmen.  
  
 Die Eigenschaftenseitentyp\-ID wird standardmäßig wie folgt angezeigt:  
  
 *ProjectName*.*ShortName*PropPage.1  
  
 Wenn Sie den kurzen Namen in diesem Dialogfeld ändern, wird die Eigenschaftenseitentyp\-ID wie folgt angezeigt:  
  
 *ProjectName*.*NewShortName*PropPage.1  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Anwendungseinstellungen, MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Steuerelementeinstellungen, MFC\-ActiveX\-Steuerelement\-Assistent](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md)