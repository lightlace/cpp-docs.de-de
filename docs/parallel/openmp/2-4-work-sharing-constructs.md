---
title: 2.4 Arbeitsteilungskonstrukte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c00eb94055f26954a283a6172f69228804832ac4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte
Ein Konstrukt Freigeben von Arbeit verteilt die Ausführung der zugeordneten Anweisung zwischen den Mitgliedern des Teams, die sie auftreten. Die Arbeit sharing-Direktiven neue Threads nicht starten, und es keine implizite Barriere beim Einstieg in eine Arbeit sharing-Konstrukt ist.  
  
 Erstellt die Abfolge der Freigabe von Arbeit und **Barriere** Direktiven aufgetreten müssen für jeden Thread in einem Team identisch sein.  
  
 OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese werden in den folgenden Abschnitten beschrieben:  
  
-   **für** Richtlinie  
  
-   **Abschnitte** Richtlinie  
  
-   **einzelne** Richtlinie