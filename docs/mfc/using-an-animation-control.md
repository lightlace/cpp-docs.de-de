---
title: Verwenden eines Animationssteuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3da9684d0218c631cbd745475d48f1cf23addde5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404565"
---
# <a name="using-an-animation-control"></a>Verwenden eines Animationssteuerelements

Typische Nutzung eines Animationssteuerelements folgt das folgenden Muster:

- Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sollten Ihnen eine [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) Member in der Dialogfeldklasse, die das Animationssteuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/canimatectrl-class.md#create) Member-Funktion, um das Steuerelement als untergeordnetes Fenster von einem beliebigen Fenster zu erstellen.

- Laden Sie in das Animationssteuerelement durch Aufrufen der [öffnen](../mfc/reference/canimatectrl-class.md#open) Member-Funktion. Das Animationssteuerelement in einem Dialogfeld ein guter Ausgangspunkt zu diesem Zweck ist, in der Dialogfeldklasse [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.

- Geben Sie den Clip durch Aufrufen der [spielen](../mfc/reference/canimatectrl-class.md#play) Member-Funktion. Das Animationssteuerelement in einem Dialogfeld ein guter Ausgangspunkt zu diesem Zweck ist, in der Dialogfeldklasse `OnInitDialog` Funktion. Aufrufen von `Play` ist nicht erforderlich, wenn das Animationssteuerelement das ACS_AUTOPLAY-Format festgelegt wurde.

- Wenn Sie Teile des Clips angezeigt oder wiedergegeben Frame nach dem anderen, verwenden werden möchten die `Seek` Member-Funktion. Um einen Clip zu beenden, der wiedergegeben wird, verwenden die `Stop` Member-Funktion.

- Wenn Sie nicht beabsichtigen, um das Steuerelement sofort zu zerstören, entfernen Sie den Clip aus dem Speicher durch Aufrufen der `Close` Member-Funktion.

- Wenn das Animationssteuerelement in einem Dialogfeld ist es und `CAnimateCtrl` Objekt wird automatisch zerstört. Wenn nicht der Fall, Sie sicherstellen, dass sowohl das Steuerelement müssen und die `CAnimateCtrl` Objekt ordnungsgemäß zerstört werden. Zerstören das Steuerelement automatisch schließt des AVI-Clips.

## <a name="see-also"></a>Siehe auch

[Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

