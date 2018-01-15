---
title: "Eigenschaftenblätter und Eigenschaftenseiten in MFC | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24a66bf9e062e43225827afdbb0bba45511c5f13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>Eigenschaftenblätter und Eigenschaftenseiten in MFC
Ein Eigenschaftenblatt, auch bekannt als eine Registerkarte (Dialogfeld), wird ein Dialogfeld mit Eigenschaftenseiten. Jede Eigenschaftenseite basiert auf einer Dialogfeldvorlagen-Ressource und Steuerelemente enthält. Es wird auf einer Seite mit einer Registerkarte im Vordergrund eingeschlossen. Die Registerkarte die Seite den Namen und zwecks angibt. Benutzer klicken Sie auf eine Registerkarte im Eigenschaftenblatt zum Auswählen eines Satzes von Steuerelementen.  
  
 Verwenden Sie Seiten, um die Steuerelemente im Eigenschaftenblatt zu sinnvollen Sätzen zusammengefasst. Das eigenständige Eigenschaftenblatt weist normalerweise auf mehrere Steuerelemente. Diese gelten für alle Seiten.  
  
 Eigenschaftenblätter basieren auf Klasse [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Eigenschaftenseiten basieren auf Klasse [CPropertyPage](../mfc/reference/cpropertypage-class.md).  
  
 Ein Eigenschaftenblatt ist eine besondere Art von (Dialogfeld), die in der Regel so ändern Sie die Attribute des einige externe Objekt, z. B. die aktuelle Auswahl in einer Ansicht verwendet wird. Das Eigenschaftenblatt besitzt drei Hauptteilen zusammen: das Dialogfeld enthält eine oder mehrere Eigenschaftenseiten dargestellt einzeln nacheinander, und einer Registerkarte am oberen Rand jeder Seite, die der Benutzer klickt, um die Seite auszuwählen. Eigenschaftenblätter eignen sich für Situationen, in denen mehrere ähnliche Gruppen von Einstellungen oder der Optionen zum Ändern der haben. Ein Eigenschaftenblatt gruppiert Informationen in einer leicht verständliche Weise.  
  
> [!NOTE]
>  Wenn Sie versuchen, ein Eigenschaftenblatt zeigen `CPropertySheet::DoModal`, vom System möglicherweise eine nicht abgefangene Ausnahme generiert. Diese Ausnahme tritt auf, da das System versucht wird, so ändern Sie die [Fensterstile](../mfc/reference/styles-used-by-mfc.md#window-styles) des Objekts, bevor das Objekt erstellt wurde. Weitere Informationen über diese Ausnahme sowie Informationen zum vermeiden oder behandeln, finden Sie unter [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal).  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

