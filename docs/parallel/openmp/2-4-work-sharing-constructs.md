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
ms.workload: cplusplus
ms.openlocfilehash: 476e4e23b22527accaa095d80b827c95aed58c15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte
Ein Konstrukt Freigeben von Arbeit verteilt die Ausführung der zugeordneten Anweisung zwischen den Mitgliedern des Teams, die sie auftreten. Die Arbeit sharing-Direktiven neue Threads nicht starten, und es keine implizite Barriere beim Einstieg in eine Arbeit sharing-Konstrukt ist.  
  
 Erstellt die Abfolge der Freigabe von Arbeit und **Barriere** Direktiven aufgetreten müssen für jeden Thread in einem Team identisch sein.  
  
 OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese werden in den folgenden Abschnitten beschrieben:  
  
-   **für** Richtlinie  
  
-   **Abschnitte** Richtlinie  
  
-   **einzelne** Richtlinie