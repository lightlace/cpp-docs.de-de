---
title: Das Headerelement anpassen&#39;s Darstellung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e09f8bc0b61e22435ee348968f117940b57132e3
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930874"
---
# <a name="customizing-the-header-item39s-appearance"></a>Das Headerelement anpassen&#39;s Darstellung
Durch Festlegen der *DwStyle* Parameter bei der Erstellung von einem Headersteuerelement ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md#create)) definieren Sie die Darstellung und Verhalten des Headers Elemente oder des Headersteuerelements selbst.  
  
 Hier wird eine Stichprobe die Formatvorlagen, die Sie festlegen können, und ihren Zweck:  
  
-   Um einen Headerelement, das Aussehen einer Schaltfläche darzustellen, verwenden die **HDS_BUTTONS** Stil.  
  
     Verwenden Sie dieses Format, wenn Sie zum Ausführen von Aktionen als Reaktion auf Mausklicks auf ein Headerelement, wie Daten nach einer bestimmten Spalte sortieren, wie in Microsoft Outlook verwendet werden soll.  
  
-   Um die Headerelemente ein "hot Track" Erscheinungsbild verleihen, wenn der Mauszeiger darüber bewegt, verwenden die **HDS_HOTTRACK** Stil.  
  
     Hot Track zeigt eine 3D Gliederung Weg von der Zeiger auf ein Element in einer ansonsten flachen Leiste.  
  
-   Um anzugeben, dass das Headersteuerelement ausgeblendet werden soll, verwenden Sie die **HDS_HIDDEN** Stil.  
  
     Die **HDS_HIDDEN** Stil gibt an, dass das Headersteuerelement als Datencontainer und kein visuelles Steuerelement verwendet werden sollen. Dieses Format des Steuerelements wird nicht automatisch ausgeblendet, aber stattdessen wirkt sich auf das Verhalten des `CHeaderCtrl::Layout`. Der zurückgegebene Wert in der *cy* Mitglied der `WINDOWPOS` Struktur werden auf 0 (null) gibt an, dass das Steuerelement nicht für den Benutzer sichtbar sein soll.  
  
 Weitere Informationen zu diesen Eigenschaften finden Sie unter [Elemente](http://msdn.microsoft.com/library/windows/desktop/bb775238) im Windows SDK. Informationen zum Hinzufügen von Elementen zum Headersteuerelement finden Sie unter [Hinzufügen von Elementen zum Headersteuerelement](../mfc/adding-items-to-the-header-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

