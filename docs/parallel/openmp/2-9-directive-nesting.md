---
title: 2.9 Schachtelung von | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd3c4f790681b1b044f435c03d185585b565eb62
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
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