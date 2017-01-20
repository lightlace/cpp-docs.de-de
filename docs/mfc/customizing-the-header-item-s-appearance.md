---
title: "Anpassen der Darstellung von Headerelementen"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl-Klasse, Anpassen von Elementen"
  - "HDS_Stile"
  - "Headersteuerelemente, Anpassung von Elementen"
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Anpassen der Darstellung von Headerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem *dwStyle* \-Parameter, wenn Sie zunächst ein Header\-Steuerelement \([CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)\) erstellen festlegen, können Sie die Darstellung und das Verhalten von Kopfzeilenelementen oder des Header\-Steuerelements selbst definieren.  
  
 Im Folgenden ein Sampling der Stile, die Sie festlegen können und ihr Zweck:  
  
-   Um ein Headerelement wie ein Pushbutton angezeigt werden, verwenden Sie das Format `HDS_BUTTONS`.  
  
     Verwenden Sie dieses Format, wenn Sie Aktionen in Reaktion auf Mausklicks auf einem Headerelement, wie Daten sortieren durch eine bestimmte Spalte ausführen möchten, wie in Microsoft Outlook verwendet wird.  
  
-   Um den Kopfzeilenelementen eine "HotTracking" Aussehen zu verleihen wenn der Mauszeiger über das Element bewegt wird, verwenden Sie das Format `HDS_HOTTRACK`.  
  
     das Hottracking wird 3D\-Konturen an, während der Mauszeiger über ein Element in einer flachen andernfalls Leiste übergibt.  
  
-   Um anzugeben dass das Header\-Steuerelement ausgeblendet werden soll, verwenden Sie das Format `HDS_HIDDEN`.  
  
     Das Format `HDS_HIDDEN` gibt an, dass das Header\-Steuerelement vorgesehen, als Datencontainer und nicht visuelles Steuerelement verwendet werden.  Dieses Format nicht automatisch blendet das Steuerelement aber stattdessen die beeinflusst das Verhalten von `CHeaderCtrl::Layout`.  Der Wert, der im **cy**\-Member `WINDOWPOS` der Struktur zurückgegeben wird, ist ungewöhnlich angibt, dass das Steuerelement dem Benutzer nicht sichtbar sein soll.  
  
 Weitere Informationen über diese Eigenschaften, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Elemente](http://msdn.microsoft.com/library/windows/desktop/bb775238).  Informationen zum Hinzufügen von Elementen zu einem Header\-Steuerelement, finden Sie unter [Hinzufügen von Elementen zum Header\-Steuerelement](../mfc/adding-items-to-the-header-control.md).  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)