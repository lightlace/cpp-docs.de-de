---
title: 2.9 Schachtelung von | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28e690ba531b4b37973bc2555d904317181ff918
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691338"
---
# <a name="29-directive-nesting"></a>2.9 Schachtelung von Anweisungen
Dynamische Schachtelung von Direktiven muss die folgenden Regeln einhalten:  
  
-   Ein **parallele** Richtlinie dynamisch in einem anderen **parallele** logisch richtet ein neues Team, die nur den aktuellen Thread besteht, es sei denn, die Parallelität geschachtelt ist aktiviert.  
  
-   **für**, **Abschnitte**, und **einzelne** Direktiven, die auf den gleichen binden **parallele** dürfen nicht ineinander geschachtelt werden.  
  
-   **kritische** Direktiven mit demselben Namen dürfen nicht ineinander geschachtelt werden. Beachten Sie, dass diese Einschränkung ist nicht ausreichend, Deadlock zu verhindern.  
  
-   **für**, **Abschnitte**, und **einzelne** Direktiven sind nicht zulässig, in dem dynamischen Wertebereich **kritische**, **sortiert**, und **master** Regionen aus, wenn die Anweisungen auf den gleichen binden **parallele** als Regionen.  
  
-   **Barriere** Direktiven sind nicht zulässig, in dem dynamischen Wertebereich **für**, **sortiert**, **Abschnitte**, **einzelne**, **master**, und **kritische** Regionen aus, wenn die Anweisungen auf den gleichen binden **parallele** als Regionen.  
  
-   **Master** Direktiven sind nicht zulässig, in dem dynamischen Wertebereich **für**, **Abschnitte**, und **einzelne** Direktiven Wenn die **Master** Direktiven binden, auf das gleiche **parallele** als die Arbeit sharing-Direktiven.  
  
-   **sortiert** Direktiven sind nicht zulässig, in dem dynamischen Wertebereich **kritische** Regionen aus, wenn die Anweisungen auf den gleichen binden **parallele** als Regionen.  
  
-   Jede Richtlinie, die berechtigt ist, wenn dynamisch innerhalb eines parallelen Bereichs ausgeführt ist auch zulässig, wenn außerhalb eines parallelen Bereichs ausgeführt. Wenn außerhalb eines parallelen Bereichs von benutzerdefinierten dynamisch ausgeführt wird, wird die Richtlinie von einem Team besteht nur die master-Thread ausgeführt.