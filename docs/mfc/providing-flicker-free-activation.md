---
title: Bereitstellen flimmerfreier Aktivierung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: d979a6f633926bed1ad59de86829b9ac27b0d0cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438141"
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

