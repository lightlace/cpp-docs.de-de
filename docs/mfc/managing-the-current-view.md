---
title: Verwalten der aktuellen Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca9738f9b6083ef88c2f72e1608121f849f8e909
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425364"
---
# <a name="managing-the-current-view"></a>Verwalten der aktuellen Ansicht

Im Rahmen der Standardimplementierung von Rahmenfenstern verfolgt des ein Rahmenfenster eine derzeit aktive Ansicht. Wenn das Rahmenfenster auf mehr als eine Ansicht, z. B. in einem Splitterfenster enthält ist die aktuelle Ansicht die aktuellste Ansicht verwendet. Die aktive Ansicht ist unabhängig von der aktiven Fenster in Windows oder den aktuellen Eingabefokus.

Wenn die aktive Ansicht ändert, ändert das Framework benachrichtigt die aktuelle Ansicht, indem er seine [OnActivateView](../mfc/reference/cview-class.md#onactivateview) Member-Funktion. Sie können feststellen, ob die Sicht wird aktiviert oder deaktiviert werden, indem Sie untersuchen `OnActivateView`des *bActivate* Parameter. In der Standardeinstellung `OnActivateView` setzt den Fokus auf der aktuellen Ansicht bei der Aktivierung. Sie können außer Kraft setzen `OnActivateView` ausführen, besondere Bearbeitung, wenn die Sicht deaktiviert oder erneut aktiviert wird. Beispielsweise empfiehlt es sich, bieten besondere visuelle Hinweise, um die aktive Ansicht von anderen, inaktive Sichten zu unterscheiden.

Ein Rahmenfenster leitet Befehle aus, um die aktuelle (aktive) anzeigen, wie in beschrieben [Befehlsrouting](../mfc/command-routing.md), als Teil des standardbefehlsroutings.

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

