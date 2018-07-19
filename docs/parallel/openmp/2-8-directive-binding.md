---
title: 2.8 Direktivenbindung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02492b228b4bb47a800955f078a59ce680312a87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689453"
---
# <a name="28-directive-binding"></a>2.8 Direktivenbindung
Dynamisches Binden von Direktiven muss die folgenden Regeln einhalten:  
  
-   Die **für**, **Abschnitte**, **einzelne**, **master**, und **Barriere** Direktiven Binden an die dynamisch Einschließen von **parallele**, sofern, unabhängig vom Wert eines beliebigen vorhanden **Wenn** -Klausel, die auf diese Richtlinie vorhanden sein kann. Wenn keine parallelen Bereichs derzeit ausgeführt wird, werden die Richtlinien von einem Team besteht nur die master-Thread ausgeführt.  
  
-   Die **sortiert** -Direktive bindet an die dynamisch einschließende **für**.  
  
-   Die **atomic** Richtlinie erzwingt exklusiven Zugriff in Bezug auf **atomic** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.  
  
-   Die **kritische** Richtlinie erzwingt exklusiven Zugriff in Bezug auf **kritische** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.  
  
-   Eine Richtlinie kann nie dynamisch an keiner anderen Direktive außerhalb der nächsten binden einschließenden **parallele**.