---
title: Bereitstellen flimmerfreier Aktivierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9f780472b8256f6d8332ecbde08138d85c8ebd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378321"
---
# <a name="providing-flicker-free-activation"></a>Bereitstellen flimmerfreier Aktivierung

Wenn das Steuerelement sich genauso wie im inaktive und aktive Zustand zeichnet (und keine fensterlosen Aktivierung verwendet) können ausgeschlossen werden die Zeichenoperationen und die damit verbundene Flimmern, die normalerweise auftreten, wenn es sich bei den Übergang zwischen den inaktiv machen und aktiven Status. Um dies zu erreichen, fügen die **NoFlickerActivate** -Flag in einem Satz von Flags, die vom [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **flimmerfreier Aktivierung** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite, wenn das Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellen.

Wenn Sie fensterlosen Aktivierung verwenden, ist diese Optimierung wirkungslos.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

