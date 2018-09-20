---
title: Verarbeiten von Benachrichtigungen des Headersteuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7c6fa8a85aee06aca3b1bf804a06df428e82cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387756"
---
# <a name="processing-header-control-notifications"></a>Verarbeiten von Benachrichtigungen des Headersteuerelements

In Ihrer Klasse Ansichts- oder Dialogfeldobjekt mithilfe des Fensters Eigenschaften zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung für beliebige Header-Steuerelemente ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) benachrichtigungsmeldungen werden sollen verarbeiten (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)). Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer klickt, oder ein Headerelement zieht eine Trennlinie zwischen Elementen und So weiter doppelklickt.

Die benachrichtigungsmeldungen Zusammenhang mit einem Kopfzeilen-Steuerelement finden Sie in [Header Steuerelementverweis](https://msdn.microsoft.com/library/windows/desktop/bb775239) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

