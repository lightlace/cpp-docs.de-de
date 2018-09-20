---
title: Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement | Microsoft-Dokumentation
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
ms.openlocfilehash: c881e31d178d6303939c94d68e2824fb11ec2cbd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425395"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement

Siehe [Grundleisten-Steuerelemente und Bänder](../mfc/rebar-controls-and-bands.md), jedes Band kann nur ein untergeordnetes Fenster (oder Steuerelement) enthalten. Dies kann eine Einschränkung sein, wenn Sie mehr als ein untergeordnetes Fenster pro-Band-haben möchten. Eine praktische problemumgehung ist das Erstellen einer Ressource Leiste mit mehreren Steuerelementen, und klicken Sie dann ein Infoleistenband (enthält die Dialogleiste) für das Grundleistensteuerelement hinzufügen.

Wenn Sie das Dialogfeld Leiste Band transparent angezeigt werden möchten, würden Sie normalerweise den erweiterten Stil für das Dialogfeld Bar-Objekt WS_EX_TRANSPARENT festlegen. Da WS_EX_TRANSPARENT einige Probleme mit der ordnungsgemäß Zeichnen des Hintergrunds des einer Dialogleiste verfügt, müssen Sie jedoch ein wenig zusätzlichen Arbeit, um den gewünschten Effekt zu erreichen sind.

Die folgenden Verfahren Details erweitert die erforderlichen Schritte zum Transparenz zu erzielen, ohne die WS_EX_TRANSPARENT Stil.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Implementieren Sie eine transparente Dialogleiste in ein Infoleistenband

1. Mithilfe der [Dialogfeld Klasse hinzufügen](../mfc/reference/adding-an-mfc-class.md), eine neue Klasse hinzufügen (z. B. `CMyDlgBar`), das Ihr Dialogfeld Bar-Objekt implementiert.

1. Fügen Sie einen Handler für die Nachricht WM_ERASEBKGND hinzu.

1. Ändern Sie den neuen Handler auf den vorhandenen Code entsprechend das folgende Beispiel:

     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. Fügen Sie einen Handler für die Nachricht WM_MOVE hinzu.

1. Ändern Sie den neuen Handler auf den vorhandenen Code entsprechend das folgende Beispiel:

     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Die neuen Handler simulieren die Transparenz der Dialogleiste durch Weiterleiten der Nachricht WM_ERASEBKGND, für das übergeordnete Fenster, und erzwingen eine "Repaint" jedes Mal, wenn das Dialogfeld Bar-Objekt verschoben wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

