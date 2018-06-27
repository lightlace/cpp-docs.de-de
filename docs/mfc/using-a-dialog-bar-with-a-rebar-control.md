---
title: Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa2628df5f446105e6b7881709a0c72c19fe230e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950489"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement
Siehe [Grundleisten-Steuerelemente und Bänder](../mfc/rebar-controls-and-bands.md), jedes Band kann nur ein untergeordnetes Fenster (oder Steuerelement) enthalten. Dies möglicherweise eine Einschränkung, wenn mehr als ein untergeordnetes Fenster pro Band sein sollen. Eine praktische problemumgehung wird zum Erstellen einer Dialogfeldressource-Leiste mit mehreren Steuerelementen und fügen Sie dann ein Grundleisten-Band (mit der Dialogleiste) für das Grundleistensteuerelement.  
  
 Normalerweise mussten Sie das Dialogfeld Leiste Band transparent angezeigt werden, legen Sie für den erweiterten Stil für die Leiste Dialogfeldobjekt WS_EX_TRANSPARENT. Da WS_EX_TRANSPARENT einige Probleme mit der ordnungsgemäß zeichnet den Hintergrund einer Dialogleiste aufweist, müssen Sie tun einiger zusätzlichen Schritte, um den gewünschten Effekt zu erzielen.  
  
 Die folgenden Verfahren sind die erforderlichen Schritte zum Transparenz zu erzielen, ohne die WS_EX_TRANSPARENT Verwendung erweiterter Stil.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>So implementieren Sie eine transparente Dialogleiste in einem Grundleisten-Band-  
  
1.  Mithilfe der [Klasse hinzufügen (Dialogfeld)](../mfc/reference/adding-an-mfc-class.md), eine neue Klasse hinzufügen (z. B. `CMyDlgBar`), das die Balken Dialogfeldobjekt implementiert.  
  
2.  Fügen Sie einen Handler für die WM_ERASEBKGND-Nachricht hinzu.  
  
3.  Der neue Handler ändern Sie den vorhandenen Code entsprechend das folgenden Beispiel:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Fügen Sie einen Handler für die WM_MOVE Nachricht hinzu.  
  
5.  Der neue Handler ändern Sie den vorhandenen Code entsprechend das folgenden Beispiel:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Die neuen Handler simulieren die Transparenz der Dialogleiste durch Weiterleiten der Nachricht WM_ERASEBKGND an das übergeordnete Fenster und Neuzeichnen erzwungen, jedes Mal, wenn das Dialogfeld Bar-Objekt verschoben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

