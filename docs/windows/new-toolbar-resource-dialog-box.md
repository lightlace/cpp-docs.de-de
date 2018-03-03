---
title: Neue Symbolleiste Dialogfeld "Ressource" | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c30301b8887013d72e7ae2ab2d70650de7d7f0e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="new-toolbar-resource-dialog-box"></a>Neue Symbolleistenressource (Dialogfeld)
Das Dialogfeld "Neue Symbolleistenressource" können Sie angeben, die Breite und Höhe von Schaltflächen, die Sie auf eine Symbolleistenressource hinzufügen. Der Standardwert ist 16 x 15 Pixel.  
  
 Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048. Wenn Sie festlegen, also die **Breite der Schaltfläche** auf 512, können Sie nur vier Schaltflächen haben. Wenn Sie die Breite auf 513 festlegen, können Sie nur drei Schaltflächen verfügen.  
  
 **Schaltflächenbreite**  
 Dient zur Eingabe der Breite für das Symbolleisten-Schaltflächen, den Sie aus einer Bitmapressource eine Symbolleistenressource konvertieren. Die Bilder werden zugeschnitten, um die Breite und Höhe angegeben, und die Farben werden entsprechend Standardsymbolleiste Farben (16 Farben) verwenden.  
  
 **Schaltflächenhöhe**  
 Dient zur Eingabe der Höhe für die Schaltflächen der Symbolleiste, den Sie aus einer Bitmapressource eine Symbolleistenressource konvertieren. Die Bilder werden zugeschnitten, um die Breite und Höhe angegeben, und die Farben werden entsprechend Standardsymbolleiste Farben (16 Farben) verwenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 MFC oder ATL  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften von Symbolleisten-Schaltfläche](../windows/toolbar-button-properties.md)   
 [Konvertieren von Bitmaps in Symbolleisten](../windows/converting-bitmaps-to-toolbars.md)   
 [Symbolleisten-Editor](../windows/toolbar-editor.md)

