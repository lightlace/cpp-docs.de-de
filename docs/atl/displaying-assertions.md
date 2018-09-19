---
title: Anzeigeassertionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff7b9b29808e310be2d5568add64a0294bc67e7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762381"
---
# <a name="displaying-assertions"></a>Anzeigeassertionen

Wenn der Client mit dem Dienst verbundenen angezeigt wird, nicht mehr reagiert, kann der Dienst bestätigt und ein Meldungsfeld an, die Sie nicht sehen können angezeigt haben. Sie können dies nachprüfen, mithilfe von Visual C++-Debugger zum Debuggen des Codes (finden Sie unter [mithilfe des Task-Manager](../atl/using-task-manager.md) weiter oben in diesem Abschnitt).

Wenn Sie feststellen, dass Ihr Dienst ein Meldungsfeld angezeigt wird, die Sie nicht sehen können, möchten Sie möglicherweise Festlegen der **Dienst ermöglichen, für die Interaktion mit Desktop** -Option vor der Verwendung des Diensts erneut. Diese Option ist ein Startparameter, der Meldungsfelder angezeigt werden, durch den Dienst auf dem Desktop angezeigt werden kann. Um diese Option festlegen zu können, öffnen Sie die Anwendung Dienste Systemsteuerung, wählen Sie den Dienst, klicken Sie auf **Start**, und wählen Sie dann die **Dienst ermöglichen, für die Interaktion mit Desktop** Option.

## <a name="see-also"></a>Siehe auch

[Tipps zum Debuggen](../atl/debugging-tips.md)

