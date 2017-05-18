---
title: Statische Stile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SS_SUNKEN
- SS_CENTER
- SS_ENHMETAFILE
- SS_RIGHT
- SS_BLACKRECT
- SS_LEFTNOWORDWRAP
- SS_GRAYFRAME
- SS_USERITEM
- SS_GRAYRECT
- SS_WHITEFRAME
- SS_ETCHEDFRAME
- SS_ETCHEDVERT
- SS_WHITERECT
- SS_PATHELLIPSIS
- SS_WORDELLIPSIS
- SS_NOPREFIX
- SS_BITMAP
- SS_SIMPLE
- SS_CENTERIMAGE
- SS_BLACKFRAME
- SS_OWNERDRAW
- SS_REALSIZEIMAGE
- SS_RIGHTJUST
- SS_ICON
- SS_NOTIFY
- SS_ETCHEDHORZ
- SS_LEFT
- SS_ENDELLIPSIS
dev_langs:
- C++
helpviewer_keywords:
- SS_ICON constant
- SS_WHITEFRAME constant
- SS_BLACKFRAME constant
- SS_ETCHEDHORZ constant
- SS_OWNERDRAW constant
- SS_BITMAP constant
- SS_NOPREFIX constant
- SS_NOTIFY constant
- SS_CENTER constant
- SS_REALSIZEIMAGE constant
- SS_ETCHEDFRAME constant
- SS_CENTERIMAGE constant
- SS_SUNKEN constant
- SS_ENDELLIPSIS constant
- SS_WORDELLIPSIS constant
- SS_WHITERECT constant
- SS_ETCHEDVERT constant
- SS_GRAYFRAME constant
- SS_LEFTNOWORDWRAP constant
- SS_LEFT constant
- SS_SIMPLE constant
- static styles
- SS_ENHMETAFILE constant
- SS_GRAYRECT constant
- SS_USERITEM constant
- SS_PATHELLIPSIS constant
- SS_BLACKRECT constant
- SS_RIGHT constant
- SS_RIGHTJUST constant
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
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
ms.openlocfilehash: ad34c688fdfd3c2b4c81a0a03fbce53a905162ad
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="static-styles"></a>Statische Stile
-   **SS_BITMAP** gibt an, eine Bitmap in der statischen Steuerelement angezeigt werden. Der angegebene Text ist der Name einer Bitmap (kein Dateiname), die an anderer Stelle in der Ressourcendatei definiert. Das Format ignoriert die nWidth und nHeight-Parameter. das Steuerelement die Größe automatisch an die Bitmap angepasst.  
  
-   **SS_BLACKFRAME** gibt ein Feld mit einem Rahmen gezeichnet, die mit der gleichen Farbe als Fensterrahmen. Die Standardeinstellung ist schwarz.  
  
-   **SS_BLACKRECT** gibt ein Rechteck mit der Farbe, die zum Zeichnen der Fensterrahmen ausgefüllt. Die Standardeinstellung ist schwarz.  
  
-   **SS_CENTER** wird ein einfaches Rechteck, und zeigt den angegebenen Text im Rechteck zentriert. Der Text wird formatiert, bevor er angezeigt wird. Wörter, die nach dem Ende einer Zeile erweitert werden, werden automatisch an den Anfang der nächsten Zeile zentriert umschlossen.  
  
-   **SS_CENTERIMAGE** gibt an, dass die Bitmap oder das Symbol kleiner als das den Clientbereich des statischen Steuerelements der Rest des Clientbereichs mit der Farbe des Pixels in der oberen linken Ecke der Bitmap oder Symbol ausgefüllt ist. Enthält die statische Steuerelement eine einzelne Textzeile, wird der Text vertikal im Clientbereich des Steuerelements zentriert.  
  
-   **SS_ENDELLIPSIS** oder **SS_PATHELLIPSIS** ersetzt einen Teil der angegebenen Zeichenfolge mit Ellipsen, bei Bedarf, damit das Ergebnis in das angegebene Rechteck passt.  
  
     Sie können angeben, **SS_END_ELLIPSIS** Zeichen am Ende der Zeichenfolge zu ersetzen oder **SS_PATHELLIPSIS** innerhalb der Zeichenfolge zu ersetzen. Wenn die Zeichenfolge umgekehrten Schrägstrich enthält (\\) Zeichen **SS_PATHELLIPSIS** behält so viel des Texts nach dem letzten umgekehrten Schrägstrich wie möglich.  
  
-   **SS_ENHMETAFILE** gibt an, eine erweiterte Metadatei im statischen Steuerelement angezeigt werden. Der angegebene Text ist der Name einer Metadatei. Ein statisches EMF-Steuerelement hat eine feste Größe; die Metadatei wird skaliert Clientbereich des statischen Steuerelements passt.  
  
-   **SS_ETCHEDFRAME** zeichnet den Rahmen der statisches Steuerelement unter Verwendung der **EDGE_ETCHED** edge-Stil.  
  
-   **SS_ETCHEDHORZ** zeichnet die oberen und unteren Randes des statischen Steuerelements mithilfe der **EDGE_ETCHED** edge-Stil.  
  
-   **SS_ETCHEDVERT** zeichnet die linken und rechten Randes des statischen Steuerelements mit dem EDGE_ETCHED Edge-Stil.  
  
-   **SS_GRAYFRAME** gibt ein Feld mit einem Rahmen gezeichnet, die mit der gleichen Farbe wie der Hintergrund (Desktop). Die Standardeinstellung ist grau.  
  
-   **SS_GRAYRECT** gibt ein Rechteck mit der Farbe verwendet, um den Bildschirm ausfüllen ausgefüllt. Die Standardeinstellung ist grau.  
  
-   **SS_ICON** kennzeichnet ein Symbol im Dialogfeld angezeigt. Der angegebene Text ist der Name eines Symbols (kein Dateiname), die an anderer Stelle in der Ressourcendatei definiert. Die `nWidth` und `nHeight` Parameter werden ignoriert, und das Symbol passt sich automatisch.  
  
-   **SS_LEFT** wird ein einfaches Rechteck, und zeigt den angegebenen Text Flush-Links in dem Rechteck. Der Text wird formatiert, bevor er angezeigt wird. Wörter, die nach dem Ende einer Zeile erweitert werden werden automatisch an den Anfang der nächsten leeren linken Zeile umbrochen.  
  
-   **SS_LEFTNOWORDWRAP** wird ein einfaches Rechteck, und zeigt den angegebenen Text Flush-Links in dem Rechteck. Registerkarten werden erweitert, aber Wörter sind nicht eingeschlossen. Text, der hinter dem Ende einer Zeile hinausgeht, wird abgeschnitten.  
  
-   **SS_NOPREFIX** , wenn dieses Format angegeben wird, wird Windows kaufmännisches und-Zeichen (&) Zeichen im Text des Steuerelements Accelerator Präfixzeichen werden interpretiert. In diesem Fall das kaufmännische und-Zeichen wird entfernt, und das nächste Zeichen in der Zeichenfolge unterstrichen ist. Wenn ein statisches Steuerelement Text enthalten, in denen ist dieses Feature nicht erwünscht, **SS_NOPREFIX** hinzugefügt werden kann. Diese statischen Steuerelementformats möglicherweise definierten statischen Steuerelemente enthalten. Sie können kombinieren **SS_NOPREFIX** mit anderen Arten mit dem bitweisen OR-Operator. Dies wird am häufigsten verwendet, wenn Dateien oder andere Zeichenfolgen, die ein kaufmännisches und-Zeichen enthalten kann, in ein statisches Steuerelement in einem Dialogfeld angezeigt werden müssen.  
  
-   **SS_NOTIFY** das übergeordnete Fenster sendet **STN_CLICKED**, **STN_DBLCLK**, **STN_DISABLE**, und **STN_ENABLE** Benachrichtigung Nachrichten, wenn der Benutzer klickt, oder das Steuerelement doppelklickt.  
  
-   **SS_OWNERDRAW** gibt an, dass der Besitzer des statischen Steuerelements zum Zeichnen des Steuerelements verantwortlich ist. Das Besitzerfenster empfängt eine `WM_DRAWITEM` angezeigt, wenn das Steuerelement gezeichnet werden muss.  
  
-   **SS_REALSIZEIMAGE** wird verhindert, dass ein statisches Steuerelement Symbol oder eine Bitmap (d. h. statische Steuerelemente, die die **SS_ICON** oder **SS_BITMAP** Stil) aus, dessen Größe geändert, wie Laden oder gezeichnet wird. Wenn das Symbol oder eine Bitmap größer als der Zielbereich ist, wird das Bild abgeschnitten.  
  
-   **SS_RIGHT** bezeichnet ein einfaches Rechteck und zeigt den angegebenen Text Flush rechts im Rechteck. Der Text wird formatiert, bevor er angezeigt wird. Wörter, die nach dem Ende einer Zeile auftreten würde werden automatisch an den Anfang der nächsten Zeile Flush rechts eingebunden.  
  
-   **SS_RIGHTJUST** gibt an, dass der unteren rechten Ecke eines statischen Steuerelements mit der **SS_BITMAP** oder **SS_ICON** Stil ist, bleiben behoben, wenn die Größe des Steuerelements geändert wird. Nur die oberen und linken Rand werden angepasst, um eine neue Bitmap oder ein Symbol zu unterstützen.  
  
-   **SS_SIMPLE** wird ein einfaches Rechteck, und zeigt eine einzelne Textzeile Flush-Links in dem Rechteck. Die Zeile des Texts werden nicht gekürzt oder in keiner Weise geändert. (Übergeordnete Fenster oder Dialogfeld das des Steuerelements muss nicht verarbeiten der `WM_CTLCOLOR` Nachricht.)  
  
-   **SS_SUNKEN** ein statisches Steuerelement Hälfte vertieft umrahmt.  
  
-   **SS_USERITEM** gibt ein benutzerdefiniertes Element.  
  
-   **SS_WHITEFRAME** gibt ein Feld mit einem Rahmen, die mit der gleichen Farbe wie der Hintergrund gezeichnet. Der Standardwert ist Weiß.  
  
-   **SS_WHITERECT** gibt ein Rechteck mit der Farbe verwendet, um das Fenster ausfüllen ausgefüllt. Der Standardwert ist Weiß.  
  
-   **SS_WORDELLIPSIS** Text passt nicht, und fügt Auslassungspunkte abgeschnitten.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../../mfc/reference/cstatic-class.md#create)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Statische Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760773)


