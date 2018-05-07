---
title: Headersteuerelement und Listensteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a84386781bf28edb9223f608fa7a64040eb68379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="header-control-and-list-control"></a>Headersteuerelement und Listensteuerelement
In den meisten Fällen verwenden Sie das Headersteuerelement, das in eingebettet ist ein [CListCtrl](../mfc/reference/clistctrl-class.md) oder [CListView](../mfc/reference/clistview-class.md) Objekt. Es gibt jedoch Situationen, in denen ein separates Headerobjekt Steuerelement wünschenswert sein, z. B. das Bearbeiten von Daten, die in Spalten oder Zeilen angeordnet sind, einem [CView](../mfc/reference/cview-class.md)-abgeleitetes Objekt. In diesen Fällen benötigen Sie mehr Kontrolle über die Darstellung und das Standardverhalten des eingebetteten Headersteuerelements.  
  
 In den meisten Fällen, dass Sie dem Headersteuerelement Standard bereitstellen möchten, Standardverhalten, das Sie verwenden möchten [CListCtrl](../mfc/reference/clistctrl-class.md) oder [CListView](../mfc/reference/clistview-class.md) stattdessen. Verwendung `CListCtrl` Wenn Sie die Funktionalität des Standard-Headersteuerelements, eingebettet in einem Listenansicht-Steuerelement allgemeine möchten. Verwendung [CListView](../mfc/reference/clistview-class.md) Wenn Sie die Funktionalität des Standard-Headersteuerelements, eingebettet in einem Objekt anzeigen möchten.  
  
> [!NOTE]
>  Diese Steuerelemente nur ein integrierte Headersteuerelement einschließen, wenn Listenansicht-Steuerelement erstellt wird, mit der `LVS_REPORT` Stil.  
  
 In den meisten Fällen kann die Darstellung des eingebetteten Headersteuerelements geändert werden, durch Ändern der Stile eines enthaltenden Listenansicht-Steuerelement. Darüber hinaus kann Informationen über das Headersteuerelement über Memberfunktionen des übergeordneten Listenansicht-Steuerelement abgerufen werden. Allerdings wird für die vollständige Kontrolle und Zugriff auf die Attribute und-Stile eines eingebetteten Headersteuerelement empfohlen, dass ein Zeiger auf das Headersteuerelement-Objekt abgerufen werden.  
  
 Das Steuerelementobjekt eingebettete Header kann entweder aus zugegriffen werden **CListCtrl** oder `CListView` mit einem Aufruf von der jeweiligen Klasse `GetHeaderCtrl` Memberfunktion. Der folgende Code veranschaulicht dies:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Verwenden von Image Listen in Headersteuerelementen](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

