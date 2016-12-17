---
title: "Schaltfl&#228;chenstile"
ms.custom: na
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "BS_DEFPUSHBUTTON"
  - "BS_NOTIFY"
  - "BS_MULTILINE"
  - "BS_AUTOCHECKBOX"
  - "BS_3STATE"
  - "BS_BITMAP"
  - "BS_TOP"
  - "BS_PUSHBUTTON"
  - "BS_PUSHLIKE"
  - "BS_AUTO3STATE"
  - "BS_CHECKBOX"
  - "BS_AUTORADIOBUTTON"
  - "BS_RADIOBUTTON"
  - "BS_OWNERDRAW"
  - "BS_LEFT"
  - "BS_USERBUTTON"
  - "BS_RIGHTBUTTON"
  - "BS_RIGHT"
  - "BS_LEFTTEXT"
  - "BS_TEXT"
  - "BS_BOTTOM"
  - "BS_GROUPBOX"
  - "BS_FLAT"
  - "BS_VCENTER"
  - "BS_ICON"
  - "BS_CENTER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BS_3STATE-Konstante"
  - "BS_AUTO3STATE-Konstante"
  - "BS_AUTOCHECKBOX-Konstante"
  - "BS_AUTORADIOBUTTON-Konstante"
  - "BS_BITMAP-Konstante"
  - "BS_BOTTOM-Konstante"
  - "BS_CENTER-Konstante"
  - "BS_CHECKBOX-Konstante"
  - "BS_DEFPUSHBUTTON-Konstante"
  - "BS_FLAT-Konstante"
  - "BS_GROUPBOX-Konstante"
  - "BS_ICON-Konstante"
  - "BS_LEFT-Konstante"
  - "BS_LEFTTEXT-Konstante"
  - "BS_MULTILINE-Konstante"
  - "BS_NOTIFY-Konstante"
  - "BS_OWNERDRAW-Konstante"
  - "BS_PUSHBUTTON-Konstante"
  - "BS_PUSHLIKE-Konstante"
  - "BS_RADIOBUTTON-Konstante"
  - "BS_RIGHT-Konstante"
  - "BS_RIGHTBUTTON-Konstante"
  - "BS_TEXT-Konstante"
  - "BS_TOP-Konstante"
  - "BS_USERBUTTON-Konstante"
  - "BS_VCENTER-Konstante"
  - "Schaltflächenobjekte (CButton), Schaltflächenstile"
  - "Stile, Schaltflächeobjekte"
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: 20
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Schaltfl&#228;chenstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden Schaltflächentypen und Stile beschrieben.  
  
## Schaltflächentypen  
 In der folgenden Tabelle werden Schaltflächentypen aufgeführt.  Sie können optional eine der folgenden Möglichkeiten auswählen.  Wenn Sie keinen Schaltflächentyp angeben, ist der Standard  `BS_PUSHBUTTON`.  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|`BS_3STATE`|Erstellt eine Kontrollkästchen\-Schaltfläche mit drei Zuständen: `BST_CHECKED`, `BST_INDETERMINATE` und  `BST_UNCHECKED`.  Durch Klicken auf die Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, das ändert allerdings den Zustand der Schaltfläche nicht.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Kontrollkästchens angezeigt.  Um Text auf der linken Seite des Kontrollkästchens anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_AUTO3STATE`|Erstellt eine Kontrollkästchen\-Schaltfläche mit drei Zuständen: `BST_CHECKED`, `BST_INDETERMINATE` und  `BST_UNCHECKED`.  Durch Klicken auf die Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, und der Zustand der Schaltfläche wird geändert.  Die Schaltflächenzustände ändern nacheinander von `BST_CHECKED` zu `BST_INDETERMINATE` zu `BST_UNCHECKED`.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Kontrollkästchens angezeigt.  Um Text auf der linken Seite des Kontrollkästchens anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_AUTOCHECKBOX`|Erstellt eine Kontrollkästchen\-Schaltfläche mit zwei Zuständen: `BST_CHECKED` und `BST_UNCHECKED`.  Durch Klicken auf die Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, und der Zustand der Schaltfläche wird geändert.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Kontrollkästchens angezeigt.  Um Text auf der linken Seite des Kontrollkästchens anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_AUTORADIOBUTTON`|Erstellt ein Optionsfeld mit zwei Zuständen: `BST_CHECKED` und `BST_UNCHECKED`.  Optionsfelder werden normalerweise in Gruppen verwendet, wobei jede Gruppe über maximal eine aktivierte Option auf einmal verfügt.  Durch Klicken auf der Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, der Zustand des Optionsfelds wird auf `BST_CHECKED` festgelegt, und die Zustände aller anderen Optionsfelder aus der Optionsfeldgruppe werden auf `BST_UNCHECKED` festgelegt.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Optionsfelds angezeigt.  Um Text auf der linken Seite des Optionsfelds anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_CHECKBOX`|Erstellt eine Kontrollkästchen\-Schaltfläche mit zwei Zuständen: `BST_CHECKED` und `BST_UNCHECKED`.  Durch Klicken auf die Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, das ändert allerdings den Zustand der Schaltfläche nicht.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Kontrollkästchens angezeigt.  Um Text auf der linken Seite des Kontrollkästchens anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_COMMANDLINK`|Erstellt eine Befehlslinkschaltfläche.  Eine Befehlslinkschaltfläche ist eine spezielle Befehlsschaltfläche von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)], die einen grünen Pfeil auf der linken Seite des zentralen Texts und eines Hinweises unterhalb des zentralen Texts anzeigt.  Sie können den Hinweistext mithilfe von [CButton::SetNote](../Topic/CButton::SetNote.md) festlegen.|  
|`BS_DEFCOMMANDLINK`|Erstellt eine Befehlslinkschaltfläche.  Eine Befehlslinkschaltfläche ist eine spezielle Befehlsschaltfläche von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)], die einen grünen Pfeil auf der linken Seite des zentralen Texts und eines Hinweises unterhalb des zentralen Texts anzeigt.  Sie können den Hinweistext mithilfe von [CButton::SetNote](../Topic/CButton::SetNote.md) festlegen.  Wenn sich die Schaltfläche in einem Dialogfeld befindet, sendet das Drücken der EINGABETASTE eine `BN_CLICKED`\-Benachrichtigung an das Dialogfeld, selbst wenn der Eingabefokus nicht auf der Schaltfläche liegt.|  
|`BS_DEFPUSHBUTTON`|Erstellt eine Befehlsschaltfläche mit einem dicken schwarzen Rand.  Wenn sich die Schaltfläche in einem Dialogfeld befindet, sendet das Drücken der EINGABETASTE eine `BN_CLICKED`\-Benachrichtigung an das Dialogfeld, selbst wenn der Eingabefokus nicht auf der Schaltfläche liegt.|  
|`BS_DEFSPLITBUTTON`|Erstellt eine unterteilte Schaltfläche.  Eine unterteilte Schaltfläche ist eine spezielle Befehlsschaltfläche von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)], die eine Schaltfläche neben einem Dropdownpfeil enthält.  Wenn Sie auf die Schaltfläche klicken, wird der standardmäßige Befehl ausgeführt.  Wenn Sie auf den Dropdownpfeil klicken, wird ein Menü mit zusätzlichen Befehlen angezeigt.  Wenn sich die unterteilte Schaltfläche in einem Dialogfeld befindet, sendet das Drücken der EINGABETASTE eine `BN_CLICKED`\-Benachrichtigung an das Dialogfeld, selbst wenn der Eingabefokus nicht auf der Schaltfläche liegt.|  
|`BS_GROUPBOX`|Erstellt ein Rechteck, in dem andere Schaltflächen gruppiert werden können.  Text, der diesem Stil zugeordnet ist, wird in der oberen linken Ecke des Rechtecks angezeigt.|  
|`BS_OWNERDRAW`|Erstellt eine Ownerdrawn\-Schaltfläche.  Die `DrawItem`\-Methode wird vom Framework aufgerufen, wenn sich ein visueller Aspekt der Schaltfläche geändert hat.  Dieser Stil muss bei Verwendung der `CBitmapButton`\-Klasse festgelegt werden.|  
|`BS_PUSHBUTTON`|Erstellt eine Befehlsschaltfläche, die eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster sendet, wenn der Benutzer auf die Schaltfläche klickt.|  
|`BS_RADIOBUTTON`|Erstellt ein Optionsfeld mit zwei Zuständen: `BST_CHECKED` und `BST_UNCHECKED`.  Optionsfelder werden normalerweise in Gruppen verwendet, wobei jede Gruppe über maximal eine aktivierte Option auf einmal verfügt.  Durch Klicken auf der Schaltfläche wird eine `BN_CLICKED`\-Benachrichtigung an das Besitzerfenster gesendet, der Zustand einer Schaltfläche in der Gruppe ändert sich allerdings nicht automatisch.  Standardmäßig wird zugehöriger Text auf der rechten Seite des Optionsfelds angezeigt.  Um Text auf der linken Seite des Optionsfelds anzuzeigen, verwenden Sie den `BS_LEFTTEXT`\-Stil oder den `BS_RIGHTBUTTON`\-Stil.|  
|`BS_SPLITBUTTON`|Erstellt eine unterteilte Schaltfläche.  Eine unterteilte Schaltfläche ist eine spezielle Befehlsschaltfläche von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)], die eine Schaltfläche neben einem Dropdownpfeil enthält.  Wenn Sie auf die Schaltfläche klicken, wird der standardmäßige Befehl ausgeführt.  Wenn Sie auf den Dropdownpfeil klicken, wird ein Menü mit zusätzlichen Befehlen angezeigt.|  
|`BS_USERBUTTON`|Veraltet, wird jedoch für die Kompatibilität mit 16\-Bit\-Versionen von Windows bereitgestellt.  Für Win32\-basierte Anwendungen sollte stattdessen `BS_OWNERDRAW` verwendet werden.|  
  
## Optionsfeld\- und Kontrollkästchen\-Stile  
 In der folgenden Tabelle werden Stile aufgeführt, die für Optionsfelder und Kontrollkästchen spezifisch sind.  Diese Stile werden bei allen anderen Schaltflächentypen ignoriert.  Sie können optional mindestens eine der folgenden Möglichkeiten auswählen.  
  
|Stil|**Beschreibung**|  
|----------|----------------------|  
|`BS_LEFTTEXT`|Bei Kombination mit einem Optionsfeld\- oder Kontrollkästchenstil wird der Text auf der linken Seite des Optionsfelds oder Kontrollkästchens angezeigt.|  
|`BS_RIGHTBUTTON`|Bei Kombination mit einem Optionsfeld\- oder Kontrollkästchenstil wird der Text auf der linken Seite des Optionsfelds oder Kontrollkästchens angezeigt.  Dieser Stil ist mit dem `BS_LEFTTEXT`\-Stil identisch.|  
|`BS_PUSHLIKE`|Dadurch wird ein Kontrollkästchen\- oder Optionsfeld im Aussehen und Verhalten zu einer Befehlsschaltfläche.  Die Schaltfläche wird gedrückt angezeigt, wenn ihr Zustand `BST_CHECKED` ist. Sie wird gedrückt und abgeblendet dargestellt, wenn ihr Zustand `BST_INDETERMINATE` ist, und freigegeben, wenn ihr Zustand `BST_UNCHECKED` ist.|  
  
## Textausrichtungsstile  
 In der folgenden Tabelle werden die Optionen für horizontale und vertikale Textausrichtung aufgeführt.  Sie können optional eine der folgenden Möglichkeiten auswählen.  
  
|Stil|**Beschreibung**|  
|----------|----------------------|  
|`BS_LEFT`|Links richtet den Text im Schaltflächenrechteck aus.  Wenn die Schaltfläche allerdings ein Kontrollkästchen oder ein Optionsfeld ist, die nicht über den `BS_RIGHTBUTTON`\-Stil verfügt, wird der Text auf der rechten Seite des Kontrollkästchens oder des Optionsfelds links ausgerichtet.|  
|`BS_RIGHT`|Rechts richtet den Text im Schaltflächenrechteck aus.  Wenn die Schaltfläche allerdings ein Kontrollkästchen oder ein Optionsfeld ist, die nicht über den `BS_RIGHTBUTTON`\-Stil verfügt, wird der Text auf der rechten Seite des Kontrollkästchens oder des Optionsfelds rechts ausgerichtet.|  
|`BS_CENTER`|Zentriert Text horizontal im Schaltflächenrechteck.|  
|`BS_TOP`|Setzt Text an den oberen Rand des Schaltflächenrechtecks.|  
|`BS_BOTTOM`|Setzt Text an den unteren Rand des Schaltflächenrechtecks.|  
|`BS_VCENTER`|Zentriert Text vertikal im Schaltflächenrechteck.|  
  
## Schaltflächeninhaltsoptionen  
 In der folgenden Tabelle sind die Optionen aufgeführt, die angeben, was in der Schaltfläche angezeigt wird.  Schaltflächentypen, die nur Text anzeigen, ignorieren diese Stile.  Sie können optional eine der folgenden Möglichkeiten auswählen.  
  
|Stil|**Beschreibung**|  
|----------|----------------------|  
|`BS_BITMAP`|Gibt an, dass die Schaltfläche eine Bitmap anzeigt.|  
|`BS_ICON`|Gibt an, dass die Schaltfläche ein Symbol anzeigt.|  
|`BS_TEXT`|Gibt an, dass die Schaltfläche Text anzeigt.|  
  
## Weitere Optionen  
 In der folgenden Tabelle werden zusätzliche Optionen aufgeführt, die Sie mit jedem Schaltflächentyp verwenden können.  Sie können optional mindestens eine der folgenden Möglichkeiten auswählen.  
  
|Stil|**Beschreibung**|  
|----------|----------------------|  
|`BS_FLAT`|Gibt an, dass die Schaltfläche zweidimensional ist und nicht zum Erstellen eines dreidimensionalen Bilds mit Standardschattierung gezeichnet wird.|  
|`BS_MULTILINE`|Bricht den Schaltflächentext in mehrere Zeilen um, wenn die Zeichenfolge für eine einzelne Zeile im Schaltflächenrechteck zu lang ist.|  
|`BS_NOTIFY`|Aktiviert eine Schaltfläche, um die Benachrichtigungsmeldungen `BN_DBLCLK`, `BN_KILLFOCUS` und `BN_SETFOCUS` an das übergeordnete Fenster zu senden.  Beachten Sie, dass die Schaltflächen die `BN_CLICKED`\-Benachrichtigung unabhängig von der Angabe dieses Stil senden.|  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../Topic/CButton::Create.md)   
 [Button Stile](http://msdn.microsoft.com/library/windows/desktop/bb775951)   
 [BN\_CLICKED Notification](_win32_bn_clicked_notification)