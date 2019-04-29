---
title: Verwenden von CAnimateCtrl
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
ms.openlocfilehash: b967cc6dde6b4f639ef081b3821f6a7e5a2fe295
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351640"
---
# <a name="using-canimatectrl"></a>Verwenden von CAnimateCtrl

Ein Animationssteuerelement, dargestellt durch die Klasse [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), wird ein Fenster, das einen Clip in Audio Video überlappen (AVI)-Format angezeigt, das standardmäßige Windows-Video-oder Audio-Format. Ein AVI-Clips ist eine Reihe von Bitmapbildern wie einen Film.

Da sich der Thread ausgeführt weiterhin, während des AVI-Clips angezeigt wird, werden ein gängiges Szenario für ein Animationssteuerelement Systemaktivität während eines längeren Vorgangs anzugeben. Beispielsweise zeigt das Dialogfeld Windows suchen eine gleitende Lupe, als das System sucht nach einer Datei.

Animationssteuerungselemente können nur einfache AVI-Clips wiedergeben, und sie unterstützen keine Sound. (Eine vollständige Liste der Einschränkungen, finden Sie unter [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Da die Funktionen von eines Animationssteuerelements erheblich eingeschränkt sind und vorbehalten ist, sollten Sie Alternative z. B. das MCIWnd-Steuerelement verwenden, wenn Sie ein Steuerelement Multimediawiedergabe bzw. die Aufzeichnung zu benötigen. Weitere Informationen über das Steuerelement MCIWnd finden Sie unter der multimedia-Dokumentation.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Verwenden eines Animationssteuerelements](../mfc/using-an-animation-control.md)

- [Von Animationssteuerelementen gesendete Benachrichtigungen](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)
