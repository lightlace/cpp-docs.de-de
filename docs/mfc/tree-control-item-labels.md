---
title: Elementbezeichnungen in Struktursteuerelementen Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d9baece3986b00aa2fbcea2b4b64217618834a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-labels"></a>Elementbezeichnungen in Struktursteuerelementen
Den Text der Bezeichnung für ein Element wird in der Regel angeben, wenn Sie das Element des Strukturansicht-Steuerelements hinzufügen ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Die `InsertItem` kann Member-Funktion übergeben, eine [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) Struktur, die die Eigenschaften des Elements, z. B. eine Zeichenfolge, enthält der Text der Bezeichnung definiert. `InsertItem`verfügt über mehrere Überladungen, die mit verschiedenen Kombinationen von Parametern aufgerufen werden kann.  
  
 Ein Strukturansicht-Steuerelement belegt Speicher für das Speichern jedes Element; der Text, der den Elementnamen beanspruchen ein beträchtlicher Teil der dieser Arbeitsspeicher ab. Wenn Ihre Anwendung eine Kopie der Zeichenfolgen in der Strukturansicht-Steuerelement verwaltet, können Sie die arbeitsspeicheranforderungen des Steuerelements verringern, indem Sie angeben der **LPSTR_TEXTCALLBACK** Wert in der **PszText** Mitglied `TV_ITEM` oder `lpszItem` Parameter anstelle der Übergabe von tatsächlichen Zeichenfolgen an die Strukturansicht-Steuerelements. Mit **LPSTR_TEXTCALLBACK** bewirkt, dass das Strukturansicht-Steuerelement den Text der Bezeichnung für ein Element aus der Anwendung abrufen, wenn das Element neu gezeichnet werden muss. Zum Abrufen des Texts des Strukturansicht-Steuerelements sendet eine [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) Benachrichtigung, die die Adresse des umfasst eine [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) Struktur. Sie müssen reagieren durch Festlegen der entsprechenden Member der Struktur enthalten.  
  
 Ein Strukturansicht-Steuerelement verwendet Arbeitsspeichers aus dem Heap des Prozesses, der das Strukturansicht-Steuerelement erstellt. Die maximale Anzahl von Elementen in einem Strukturansicht-Steuerelement basiert auf der Menge an Arbeitsspeicher, die im Heap verfügbar. Jedes Element nimmt 64 Bytes.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

