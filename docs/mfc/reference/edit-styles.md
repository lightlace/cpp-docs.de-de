---
title: Bearbeiten von Stilen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ES_READONLY
- ES_WANTRETURN
- ES_UPPERCASE
- ES_NUMBER
- ES_AUTOHSCROLL
- ES_LOWERCASE
- ES_RIGHT
- ES_MULTILINE
- ES_PASSWORD
- ES_NOHIDESEL
- ES_OEMCONVERT
- ES_LEFT
- ES_CENTER
dev_langs:
- C++
helpviewer_keywords:
- ES_WANTRETURN constant
- edit styles [MFC]
- ES_RIGHT constant
- ES_READONLY constant
- ES_PASSWORD constant
- ES_MULTILINE constant
- ES_LEFT constant
- ES_AUTOVSCROLL constant
- ES_OEMCONVERT constant
- ES_LOWERCASE constant
- ES_NUMBER constant
- ES_UPPERCASE constant
- ES_NOHIDESEL constant
- ES_AUTOHSCROLL constant
- ES_CENTER constant
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 275e0d2dede038bdbe9061bc8051408442aa70bf
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="edit-styles"></a>Bearbeiten von Stilen
-   **ES_AUTOHSCROLL** automatisch den Bildlauf nach rechts um 10 Zeichen bei der Benutzer ein Zeichen am Ende der Zeile. Wenn der Benutzer die EINGABETASTE drückt, den Bildlauf des Steuerelements alle an Position 0.  
  
-   **ES_AUTOVSCROLL** automatisch den Bildlauf eine Seite nach oben beim Drücken der EINGABETASTE in der letzten Zeile.  
  
-   **ES_CENTER** Rechenzentren Text in einem ein- oder mehrzeiligen edit-Steuerelement.  
  
-   **ES_LEFT** richtet Text in einem ein- oder mehrzeiligen edit-Steuerelement.  
  
-   **ES_LOWERCASE** konvertiert alle Zeichen in Kleinbuchstaben, wie sie in das Bearbeitungssteuerelement eingegeben wurden.  
  
-   **ES_MULTILINE** ein mehrzeiliges Bearbeitungssteuerelement festlegt. (Der Standardwert ist ein einzeiliger.) Wenn die **ES_AUTOVSCROLL** Stil angegeben wird, das Edit-Steuerelement zeigt, wie viele Zeilen wie möglich und vertikal verschiebt, wenn der Benutzer die EINGABETASTE drückt. Wenn **ES_AUTOVSCROLL** ist nicht angegeben, das Edit-Steuerelement zeigt so viele Zeilen wie möglich und Signaltöne Wenn die EINGABETASTE gedrückt wird, wenn keine weiteren Zeilen angezeigt werden können. Wenn die **ES_AUTOHSCROLL** Stil angegeben ist, wird das mehrzeilige Edit-Steuerelement automatisch ein horizontaler Bildlauf durchgeführt Wenn die Einfügemarke nach dem rechten Rand des Steuerelements wechselt. Um eine neue Zeile zu beginnen, muss der Benutzer die EINGABETASTE drücken. Wenn **ES_AUTOHSCROLL** ist nicht angegeben wird, das automatisch umschließt Wörter an den Anfang der nächsten Zeile bei Bedarf, eine neue Zeile wird auch gestartet werden, wenn Sie die EINGABETASTE drücken. Die Position der Wordwrap wird durch die Fenstergröße bestimmt. Wenn die Fenstergröße ändert, die Wordwrap Position ändert sich und der Text wird erneut angezeigt. Mehrzeilige Edit-Steuerelemente können Bildlaufleisten angezeigt. Ein Edit-Steuerelement mit Bildlaufleisten verarbeitet eigene Bildlaufleisten-Nachrichten. Edit-Steuerelemente ohne Bildlauf Balken Rollen wie oben beschrieben, und Verarbeiten von Fehlermeldungen führen Sie einen Bildlauf durch das übergeordnete Fenster gesendet.  
  
-   **ES_NOHIDESEL** ein Bearbeitungssteuerelement Blendet normalerweise die Auswahl, wenn das Steuerelement den Eingabefokus verliert und die Auswahl, kehrt Wenn das Steuerelement den Eingabefokus erhält. Angeben von **ES_NOHIDESEL** werden standardmäßig gelöscht.  
  
-   **ES_NUMBER** nur Ziffern in das Bearbeitungssteuerelement eingegeben werden können.  
  
-   **ES_OEMCONVERT** in das Bearbeitungssteuerelement eingegebenen Text aus dem ANSI-Zeichensatz an den OEM-Zeichensatz und klicken Sie dann auf ANSI-Format konvertiert wird. Dadurch korrekte Konvertierung Ruft die Anwendung die `AnsiToOem` -Funktion von Windows eine ANSI-Zeichenfolge in das Bearbeitungssteuerelement in OEM-Zeichen konvertiert. Dieses Format eignet sich am besten für Edit-Steuerelemente, die Dateinamen enthalten.  
  
-   **ES_PASSWORD** zeigt alle Zeichen als ein Sternchen (**\***), wie sie in das Bearbeitungssteuerelement eingegeben werden. Eine Anwendung kann mithilfe der `SetPasswordChar` Member-Funktion, um das Zeichen zu ändern, die angezeigt wird.  
  
-   **ES_READONLY** verhindert, dass Benutzer eingeben oder Bearbeiten von Text im Bearbeitungssteuerelement.  
  
-   **ES_RIGHT** rechts richtet Text in einem ein- oder mehrzeiligen edit-Steuerelement.  
  
-   **ES_UPPERCASE** konvertiert alle Zeichen in Großbuchstaben dargestellt, wie sie in das Bearbeitungssteuerelement eingegeben wurden.  
  
-   **ES_WANTRETURN** gibt an, dass ein Wagenrücklauf eingefügt werden, wenn der Benutzer die EINGABETASTE drückt, während der Eingabe von Text in einem mehrzeiligen Edit-Steuerelement in einem Dialogfeld. Ohne dieses Format hat das Drücken der EINGABETASTE dieselbe Wirkung wie das Dialogfeld Kontrollkästchen standardmäßig Pushbutton drücken. Dieses Format wirkt sich nicht auf eine einzeilige edit-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../../mfc/reference/cedit-class.md#create)   
 [Bearbeiten Sie die Stile von Listensteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775464)


