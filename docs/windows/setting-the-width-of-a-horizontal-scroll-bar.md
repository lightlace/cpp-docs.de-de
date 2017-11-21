---
title: Festlegen der Breite einer horizontalen Bildlaufleiste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 97015327803a82161e8dc121e8085e63b791acdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Festlegen der Breite einer horizontalen Bildlaufleiste
Wenn Sie ein Dialogfeld mit der MFC-Klassen ein Listenfeld mit einer horizontalen Bildlaufleiste hinzugefügt haben, wird die Bildlaufleiste nicht automatisch in der Anwendung angezeigt.  
  
### <a name="to-make-the-scroll-bar-appear"></a>Um die Bildlaufleiste sichtbar  
  
1.  Legen Sie eine maximale Breite für das breiteste Element durch den Aufruf [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) im Code.  
  
     Ohne diesen Wert die Bildlaufleiste selbst nicht angezeigt, wenn die Elemente im Listenfeld breiter als das Feld sind.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](https://msdn.microsoft.com/library/f45fce5x.aspx) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](https://msdn.microsoft.com/library/xbx3z216.aspx). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Anforderungen  
  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

