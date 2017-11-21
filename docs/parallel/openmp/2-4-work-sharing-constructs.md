---
title: 2.4 Arbeitsteilungskonstrukte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5353bc51f6a701201520f700057ef76ce7778191
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte
Ein Konstrukt Freigeben von Arbeit verteilt die Ausführung der zugeordneten Anweisung zwischen den Mitgliedern des Teams, die sie auftreten. Die Arbeit sharing-Direktiven neue Threads nicht starten, und es keine implizite Barriere beim Einstieg in eine Arbeit sharing-Konstrukt ist.  
  
 Erstellt die Abfolge der Freigabe von Arbeit und **Barriere** Direktiven aufgetreten müssen für jeden Thread in einem Team identisch sein.  
  
 OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese werden in den folgenden Abschnitten beschrieben:  
  
-   **für** Richtlinie  
  
-   **Abschnitte** Richtlinie  
  
-   **einzelne** Richtlinie