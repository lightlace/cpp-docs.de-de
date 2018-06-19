---
title: Festlegen der Breite einer horizontalen Bildlaufleiste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34545a01c01146992c7d88ecabec1a29a7b438f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892791"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Festlegen der Breite einer horizontalen Bildlaufleiste
Wenn Sie ein Dialogfeld mit der MFC-Klassen ein Listenfeld mit einer horizontalen Bildlaufleiste hinzugefügt haben, wird die Bildlaufleiste nicht automatisch in der Anwendung angezeigt.  
  
### <a name="to-make-the-scroll-bar-appear"></a>Um die Bildlaufleiste sichtbar  
  
1.  Legen Sie eine maximale Breite für das breiteste Element durch den Aufruf [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) im Code.  
  
     Ohne diesen Wert die Bildlaufleiste selbst nicht angezeigt, wenn die Elemente im Listenfeld breiter als das Feld sind.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

