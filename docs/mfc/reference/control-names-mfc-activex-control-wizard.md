---
title: Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.names
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 28ef331cb66ee184c4bc104fedddf69e9296367c
ms.lasthandoff: 04/04/2017

---
# <a name="control-names-mfc-activex-control-wizard"></a>Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent
Geben Sie die Namen für die Control-Klasse und die Page-Klasse, die Typnamen, und geben Sie die Bezeichner für das Steuerelement. Mit Ausnahme von **Kurzname**, alle anderen Felder können unabhängig voneinander bearbeitet werden. Wenn Sie den Text für ändern **Kurzname**, in den Namen der alle anderen Felder auf dieser Seite wird die Änderung übernommen. Dieses naming Verhalten wurde entworfen, um alle Namen leicht erkennbaren für Sie bereitzustellen bei der Entwicklung Ihrer Kontrolle.  
  
 **Kurzname**  
 Geben Sie einen abgekürzten Namen für das Steuerelement. Dieser Name basiert standardmäßig auf den Projektnamen, die Sie gemäß den **neues Projekt** (Dialogfeld). Der Namen, den Sie angeben, bestimmt die Klassennamen, den Typnamen und die Typ-IDs, wenn Sie diese Felder einzeln ändern.  
  
 **Steuerelementname-Klasse**  
 Standardmäßig der Namen der Steuerelementklasse basiert auf den kurzen Namen und `C` als Präfix und `Ctrl` als Suffix. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, ist der Name der Steuerelementklasse `CPriceCtrl`.  
  
 **Steuerelement .h-Datei**  
 Der Name der Headerdatei basiert standardmäßig auf den kurzen Namen mit `Ctrl` als Suffix und `.h` als Dateierweiterung. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, ist der Name der Headerdatei `PriceCtrl.h`. Der Name in diesem Feld sollte den Namen der Steuerelementklasse übereinstimmen.  
  
 **Steuerelement cpp-Datei**  
 Der Name der Headerdatei basiert standardmäßig auf den kurzen Namen mit `Ctrl` als Suffix und `.cpp` als Dateierweiterung. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, ist der Name der Headerdatei `PriceCtrl.cpp`. Der Name in diesem Feld übereinstimmen, den Headernamen an.  
  
 **Steuerelementtypnamen**  
 Der Name des Steuerelementtyps basiert standardmäßig auf den kurzen Namen, gefolgt von `Control`. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, ist der Name der Steuerelementklasse Typ `Price Control`. Wenn Sie den Wert in diesem Feld ändern, stellen Sie sicher, dass der Name eine Vererbung angibt.  
  
 **Steuerelementtyp-ID**  
 Legt die Steuerelement-ID von der Control-Klasse. Wenn es zu einem Projekt hinzugefügt wird, schreibt das Steuerelement diese Zeichenfolge in der Registrierung. Containeranwendungen verwenden Sie diese Zeichenfolge zum Erstellen einer Instanz des Steuerelements.  
  
 Standardmäßig basiert auf den Projektnamen, den Sie angegeben haben, in die Steuerelement-ID der **neues Projekt** (Dialogfeld), und den kurzen Namen. Dieser Name sollte den vollständigen Typnamen übereinstimmen.  
  
 Standardmäßig wird die Steuerelement-ID wie folgt angezeigt:  
  
 *ProjectName.ShortName*. 1.  
  
 Wenn Sie den kurzen Namen in diesem Dialogfeld ändern Sie die Steuerelement-ID sieht wie folgt aus:  
  
 *Wird*. 1.  
  
 **Name der PropPage-Klasse**  
 Wird standardmäßig der Name der Eigenschaft Page-Klasse basiert auf den kurzen Namen und `C` als Präfix und `PropPage` als Suffix. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, Seite "der Name der Klasse ist `CPricePropPage`. Diese Namen übereinstimmen, den Klassennamen für das Steuerelement mit angefügtem `PropPage`.  
  
 **PropPage .h-Datei**  
 Wird standardmäßig der Name der Eigenschaft Seite Headerdatei wird basierend auf den kurzen Namen mit als eine `PropPage` als Suffix und `.h` als Dateierweiterung. Angenommen, wenn das Steuerelement der kurze Name ist `Price`, ist die Eigenschaft Header-Datei Seitennamen `PricePropPage.h`. Dieser Name sollte der Name der Klasse übereinstimmen.  
  
 **PropPage cpp-Datei**  
 Wird standardmäßig der Name der Eigenschaft Seite Implementierungsdatei basiert auf den kurzen Namen mit als eine `PropPage` als Suffix und `.cpp` als Dateierweiterung. Angenommen, wenn das Steuerelement der kurze Name ist `Price`, ist die Eigenschaft Header-Datei Seitennamen `PricePropPage.cpp`. Dieser Name sollte der Name des Header-Datei übereinstimmen.  
  
 **PropPage-Typname**  
 Standardmäßig basiert auf den kurzen Namen, gefolgt von der Eigenschaft Seite Typname `Property Page`. Beispielsweise, wenn das Steuerelement der kurze Name ist `Price`, ist die Eigenschaft Typ Seitennamen `Price Property Page`. Wenn Sie den Wert in diesem Feld ändern, stellen Sie sicher, dass die Namen die Steuerelementklasse angibt.  
  
 **PropPage Typ-ID**  
 Legt die ID der Eigenschaft Page-Klasse. Das Steuerelement schreibt diese Zeichenfolge in der Registrierung, wenn sie einem Projekt angewendet wird. Eine Steuerelementcontainer-Anwendung verwendet diese Zeichenfolge zum Erstellen einer Instanz der Eigenschaftenseite des Steuerelements.  
  
 Standardmäßig basiert auf den Projektnamen, den Sie angegeben haben, in die Typ-ID der **neues Projekt** (Dialogfeld), und den kurzen Namen. Dieser Name sollte den vollständigen Typnamen übereinstimmen.  
  
 Standardmäßig wird die Typ-ID wie folgt angezeigt:  
  
 *ProjectName.ShortName*. 1.  
  
 Wenn Sie den kurzen Namen in diesem Dialogfeld ändern, wird die Typ-ID wie folgt angezeigt:  
  
 *Wird*. 1.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Steuerelementeinstellungen Sie, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md)


