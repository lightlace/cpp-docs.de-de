---
title: Stile des Schiebeleisten Steuerelements | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SBS_VERT
- SBS_SIZEBOXBOTTOMRIGHTALIGN
- SBS_LEFTALIGN
- SBS_RIGHTALIGN
- SBS_TOPALIGN
- SBS_SIZEBOXTOPLEFTALIGN
- SBS_BOTTOMALIGN
- SBS_SIZEBOX
- SBS_HORZ
dev_langs:
- C++
helpviewer_keywords:
- SBS_HORZ constant
- SBS_TOPALIGN constant
- SBS_SIZEBOX constant
- SBS_BOTTOMALIGN constant
- SBS_VERT constant
- SBS_LEFTALIGN constant
- SBS_SIZEBOXBOTTOMRIGHTALIGN constant
- scroll bars, styles
- SBS_SIZEBOXTOPLEFTALIGN constant
- SBS_RIGHTALIGN constant
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 778fe7b0f6f6319884df4ed9c5ccbe8e34bd8d42
ms.lasthandoff: 02/24/2017

---
# <a name="scroll-bar-styles"></a>Stile des Schiebeleisten-Steuerelements
-   **SBS_BOTTOMALIGN** verwendet, mit der **SBS_HORZ** Stil. Der untere Rand der Bildlaufleiste am unteren Rand des Rechtecks im angegebenen ausgerichtet ist die **erstellen** Member-Funktion. Die Bildlaufleiste verfügt über die Standardhöhe zum System Bildlaufleisten.  
  
-   **SBS_HORZ** kennzeichnet eine horizontale Bildlaufleiste angezeigt. Wenn weder die **SBS_BOTTOMALIGN** noch **SBS_TOPALIGN** Format angegeben, die Bildlaufleiste verfügt über die Höhe, Breite und Position im angegebenen der **erstellen** Member-Funktion.  
  
-   **SBS_LEFTALIGN** verwendet, mit der **SBS_VERT** Stil. Der linke Rand der Bildlaufleiste am linken Rand des Rechtecks im angegebenen ausgerichtet ist die **erstellen** Member-Funktion. Die Bildlaufleiste verfügt über die Standardbreite für System-Bildlaufleisten.  
  
-   **SBS_RIGHTALIGN** verwendet, mit der **SBS_VERT** Stil. Der rechte Rand der Bildlaufleiste am rechten Rand des Rechtecks im angegebenen ausgerichtet ist die **erstellen** Member-Funktion. Die Bildlaufleiste verfügt über die Standardbreite für System-Bildlaufleisten.  
  
-   **SBS_SIZEBOX** kennzeichnet ein Feld. Wenn weder die **SBS_SIZEBOXBOTTOMRIGHTALIGN** noch **SBS_SIZEBOXTOPLEFTALIGN** Format angegeben, das Größeneinstellungsfeld hat, Höhe, Breite und Position im angegebenen der **erstellen** Member-Funktion.  
  
-   **SBS_SIZEBOXBOTTOMRIGHTALIGN** verwendet, mit der **SBS_SIZEBOX** Stil. Unten rechts neben dem Größeneinstellungsfeld mit der rechten unteren Ecke des Rechtecks im angegebenen ausgerichtet ist die **erstellen** Member-Funktion. Das Größeneinstellungsfeld ist die Standardgröße für System Felder.  
  
-   **SBS_SIZEBOXTOPLEFTALIGN** verwendet, mit der **SBS_SIZEBOX** Stil. Die linke obere Ecke des Größeneinstellungsfeld mit der linken oberen Ecke des Rechtecks in angegebenen ausgerichtet ist die **erstellen** Member-Funktion. Das Größeneinstellungsfeld ist die Standardgröße für System Felder.  
  
-   **SBS_SIZEGRIP** wie **SBS_SIZEBOX**, jedoch mit einer erhöhten Kante.  
  
-   **SBS_TOPALIGN** verwendet, mit der **SBS_HORZ** Stil. Der obere Rand der Bildlaufleiste orientiert sich am oberen Rand des Rechtecks im angegebenen der **erstellen** Member-Funktion. Die Bildlaufleiste verfügt über die Standardhöhe zum System Bildlaufleisten.  
  
-   **SBS_VERT** kennzeichnet eine vertikale Bildlaufleiste angezeigt. Wenn weder die **SBS_RIGHTALIGN** noch **SBS_LEFTALIGN** Format angegeben, die Bildlaufleiste verfügt über die Höhe, Breite und Position im angegebenen der **erstellen** Member-Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)   
 [Steuerelementtypen für die Bildlaufleiste](http://msdn.microsoft.com/library/windows/desktop/bb787533)


