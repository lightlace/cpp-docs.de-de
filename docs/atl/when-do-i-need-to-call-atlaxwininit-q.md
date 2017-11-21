---
title: "Wann benötige ich AtlAxWinInit aufrufen? | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinInit
dev_langs: C++
helpviewer_keywords: AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2ec7d8d15b8219071b593368ed539d92ff3c9032
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Wann benötige ich AtlAxWinInit aufrufen?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) registriert die **"AtlAxWin80"** Fensterklasse (plus ein Paar von benutzerdefinierten fenstermeldungen), damit diese Funktion aufgerufen werden muss, bevor Sie versuchen, ein Hostfenster zu erstellen. Sie müssen jedoch nicht immer zum Aufrufen dieser Funktion explizit, seit das hosting-APIs (und die Klassen, die diese verwenden) häufig mit dieser Funktion wird für Sie. Es gibt keinen Schaden in mehr als einmal Aufrufen dieser Funktion. .  
  
## <a name="see-also"></a>Siehe auch  
 Wann benötige ich AtlAxWinTerm aufrufen     
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)
