---
title: Wann benötige ich AtlAxWinInit aufrufen? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9aa1dd14ccae555d4ab9acbbac15e9b66cafe6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360272"
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Wann benötige ich AtlAxWinInit aufrufen?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) registriert die **"AtlAxWin80"** Fensterklasse (plus ein Paar von benutzerdefinierten fenstermeldungen), damit diese Funktion aufgerufen werden muss, bevor Sie versuchen, ein Hostfenster zu erstellen. Sie müssen jedoch nicht immer zum Aufrufen dieser Funktion explizit, seit das hosting-APIs (und die Klassen, die diese verwenden) häufig mit dieser Funktion wird für Sie. Es gibt keinen Schaden in mehr als einmal Aufrufen dieser Funktion. sein.  
  
## <a name="see-also"></a>Siehe auch  
 Wann benötige ich AtlAxWinTerm aufrufen     
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)
