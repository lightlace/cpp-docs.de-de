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
ms.openlocfilehash: 47894c14e3b3d694847f94e7f981c9397383e598
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382905"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement
Siehe [Grundleisten-Steuerelemente und Bänder](../mfc/rebar-controls-and-bands.md), jedes Band kann nur ein untergeordnetes Fenster (oder Steuerelement) enthalten. Dies möglicherweise eine Einschränkung, wenn mehr als ein untergeordnetes Fenster pro Band sein sollen. Eine praktische problemumgehung wird zum Erstellen einer Dialogfeldressource-Leiste mit mehreren Steuerelementen und fügen Sie dann ein Grundleisten-Band (mit der Dialogleiste) für das Grundleistensteuerelement.  
  
 Normalerweise mussten Sie das Dialogfeld Leiste Band transparent angezeigt werden, legen Sie die **WS_EX_TRANSPARENT** erweiterter Stil für das Dialogfeld Bar-Objekt. Aber da **WS_EX_TRANSPARENT** gibt es einige Probleme mit ordnungsgemäß zeichnet den Hintergrund einer Dialogleiste, benötigen Sie ein wenig zusätzlichen Schritte, um den gewünschten Effekt zu erzielen möchten.  
  
 Nachfolgend sind die Schritte aufgeführt, die zur Erreichung der Transparenz ohne Verwendung der **WS_EX_TRANSPARENT** erweiterter Stil.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>So implementieren Sie eine transparente Dialogleiste in einem Grundleisten-Band-  
  
1.  Mithilfe der [Klasse hinzufügen (Dialogfeld)](../mfc/reference/adding-an-mfc-class.md), eine neue Klasse hinzufügen (z. B. `CMyDlgBar`), das die Balken Dialogfeldobjekt implementiert.  
  
2.  Fügen Sie einen Handler für das `WM_ERASEBKGND` Nachricht.  
  
3.  Der neue Handler ändern Sie den vorhandenen Code entsprechend das folgenden Beispiel:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Fügen Sie einen Handler für das `WM_MOVE` Nachricht.  
  
5.  Der neue Handler ändern Sie den vorhandenen Code entsprechend das folgenden Beispiel:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Die neuen Handler simulieren die Transparenz der Dialogleiste durch Weiterleitung der `WM_ERASEBKGND` Meldungen an das übergeordnete Fenster und Neuzeichnen erzwungen, jedes Mal, wenn das Dialogfeld Bar-Objekt verschoben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

